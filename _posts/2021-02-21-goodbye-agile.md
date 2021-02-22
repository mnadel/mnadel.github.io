---
title: Goodbye Agile, Hello Agility
date: 2021-02-21
permalink: /post/goodbye-agile-hello-agility
description: A story about why (and a little bit of how) we adopted Kanban.
layout: default
redirect_from:
  - /goodbye-agile-hello-agility
---

# Goodbye Agile, Hello Agility

February 21, 2021

Leading into early 2020 we were doing what we called Scrum-Lite. Although, to be pedantic, it was closer to elements of [XP](http://www.agile-process.org/) repackaged with more-familiar Scrum terminology. Our (only) ceremonies were daily Standups (dev + product + design) and weekly Sprints and Demos. We didn't carry a Backlog, which eliminated much of the activities prescribed by Scrum.

Things were going alright, but at Drip we stress a culture of [kaizen](https://en.wikipedia.org/wiki/Kaizen) &mdash; one of continuous improvement. Valuing [lean practices](https://en.wikipedia.org/wiki/Lean_software_development) and agility over dogmatic adherence to any particular Agile implementation, I saw an opportunity to address a specific issue we were facing &mdash; that of stalled projects &mdash; by changing our process.

What follows is an internal document I used back in March of 2020 outlining the issue and proposing a solution to address it. The _Reflection_ section following that is a recent reflection on whether Kanban helped address the issues we were seeing.

## Background

I am encouraged by our velocity! Looking past the horizon, however, I don't think we've solved the fundamental problem that I've heard expressed by the team in various ways, including in our most recent retrospective: projects, at some point, have a tendency to feel like they're stalling.

Additionally, I know that we enjoyed mobbing. It was invigorating and engaging, and, importantly, it helps minimize knowledge silos. Everyone seemed energized by the proposal that as our tasks wind down, we ramp up mobbing. However, mobbing has largely dropped by the wayside, and I don't think anything besides overcoming inertia has prevented us from mobbing more.

One of our company's strategic priorities is "Unleash our people." And I would not be doing my job if I weren't constantly thinking about how to help you all be your best (professional) selves. Long story short, based on conversations I've had with [my peer] [Stephanie](https://www.linkedin.com/in/stephanie-simons-she-her-92444ab2/), who has a bunch of experience in using Kanban with her teams, I see it as a potential pathway to addressing these two issues.

To give you some background, Kanban is not a software development process. In fact, as you may know, it originated in manufacturing, and rose to prevalence at Toyota on their production line under the direction of Taiichi Ohno in the 60s. It was brought to the broader business management community in the mid-80s by way of Eliyahu Goldratt's book, [The Goal](https://www.tocinstitute.org/the-goal-summary.html). In his book, Goldratt develops the Theory of Constraints, which is derived from mathematical queueing theory and is one of the foundations of Kanban. It wasn't until 2010 that David Anderson documented his experience applying Kanban to software in his book [Kanban: Successful Evolutionary Change for Your Technology Business](https://shop.leankanban.com/products/kanban-successful-evolutionary-change-for-your-technology-business).

Kanban, itself, is a meta-process designed to help teams implement continuous improvements in their production processes. Kanban has two rules:

1. Make the work visible
2. Limit work in progress (WIP)

These two rules form the basis of implementing a Kanban system: a pull-based flow system, which, in turn, allows teams to continually optimize how work flows through the system.

Making the work visible, I believe, will help address the first issue of projects feeling like they're stalling. In the absence of a (Jira) ticket, or one that is in flight for weeks, it's hard to visualize progress or detect when we've uncovered hidden complexity. If we are continually visualizing the work and seeing it flow through the system, I hypothesize it'll help alleviate the feeling that projects feel stalled. And, moreover, if we do detect that tasks are legitimately stalled because of incidental complexity, it'll be readily visible and something we can proactively address, therein contributing to forward progression and momentum. It's a virtuous cycle!

Kanban is more than just an improved visualization system, though. Kanban isn't Kanban without WIP limits. WIP limits mean we will intentionally limit starting new tasks until (enough) current tasks are completed. This swings the pendulum from optimizing for utilization (where everyone has "something to do" and isn't sitting idle or looking for work) to a focus on completing work. This clearly addresses the stalled-project problem we're trying to solve by focusing efforts on completing work, thereby contributing to forward progress and momentum. Another virtuous cycle!

WIP limits have the added benefit of codifying a social contract around when we pair and mob. By playing with the WIP limits, we can tweak how frequently we mob. If, for example, we can only have three tasks in progress at any given time, then by definition some of us will be mobbing (or all of us will be pairing). It changes the conversation from an open-ended adhoc plea of "I'm doing X, feel free to pair/mob with me!" to a more specific "I cannot pick up a new ticket, so I'm going to mob with you."

## Our Own Flavor of Kanban

What this means for us is that we need to better visualize our work and institute WIP limits. Better visualization will take the form of additional columns in Jira. To start with, I'm proposing the following: IDEA &rarr; SPECIFY &rarr; TODO &rarr; DEV &rarr; VERIFY &rarr; DONE. These states are meant to get us started with something useful, and I fully expect (indeed: insist) to tweak and adjust as we learn more. To see what this looks like, check out [this test] project in Jira. I'll be migrating us to this Classic project, as it has some important features that are missing in Next-Gen projects (namely, indication of how long a task is in a column).

The IDEA will contain items that are SWAGged, i.e. they'll contain just enough information that we were able to come up with a SWAG. This helps us have ROI conversations that inform the priority of these items.

From IDEA, items move into SPECIFY. These are essentially on-deck items. This is where (and when) on-demand planning happens. When a SPECIFY item is picked up, the owner's responsibility is to break it down into small tickets (ideally no more than one day of effort, 2-3 days max) in the TODO column. The result is a more detailed plan. But the TODO column does have a WIP limit. If a SPECIFY task's decomposition is too big to fit into the TODO column, then break the SPECIFY task apart in-place in order to adhere to our limits by specifying smaller chunks of better-understood work.

The items in TODO is from where new work is picked. When you're ready to pull a new task, grab the topmost ticket from TODO that you've got the skills to do. (This is where we can inject escalated bugs, etc.) Or, better yet, pick up the top task — and if you're not sure how to do it, pair with somebody that does!

When picking up an item from TODO, you'll move it into DEV. If you cannot because there are already too many tasks in that column, you pair/mob!

Tasks then move from DEV into VERIFY. This could be a simple deploy/test step, or it could be a more complex wire-up-all-the-things step. At this stage of the lifecycle it's about shipping something to the customer (and so still valuable for us to be pairing/mobbing). Finally, once you've verified it's all good, drag to DONE.

The final piece of the puzzle are the WIP limits. Using the Theory of Constraints, we can probably calculate the ideal WIP limits (any takers?!), but I think we'll likely trial-and-error our way to what works for us and strikes a good balance between throughput and pairing/mobbing.

Now, for the hard part. For this to work, there's a few things that we need to be disciplined about:

1. Everything we're working on must be represented in Jira. We're not doing Kanban if we're not using WIP limits, and WIP limits are irrelevant if we're doing stuff that's not tracked in Jira.
2. Tasks in Jira need to be small (2-3 days max for starters). Large tasks prevent us from visualizing the progression of work, which will lead to a feeling of projects being stalled.

Initially we'll take a MITA (Mike Is The Asshole) approach to ensuring the above happens. Please feel free to blame me for any discomfort or awkwardness. e.g. "Sorry, Mike is an asshole and is making me pair with you" or "Ugh I wish I could start that task, but Mike is being an asshole" and also "Mike's an asshole and we need to break this down before we continue working on it." But believe it or not, I do find it exhausting to be an asshole. So, eventually I'd like everyone to take part in ensuring we're being disciplined in how we implement Kanban.

## References

1. [Agile Project Management With Kanban](https://www.microsoftpressstore.com/store/agile-project-management-with-kanban-9780735698956); a 250-page textbook, by Brechner
2. [Essential Kanban Condensed](https://resources.kanban.university/guide/); a 90-page distillation of Anderson's book, by Anderson

# Reflection

Kanban is currently working quite well for us. A couple of folks have recently, and independently, mentioned that they feel engaged and that the team is super productive. And indeed, we're shipping consequential changes every one to two weeks. Projects haven't felt stalled in quite some time. I believe this is largely due to two things:

1. Optimizing for finishing work as a team rather than individuals being busy (i.e. one of our stated goals in moving to Kanban)
2. A focus on incrementally delivering product (a different, but related, thread we've been tugging on as a Product Engineering organization &mdash; a likely post for a different day)

Upon reflecting on where we're at, I'm now realizing we're still not pairing and mobbing as frequently as we should. To be fair, we've yet to tweak our WIP limits (though we're doing a pretty decent job adhering to them!). Looks like I've got a topic for our next retro!

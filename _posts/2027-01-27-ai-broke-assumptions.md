---
title: AI Broke Our Assumptions About Team Scale
date: 2026-01-27
layout: post
permalink: /post/ai-broke-our-assumptions
redirect_from:
  - /ai-broke-our-assumptions
---
There's a long-held belief that microservices become necessary at a certain organizational scale. It's time to start thinking about decomposing your system when you have enough engineers that coordination costs outweigh the overhead of operating a distributed system. The trigger is typically headcount.

But what happens when AI-assisted coding decouples the velocity of change from headcount?

Our 10-person team using Claude and Cursor is pushing changes at the rate of a team 3-4x our size. And we're starting to see the problems that come with that scale: merge conflicts in hot files, PRs that sprawl across traditional boundaries, reviewers who can't keep pace with the velocity of change, architecture evolving faster than we can track by traditional methods.

A 30-person team pushing 30-person levels of change creates linear pressure — coordination mechanisms are sized to match the velocity of change. The problem isn't absolute throughput. It's the ratio of output to coordination capacity.

AI scales the numerator while holding the denominator constant.

Your team can produce at 3-4x the rate, but you still have the same number of reviewers, the same hours to hold architectural context in your head, the same bandwidth to onboard new hires and document decisions. Code review processes, ownership models, architectural governance — all of it assumes a ratio between team size and output.

AI-assisted coding breaks this assumption.

Where are you seeing the cracks forming?


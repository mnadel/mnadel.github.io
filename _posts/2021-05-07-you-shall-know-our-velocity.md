---
title: You Shall Know Our Velocity
subtitle: Three thousand deploys a year isn't just a vanity metric.
date: 2021-05-07
layout: post
permalink: /post/you-shall-know-our-velocity
redirect_from:
  - /you-shall-know-our-velocity
---

Not just the title of [Dave Eggers's debut novel](https://en.wikipedia.org/wiki/You_Shall_Know_Our_Velocity), but also the heart and soul of how Drip operates. Drip's Product Machine, very intentionally, optimizes for velocity. Not in the "move fast and break things" sense, but because velocity is a means to accuracy. It is the foundational strategy of our culture: one that values organizational learning and extreme ownership. This post will give you a sense of why and a brief glimpse of how.

## Learning

We know what we don't know and have the burning intellectual curiosity to find answers to our questions. This extends through to the core of Product, Design, and Engineering alike. The beauty is that the three disciplines form a cohesive team that focuses this energy on solving first-level (i.e. revenue-generating) problems for our customers. One of our approaches to learning is through experimentation. This does mean that we sometimes fail. To grow and do amazing things requires that you take risks. Indeed, if we find ourselves never failing that means our goals aren't audacious enough. Learning is one source of Drip's superpowers.

## Ownership

Radical ownership requires bold action and organizational support. Drip has both in abundance. What does that look like, though? Have you ever had an epiphany on a walk, while working out, or in the shower? Or maybe in a dream? If you knew it'd take months to get that idea implemented — what would you do with it? Tuck it into the back of your kind? Write it in a notebook? Create a Jira ticket and  buy your product owner a bottle of their favorite beverage in hopes that they'll prioritize that ticket? The lag between idea and working software is called lead time. At Drip we measure lead time in days, not weeks or months. This doesn't mean we have chaos. In fact, it's the opposite: it's a well-synchronized team, all running in the same direction, passing the ball to whomever's in the best position to score. In less metaphorical terms, we have folks who care &mdash; about our customers, our business, and each other &mdash; and trust each other enough to provide the support and tools necessary, then get the hell out of the way. Extreme ownership is another source of Drip's superpowers.

## Velocity

Given the above, nothing short of a high-velocity environment will suffice. Low-velocity stifles learning. Getting customer feedback on an experiment three months from now has very different economics than if you can get feedback three days from now. Velocity and extreme ownership go hand in hand. It's much harder to quickly deliver incremental value to customers when process, hand-offs, and bureaucracy get in the way.

There's a handful of practices that have been instrumental in helping us maintain velocity as we scale:

1. We practice continuous delivery; our main branch is always deployable.
1. We use short-lived feature branches, predominantly as a peer review mechanism.
1. We leverage feature toggles to decouple deployments and releases.
1. We've implemented zero-downtime rolling deploys so that we can deploy on-demand, any time of the day or week.
1. We deploy numerous small changes a dozen times a day; the smaller the delta, the easier it is to reason about the system as it evolves.

Almost 3000 deploys a year isn't a vanity metric: delivering software this way is truly transformative &mdash; not just for Engineering, but for Product and Design alike. It unlocks new superpowers.

---
layout: post
title: Discovering a Person's API
---
> The great thing about TCP jokes is that you always get them...I would tell some UDP jokes too but I never know if anyone gets them.

Humans are messy.

Organizations are made of people and are similarly messy places. This messiness often manifests in tension. The tension can be healthy, akin to agonist-antagonist muscle pairs.

Product indexes toward shipping new features. Engineering indexes towards the ever elusive technical debt that "needs" to be paid down.

**Discovering a person's and organization's API** is a model I've found helpful in reasoning about and navigating these differences.

There are all sorts of downsides to focusing on a person's intentions. The [fundamental attribution error](https://en.wikipedia.org/wiki/Fundamental_attribution_error) comes to mind.

I'm not saying that understanding _why_ someone wants something isn't without value. But it's wasted effort if there's a more fundamental miscommunication occurring.

This is actually the premise of the [DISC assessment](https://en.wikipedia.org/wiki/DISC_assessment). Don't focus on people's motivations; rather understand their behavioral tendencies.

Reframing the problem to APIs is another way to approach the same concept, one that may resonate with folks who have a technical background.

In the example above, Product may better receive a discussion about addressing a technical issue if it's framed in terms of avoiding an increasing and now imminent likelihood of downtime. That's the interface that makes interactions more easily understood.

One individual I managed was having a hard time getting through to someone on another team. Our conversation went something like this.

> **EM**: I just don't get it. Everytime I try to review project tradeoffs with $X, it's like we're saying the same thing but still disagreeing.  
> **Me**: I hear you. It's like they have an entirely different API. Like you're speaking REST and they're using gRPC.  
> **EM**: Exactly!

Sometimes the APIs between people and organizations are naturally compatible.

Othertimes we're off by a minor version but one of us is backwards compatible.

And sometimes we're not even speaking the same protocol. One is on HTTP and the other is on Telnet.

Here's another expample. I found that every time a coworker and I discussed a topic we both reiterated our points, which largely seemed to be in agreement. Eventually I'd say something like, "I think we're in violent agreement." And they'd agree!

Neither of us felt like we could cut the back-and-forth short. We were in an ACK loop not realizing what our APIs were signaling.

If you're having trouble communicating with a person or organization on an issue, consider your respective APIs.

_Left unexplored is the case where the API differences between two people or a person and org are so fundamentally divirgenct that they're hopelessly incompatible._
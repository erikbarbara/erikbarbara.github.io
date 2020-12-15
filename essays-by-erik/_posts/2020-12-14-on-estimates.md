---
layout: post
title: On Estimates
---
> ...current programming practice is closer to novel writing than it is to engineering. The novelists are bound only by their imaginations, which is somewhat as the programmers are when they are writing software. Both activities have a large creative component, and while you would like to make programming resemble engineering, it will take a lot to make programming resemble engineering, it will take a lot of time to get there–and maybe you really, in the long run, do not want to do it! Maybe it just sounds good.
>
> — [Richard Hamming, The Art of Doing Science and Engineering](https://www.amazon.com/Art-Doing-Science-Engineering-Learning/dp/1732265178){:target="_blank"}

One of the challenges software engineers and engineering leaders face is that of providing estimates.

> How long will $X take?

Sounds simple. It's often anything but, especially for any $X that will take more than a few hours.

In many ways, we've done ourselves a disservice by naming our discipline software engineering. I don't know for certain, but I'd wager that when a civil engineer goes to design a bridge, they follow a pretty standard process. The number of ways for building a bridge is not just finite, but charted. Type? Suspension. Ok, we have five options. How many cars? $Y per hour. Ok, we have two options. Etc.

Software engineering though is more art than science. It's fundamentally a creative endeavor. And this bit is hard to convey, especially to those who haven't done it.

How can it be a creative endeavor? It's got engineering right in the name?

How can you not tell me how long it will take to add a button to do $Z? Two weeks? I'm not asking for you to design a car (something that takes many years by the way).

How do you capture and convey this dilemna to those who haven't experienced it?

Maybe it's like asking an artist how long it will take to make an installation. If you want it faster, it won't be as good. Quality art takes time. [This video](https://vimeo.com/226508728){:target="_blank"} drives the point home.

But even that doesn't do the issue justice for software engineers. There are two more variables at play.

First, we're often being asked to build on top of something that already exists. Maybe the engineer is fortunate enough to have prior experience with that system or codebase. Regardless, whatever was built before certainly required time constraints and tradeoffs.

Second, we're being asked to build something that may very well be built on in the future, but we don't know exactly how it will be used or extended. So, we build with assumptions and with imperfect knowledge of the trade-offs to come on top of something that was built with assumptions and with imperfect knowledge of the trade-offs to come.

Neither of those points are exactly unlike other engineering disciplines. But I think the radical things that software engineers are asked to add to their systems are much more radical than other disciplines.

A building might be a candidate for an expansion. But what if the building was a skyscraper and we want to add a pool? What if the pool has to be on the top floor? What if it has to cantilever over the top with a see through bottom and support 500 people?

Now we're starting to see the challenge. The building would have had fundamentally different design assumptions if we knew this was a use case we wanted to support when we were originally building it. We may be able to make the modifications to allow for this change, but it could take a long time and be expensive.

Similarly, changes to a car model are often incremental. Maybe a redesign happens, but if it's radical enough then it starts from scratch and requires new ways of doing things. These new ways require inventing technology and methods that don't exist. How long will that invention take? Just have the engineers [think harder](http://wiki.c2.com/?FeynmanAlgorithm){:target="_blank"} I guess.

Often extensions to software systems take the product in unforeseen directions. This is part of discovering product market fit, of coming to better understand what problems are worth solving for users, etc.

Altogether software engineering suffers from the problems of many "right" ways of doing something combined with building on a system that was never designed with the new use case in mind.

These properties make it a creative endeavor.

And so estimating is difficult.

_h/t to my former colleague [Glenn Stempeck](https://www.linkedin.com/in/glenn-stempeck/){:target="_blank"} for the pool analogy; he also wrote [this excellent essay](https://medium.com/@glennstempeck/software-engineering-like-a-6-000-piece-hogwarts-lego-castle-bc7441d0b1b5){:target="_blank"} on the perils of splitting a team's focus._

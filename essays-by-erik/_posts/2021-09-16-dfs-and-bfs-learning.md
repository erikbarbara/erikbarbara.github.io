---
layout: post
title: Depth-first and Breadth-first Learning
---
I've encountered two patterns of learning when working with engineers. These patterns apply to most people. But I've spent most of my career working with engineers.

The two categories are useful to describe where people gravitate. Reality is less binary and is instead a spectrum.

I bring these up when onboarding a new engineer to learn how _they_ learn. It's typically clear in how they approach their first tasks as well.

<img src="https://miro.medium.com/max/1280/1*GT9oSo0agIeIj6nTg3jFEA.gif" alt="Illustration of DFS Preorder and BFS Searches" width="350px"/>

## Breadth-first Learning

This is the model I tend toward. I self-deprecatingly call this the `StackOverflow Coder`.

A breadth-first learner scans the solution space and returns to the work when they believe they have minimally viable knowledge.

Despite the deprecating name, this shouldn't be confused with brute forcing. There is intentionality in the learning. The goal is to not over-optimize in depth or expertise of knowledge. The goal is getting to tangible value sooner.

If the first scan didn't result in a workable solution, the learner goes deeper. It's akin to a breadth-first search algorithm. The learner assumes that nodes in each subsequent layer in the tree require geometrically more effort to learn than the previous depth.

## Depth-first Learning

These learners tend to be more "ready, aim, aim, aim, fire".

A depth-first learner goes deep into a subject before writing a line of code or starting on the implementation. This is particularly true if it's their first time working with a concept.

They find comfort in developing depth and familiarity with the subject. And the depth of knowledge they gain can pay dividends when the problem being solved has nuance or if they specialize in that subject matter over a long period of time. The trade-off is that tangible results take longer to bootstrap.

## Trade-offs

There isn't a right answer about which model is best. There are simply trade-offs and contexts in which to apply each.

I find breadth-first works best when starting at a new company. You're assigned your first task. Your manager picked a starter task. You're supposed to send a new parameter in an API call.

Do you research Rails, controllers, the philosophy, etc.?

Or do you dive into the code, reproduce the issue, look at the existing routes, make an educated guess at how to implement the change, and iterate?

Conversely, I once worked on a project that required using the OpenID Connect protocol for authentication.

My approach was to find a popular library for the framework we were using, install it, and get basic authentication working. I was confident we were 90% done!

My manager was a depth-first learner. They printed out (yes on paper) the OIDC spec, sat down at their desk and read it with a highlighter. Then they looked at the source code of the library I had chosen and pointed out two or three important implementation details that had been skipped.

I felt a bit like King George III in Hamilton.

> I wasn't aware that was something a person could do. 
> 
> – [I Know Him, Hamilton](https://www.youtube.com/watch?v=hGibKLo3SC0){:target="_blank"}

From this experience, I've developed a (still too intuitive) heuristic for deciding when I need to go deep on a topic.

A strong team is comprised of both types of learners. And mature professionals will know when to adopt their non-dominant approach.

> There’s an opportune time to do things, a right time for everything on the earth.
> 
> – [Ecclesiastes 3:1](https://www.biblegateway.com/passage/?search=Ecclesiastes+3%3A1&version=MSG){:target="_blank"}

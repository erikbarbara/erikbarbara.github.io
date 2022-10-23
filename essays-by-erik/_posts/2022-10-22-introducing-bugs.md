---
layout: post
title: Square Root
---
Occasionally I'm asked why even seemingly simple software is riddled with bugs.

For example, a friend or family member asks why their favorite app had an obvious bug recently.

> Come on, you just have to upload photos and let me see others'. Why is that so hard?

I've developed a small illustration to help convey the challenges. Let's start simple and build up.

Imagine you're asked to make a black box. This is our app.

The user punches in a number and it returns the square root of that number.

Ok. Let's go!

The user inputs zero. And we return...zero.

The user inputs four. And we return...two.

So far so good? Great!

Actually, we already have our first bug. Maybe. Both two and negative two are square roots of four.

Did we want our black box to return only the implied (positive) square root of the input? Or did you want any of the possible square roots?

I can hear the protestations now.

> But you didn't tell me that's what you wanted!

You don't say!

This is the exact problem engineers face when developing software. 

Our illustration had one simple job, and we're already into the ambiguity of requirements.

Now imagine developing high-stakes software. Maybe it needs to send rockets to space. Maybe it will process your mortgage application screening you for creditworthiness. Maybe it will drive your car autonomously.

It's a minor miracle software works as well as it does. There's an army of engineers employed at the companies building the software we use daily.

And they care about what they build. A lot. They sweat the details to minimize issues like the ones above.

In spite of all of this, there will always be bugs.
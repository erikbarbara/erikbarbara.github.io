---
layout: post
title: DevOops with Python Datetimes
---
Let me tell you about the time we dropped all the data we had in a production Elasticsearch cluster just days before cutting over to it for a huge feature release.

[I previously alluded](/essays/2020/10/02/the-right-fallacy.html) to the pain of trading off the strengths and weaknesses of MySQL with those of Elasticsearch.

_If terms like document and index are lost on your in the context of Elasticsearch, [here's](https://medium.com/@hansrajchoudhary_88463/elasticsearch-things-you-should-know-about-es-to-be-useful-fbc537a04086) a high-level overview._

One of the challenges we encountered was cluster maintenance. Elasticsearch is best not left to grow unbounded. So we made a decision to cap data retention in our system at 180 days.

We wrote a Python process that would run regularly and check whether data needed to be purged. In Elasticsearch, it would have been more expensive to query and delete every single document that was older than 180 days. Instead, we decided to drop indexes that were older than this time period.

But of course, it wasn't that simple. For most of our clusters, we stored our data in monthly indexes. This meant that every authentication that took place in December 2019 was stored in an `auths-monthly-2019-12` index. On a few of our larger clusters at the time, we kept data in weekly indexes.

In order to do this, the process we wrote had to parse the index name and convert a portion of the name to a date. If it was older than 180 days, we could drop it.

_Not really though. We had to add a bit of extra logic. If it's June 15th and we're evaluating whether to drop an index, we have to ask ourselves what the youngest data in the index is. So if it's an index for December 2019, we have to check whether data from December 31st is old enough to drop._

Let's see how this looks in practice.

If the index name was `auths-daily-2016-06-06`, then we'd parse `2016-06-06` to a date. If that date was older than 180 days from today, we could drop the index.

```python
>>> datetime.strptime('2016-06-06','%Y-%m-%d').date()
datetime.date(2016, 6, 6)
```

We kept daily indexes in local development, but otherwise, this wasn't a huge use case. Our retention code worked as expected.

We did keep monthly indexes though. So `auths-monthly-2016-06` was parsed like below.

```python
>>> datetime.strptime('2016-06','%Y-%m').date()
datetime.date(2016, 6, 1)
```

Puurrrfect. Data retention working as expected.

Like I mentioned, a few of our large clusters had weekly indexes. Let's parse `auths-weekly-2016-26`.

```python
>>> datetime.strptime('2016-26','%Y-%W').date()
datetime.date(2016, 1, 1)
```

Wat? January 1, 2016 for the 26th week of the year.

The first time that we ran our data retention code against a weekly index was...in production...when we turned the retention process on...against our largest cluster...days before preparing to go live with a huge feature release that depended on the ES data.

_Don't worry, we recovered it rather quickly._

It turns out you need to include a day of the week.

```python
>>> datetime.strptime('2016-26-0','%Y-%W-%w').date()
datetime.date(2016, 7, 3)
```

_Why the 0th day of the week gives you a date that's older than the 1st day of the week is another matter altogether._

What's the moral of this story?

First, it's just a (now) fun war story (or bit of scar tissue or wisdom of production lesson) that I wanted to share.

Second, it illustrates the difficulty of eliminating bugs in software. Now the TDD folks will say that unit tests would have caught this.

We did have unit tests.

We didn't have ones to test weekly index parsing though.

Even if we had written those tests, the developer may just have easily have written the test to check that `auth-weekly-2016-0` returned January, 1, 2016. And it would have.

This still wouldn't have uncovered the unexpected behavior.

TDD diehards may say we should have written **2** unit tests per unit of time we were parsing!

Fine.

However, the nature of a startup is that it defaults to death. When things start, the only thing that matters is shipping code, getting product into customer hands. As time goes on, protecting existing revenue may become more important. Customers come to expect the same level of quality in your new features as they do in your rock solid existing product.

I hesitate to conclude that there's not a lesson to be learned here. I'm sure there is. I just don't think it's necessarily satisfying to most.

Bugs happen. We'll fix them when they do. At least I know a bit more about Python's datetime internals now.

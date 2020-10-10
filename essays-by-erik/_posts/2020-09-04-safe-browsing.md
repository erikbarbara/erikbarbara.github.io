---
layout: post
title: Safe Browsing
---
#### Background

One of the first responsibilities I had as I became an Engineering Manager at Duo Security was the launch of a greenfield phishing product, Duo Insight.

_Side note, there was an internal employee poll at the time on what to name the new product. The record will show that `Tackle Box` was the winner. Get it? Phishing? Fishing? Tackle box? Yes, that's what I voted for. Still a missed opportunity in my mind._

Duo's core product was centered around 2FA, which guards against stolen credentials. However, we had decided there was an opportunity to demonstrate the need for 2FA by allowing companies to phish their own employees for free. The story behind the decision to build the product is a different blog post (or three). But decide to build it we did!

So let me state it like this. My team was tasked with allowing any company to send fake phishing emails to their employees that looked like Google Drive, Office 365, Salesforce, or Outlook messages linked to fake login pages in less than 5 minutes.

The largest companies in tech have been working for a very long time to counter nearly every aspect of what we were doing.

Blocking unwanted emails at all? Check.

Blocking emails that are suspiciously similar in content and look and feel to popular services? Check

Blocking emails that use brand names but come from email addresses not associated with those brand names? Check

Blocking sites that seem suspicious? Check

Stopping phishing is a problem that Fortune 100 tech companies have spent enormous amounts of money building into their products to keep users safe.

So why shouldn't a team of 5 engineers, product managers, and designers be able to launch this product? Knowing what I know now, I would never have thought we could do it. But that's the power of naivete. It turns out that it's trivial to send an email; getting it to show up in someone's inbox though is pretty difficult.

#### Launch

Anyways, we spent 12 months building this product. I took over the team as a new manager about 4 months before launch (the classic story of "There's just a few more things remaining. Your team should be able to finish it in a sprint or two.")

We finally launch the product mid-summer and all goes smoothly at first.

#### Crisis

Then one day a Technical Support Engineer Slacks the #duo-insight channel and reports that a customer is seeing this view.

<img src="https://upload.wikimedia.org/wikipedia/en/d/d0/Google_Safe_Browsing_Screenshot.png" alt="Google Safe Browsing - Deceptive Site Ahead" width="250px"/>

That's Chrome's display for a site on the [Google Safe Browsing](https://en.wikipedia.org/wiki/Google_Safe_Browsing) list.

I distinctly remember that I was in an Engineering Staff Meeting at the time when I looked down at my phone and saw the message. I got up, went back to my desk, went to the tool on my laptop, and tried it myself. Sure enough, that URL had been burnt by Safe Browsing.

No problem, this is why we had multiple services and domains.

I go to another site. Same story.

I pull another engineer from my team out of the meeting and have them try on their laptop. Not good.

Every domain and service that we had built this product around was now being flagged by Safe Browsing across every major browser.

It turns out registering all of these domains as part of the same Amazon Certificate Manager cert was a bad idea. Safe Browsing grabbed all the sites on the cert and added them to their list.

Worse still, the interconnected web of tools that keep the internet safe was propagating this list through itself. Soon it wasn't just browsers that were blocking our domains. After a few more tests, any emails sent out from our tool were automatically being blocked by the most popular built-in and off-the-shelf spam defense products.

I pulled our VP of Security into what was now becoming a war room. He had warned that we should proactively reach out to these groups and get their feedback before launch. He reminded me that he said this would happen. He wasn't wrong.

As a new manager though and with the pressure of hearing "this should only take a few more sprints" and then having 4 months go by, I felt we couldn't delay launch longer. Lesson learned.

Luckily, Duo had people deeply connected with the security community at nearly all major companies. I ate crow and asked these folks to reach out to their contacts at these places.

Google's reply was something like this.

> So, you're telling us that Safe Browsing is blocking a site that has a lookalike domain (e.g. drive-accounts-google-com.com) for one of our products (e.g. Google Docs) that's being linked in phishing emails that are fake but indistinguishable from real ones and that link to a fake login page that looks like the Google sign-in page that's using our branding and logo? Sounds like Safe Browsing is working as designed. Good luck with your little, new product though.

Ok. We should have anticipated that response too.

But we were trying to make the internet safer! Couldn't they just allow our service? No.

#### Decision

In the midst of all this, I had sales people asking me when the site would be back up. I had marketing asking for the status because they had just launched a demand gen campaign around this. Product had ideas. Security wanted to rethink the entire product. And Duo had just invested over $1M for over a year to make this product. And it was now the web app equivalent of being bricked.

I was walking from our conference room huddle to the kitchen at one point and Zack Urlocker, our COO, came up to me. I thought I was about to get a good chewing out or better yet fired. At the least I thought I was going to get an opinion. And in a way I did.

> Erik, you're getting a million opinions right now. At the end of the day though it's you and your engineers who have to fix the problem. You make the call. You own the decisions. You can listen to everyone else but you make the call.

In the depths of this crisis, as a new manager, surrounded by chaos, this is what I needed to hear.

#### Conclusion

We eventually took a number of measures to get Duo Insight back online. Remarkably, it took just a few days. We removed the lookalike domains, had emails and login pages that were stylistically similar to the services we were phishing with but that didn't include their logos, added explainers about how our tool did not collect passwords to the root of each domain where Safe Browsing looks, performed transparent domain registration, etc. I think in the 4 years that followed we might have had one additional domain burned. But nothing of the magnitude of the initial crisis.

#### Postscript

In early 2020, we shuttered Duo Insight due to lack of traction and to focus on higher-lever product development opportunities.

I learned a ton about product development, market opportunity evaluation, making decisions, and leading teams during this time.

I'm incredibly proud of my team for collaborating with subject matter experts at Duo and in the industry and then taking that information, owning the decision, and solving this problem.

I also feel a bit better knowing that the internet is working really hard to make doing bad things even harder.
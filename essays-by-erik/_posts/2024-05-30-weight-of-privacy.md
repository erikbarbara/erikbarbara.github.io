---
layout: post
title: The Weight of Privacy
---
_N.B. The goal of examples and cases below is to examine what went wrong, not cast aspersions at companies or past decisions._

## What Is Privacy?

[Video: Steve Jobs On Privacy](https://www.youtube-nocookie.com/embed/BlisJgS_lyA?rel=0){:target="_blank"} (34s)

**Privacy is the right to control *your* data.** Boil away the legal details and this is its essence.

This post provides a survey of real privacy issues, and how they can be mitigated. The goal is to convey the weight of privacy that we all bear as engineers handling user data.

## Why Care about Privacy?

[Video: Mythic Quest Has Been Hacked](https://www.youtube-nocookie.com/embed/EZVPEeG4h7s?rel=0){:target="_blank"} (42s)

Respecting privacy **is** users first.

Set aside the alphabet soup (GDPR, CCPA) of privacy legislation and how you may feel about these laws. Many, many users care deeply about how their and their customers’ data is used; a significant degree consider privacy to be a fundamental [human right](https://www.un.org/en/about-us/universal-declaration-of-human-rights#:~:text=Article%2012,against%20such%20interference%20or%20attacks.){:target="_blank"}. Not sufficiently considering user privacy in your products and systems is to disrespect your users’ privacy, violate their rights, and go against company values to put users first.

When users discover violations, trust is lost. Users expect that by default:
* Products protect privacy ([Public By Default: What Venmo and the Whole World Knows About You](https://22-8miles.com/public-by-default/){:target="_blank"})
* Data access is limited ([Tesla workers shared sensitive images](https://www.reuters.com/technology/tesla-workers-shared-sensitive-images-recorded-by-customer-cars-2023-04-06/){:target="_blank"})
* Internal tools are safe ([Uber Allegedly Stalked Users, Snapchat Employees Abused Data Access](https://www.forbes.com/sites/kashmirhill/2014/10/03/god-view-uber-allegedly-stalked-users-for-party-goers-viewing-pleasure/){:target="_blank"})

This is trust that takes years to build, but would take seconds to break, and may take forever to repair.

## Privacy Engineering (and How It Is Different from Security Engineering)

Privacy engineering teams builds frameworks to meet the privacy expectations of users.
Security and privacy are adjacent but distinct disciplines. Privacy is about the right to control how personal data is collected and used. Security is about protecting that data, including preventing unauthorized access, data corruption, or theft. Often good practices overlap between the two.

The first OWASP Top 10 dropped in 2003 with your favorite PHP and IIS-powered site vulnerable to script kiddies. Twenty years later robust security protections come out-of-the-box in popular frameworks. For example, a default Rails app provides protections for CSRF, SQL injection, and more.

Privacy engineering is today where web app security was 20 years ago. There are few paved paths and even fewer plug-and-play frameworks for achieving the ends expected by users and demanded by legislation. Because of this, the frameworks companies use to ensure they respect user privacy evolve drastically year-to-year.

By seeing the consequences of privacy issues in practice, you can better understand why you’re asked to implement privacy controls or adopt privacy frameworks.

## Selected Case Studies and Lessons

> Invert, always invert.
> 
> — Charlie Munger

The front page test is an excellent litmus test for privacy issues. It’s useful to examine real-world privacy issues and then invert these into practices to adopt instead.

### Was clear, plain-terms consent obtained before data collection or use?

In 2011, Google [agreed](https://www.ftc.gov/news-events/news/press-releases/2011/03/ftc-charges-deceptive-privacy-practices-googles-rollout-its-buzz-social-network){:target="_blank"} to an FTC consent decree requiring 20 years of independent privacy audits. This came from Google Buzz sign-up and data sharing. In the FTC’s own words:

> Google led Gmail users to believe that they could choose whether or not they wanted to join the network, [but] the options for declining or leaving the social network were ineffective…the controls for limiting the sharing of their personal information were confusing and difficult to find[.] [Consumers were] concerned about public disclosure of their email contacts which included, in some cases, ex-spouses, patients, students, employers, or competitors.

In another case in 2022, CNIL–France’s privacy regulator–[fined](https://www.theverge.com/2022/1/7/22871719/france-fines-google-facebook-cookies-tracking-dark-patterns-eprivacy){:target="_blank"} Google and Facebook €150M and €60M respectively for nudging users to “accept all” cookies in their consent banners. Consent must be provided freely. That means making it as easy to reject non-essential cookies as accept them.

<img src="https://web.archive.org/web/20220114092730im_/https://pbs.twimg.com/media/FJDVVirX0AI1Qlt.png" alt="Opt-out checkbox" width="600px"/>

In 2022, a Twitter user [called out](https://web.archive.org/web/20220114092730/https://twitter.com/type__error/status/1481918942474035203){:target="_blank"} Stripe for a checkbox to subscribe to email product updates. The issue was quickly remediated once flagged.

Users have high standards for companies and expect the same excellence and clarity in the privacy experience as the rest of the product experience.

#### Inversion

> Privacy means people know what they are signing up for in plain English…Ask them.
> 
> — Steve Jobs

When building user journeys–for example, signup pages–Jobs’ advice from the first video is trustworthy.

Ask users unambiguously for permission. A user is signing up for a product? Ask them. Want to collect web analytics? Ask them. And if asking is difficult for whatever reason, ask your privacy-focused colleagues whether there are alternatives.

Respecting the [Global Privacy Control](https://globalprivacycontrol.org/) setting for _all_ users is a clear illustration of prioritizing and respecting users' privacy. Beyond merely complying with legal requirements, you can prioritize users' privacy preferences. Even in jurisdictions where it’s not required, respect users’ GPC setting opting them out of advertising cookies. Users with the GPC setting proactively communicate their preference, so respect this and don’t set those cookies or use their data for that purpose.

### Did the reason for collecting the data remain consistent?

In 2022 as part of a 20 year consent decree, the FTC [ordered](https://www.ftc.gov/news-events/news/press-releases/2022/05/ftc-charges-twitter-deceptively-using-account-security-data-sell-targeted-ads){:target="_blank"} Twitter to pay $150M for collecting phone numbers for 2FA and then using those numbers for targeted ads. The data used was not clearly annotated, leading to this mishap. Users were frustrated. They provided their phone numbers with the understanding that they’d protect their accounts, not enable advertising.

A 2020 blog post was picked up by [Hacker News](https://news.ycombinator.com/item?id=22936818){:target="_blank"} with concerns over Stripe’s collection of advanced fraud signals. There were concerns that Stripe's privacy policy allowed for using this data for advertising purposes. Patrick Collison, Stripe's CEO, quickly promised that this data is collected exclusively for anti-fraud purposes. Stripe followed this up with a [blog post](https://stripe.com/blog/advanced-fraud-detection-updates){:target="_blank"} and updates to its privacy policy.

Distrust of how companies use data is the norm. Regardless of your intent, users are quick to point out incongruencies and potential loopholes between policies and practices.

#### Inversion

You must adhere to the purposes of processing for which data was collected. In practice this is called business purpose limitation. If data was collected for anti-fraud purposes then that’s what the data can be used for. You can’t later change your mind without gathering consent again.

Individuals have the right to a copy of their data (via a Data Subject Access Request), often grouped by the purposes of processing. Imagine seeing data a user provided for risk purposes displayed under analytics because it was copied inappropriately from one system to another. Users also have the right to be forgotten and for their data to be deleted.

Data annotations are key to knowing what data you have, to whom it belongs, and why it was collected. Annotations are foundational to infrastructure limiting access to closed account data, a special case of business purpose limitation. They can also be used to identify data to delete when you no longer have a justification for retaining it.

When creating or editing data models, add annotations. Yes, this should be the case even if the dataset is intended to be short-lived or only go to QA. Usage evolves, data is forgotten, people move on. Without annotations you can’t account for the data you have.

While privacy engineering teams can create inference models and tools to improve the ease of annotation and accuracy, you are ultimately the expert in your data and responsible for us handling it well.

### Is access to data limited to proper use cases?

In 2024, a Carta employee inappropriately accessed and [shared](https://www.axios.com/2024/01/08/carta-credibility-startup-founder-allegations#:~:text=In%20short%2C%20someone%20on%20Carta%27s%20%22liquidity%20solutions%22%20team%20had%20accessed%20Linear%27s%20confidential%20cap%20table%20data%3B%20leveraging%20the%20core%20product%20as%20lead%20gen%20for%20a%20more%20lucrative%20effort.%20It%20was%20a%20massive%20ethical%20breach%2C%20no%20matter%20how%20different%20lawyers%20might%20interpret%20Carta%27s%20privacy%20policy.){:target="_blank"} customer data to generate interest in an unauthorized, secondary sale of stock. As a result and to stave off brand damage, within 72 hours Carta shuttered their entire secondary stock sale business.

> One VC [said] it was akin to ‘Oracle using your database to share supply-chain data or Salesforce using your CRM data to inquire about the state of your sales leads.’

Abuse of internal tools and data access is deeply corrosive to user trust.

#### Inversion

Least privilege dictates that only the people and workloads that need access to specific data for their job have it. That access must also be monitored and audited.

Authorization controls including two-person confirmation and expiring permissions on internal tools and data can enforce least privilege. These checks may add friction to your workflow. And, yes, you are trying to help your users. Remember though that the abuses mentioned at the beginning of this article stemmed from permissive access. Continual investments in ergonomics can minimize the impact of these controls on daily productivity.

In the long term, privacy preserving technologies like tokenization, pseudonymization, and differential privacy can enable open access to data without compromising an individual’s privacy.

## A Vector, Not a Destination

Like security or reliability, privacy is a vector, not a destination. There will not come a time when the work is done.

In all likelihood, your company's use of data is complex and building excellent privacy controls means that privacy engineering teams must make it simple for engineers to reason about its collection and use.

While building your own products and systems, reflect on the above cases. Whether you are using a privacy engineering framework or implementing controls on your own, we all bear the weighty responsibility of respecting user data and privacy.
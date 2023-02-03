---
layout: post
title: Strange Things
---
A collection of strange experiences I've had in corporate America.

## Corporate Espionage

I worked at a Fortune 500 via acquisition. I had high-privilege access to the acquisition company's systems. One day I was asked to join a video conference with a member of the security team. They informed me that the parent company's corporate espionage team suspected insiders in the broader org.

I was given a few usernames and asked to see if they appeared at all in our systems' audit logs. I was instructed not to search for those usernames on the corporate directory or elsewhere. They were unsure what other systems these individuals may have infiltrated, and didn't want searches to tip them off that the mole was compromised.

Never heard where that one went. But it was my first personal exposure to the reality of corporate espionage.

**Lesson learned**: Spycraft persists, especially in high tech fields.

## Stickup Stills

Another time I was contacted by corporate legal from a Fortune 500. They were cooperating with law enforcement on a local crime. Someone had robbed a convenience store at gunpoint wearing a jacket with a company logo on it. This was a rare jacket that not many employees would have. They suspected that it had been donated to an organization and picked up at a secondhand store. However, the police still wanted to rule out that this wasn't an employee in our office.

I was a long-tenured employee who had interacted with many folks in that office throughout the years. Hence why I was brought in. Before they showed me the security camera stills, the attorneys briefed me that it's natural to want to be helpful. However, unless I really did recognize this person don't say something like "Hmmm...well maybe it kind of sort of looks like..." I should just state whether I recognize the person or not.

**Lesson learned**: Answer the question you're asked, nothing more; being helpful sometimes isn't.

## Embargoed Vulnerabilities

Not too surprising now, but when I was early in my security career I learned that vulnerabilities get embargoed. This works similar to press stories.

A company may discover a bad vulnerability in a piece of open source software. They share the issue privately with the organization that maintains the software of course to determine a fix. Before the vulnerability is publicly disclosed, the discovering organization may decide to share it with critical partners under embargo.

The idea is to give them a heads-up and a chance to fix the issue on their own systems before it goes public and is explicted. The partner is sufficiently important to the main organization's security that just letting them patch the issue after public disclosure would present sufficient risk.

I've worked a few of these. You're always under pressure to remediate on a tight timeline and sharing context for the changes with as few people as possible.

**Lesson learned**: It's nice to have powerful friends who find you important.

## Performance Management

I was working for a company that had rolled out a new tool for managers to complete performance reviews. There was weird UI issue that kept recurring, so I decided to open Developer Tools. While inspecting the issue I noticed something weird about the network calls.

Two parameters were being passed when loading a performance review: the ID for the employee's review and the email address of the person loading the review.

```json
{
    "employee_id": 1234,
    "email": "erik@example.com"
}
```

Huh, that seems goofy. What happens if I change employee ID to my own and my email to my boss's?

```json
{
    "employee_id": 5678,
    "email": "john@example.com"
}
```

Sure enough, there was my performance review. Fun! I reported it to HR, an incident was opened, the vuln was fixed. They ended up pulling audit logs to see who else may have accessed records with a mismatch between the signed in employee and the email address.

Some time later, I mentioned that I found this issue to another employee. They told me about a case from years before where interview scorecards were being exported to the company's data warehouse with limited access controls. Numerous employees found out and queried the data before it was reported.

Audit logs were pulled again and HR reached out to the employees who accessed the data. Most employees either selected a few rows or just their own interview results.

```sql
select * from interview_scorecards limit 5;
-- or 
select * from interviews_scorecards where username = 'erik';
```

But a few had queried well beyond personal curiosity it seems.

**Lesson learned**: If you find a vuln don't abuse your discovery. Report it responsibly and move on with your life. The audit logs don't lie.

---
layout: post
title: Winter Is Coming
---
> Winter is coming.
> 
> – Official motto, House of Stark

A year ago most engineers–myself included–thought that Copilot and Cursor was "cute". That's nice. They can write my tests or auto-complete a few lines.

Today engineers turn over entire features to Claude Code and let it burn tokens.

A sea change has occurred in AI capabilities in past the 6 months. 

Security is not unaffected. A few announcements from Anthropic alone.

* "...we've found and validated more than 500 high-severity vulnerabilities." – [Evaluating and mitigating the growing risk of LLM-discovered 0-days](https://red.anthropic.com/2026/zero-days/)
* "...discovered 22 vulnerabilities over the course of two weeks...a fifth of all high-severity Firefox vulnerabilities that were remediated in 2025." – [Partnering with Mozilla to improve Firefox’s security](https://red.anthropic.com/2026/firefox/)
* "...capable of identifying and then exploiting zero-day vulnerabilities in every major operating system...subtle or difficult to detect...the oldest we have found so far being a now-patched 27-year-old bug in OpenBSD—an operating system known primarily for its security." – [Assessing Claude Mythos Preview’s cybersecurity capabilities](https://red.anthropic.com/2026/mythos-preview/)

Where does this leave us? My 🔮 is cloudy, but here is a guess.

## Micro-pessimism

The next year 2-3 years will be bad. It will feel like a reset of websites to the early 00's when the OWASP top 10 were not the norm, not a cautionary tail.

We'll see unprecedented numbers and severities of vulnerabilities disclosed in open source projects that are foundational to modern software. Teams will be buried alone in triage and patching.

Adversaries will abuse foundational models to identify and exploit new vulnerabilities. This could be in open source, compromising supply chains, or directly attacking corporate applications.

There are tremendous asymmetries for attackers in this time horizon. They can scale up more agents. They can hunt liberally across multiple companies and attack surfaces. In spite of oragnizations' best defenses, failure only requires one successful attack. And of course, attackers have an asymmetry in morals.

Given this, there are just a few obviously useful asymmetries in the other direction. In most cases, this isn't public information.

First and similarly, organizations know their most worrisome areas (weakest, most important). They're aware of what keeps them up late.

Second, organizations are the only ones with access to their codebase. 

Organizations should act on both in combination. This is something attackers can't do. They're limited to an external attack surface. Run agentic vulnerability scanners against their codebases. Direct them to the most worrisome areas and entry points first. Prioritize ruthlessly. Repeat.

Go.

## Macro-optimism

That said. I think the future can be bright. The systems we build and code we write 1-2 years from now, reviewed by frontier models for flaws from the start, can be the most secure in history.

5 years from now, we'll shake out the worst of the historical issues. The new norm will be laughably secure systems.

Onward.

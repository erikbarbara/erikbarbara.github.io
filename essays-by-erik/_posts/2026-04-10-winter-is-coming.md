---
layout: post
title: Winter Is Coming
---
> Winter is coming.
> 
> – House of Stark

A year ago, most engineers, myself included, thought Copilot and Cursor were "cute". That's nice. They can write tests or auto-complete a few lines.

Today engineers turn over entire features to Claude Code and let it burn.

A sea change has occurred in AI capabilities these past 6 months. 

Security is not unaffected. A few recent Anthropic announcements:

> ...found and validated more than 500 high-severity vulnerabilities.
> 
> – [Evaluating and mitigating the growing risk of LLM-discovered 0-days](https://red.anthropic.com/2026/zero-days/)

> ...discovered 22 vulnerabilities over the course of two weeks...a fifth of all high-severity Firefox vulnerabilities that were remediated in 2025.
> 
> [Partnering with Mozilla to improve Firefox’s security](https://red.anthropic.com/2026/firefox/)

> ...capable of identifying and then exploiting zero-day vulnerabilities in every major operating system...subtle or difficult to detect...27-year-old bug in OpenBSD—an operating system known primarily for its security.
> 
> [Assessing Claude Mythos Preview’s cybersecurity capabilities](https://red.anthropic.com/2026/mythos-preview/)

Where does this leave us? My 🔮 is cloudy, but here is a guess.

## Micro-pessimism

The next 2-3 years will be bad. It will feel like a reset of the internet to the early 00's when OWASP Top 10 in the wild was the norm, not a cautionary tail.

We'll see an unprecedented volume of high-severity vulnerabilities in open source projects foundational to modern software. Teams will be buried in triage and patching.

Adversaries will abuse frontier models to identify and exploit new vulnerabilities in open source, compromise supply chains, and directly attack corporate applications.

There are tremendous asymmetries for attackers. They can scale up more agents, hunting across companies and attack surfaces. In spite of organizations' best defenses, failure only requires one successful attack. And of course, attackers have an asymmetry in morals.

Given this, there are only a few obviously useful asymmetries in the other direction.

First, organizations know their most worrisome areas (weakest \|\| most important). They know what keeps them up.

Second, organizations are the only ones with access to their codebase. 

Organizations should act on both in combination. Run agentic vulnerability scanners against codebases. Direct them to the most worrisome areas and entry points first. Prioritize ruthlessly. Repeat.

Because attackers can't–yet. They're limited to external attack surfaces.

Go.

## Macro-optimism

The future can be better. The systems we build and code we write 1-2 years from now, reviewed by frontier models for flaws from the start, can be the most secure in history.

5 years from now, we can shake out the worst of the legacy issues. The new norm can be laughably secure systems.

Onward.
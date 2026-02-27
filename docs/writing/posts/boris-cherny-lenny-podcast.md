---
draft: false
date: 2026-02-27
categories:
  - fde
  - ai
---

# What Claude Code's Creator Validated About Forward Deployed Engineering

Last week, Boris Cherny appeared on [Lenny's Podcast to talk about Claude Code](https://www.lennysnewsletter.com/p/head-of-claude-code-what-happens) — the AI coding assistant that now generates 4% of all GitHub commits and helped Anthropic achieve a 200% productivity increase.

Every major insight Boris described — from building for future capability rather than current constraints to finding product-market fit through "latent demand" — perfectly captured what we'd been doing as Forward Deployed Engineers at Palantir for over a decade. It was like listening to someone independently discover gravity.

For seven years at Palantir, I lived the FDE model: small, elite teams embedded directly with customers, building systems ahead of their current capability, discovering requirements by watching how people actually worked rather than what they said they needed. Boris validated that this approach isn't legacy — it's the future of how we'll build AI products.

## Building Six Months Ahead

"Build for the model 6 months from now, not today," Boris said. The Claude Code team deliberately avoided over-scaffolding. They gave the model tools and goals and got out of the way, betting on rapid capability improvements rather than constraining the system to current limitations.

This hit me because it's exactly how FDEs approach customer deployments. We don't build systems for where an organization is today — we build for where they'll be in six months. When I was deploying Palantir at large enterprises, the worst mistake was to over-constrain the system to current workflows. The org would evolve, their data would grow, their processes would mature, and suddenly the system we'd carefully tailored to their "requirements" became a straightjacket.

The best FDE deployments gave customers slightly more capability than they could immediately use. We'd build data pipelines that could handle 10x their current volume. We'd create analysis workflows that assumed they'd eventually want to ask more sophisticated questions. We'd design user interfaces that didn't require retraining when their team grew from 5 to 50 people.

This wasn't over-engineering — it was under-constraining. Just like Claude Code bet on the model getting smarter, we bet on the customer getting more sophisticated.

## Latent Demand as Product Compass

One of Boris's revelations was that Claude Code's breakthroughs came from watching how people used it in creative ways. Data scientists running SQL queries in terminal windows. Non-technical users asking it to help grow tomatoes. People recovering corrupted wedding photos. This "latent demand" led to Cowork, built in just 10 days because they could see exactly what users were trying to do.

"Latent demand" is just Boris's term for what FDEs do every single day: sit with users and watch how they actually work.

The best features I ever built came from observing workarounds. An analyst who'd manually copy-paste data between systems every morning because the official integration was too rigid. An operations team that kept a separate spreadsheet to track what the official dashboard couldn't show them. An investigator who'd screenshot charts to paste into Word documents because the export function didn't capture what they needed to communicate.

These weren't feature requests — they were organizational antibodies. Users working around the system to get their real job done. Standard product management would survey these users and ask what features they wanted. They'd probably say "better export" or "more integration options." But that's not what they actually needed.

FDEs watch the workflow, not the words. We see the person taking screenshots and realize they don't need better export — they need a way to tell stories with data. We see the manual copy-pasting and realize the issue isn't integration — it's that the official process doesn't match how the work actually flows.

The most successful FDE engagements came from finding latent demand the customer couldn't articulate themselves. Not because they were dumb, but because they were so close to their daily work they couldn't see the pattern.

## Ideas Over Engineering Capacity

"Coding is largely solved," Boris said. "The bottleneck is ideas and prioritisation." In the AI era, the new scarcity isn't engineering capacity — it's knowing what to build.

This validates everything FDEs were designed to solve. We were never primarily about coding. Yes, we could write software — often quite quickly — but our real value was understanding the problem deeply enough to know what to build.

The best FDE I worked with at Palantir wasn't the best coder on the team. They were the person who could sit in a room with a counter-terrorism unit and figure out what actually mattered. Who could distinguish between what the organization said it needed and what would actually make their mission successful. Who could see patterns across different deployments and recognize when a specific customer's problem was actually a general case of something we'd solved before.

This person would often write less code than junior engineers on the team. But they'd save months of work by solving the right problem the first time.

Now that AI can generate most code, this skill becomes even more critical. If Claude can write your functions, your value is knowing which functions need to exist.

## The Death of "Software Engineer"

"The title 'software engineer' is dying," Boris observed. "Builder is the new reality." As AI democratizes coding, roles blur between engineering, product, design, and deployment.

FDEs were always "builders." Our job description was impossible to write because we did everything: product research, technical architecture, user interface design, data engineering, deployment operations, user training, and ongoing support. We didn't fit neatly into any org chart because the role was defined by outcome, not function.

Traditional software engineering was about implementing specifications. Someone else figured out what to build; engineers built it. But FDE work was always end-to-end ownership. We figured out what to build, built it, deployed it, and lived with the consequences.

This frustrated a lot of people who wanted clean role boundaries. But it was extraordinarily effective for solving complex, novel problems where the solution space wasn't well-defined.

The industry is catching up to what Palantir figured out years ago: when you're building something truly new, you need people who can think across the entire stack — technical, product, and operational. "Builder" is a better word than "engineer" because it captures the full scope.

## What This Means for AI Companies

If you're building AI products today, the FDE model isn't legacy — it's your playbook.

Stop organizing around functional silos. Find people who can think across the whole problem, give them access to the best tools, and embed them directly with customers. Build slightly ahead of current capability rather than constraining to current workflows. Watch how people actually use your product, especially the ways they "misuse" it.

Most importantly: understand that your bottleneck isn't engineering capacity anymore. It's product judgment. It's knowing what to build. It's finding the latent demand that customers can't articulate themselves.

The companies that figure this out first will eat everyone else's lunch. Not because they have better AI models, but because they'll build the right things.

Boris Cherny just validated fifteen years of FDE practice. The future belongs to builders who can think end-to-end, work embedded with customers, and see patterns others miss.

The tooling has changed. The principles haven't.


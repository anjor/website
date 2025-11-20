---
draft: false
date: 2025-11-20
categories:
  - hiring
---

# The FDE Manifesto: What Would Stokes Do?

This is a version of a document I had written during my time at Palantir. 

Stokes was a legendary FDE at Palantir, and I learnt a lot by emulating his way of operating.
This wasn't hero worship—it was shorthand for a specific way of operating that separated exceptional FDEs from the rest.

Here are the tactical principles that define that approach.

## Never Take Shortcuts That Compound

- Don't make config changes that aren't product defaults
- Never restart services "just to see if it fixes things"—you're destroying evidence
- Never deploy dirty builds. If you're on a branch, getting back to mainline is P0
- Every custom modification is technical debt with compound interest

## Own the Product Stack

- Clone the repos. Make them build. Start submitting PRs
- When you get a stacktrace, read it. Form a hypothesis before opening tickets
- Know the architecture cold—when telemetry fails, it's your only map
- If a workflow is blocked on a feature, scope it and build it yourself

## Treat Information as Infrastructure

- Ensure logs and metrics are collected properly from day one
- Master telemetry tools—they're not optional
- Read everything: docs, runbooks, release notes, support tickets, Stack Overflow
- Monitor what other teams are encountering—their problems will be yours soon

## Root Cause Everything

- Never accept "it's working now" as resolution
- Gather data and form hypotheses before implementing fixes
- You must be able to explain why the product broke and why your fix worked
- Document your debugging process for future you

## Build Strategic Relationships

- Every support ticket is a relationship-building opportunity with core engineers
- Contribute field signal to product direction—you're their eyes and ears
- Know the product team's roadmap and weigh in based on deployment reality
- Getting your tickets prioritized is a function of relationships, not just severity

## The Strategic Thread

These aren't random best practices. They're behaviours that compound into a strategic advantage: **radical ownership of outcomes**.

When you refuse shortcuts, you're choosing long-term system health over short-term wins. When you master the product stack, you're becoming a peer to the product team, not a consumer. When you root cause everything, you're building institutional knowledge that makes future problems trivial.

This is what makes the FDE model powerful. You're not there to implement solutions—you're there to own outcomes completely. That ownership manifests in these specific, tactical behaviors that seem small but fundamentally change how you operate.

The question isn't whether you can do these things. It's whether you will.

---

*Building an FDE organization? These principles are your hiring rubric. Look for engineers who already think this way.*

---
draft: false
date: 2026-02-22
categories:
  - hiring
  - ai
---
# Interviewing in the age of AI

Interviews have always been a bad proxy. You get maybe an hour with someone and you're supposed to figure out whether they'll be effective in a role that plays out over months and years. You can't replicate real working conditions—the codebase they'd actually work in, the team dynamics, the ambiguity of real problems. So you construct artificial scenarios and hope the signal transfers.

That fundamental challenge hasn't changed. However, AI has made the gaps in our proxies impossible to ignore.

## The signal problem

The core question in any interview is: *can this person actually do the job?* Everything else—the whiteboard problems, the take-homes, the system design rounds—is just scaffolding to get at that question indirectly.

But with AI, it's now possible to offload much of the thinking and problem-solving itself, making the assessment even harder.

When someone submits a clean take-home with sensible architecture and thorough tests, one used to be able to assume a baseline of understanding behind it. This is no longer true. 
Not because the code is bad—it's often excellent. But GitHub Copilot, Claude, and ChatGPT have converged on identical patterns. A few years ago, messy but functional code suggested a real engineer working under pressure. Now, *too-perfect* code could be the tell, but penalising clean code is obviously absurd.

At the same time **banning AI isn't the answer**. I *want* engineers using AI. It's the most significant productivity tool to hit software engineering in decades, and anyone not using it is leaving value on the table. The question I'm actually trying to answer in an interview is "can you think *with* AI, or are you just deferring *to* it?"

## Old formats, honest limitations

These interview formats didn't suddenly break. They always had limitations as proxies for real work. AI just made those limitations undeniable.

**Long take-home exercises** were always a noisy signal. A four-hour project tells you someone can deliver polished work with unlimited resources and no time pressure—which is rarely what the actual job looks like. AI turned the noise up to eleven: now the output mostly tells me the candidate has access to coding tools. Table stakes.

**LeetCode-style problems** were always testing a narrow skill—pattern recognition and algorithmic recall—that correlates weakly with day-to-day engineering. AI happens to be exceptionally good at exactly this narrow skill, so now I can't even get the weak signal I used to.

**Anything with a "correct answer"** has this problem. The clearer the specification, the easier it is for AI to solve. Which is ironic—we used to think clear specs made for fair interviews, which they did. They also made for easy prompts.

I'm not saying these formats are worthless. But the signal they produce has shifted from "can this person solve problems?" to something murkier. And rather than trying to salvage them, I'd ask: what formats actually test the thing I care about?

## What I'm looking for now

The formats I've been experimenting with share a common thread: they test whether someone can think, not whether they can produce output. AI is great at producing output, but thinking, judging and validating is still a human job.

### Shorter exercises + longer conversations

Instead of a four-hour take-home, a thirty-minute exercise followed by forty-five minutes of discussion. The code is a starting point, not the deliverable.

*Why did you structure it this way? What would you change if the requirements shifted to X? Where would this break at scale? What's the ugliest part of this code?*

AI can generate code. It can't explain the tradeoffs you *considered and rejected*. It can't tell me about the moment you started down one path, realised it was wrong, and backed out. And I also just ask directly: how did you use AI? That question alone is surprisingly revealing. Someone who used AI well can articulate what they delegated, what they modified, and what they rejected. Someone who deferred to it entirely tends to get vague.

Those conversations reveal thinking—including whether someone used AI effectively as a tool versus blindly accepting its first suggestion.

### Live investigation instead of live coding

Writing code from scratch under interview pressure was always a weird skill to test. It didn't map well to real work even before AI.

Investigation is different. I give candidates a system that's misbehaving—not a syntax error, something behavioural. A race condition. A caching issue. A misunderstood API contract. And yes, they can use whatever tools they want, including AI.

What I'm watching isn't whether they can find the bug. Claude Code can find bugs. What I'm watching is everything *around* the finding: how they scope the problem, what questions they ask before touching the code, which hypotheses they form first, what they choose to validate versus take on faith.

The person directing the investigation matters more than the investigation itself. A strong engineer will use AI to speed up the search but still decide *where to search*. They'll sanity-check the AI's suggestion against their own understanding rather than blindly applying a fix. They'll know when the tool is confidently wrong.

Someone who's genuinely thinking will say things like "that can't be the issue because X" or "let me verify this assumption first." Someone who's outsourced the thinking will paste the error into a chat window and accept whatever comes back.

Watching someone use AI *well* during an interview is actually one of the strongest positive signals I've found. When a candidate uses AI to quickly test a hypothesis, then critically evaluates the result and adjusts course — that's exactly the workflow I want to see on the job.

### System design with real constraints

AI is great at generating architecture diagrams and textbook answers. It's less great at navigating the messy reality of *your specific situation*.

When I ask about system design, I focus on constraints. *What if we need to support 10x the traffic? What if the team is two people? What if we need to ship in four weeks? What if this has to run in air-gapped environments?*

Good engineers make different choices in different contexts. They can explain *why* this context changes the answer. Someone who's genuinely thinking—whether or not they used AI to explore options—will navigate these pivots fluidly. Someone who's outsourced the thinking will flounder when the constraints shift.

### Roleplay scenarios

This is the most experimental—but possibly the most promising.

FDE and customer-facing engineering roles need skills that are fundamentally about human judgment: real-time conversation, reading the room, managing frustrated stakeholders, diagnosing problems under pressure.

I've started using roleplay scenarios where I play a customer with a problem, and the candidate has to figure out what's actually wrong—not what I *say* is wrong.

## Concrete example: The Broken Dashboard

Here's the shape of an interview I've been running lately.

I play a frustrated stakeholder—a senior executive at a large organisation. Something is wrong with a dashboard that feeds into a critical business process. The numbers don't match what another team is reporting. There's time pressure. The candidate's job is to help me figure out what's going on.

The scenario is designed so that the obvious explanation ("the dashboard is broken, fix the code") is wrong. The real root causes are subtler—the kind of thing you'd only uncover by asking careful questions about data sources, definitions, and upstream processes. There's no bug to patch. The discrepancy is fully explainable, but only if you resist the urge to jump to conclusions.

I won't give away more than that—I plan to continue using this interview.

### What this tests

**Problem diagnosis under pressure.** Does the candidate immediately promise to "fix" the thing, or do they slow down and figure out what's actually happening?

**Customer communication.** Can they manage a frustrated stakeholder while still asking clarifying questions? Do they resist the urge to commit to solutions before understanding the problem?

**Data literacy.** Do they think to ask about how the numbers are generated? Or do they assume the system is broken because that's what the customer said?

**Ownership.** When they figure out the root cause, do they offer a path forward—both for the immediate crisis and the longer-term fix?

### Why this works

This isn't a prompt you can give to ChatGPT. There's no code to generate. The "answer" emerges through conversation—through noticing that the stakeholder doesn't actually understand how the system works, through asking the right diagnostic questions, through realising that different teams might be measuring different things.

It tests the thing that actually matters in deployment roles: can you figure out what's really going on, communicate clearly under pressure, and move towards a resolution? Those skills don't change regardless of what tools you're using—and they're the hardest to fake.

## What I'm still figuring out

I won't pretend I've cracked this. Some open questions:

**Consistency.** Roleplay scenarios are harder to evaluate objectively than coding tests. Different interviewers might reach different conclusions about the same conversation.

**Fairness.** These approaches favour candidates who are comfortable thinking out loud, explaining their reasoning, engaging in back-to-back. That might disadvantage candidates who are brilliant but less verbally fluent.

**Scalability.** A forty-five-minute investigation exercise with live observation doesn't scale like a take-home. You need more interviewers, more coordination.

**AI will keep improving.** Maybe next year there's an AI that can roleplay its way through a customer scenario. Maybe debugging exercises become as compromised as LeetCode. I expect to keep iterating on this—the target is always moving.

## The goal hasn't changed

I want to hire people who can do the job. The job now includes using AI effectively—so I'm not designing interviews to exclude AI. Instead, I'm designing interviews that reveal whether someone can *think*, whether or not they have AI in the room.

The best engineers I work with use AI constantly. They also know when to override it, when to dig deeper, when the AI's confident answer is confidently wrong. That judgment is what I'm interviewing for.

I think interviews are heading somewhere interesting. The formats that survive will be the ones that test what AI can't fake: genuine understanding, real-time judgment, and the ability to navigate ambiguity with another human. The interviews of five years from now will look less like exams and more like working sessions — because that's what they should have been all along.

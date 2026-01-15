---
draft: false
date: 2025-07-05
categories:
  - hiring
---
# The Database Selection Trap: Why Your Technical Interviews Might Be Testing the Wrong Things

I recently watched a talented engineer fail a system design interview, and it made me question everything I thought I knew about technical hiring.

The candidate was asked to design a data model for a food delivery platform. They chose PostgreSQL. When the requirements evolved—millions of drivers, real-time location updates, flexible schemas—they couldn't pivot to NoSQL. Despite perfect nudges from the interviewer, they remained stuck.

Here's what haunted me: In any real engineering role, this person would have thrived. They'd have teammates suggesting alternatives. They'd have design reviews. They'd have documentation and prior art to reference.

But in that interview room, artificially isolated from every resource that makes modern engineering possible, they failed.

This isn't a story about lowering the bar. It's about recognizing that many of our "standard" technical interviews are testing the wrong things entirely.

## The Comfort of Cargo Cult Interviews

We've all been there. You're tasked with building a hiring process, so you do what seems logical: look at what successful companies do and copy it. Google does system design interviews? So do we. Facebook does algorithm challenges? Add it to the list.

But here's the problem: we copy the form without understanding the function.

That database selection question? It made perfect sense... until I asked myself what we were actually testing:
- Can this person independently choose the right database in isolation?
- Or can this person build great systems in a collaborative environment?

These are fundamentally different skills. And only one of them matters for the job.

## The Three Interview Traps That Filter Out Great Engineers

After auditing dozens of hiring processes, I've identified three common traps that eliminate potentially excellent engineers for the wrong reasons:

### 1. The Isolation Trap

**The Setup:** Candidate must solve everything alone, from first principles, without any external resources.

**The Problem:** This isn't how engineering works. Ever. Modern engineering is collaborative, iterative, and builds on existing knowledge. The best engineers aren't those who can reinvent everything in isolation—they're those who can leverage their team and tools effectively.

**Real Example:** A senior engineer with 10 years of experience couldn't remember the exact syntax for a specific PostgreSQL window function. In reality, they'd look it up in 30 seconds. In the interview, they struggled for 10 minutes and lost confidence.

### 2. The Perfection Trap

**The Setup:** One significant stumble means failure, regardless of overall performance.

**The Problem:** Engineering is about recovery and iteration, not perfection. Some of the best engineers I've worked with are great precisely because they recognize mistakes quickly and course-correct effectively. But our interviews often punish any deviation from the "perfect" answer.

**Real Example:** A candidate designed 90% of an excellent solution but made one architectural decision that would have caused scaling issues. Instead of seeing if they could identify and fix it with feedback (like they would in a real design review), they were marked down significantly.

### 3. The Specific Knowledge Trap

**The Setup:** Testing specific technical knowledge rather than fundamental thinking.

**The Problem:** Technology changes. What matters is engineering judgment, learning ability, and problem-solving approach. But we often test whether someone memorized the specific technologies we happen to use today.

**Real Example:** A brilliant engineer "failed" because they weren't familiar with Kafka. They understood event-driven architectures perfectly and had used RabbitMQ extensively. Given a week on the job, they'd be productive with Kafka. But the interview didn't capture that.

## A Better Way: Design Interviews That Mirror Reality

The solution isn't to make interviews easier. It's to make them more realistic. Here's a framework I use with my clients:

### Step 1: Start With Role Reality

Before designing any interview, answer these questions:
- What does a typical day look like for this engineer?
- What resources do they have access to?
- How do they collaborate with others?
- What does "great performance" actually look like?

### Step 2: Map Backwards to Interview Signals

For each critical skill, ask:
- What's the minimal signal we need to assess this?
- How can we test this in a way that mirrors reality?
- What support would they have in the real role?

### Step 3: Build in Collaboration and Iteration

Instead of testing isolated perfection, test realistic excellence:
- Allow candidates to ask clarifying questions (like they would with stakeholders)
- Provide feedback and see how they incorporate it (like in code review)
- Let them reference documentation for syntax (like they would with Google)
- Focus on their thinking process, not memorized solutions

## Case Study: Redesigning the System Design Interview

Here's how we transformed that problematic database interview:

**Old Version:**
"Design a data model for a food delivery system. Choose your database and justify it."

**New Version:**
"Let's design a data model for a food delivery system together. Here's our current scale and requirements. As we go, I'll play the role of your teammate and share what we've learned from our existing systems."

The key changes:
1. **Collaborative framing** - "together" and "teammate" set the tone
2. **Living requirements** - Requirements evolve during the discussion, like real projects
3. **Historical context** - They can ask about existing systems and constraints
4. **Focus on reasoning** - We care more about how they think through trade-offs than their initial choice

The result? We started identifying engineers who would excel in our actual environment, not those who could perform in artificial interview conditions.

## The Hidden Cost of Bad Interviews

Every time we filter out a great engineer because they stumbled on an artificial constraint, we're not just losing a potential hire. We're:
- Reinforcing biases toward certain backgrounds (those who've practiced these specific interview formats)
- Extending our hiring timeline as we search for unicorns who excel at interviews AND engineering
- Building teams that optimize for interview performance over actual job performance

## Your Next Step: The One-Question Audit

Pick one question from your current interview process. Just one. Now ask yourself:

*"If a strong engineer failed this specific question but excelled at everything else, would I bet they'd fail in the actual role?"*

If the answer is no, you're testing the wrong thing.

## The Path Forward

Great hiring isn't about finding engineers who can solve puzzles in isolation. It's about identifying those who will thrive in your specific environment, collaborate effectively with your team, and deliver value to your customers.

That means designing interviews that test for reality, not ritual.

Start with one interview. Make it 10% more realistic. See what changes.

Because somewhere out there is an engineer who would be fantastic on your team but can't remember if MongoDB uses documents or collections in the heat of an interview.

Do you really want to miss out on them because of that?

---

*Implementing an FDE hiring program? See my [FDE Advisory Materials](https://anjor.github.io/fde-advisory-materials/) for interview templates, scorecards, and detailed process guides.*

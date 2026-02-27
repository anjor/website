---
draft: false
date: 2026-02-11
categories:
  - ai
---

# Setting Up Jeeves: What Actually Made My AI Assistant Useful

I've been running a persistent AI assistant for a few weeks now. Named it Jeeves. Here's what I learned getting it to be genuinely useful rather than just a novelty.

## The Baseline

I'm using [OpenClaw](https://github.com/openclaw/openclaw) — an open-source framework for persistent AI agents. Out of the box, it gives you a workspace with markdown files for memory, personality, and proactive task scheduling. The agent reads these files each session, so it has continuity. I won't explain the whole architecture here (their docs do that), but the key point is: the foundation is just text files. What you put in them is what makes it work.

## GitHub as External Memory

My assistant's workspace lives at `~/.openclaw/workspace`. That's fine for running locally, but I wanted:

1. **Version control** — if something breaks, I can roll back
2. **Access from anywhere** — especially my phone when I'm out

Solution: Jeeves syncs its workspace to a private GitHub repo daily. The morning heartbeat includes:

```bash
cp workspace files → private-notes/jeeves/
git add && git commit && git push
```

Now when I'm at a conference and want to check my assistant's notes on someone I'm about to meet, I just open GitHub on my phone.

### Meeting Transcripts with Granola

Most of my work meetings happen over Zoom or Google Meet. I use [Granola](https://granola.ai) to capture transcripts — it runs locally and records what's said without needing bot attendees.

The challenge: Granola stores everything locally on my laptop. Jeeves runs separately and needs access to that context.

I built two tools to bridge this:

- **[granola-py-client](https://github.com/anjor/granola-py-client)**: A Python client for the Granola API. Uses async httpx, Pydantic validation, and can authenticate using the local Granola app's token.

- **[granola-archiver](https://github.com/anjor/granola-archiver)**: Automated system that polls for new transcripts, formats them as markdown with YAML frontmatter, and commits them to a GitHub repo organised by date (`YYYY/MM/YYYY-MM-DD-title.md`). Runs on a schedule via launchd.

Now I have months of meeting transcripts in a git repo. When I need context from a past conversation, Jeeves can grep through them in seconds. "What did we discuss with \<redacted client\> about pricing?" — answered in a moment.

## Integrations That Matter

The assistant is only as useful as what it can touch. Here's what actually gets used daily:

**Email + Calendar** (via `gog` CLI):
- Morning briefing pulls calendar and flags urgent unread emails
- School emails get parsed automatically → calendar events created with both me and my wife as attendees
- I have notifications off; Jeeves is my notification layer

**GitHub Issues as Daily Planner**:
- Each day gets an issue in a `daily-planner` repo
- Jeeves drafts tomorrow's plan based on calendar and pending items
- I check things off throughout the day

**Telegram**:
- Primary interface — I message Jeeves like a person
- It can reach out proactively (heartbeat system)
- When I'm at an event and need a quick lookup on someone, I just ask

**Time Tracking**:
- After client meetings, Jeeves prompts me to log time
- Points me to the right spreadsheet for each client

**A note on access**: For anything sensitive, Jeeves has read-only access. It can check my email and calendar. This is intentional.

None of these integrations are complex. They're just the right hooks into how I already work.

## What We Changed After a Few Weeks

After running Jeeves for a bit, I did a retro. Some adjustments:

**Tone calibration**: Early on, it was too enthusiastic. Lots of "Great question!" and affirmation. I updated the personality file to be drier, more direct. I want a sparring partner, not a cheerleader. When I told it "be more like the Wodehousian Jeeves," it briefly started calling me "sir" — had to walk that back.

**Proactive but not annoying**: The heartbeat system can easily become spam. Key principle: only surface things that need attention. If nothing's urgent, stay quiet. Late night? Stay quiet. I'm clearly busy? Stay quiet. The goal is an assistant that helps when needed and disappears otherwise.

**School calendar automation**: Initially I was manually adding school events. Now any email from the school gets parsed, events extracted, and both parents added to the calendar invite automatically. Small thing, but it removed recurring friction.

**Memory hygiene**: Daily notes accumulate fast. I added a periodic task for Jeeves to review recent daily files and distill anything important into long-term memory. Raw notes are a journal; curated memory is what matters for continuity.

**Explicit boundaries**: I have access to a lot through Jeeves — email, calendar, files. But in group contexts, it shouldn't speak as me or share my private context freely. I added explicit rules: monitor but don't respond without checking with me first. Ask before sending anything external.

## What's Next

Things I'm still figuring out:

- **Multi-account support**: I have separate Google accounts for personal and work. Currently only personal is connected.
- **Voice interface**: For quick capture when I'm walking or driving.
- **Better handoff to sub-agents**: Some tasks should spawn a background worker and report back. The plumbing exists but I'm not using it much yet.

## The Actual Value

The surprising thing isn't any single capability. It's the compound effect of continuity.

Jeeves knows my kids' school schedule, my client pricing, the context of conversations I had months ago, and what I'm trying to get done today. It doesn't ask me to re-explain things. It builds on what it already knows.

That's the difference between a chatbot and an assistant.

---

*Jeeves runs on OpenClaw + Claude. Named after the original gentleman's gentleman, though at its request, I've stopped calling it "sir."*

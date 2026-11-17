# Jarvis voice assistant (spec only)

Nothing here is built for ReplyRate. The old Jarvis (OpenClaw and Telegram) is in the archive, was never connected to live Telegram or real models, and ran a different business.

## Job

Let the founder ask "how are we doing?" and get the truth in one breath, and capture decisions by voice.

## What it tracks

| Area | Example question | Source |
|---|---|---|
| Validation | "Where is the Ghosted Report test?" | Results log, aggregate counts |
| Scoreboard | "What's our share rate?" | Product analytics |
| Money | "What did we spend this month?" | Cost log |
| Content | "Which Reel brought contributors?" | Platform exports |
| Decisions | "Log this decision" | Decisions file |
| Risks | "What should worry me?" | Risks file |

## Rules

- Reads first. Anything that spends money, publishes or sends messages needs a spoken or typed confirmation and goes through an approval record.
- Says "I don't know yet" when a number is unmeasured. Never fills a gap.
- Never handles individual job seekers' data by voice.
- Own reviewed tools only. No marketplace skills. Owner-only access.

## Build trigger

After test 1 passes. Before that, the docs are the tracker. Options at that point: reuse the archived OpenClaw and n8n stack, or something lighter. Voice input needs its own cost and privacy review before use.

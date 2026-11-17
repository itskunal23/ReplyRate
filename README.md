# AI Startup

The working company behind **ReplyRate** (working name, availability unchecked): a tool that shows job seekers which employers actually reply, so they know where to spend their next application.

> **Status, 2026-11-08: idea phase.** The direction is locked. Nothing is built except a clickable prototype that uses invented example data. No one has used this, paid for it or validated demand yet.
> **What to do next:** [NEXT_STEPS.md](NEXT_STEPS.md)

## See it

Open [`prototype/replyrate-ui/index.html`](prototype/replyrate-ui/index.html) in a browser. It shows the launch card, the working app, the math, the money and the road to the end goal.

## The idea on one page

| | |
|---|---|
| **Problem** | Job seekers apply into silence and cannot tell a hiring employer from one that never replies. |
| **Launch** | Free Ghosted Report: enter your counts, get a shareable "Ghosting Invoice" in 60 seconds. No account, no Gmail. |
| **Core loop** | Log an application, see the employer's real reply rate, decide where your next hour goes. |
| **Edge** | A shared dataset of outcomes that a résumé tool does not have. It starts empty, and that is the biggest risk. |
| **Money** | $9 best-bets report with a reply guarantee, $49 once when hired. Employers later pay to learn, never to change a score. |
| **Marketing** | Human-directed, AI-assisted Reels and Shorts. Measure data contributors, not likes. |
| **End goal** | Ghosting becomes visible and costly, so employers start replying. |
| **Honest score** | About 7/10 today, untested. Every score is judgment. See the [memo](docs/05-investment-committee/REPLYRATE_MEMO.md). |

## Project map

| Path | Contents |
|---|---|
| [`docs/`](docs/README.md) | Thesis, opportunities, research, financials, validation, memo, operating model, decisions |
| [`prototype/`](prototype/README.md) | Clickable UI with example data. Not the product. |
| [`ops/`](ops/README.md) | Mirror to the Windows folder. The only running automation. |
| [`archive/`](archive/README.md) | The retired AI media stack, restorable |
| `CLAUDE.md` | Working rules for Claude Code on this repo |

## Where the files live

- **Live project (edit here):** `\\wsl.localhost\Ubuntu\root\ai-startup`
- **Windows mirror (view here):** `C:\Users\goenk\Downloads\AI Startup`, refreshed every minute. Changes made there get overwritten.

## Ground rules

- Docs first. No product code until the [Ghosted Report test](docs/04-validation/EXPERIMENTS.md) passes.
- Nothing is published, purchased or connected without explicit owner approval.
- Secrets never enter tracked files or logs.
- Every number carries an evidence label: [V] verified, [C] calculated, [A] assumption, [H] hypothesis.

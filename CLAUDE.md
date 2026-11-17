# CLAUDE.md

AI Startup is a solo, idea-phase company building **ReplyRate** (working name): which employers actually reply to applicants. Start with `docs/README.md`. The locked direction is `docs/00-thesis/PRODUCT_SPEC.md`.

## Current status

- Idea phase. Docs and one clickable prototype with invented data. **No product code yet.**
- The next gate is the Ghosted Report test in `docs/04-validation/EXPERIMENTS.md`.
- No real user, payment or demand has been validated. Do not write as if it has.

## Environment

- Windows 11 laptop, i7-10510U, 16 GB RAM, no NVIDIA GPU.
- Project at `/root/ai-startup` in WSL distro `Ubuntu`.
- `/root/ai-startup` is mirrored one way to `C:\Users\goenk\Downloads\AI Startup` by the `ai-startup-mirror` systemd timer. **Always edit the WSL copy.**
- Files written through `\\wsl.localhost\...` or `/mnt/c` come out CRLF. Run `sed -i 's/\r$//'` on them.
- From Git Bash, prefix WSL calls with `MSYS_NO_PATHCONV=1` and run a script file, not a heredoc, when the script starts a child that reads stdin.

## Layout

- `docs/00-thesis` to `docs/07-decisions`: the company in writing
- `prototype/replyrate-ui/index.html`: single-file UI, invented data only
- `ops/mirror/`: mirror script and systemd units
- `archive/media-stack/`: retired AI media stack with its `.env` and backups. Read `archive/README.md` first.

## Rules

- **Docs before code.** Do not start product code until the validation gate passes or the owner explicitly overrides it. The owner overrode this for the job-post service only (D-008).
- Label evidence: [V] verified external, [C] calculated from stated inputs, [A] assumption, [H] untested hypothesis. Never invent data.
- Never claim demand, traction or an integration without real evidence or an actual end-to-end test.
- Record decisions in `docs/07-decisions/DECISIONS.md`. Log every test in `docs/04-validation/RESULTS_LOG.md`.
- **Always ask the owner before:** spending money or enabling paid APIs, connecting accounts, publishing, sending external messages, deleting business data, irreversible config changes.
- Budget limits: $0 to $100 startup capital, $0 to $50 per month.
- No secrets in tracked files or logs. `.env` is generated, mode 600, git-ignored.

## Product guardrails

- Never fake a percentile, a count or scarcity. Under 30 outcomes the app says "not enough data yet".
- Employers can never pay to change a score.
- No guilt notifications, punishing streaks or endless feeds. Every session ends with one next step.
- Public cards show counts, never company names. Do not name companies in Reels without samples and legal advice.
- Never sell identifiable data. 18+ only. Users are anxious and short of money: charge accordingly.
- Company names and job posts on the page are real and come from the service (D-008). Never invent or estimate a reply rate, count or repost for a real company. No rate under 30 reports.

## Archive

- `archive/media-stack` keeps compose project name `ai-media`, so its Docker volumes stay attached. Do not change it.
- Never run `docker compose down -v` on the archive.
- Jarvis is a spec only now (`docs/06-operating-model/JARVIS_VOICE_SPEC.md`). OpenClaw rules from the archive still apply if it returns: no marketplace skills, Telegram allowlist on.

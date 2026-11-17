# Decisions

Newest first. To reverse a decision, add a new entry.

## D-011 (2026-11-09): Expand ECC to the full set from main
**Choice:** the owner asked for all skills and powers. Replaces the narrower setup in D-010. Plugin tracks `main`, installed snapshot reviewed at commit `d2ef268` (unreleased, ahead of 2.2.3). `ECC_HOOK_PROFILE=strict`. All rule packs are in `.claude/rules/ecc`, and `.claude/rules/00-project-precedence.md` keeps `CLAUDE.md` on top. Added the `chrome-devtools` MCP server (`.mcp.json`, pinned 1.10.1) and global `ecc-universal@2.2.3` and `ecc-agentshield@1.6.0`.
**Left out on purpose:** `install.sh --profile full` (ECC says not to stack it on the plugin); paid or account-linked services such as ECC Pro and API-key MCP servers (need owner approval under `CLAUDE.md`).
**Reverse by:** `claude plugin uninstall ecc@ecc --scope project`, `npm uninstall -g ecc-universal ecc-agentshield`, then delete `.claude/` and `.mcp.json` in the WSL copy.

## D-010 (2026-11-09): Install ECC 2.2.3 as a project-scoped Claude Code plugin
**Choice:** the owner asked to install ECC (affaan-m/ECC, MIT). `ecc@ecc` is enabled in `.claude/settings.json`, pinned to tag `v2.2.3`, with `ECC_HOOK_PROFILE=minimal`. Rules adopted in `.claude/rules/ecc`: common coding-style and security, Python coding-style and security.
**Left out on purpose:** the `setup` wizard (it turns off commit attribution in global settings); `standard` hooks (they log every tool call and gate edits); common agents, testing and development-workflow rules (they conflict with how this repo works). This is a developer tool only. It does not change the validation gate or "docs before code".
**Reverse by:** `claude plugin uninstall ecc@ecc --scope project`, then delete `.claude/rules/ecc` and the ECC keys in `.claude/settings.json` in the WSL copy.

## D-009 (2026-11-09): Shared unlock, job watching, and safe links
Reply rates open for everyone at 30 reports, replacing the per-person give-to-get lock. People can watch a job; changes appear in the app on Today only (email needs accounts and is not built). Job links go to the employer first, then LinkedIn or Indeed. Glassdoor blocks real visitors with a security check, so Glassdoor-only jobs open a web search instead, and Glassdoor is used only for dates.

## D-008 (2026-11-09): Real employers and job posts, from JobSpy
The owner overrode the docs-before-code rule to build the job-post service (`service/`). It uses JobSpy 1.4.1 to check LinkedIn, Indeed and Glassdoor when someone searches, and stores every sighting so repost history accumulates. No proxies. Reply rates still come only from applicants, with a 30-report minimum, so real companies show no rate until then.

Open risk: LinkedIn's terms forbid scraping, and JobSpy is a scraper. Before any public launch, get legal advice and set `REPLYRATE_SITES` to drop boards that are not cleared, or move to public employer feeds (Greenhouse, Lever, Ashby). Runs on localhost only until then.

## D-007 (2026-11-09): One simple price, open to every job seeker
Free to check companies, $9 for the next 10 best bets with a reply guarantee, $49 optional once hired. The planned $15 monthly plan is dropped. Marketing addresses career stage, not age. Reply data still starts with about 200 widely applied-to companies.

## D-006 (2026-11-09): Posting history from official job boards, not LinkedIn
The owner wants job seekers to see how long jobs have been reposted. Use public job-board feeds and company career pages, because LinkedIn's terms forbid scraping. Show facts, not accusations. The collector is not built; building it needs owner approval because product code is gated on test 1.

## D-005 (2026-11-09): Product landing page leads with company search
The first screen says what the tool does and offers one action: search a company. The Ghosted Report moves lower on that page. The two-week test still uses a standalone report page, because search has nothing to show until real outcomes exist.

## D-004 (2026-11-08): Build a UI prototype with invented data only
A single-file page shows the whole product and end goal. Invented company names and example numbers, labeled as such, so nothing can be mistaken for real findings.

## D-003 (2026-11-08): Lock ReplyRate as lead idea
**Choice:** ReplyRate, launched with the Ghosted Report, marketed with Reels. The owner said "lock it" after the alternatives were reviewed. "ReplyRate" stays a working name until availability is checked.
**Alternatives:** see [Opportunities](../01-opportunities/OPPORTUNITIES.md).
**Reverse by:** failing test 1.

## D-002 (2026-11-08): Humane retention, no addictive design
The founder asked for an addictive product. We keep the honest hooks and refuse the manipulative mechanics, because users are anxious and short of money, and the product succeeds when they leave hired. See [Psychology and ethics](../00-thesis/PSYCHOLOGY_AND_ETHICS.md).

## D-001 (2026-11-08): Archive the AI media stack, rename to AI Startup
**Choice:** move the stack into `archive/media-stack`, stop its containers, keep its Docker volumes and backups.
**Reverse by:** [`archive/README.md`](../../archive/README.md). Git tag `media-stack-final` holds the last full version.

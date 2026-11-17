# Product spec (locked 2026-11-08)

Locked by the owner: ReplyRate as lead idea, launched through the Ghosted Report, marketed through Reels, with the psychology and finance ideas built in. The product name is a working name. A change here needs an entry in [Decisions](../07-decisions/DECISIONS.md).

The visual version is [`prototype/replyrate-ui/index.html`](../../prototype/replyrate-ui/index.html).

## 1. Ghosted Report (launch surface)

- Enter counts or a list. No account, no Gmail. A card in 60 seconds.
- Card line: "143 applications. 91 ghosted. 46 hours gone."
- Ghosting Invoice: addressed "Dear Employer", e.g. "46 hours of unpaid labor at $45/hour. Total due: $2,070. Status: never replied."
- The card states its rule: ghosted means no human reply after 30 days.
- Counts only. Never company names on a public card.
- After the card, one invitation: add company names to see who actually replies.

## 2. Core loop: Log, Reveal, Decide

| Step | Behavior |
|---|---|
| Log | Company, role, date. Under 15 seconds. Manual first; Gmail needs a costly Google review (from memory, check before planning on it). |
| Reveal | Reply rate, typical time to first reply, sample size. Under 30 outcomes: "Not enough data yet." |
| Decide | Up to three best bets a day. "This one has gone quiet, stop waiting." |

## 3. Screens

| Screen | Job | Key rule |
|---|---|---|
| Today | Three best bets and one thing to let go of | Finite. Ends with "You're done for today." |
| Applied | Waiting, Replied, Graveyard | Items become eligible for the Graveyard at 30 days of silence, and the user chooses |
| Companies | Search reply rates and real job posts | Shared unlock: at 30 reports a company's rate opens for everyone |
| Company | Rate, margin, timing, silence curve | Shows sample size. Employers cannot pay to change it. |
| Ghost Index | Public monthly number | Published only with stated method |
| You | "It's not you" comparison, report, hired | Comparison shown only with enough real people |

## 4. The math

- **Reply odds:** beta-binomial estimate per company, shrunk toward the field average when data is thin. Margin shown in plain words. Minimum 30 outcomes to display.
- **When silence means no:** survival analysis on time to first reply gives the chance a reply still comes after N days. Reply probability given silence to day d = p·S(d) / (p·S(d) + 1 − p).
- **Fair comparison:** adjust for role, level and field before comparing a person with others. Do not compare without it.
- **Trust (stage 2):** PageRank or EigenTrust-style weighting of vouches.

The prototype uses an exponential curve and a normal-approximation margin to illustrate this. Production needs real fitting and bias checks.

## 5. Money

See the [financial model](../03-financials/FINANCIAL_MODEL.md). Free to check companies. $9 for the next 10 best bets, with a reply guarantee. $49 optional once hired. No subscription. Employer products come later.

## 6. Out of scope until stage gates pass

Auto-apply, résumé rewriting, a feed, open anonymous chat between members, paid employer anything, Gmail sync, mobile app store release.

## 7. Done means

The [scoreboard](../04-validation/EXPERIMENTS.md#the-1010-scoreboard), not shipped features.

## 8. Posting history

Each company page shows how long its jobs have been up and how often they have been reposted. It needs no user reports, so it works on day one.

**Data source:** official public job-board feeds and company career pages only. Greenhouse, Lever and Ashby publish public job feeds that need no login. **Do not scrape LinkedIn.** Its terms forbid it, and hiQ ended up under a permanent injunction in 2022.

**Method:** take a daily snapshot and store each job's ID, normalized title and location, first seen and last seen. A repost is the same normalized role and location under a new ID, or the same ID returning after it closed.

**Limits:**
- History starts when collection starts. "Reposted for 3 months" needs 3 months of snapshots.
- Timestamp fields on each feed still need checking against official docs.
- Check each provider's terms before collecting, and keep request rates low.

**Wording:** state what happened ("up for 3 months, reposted 3 times"). Never call a specific job fake, because reposting can be legitimate.

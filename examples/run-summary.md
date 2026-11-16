# Run summary: Examplia food producers

Work order: 132 companies `now` against capacity of 80 for the next month. Hiring signals unvalidated.
Start with the 58 tier 1 companies that have a new managing director or a new site, then the first 22 in tier 2: those events came before most of your deals.
Run: xx-food-producers-2026-10, Examplia, 2026-10-09 to 2026-11-06. Started at: Market map. Guides run: all four.

*Made-up example. See [README.md](README.md).*

## Work order
| Company | Tier | Signal | Date | Why now |
|---|---|---|---|---|
| Kestmoor Bakehouse | 1 | hiring (+ staff growth) | 2026-10-14 | you are hiring a production planner |
| Orvale Dairy | 1 | new leader | 2026-09-03 | you appointed a new managing director in september |
| Tamsel Foods | 2 | expansion (+ funding) | 2026-08-11 | you opened a new production site in august |
| … | | | | |

Capacity runs out inside tier 2 `now`: all 58 tier 1, then 22 of 74 tier 2 by strength and date. After `now`: tier 1 `soon` (41).
To do before outreach: find domains for 6 of the first 80 companies (listed in `04-signals/list-signals.csv`, `signal_notes`).

## The chain
| Guide | Rows in | Rows out | Headline | Gate | Loop-backs |
|---|---|---|---|---|---|
| Market map | 96,400 register rows | 1,468 in market | Coverage 91% | Pass | L2 once: first market (198) was smaller than tier 1 |
| List quality | 1,468 | 1,412 usable | Grade A, cleaned A | Pass | |
| ICP + tiering | 1,412 | 246 / 464 / 486 in tiers 1–3, 180 excluded, 36 customers | Path A, back-test 4.2× | Pass | |
| Signals | 1,412 | 132 `now` in tiers 1–2 | Path A, 26 customers tested | Note | |

## What each guide found
- **Market map:** 1,468 food producers in four segments, 91% of the official count. Main gap: producers registered under a wholesale code.
- **List quality:** 56 companies with no accounts filed for two years set aside as dormant. Everything else confirmed.
- **ICP + tiering:** the best fit is a bakery or dairy with 20–99 staff, trading for 8 years or more. Region doesn't matter.
- **Signals:** a new managing director (4.3×) and a new production site (4.6×) came before most deals. Staff growth helps; funding doesn't.

## Labels carried
- **Hiring: unvalidated** (Signals). Old job posts are gone, so customers couldn't be tested. Removed when the next run can compare hiring against new customers' start dates.

## Loop-backs and decisions
- **Gate 1, L2:** the first market (bakeries and dairies, 20+ staff) held 198 companies, below a tier 1 of 240. The user widened it to all food manufacturing and kept "fewer than 5 staff" as a hard limit for tiering, not a map filter.
- **ICP step 4:** the user dropped the central region from their ICP after the evidence showed no difference.
- **Gate 4:** the user accepted three notes: hiring unvalidated, 6 missing domains, one flagged lost deal to review.

## Gaps
- 37 careers pages in tiers 1–2 blocked automated reading (21 in tier 1), so those rows weren't checked for hiring.
- Tier 3 and excluded rows got the register and accounts signals only.
- Producers under a wholesale code are outside the map.

## Next run
- **Signals:** rerun by 2026-12-05 (the first `now` signals start moving to `soon`); start at Signals with `03-icp-tiering/list-tiered.csv`.
- **ICP review:** after the quarter, 2027-01-22, on meetings and deals per tier; start at ICP + tiering.
- **Market map:** refresh by 2027-04, or before the next country.

User decision (2026-11-06): the team starts on the first 80 `now` companies on 2026-11-09.

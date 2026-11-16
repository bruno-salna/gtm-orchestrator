# Run Log: xx-food-producers-2026-10

*Made-up example. See [README.md](README.md).*

## Events
```
2026-10-09 · step 1 · user brought customers.csv (39 rows) and no company list · start at Market map; all four guides will run · user agreed
2026-10-09 · step 1 · guides read: local copies of gtm-market-map, gtm-list-quality, gtm-icp-tiering, gtm-signals, each with its last commit date noted
2026-10-09 · step 2 · brief written; beliefs taken before any data · signed off by user
2026-10-09 · Market map · started; step 1 filled from the brief: bakery and dairy codes, limited companies, active, 20+ staff
2026-10-10 · Market map · finished, attempt 1: 198 companies in market, coverage 92%
2026-10-10 · gate 1 · Stop: 198 companies, below tier 1 size of 240 · L2 offered
2026-10-10 · L2 · user chose to widen the market: all food manufacturing codes in four segments, and no size floor in the map ("fewer than 5 staff" stays as a hard limit for tiering) · attempt 1 moved to 01-market-map/attempt-1/
2026-10-12 · Market map · finished, attempt 2: 1,468 companies in market, coverage 91%
2026-10-12 · gate 1 · Pass (see below) · user signed off
2026-10-13 · List quality · started on market-map.csv, path A, market sizing preset
2026-10-14 · List quality · finished: grade A as received, cleaned file A, 1,412 usable rows (56 dormant suspects set aside)
2026-10-14 · gate 2 · Pass (see below) · user signed off
2026-10-15 · ICP + tiering · started; 36 of 39 customers matched (2 outside the market, 1 not found)
2026-10-20 · ICP + tiering · step 4: user dropped the central region from the matrix after the lift table showed no difference
2026-10-22 · ICP + tiering · finished: tier 1 246, back-test 5 of 6 held-out customers in the top 20% (4.2×)
2026-10-22 · gate 3 · Pass (see below) · user signed off
2026-10-27 · Signals · started; 26 customers from the last three years with start dates
2026-11-05 · Signals · finished: `now` 132 (58 tier 1, 74 tier 2), 37 careers pages blocked in tiers 1–2
2026-11-05 · gate 4 · Note (see below) · user signed off
2026-11-06 · step 7 · run summary written · user decision: start on the first 80 `now` companies on 2026-11-09
```

## Gate 1: Market map → List quality, 2026-10-10 (attempt 1)
| Check | Measured | Rule | Result |
|---|---|---|---|
| Map type | Full map | Full map | Pass |
| Coverage, overall | 92% | 80–120% | Pass |
| Coverage, by segment | Bakery 93%, dairy 90% | 60%+ each | Pass |
| Market size vs tier 1 capacity | 198 serviceable companies; tier 1 size 240 | 3× = 720 | **Stop** |
| Headcount | Known for all (the 20+ filter needs it) | Most rows | Pass |

Gate result: Stop
Loop-back: L2. Options shown: widen the market, or accept a tier 1 of under 198. User chose to widen.
User decision: loop back, 2026-10-10

## Gate 1: Market map → List quality, 2026-10-12 (attempt 2)
| Check | Measured | Rule | Result |
|---|---|---|---|
| Map type | Full map | Full map | Pass |
| Coverage, overall | 91% | 80–120% | Pass |
| Coverage, by segment | Bakery 93%, dairy 95%, meat processing 89%, other food 84% | 60%+ each | Pass |
| Market size vs tier 1 capacity | 1,468 serviceable companies; tier 1 size 240 | 3× = 720 | Pass (6.1×) |
| Headcount | Known for 1,302 of 1,468 (89%) | Most rows | Pass |

Gate result: Pass
Loop-back: none
User decision: carry on, 2026-10-12

## Gate 2: List quality → ICP + tiering, 2026-10-14
| Check | Measured | Rule | Result |
|---|---|---|---|
| Cleaned-file grade | A | A or B | Pass |
| Identified | 1,468 of 1,468 confirmed (path A) | 85%+ | Pass |
| Unverified rows | None | None | Pass |
| Usable rows vs tier 1 capacity | 1,412 serviceable; tier 1 size 240 | 3× = 720 | Pass (5.9×) |
| Register IDs on usable rows | All | Almost every row | Pass |

Gate result: Pass
Loop-back: none
User decision: carry on, 2026-10-14

## Gate 3: ICP + tiering → Signals, 2026-10-22
| Check | Measured | Rule | Result |
|---|---|---|---|
| Tier 1 vs capacity | 246; tier 1 size 240 | Within a fifth (192–288) | Pass |
| Customers outside the market | 2 of 39 | Under a fifth | Pass |
| Back-test | 5 of 6 held-out best customers in the top 20% (4.2×) | 2× chance or better | Pass |
| Evidence label | Path A | Path A | Pass |
| Worst customers | Median score 47, best customers 91 | Clearly lower | Pass |
| Belief vs evidence | Central region not supported; user dropped it | Nothing kept against the evidence | Pass |

Gate result: Pass
Loop-back: none
User decision: carry on, 2026-10-22

## Gate 4: Signals → run summary, 2026-11-05
| Check | Measured | Rule | Result |
|---|---|---|---|
| `now` vs capacity | 132 prospects in tiers 1–2; capacity 80 | At least half (40) | Pass |
| Tier 1 rows not checked | 21 of 246 (9%) not checked for hiring: careers pages blocked | Under 20% | Pass |
| Evidence for the top signals | New leader and expansion validated; hiring unvalidated (old job posts are gone) | Validated | **Note** |
| Ready to work | 6 of the first 80 `now` rows have no domain | Every `now` row | **Note** |
| Strong signals on low tiers | 1 flagged (a tier 3 lost deal with a new managing director) | None | **Note** |

Gate result: Note
Loop-back: none
User decision: carry on; the 6 domains to be found before outreach; the flagged lost deal goes to the user for a look, 2026-11-05

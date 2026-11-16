# Step 5: ICP + Tiering, Then Gate 3

## Goal
Run the [ICP + tiering](https://github.com/bruno-salna/gtm-icp-tiering) guide on the checked list, then check that tier 1 matches what the team can work and that the customers support the ICP.

Skip this step if the run starts at Signals.

## Why it matters
Signals sets the order of work inside each tier. If tier 1 is the wrong size or rests on an ICP the customers don't support, Signals will put the wrong companies first, with a convincing "why now" line on each. Fit has to be right before timing means anything.

## Hand-in
| From | What | Used in ICP + tiering |
|---|---|---|
| Step 4, or the user | `list-clean.csv` (or `market-map.csv`) | step 1: the list to tier |
| Step 3, or the user | `market-map-full.csv` | step 2: matching customers who aren't on the cleaned list |
| Brief, section 2 | The user's ICP belief, written before any data | step 1, then compared in the summary |
| Brief, section 3 | Customers, groups, "best" | steps 1 and 2 |
| Brief, sections 1 and 4 | Hard limits; tier 1 size | steps 1, 4 and 7 |

If the cleaned list came from a map built in this run, tell the guide in its step 1: it is a market map that has been checked, so its comparisons in step 3 describe the market, not a sample.

## Run the guide
Work in `03-icp-tiering/`. Follow the guide's `AGENT.md` and all seven steps, with its checkpoints after steps 1, 4 and 7. Fill its step 1 worksheet from the brief; the ICP belief is already written, so don't ask for it again.

**List every recorded field before profiling customers.** Before the guide's step 2, list every company-level field the source publishes (the country profile from the Market map names them), not only the ones the earlier guides used. Test each one that could separate customers, and always test the fields the user's beliefs point to: "they win export contracts" points to sales by country, "they're growing" to headcount over time. A field the run later uses as a signal should have been tested as fit first.

**A belief the evidence doesn't support can be tested, not just overruled.** When the user holds to a belief the customers don't back (a segment, a size), offer a test as one option: keep the matrix on the evidence and reserve a few tier 1 places, about a fifth, for the best-scoring companies the belief points to. Label the rows `user_decision`, name the review date, and compare their meetings and deals with the rest of tier 1 at the review. It costs a few places and gives better evidence than the argument.

**Check the held-out customers the matrix misses.** Before the sign-off, look at each held-out best customer below the top 20% and name the dimension that put it there. If a dimension found on few customers is what drops a held-out best customer, say so and offer to weaken or drop it. A pattern from a dozen customers that pushes a real best customer out of tier 1 may be noise.

## Gate 3: ICP + tiering → Signals
Show the user the ICP summary (the guide's step 7 checkpoint) and this gate together. Put the gate table itself in the chat, with its counts and result, before you ask for the sign-off. Writing it in the run log isn't showing it.

| Check | Pass | Note | Stop |
|---|---|---|---|
| **Tier 1 vs capacity** | Within about a fifth of tier 1 size | Between half and four-fifths of tier 1 size: the team has spare capacity | Below half of tier 1 size → **L2** |
| **Room to choose** (tier 1 as a share of serviceable tiers 1 and 2) | Half or less | Over half: tiering had little room to choose, and tier 1 is close to "everyone who fits". Say so in the run summary | |
| **Customers outside the market** (found in the full map, `in_market = false`) | None, or one or two | Under a fifth of the customers | A fifth or more → **L1** |
| **Back-test** (path A) | Held-out best customers in the top 20% at 2× chance or better | Between chance and 2× | Around chance or worse → **L5** |
| **Evidence label** | Path A | Path B: "thin evidence". Path C: "(unvalidated)" and a review point. Both travel to every later file. | |
| **Worst customers** (where given) | Score clearly lower than best customers | Score about the same: the ICP finds buyers, not good customers | |
| **Belief vs evidence** | No part of the belief kept against the evidence | A part kept against the evidence: the user's decision, logged | |

**The back-test bands are the ICP + tiering guide's own.** That guide may already have gone back to its step 3 or 4 on its own reading. Count that as the guide's work, not a loop-back. L5 applies when the result at hand-off is still around chance.

## Hand-off
| File | Goes to |
|---|---|
| `list-tiered.csv` | Signals: the list to check, with tiers |
| `list-tiered-full.csv` | The run record |
| `icp-summary.md` | The run summary: tiers, evidence, labels, review date |
| Lost deals that scored high | Signals: worth a look in the work order; something other than fit lost them |

Set `run_step` = `icp_tiering` on every row in tiers 1, 2 and 3.

## Pitfalls
- **Profiling only the fields already on the list.** The earlier guides carry what the map and checks needed: code, size, revenue, region. The source often holds more (sales by country, filing history, group links). A pattern in a field nobody looked at shows up later as customers stranded in tier 3 and a weak back-test.
- **Fixing a small tier 1 by lowering the bar.** Moving the tier 1 line down fills capacity with weaker fits. L2 asks the user to choose between a wider market, a looser ICP and accepting a small tier 1; don't pick one for them.
- **Treating a strong back-test as proof.** With six held-out customers, one customer moves the result a lot. Carry the counts into the run summary, not just the ratio.

## Done when
ICP + tiering's checklist passes, gate 3 is in the run log with its counts, and the user has signed off.

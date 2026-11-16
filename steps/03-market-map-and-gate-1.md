# Step 3: Market Map, Then Gate 1

## Goal
Run the [Market map](https://github.com/bruno-salna/gtm-market-map) guide from the brief, then check that the map covers the market and that the market is big enough for the team before anything is built on it.

Skip this step if the run starts later in the chain.

## Why it matters
Everything after this step works inside the map. If the map misses a large part of the market, every later step inherits the gap without knowing it. And if the whole market is smaller than what the team can work in a quarter, tiering can't pick a tier 1, it can only list everyone. Both are cheapest to find now.

## Hand-in
| From | What | Used in the Market map |
|---|---|---|
| Brief, section 1 | Offer, buyers, country, market, segments, hard limits | step 1: the market definition |
| Brief, section 3 | Customers' register IDs | step 1: check real customers against the definition |
| Brief, section 6 | Map use (list building by default) | step 1: how strict the filters are |

## Run the guide
Work in `01-market-map/`. Follow the guide's `AGENT.md` and all seven steps, with its checkpoints after steps 1, 2 and 6. Fill its step 1 worksheet from the brief and ask only what's missing.

**Hard limits are not market filters.** A limit from section 1 such as "nothing under 5 staff" is applied in ICP + tiering as a disqualifier, not here, unless it's also part of how the market is defined. Keeping it out of the map means the ICP can still compare customers against the whole market.

## Gate 1: Market map → List quality
Show the user the map's coverage checkpoint (its step 6) and this gate together. Put the gate table itself in the chat, with its counts and result, before you ask for the sign-off. Writing it in the run log isn't showing it.

| Check | Pass | Note | Stop |
|---|---|---|---|
| **Map type** | A full map: company rows from the register | | A sizing map only (counts, no company list). Ask the user: the chain needs company rows. |
| **Coverage, overall** | 80–120% of the official count | 60–80%, above 120%, or no official count to compare | Below 60% → **L1** |
| **Coverage, by segment** | Every segment at 60% or more | A segment below 60%: name it as a gap | |
| **Market size vs tier 1 capacity** | Serviceable companies at least 3× tier 1 size | 1–3× tier 1 size: tiering will have little room to choose | Fewer than tier 1 size → **L2** |
| **Headcount** | Known for most in-market rows | Known for under half: tiering will lean on other dimensions | |

**Serviceable = in the market and inside the brief's hard limits.** The map keeps every company, but count only the ones the team could sell to: a market of 3,000 firms where 300 clear the size limit is a market of 300. Where a hard limit can't be applied to a row (headcount unknown), count the row and say how many there are.

**Why 3×.** Tiering puts the top companies, up to capacity, in tier 1, and by default about twice that in tier 2. A market three times capacity fills both tiers. Below that, the team will reach the weaker fits within the period.

## Hand-off
| File | Goes to |
|---|---|
| `market-map.csv` | List quality: the list to check (path A) |
| `market-map-full.csv` | List quality: identity and status checks; ICP + tiering: the base the customers are matched to |
| The country profile | List quality step 2 (naming rules), ICP + tiering (every company-level field the source publishes) and Signals step 3 (where records are kept): start from it instead of from nothing |
| `market-summary.md` | The run summary: size, coverage, known gaps |

Set `run_id` on every row of both CSV files and `run_step` = `market_map` on the in-market rows.

## Pitfalls
- **Widening the market to pass the size check.** Adding neighbouring codes to reach 3× capacity changes who the market is. L2 asks the user which way to go; don't decide it quietly.
- **Reading a high coverage as complete.** Coverage above 100% usually means dormant companies the statistics don't count. List quality will find them; note it here.

## Done when
The Market map's checklist passes, gate 1 is in the run log with its counts, and the user has signed off.

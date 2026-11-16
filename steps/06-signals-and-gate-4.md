# Step 6: Signals, Then Gate 4

## Goal
Run the [Signals](https://github.com/bruno-salna/gtm-signals) guide on the tiered list, then check that the `now` list is sized to capacity, was actually checked, and is ready for the team to work.

## Why it matters
The `now` list is what the team sees. If it's empty, the team falls back on tier 1 by fit, which is fine, but should be a decision, not a surprise. If half of tier 1 couldn't be checked, an empty `now` means "unknown", not "not ready". And if `now` companies have no website, the team can't start on them this week.

## Hand-in
| From | What | Used in Signals |
|---|---|---|
| Step 5, or the user | `list-tiered.csv` | step 1: the list, with tiers |
| Brief, section 2 | Why customers bought, written before any data | step 1, then compared in step 5 |
| Brief, section 3 | Customers with start dates | steps 1, 4 and 5 |
| Brief, sections 4 and 6 | `now` capacity; look-back window; web-check tiers | steps 1 and 6 |
| Steps 3 and 4 | The country profile and country notes | step 3: start from the register and sources already found |
| Step 5 | Lost deals that scored high | the summary's review section |

## Run the guide
Work in `04-signals/`. Follow the guide's `AGENT.md` and all seven steps, with its checkpoints after steps 2, 5 and 7. Fill its step 1 worksheet from the brief; the view of why customers bought is already written, so don't ask for it again.

**Growth without headcount history.** Some registers publish only today's headcount. If growth has to be read from revenue in the filed accounts instead, record it as `custom_revenue_growth`, not `staff_growth`, and say in the signals summary why the staff signal couldn't be tested. Test it on the accounts each customer could have seen when they started, not on the latest year for everyone.

## Gate 4: Signals → run summary
Show the user the top of the work order (the guide's step 7 checkpoint) and this gate together. Put the gate table itself in the chat, with its counts and result, before you ask for the sign-off. Writing it in the run log isn't showing it.

| Check | Pass | Note | Stop |
|---|---|---|---|
| **`now` vs capacity** (tiers 1–2, prospects only) | At least half of `now` capacity. Above capacity is fine: the guide has ordered it. | A quarter to half of capacity: the rest of the team's time goes to tier 1 by fit | Below a quarter, or empty → **L6** |
| **Tier 1 rows not checked** (any kept signal) | Under 20% | 20–50%: name the blocked sources | Over half → ask the user. Blocked sources are their call, so there's no loop-back. |
| **Evidence for the top signals** | Path A, the signals behind most `now` rows validated | Thin or unvalidated: the label travels to the run summary | |
| **Ready to work** (`now` rows) | Every `now` row has a display name and a domain | Some don't: list them in the run summary as to do before outreach | |
| **Strong signals on low tiers** | None flagged | Some flagged: listed for the user, tiers unchanged | |

## Hand-off
| File | Goes to |
|---|---|
| `list-signals.csv` | The run summary's work order; the team |
| `signals.csv` | The run record: every signal with its evidence |
| `signals-summary.md` | The run summary: work order, signals used, gaps |

Set `run_step` = `signals` on every row that was checked.

## Pitfalls
- **Widening the look-back window until `now` fills up.** A twelve-month-old new leader isn't news. L6 offers it once, with the user's agreement; after that, tier 1 by fit is the honest answer.
- **Reading "no signal" as "not ready" on unchecked rows.** If job posts were blocked for half of tier 1, half of tier 1 is unknown. Say so in the first lines of the run summary.

## Done when
Signals' checklist passes, gate 4 is in the run log with its counts, and the user has signed off.

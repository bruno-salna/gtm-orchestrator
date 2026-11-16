# Step 4: List Quality, Then Gate 2

## Goal
Run the [List quality](https://github.com/bruno-salna/gtm-list-quality) guide on the map from step 3 or on the list the user brought, then check that the list is fit to build on and that its companies match the official records.

Skip this step if the run starts at ICP + tiering or later.

## Why it matters
Tiering and signals both work row by row. Every dead company, duplicate or wrong ID that gets past this step either takes a tier 1 place or misses its records in Signals. This is the last point where a bad list costs only a few hours.

## Two ways in
**A map built in this run (path A).** The list is the map, so identities are already confirmed. List quality is short: display names, duplicates and a status check. Use the **market sizing** preset by default. ICP + tiering compares customers against the whole market, so the cleaned list should still be the whole market: dead and duplicate rows leave, rows without a website stay. Website gaps are checked later, on the companies the team will actually work (gate 4).

**A list the user brought (path B or C).** Use the preset the user chose in the brief. If there's a market map for the country, from step 3 or from the user, the list is matched against it (path B). If not, the guide suggests running the Market map first; if the user declines, the list is checked on form only and labelled "(unverified)" (path C).

**Two lists: the user's list and a map built in this run.** When step 1 sent a run with a user's list back to the Market map, List quality runs on both:
- **The map** goes forward. Check it on the market sizing preset, as on path A. Gate 2 is decided on it, and it's the list ICP + tiering tiers.
- **The user's list** is checked on the preset the user chose (path B, matched against the map). It gets its own scorecard: what the list is actually worth, its coverage of the serviceable market, and the companies it's missing.
- **Carry the list's history onto the map.** CRM fields such as owner, lead status and last activity go onto the matched map rows (as `src_` columns), so nobody calls a company blind.
- **Offer an update file** for the user's system: IDs to fix, duplicates to merge, closed companies, and serviceable companies to add. The user decides whether to import it; nothing in the run depends on it.

## Hand-in
| From | What | Used in List quality |
|---|---|---|
| Step 3 or `input/` | The list | step 1 |
| Step 3 or the user | `market-map-full.csv` and the country profile | steps 2 and 4 |
| Brief, section 5 | Source, date, purpose, known problems, campaign plan | step 1 |
| Brief, sections 1 and 4 | Scope (country, market); capacity for the size check | steps 1 and 6 |

## Run the guide
Work in `02-list-quality/`. Follow the guide's `AGENT.md` and all seven steps, with its checkpoints after steps 1, 5 and 7. Fill its step 1 worksheet from the brief and ask only what's missing.

## Gate 2: List quality → ICP + tiering
Show the user the scorecard (the guide's step 7 checkpoint) and this gate together. Put the gate table itself in the chat, with its counts and result, before you ask for the sign-off. Writing it in the run log isn't showing it.

| Check | Pass | Note | Stop |
|---|---|---|---|
| **Cleaned-file grade** | A or B | C: the user decides which fixes to do first, and the decision is logged | D → **L4** |
| **Identified** (`confirmed` or `matched`, checked rows only) | 85% or more | 70–85% | Below 70% → **L3** |
| **Unverified rows** | None | Any path C rows: the label "(unverified)" travels to every later file | |
| **Usable rows vs tier 1 capacity** | Usable serviceable rows (inside the brief's hard limits, as at gate 1) at least 3× tier 1 size | 1–3× tier 1 size | Fewer than tier 1 size → **L2** |
| **Register IDs on usable rows** | On almost every row | Missing on some: Signals can only web-check those rows | Missing on most → ask the user: tiering and signals will be weak |

The Identified bands are the List quality guide's own B and C lines for that dimension.

## Hand-off
| File | Goes to |
|---|---|
| `list-clean.csv` | ICP + tiering: the list to tier |
| `list-full.csv` | The run record: every row and why it was set aside |
| `list-scorecard.md` | The run summary: grade, usable rows, labels |
| The country notes | Signals step 3, with the country profile |

Set `run_step` = `list_quality` on the usable rows. Rows set aside keep `market_map` (or stay empty if the run started here).

## Pitfalls
- **Using the outreach preset on a fresh map.** It sets aside every row without a website, so the ICP's comparison base stops being the market. Use market sizing here and check websites on the `now` rows at gate 4.
- **Passing a C because the cleaned file looks fine.** A cleaned C is a list with real gaps. It can pass with a note, but the user decides, and the decision is logged.

## Done when
List quality's checklist passes, gate 2 is in the run log with its counts, and the user has signed off.

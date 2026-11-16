# Step 1: Take In What the User Brings

## Goal
See what the user already has, work out which guides have already run on it, agree where the chain starts, and set up the run.

## Why it matters
Starting too early wastes work: there's no point rebuilding a market map the user pulled last month. Starting too late is worse: a list that looks tiered but was never checked will put dead and duplicate companies in tier 1. The columns on the file show which guides already ran, so the starting point can be read, not guessed.

## How
1. **Save what the user brings** in `input/` exactly as received. If they bring a file from one of the guides, ask for the summary that came with it too (`market-summary.md`, `list-scorecard.md`, `icp-summary.md` or `signals-summary.md`). The summary holds the decisions and labels the columns don't.
2. **Read the columns, then the values.** Use the table below to find the furthest guide that has run:

| What the file has | What it is | Start at |
|---|---|---|
| No file, or only a description of the market | Nothing yet | **Market map** |
| No columns from the series (only the company's own columns) | A bought list, a CRM export or any other list | **List quality** |
| `in_market`, `excluded_by`, `segment`, `source_date` filled | A market map | **List quality**, on its path A (see step 4) |
| `quality_usable` and `quality_id_check` filled | A cleaned list | **ICP + tiering** |
| `tier`, `icp_score`, `icp_matrix_version` filled | A tiered list | **Signals** |
| `signal_priority` and `signal_checked_date` filled | A list with signals | **Signals** again if the check is more than about a month old; otherwise step 7 only |

   - **Check the values, not just the names.** A CRM column called "Tier" is not the series' `tier`. A guide's column is real only if it uses the schema's values (`1`, `2`, `3`, `excluded`) and the guide's summary is there to back it.
   - **Without the summary, step back one guide.** A tiered list with no `icp-summary.md` has no record of its matrix or evidence. Treat it as a cleaned list and offer to tier it again.
3. **Look for reasons to start earlier.** Suggest an earlier start, and say why, when:
   - The list has no register IDs, or most of them are blank. ICP + tiering matches customers badly without them, and Signals can't match records at all. Suggest List quality, and the Market map if there's no map for the country.
   - The user brings a list but there's no market map for the country. List quality checks identity and status against a map; without one, every row stays "(unverified)" through to the work order. If the country's register can be downloaded freely, suggest the Market map first: it costs a pull, and it gives ICP + tiering the whole market to compare customers against. The user's list then joins at step 4 (see "Two lists" there). If the user declines, start at List quality on path C and log it.
   - The market map is old. If `source_date` is more than about six months back, statuses and headcounts have moved. Suggest a fresh pull.
   - The list spans several countries. One run covers one country. Ask which country this run is for; the others can be later runs with the same brief.
4. **Agree the starting point with the user.** They may have reasons to start later (a list they trust) or earlier. Write their decision in the run log.
5. **Set up the run.** Give it a `run_id` (country, market, month, e.g. `xx-food-producers-2026-11`), create the run folder (see [../AGENT.md](../AGENT.md)), and start `run-log.md` with the starting point, the guides this run will use, and the copy of each guide you read.

## Pitfalls
- **Trusting a file name.** `list-tiered-final-v3.csv` tells you nothing. The columns and the summary do.
- **Skipping List quality because the list "came from our CRM".** CRM exports are where duplicates and dead companies collect. Unless the file has `quality_` columns, it hasn't been checked.
- **Starting at Signals with an untiered list.** The Signals guide can run on any list, but with no tiers it has no fit order to fall back on. Suggest ICP + tiering first; if the user declines, note it.

## Done when
What the user brought is saved, the starting guide is agreed and written in the run log, the run folder and `run_id` exist, and the user has signed off.

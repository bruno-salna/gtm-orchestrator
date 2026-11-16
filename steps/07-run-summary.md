# Step 7: Run Summary

## Goal
Put the whole chain on one page: the work order first, then what each guide found, which labels the result carries, every loop-back and decision, and when to run it again. Get the user's decision on the work order.

## Why it matters
Each guide writes its own summary, and each is worth reading. But the person who decides what the team does on Monday needs one page: who to work, why, how far to trust it, and what's still open. The run summary is that page. The four guide summaries sit behind it for anyone who wants the detail.

## How
1. **Write `run-summary.md`** in the structure below, from the guides' own summaries and the run log. Don't recompute anything: every number comes from a guide's file.
2. **Put every label in the first line.** If any guide ran on path C or B, or List quality left rows unverified, the first line says so.
3. **Set the next dates.** Signals expire, and the ICP has a review date. Write both, and say which guide to rerun at each one.
4. **Go through [../checklist.md](../checklist.md).**
5. **Get the user's decision** on the work order. Record it in the summary and the run log.

### `run-summary.md`
```
# Run summary: <run name>

Work order: <n> companies `now` against capacity of <n> for <period>. <labels: (unverified) / thin evidence / (unvalidated)>
<one-sentence verdict: what the team should do first, and why, in plain words>
Run: <run_id>, <country>, <start date>–<end date>. Started at: <guide>. Guides run: <list>.

## Work order
<the top rows from Signals' work order: company — tier — signal — date — why now>
<where capacity runs out; what comes after `now`>
<to do before outreach: `now` rows with no domain or name review>

## The chain
<table: guide — rows in — rows out — headline result — gate result — loop-backs>

## What each guide found
- Market map: <market size, coverage, main gap>
- List quality: <grade as received and cleaned, usable rows>
- ICP + tiering: <who fits in one line, tier 1 size, evidence path, back-test>
- Signals: <the signals that mattered, evidence path, rows not checked>

## Labels carried
<each label, the guide it came from, and what would remove it>

## Loop-backs and decisions
<each loop-back: gate, rule, where it went, what changed>
<each user decision against a gate rule or a guide's evidence>

## Gaps
<blocked sources, unchecked rows, segments with low coverage, anything the user should know before trusting the order>

## Next run
- Signals: rerun by <date> (the `now` signals start expiring); start at Signals with `list-tiered.csv`
- ICP review: <date or outcome count from the ICP summary>; start at ICP + tiering
- Market map: refresh after <about six months>, or before entering the next country
```

See [../examples/](../examples/) for a made-up filled-in version.

## Checkpoint
Show the user the run summary. They decide whether the team starts on the work order, or which step to revisit. Record the decision.

## Pitfalls
- **A summary that reads better than the parts.** If the ICP is unvalidated and half of tier 1 wasn't checked, the work order is a sensible start, not a forecast. Say it in the first lines.
- **Dropping a guide's caveats.** Each guide's caveats still apply. Carry the ones that change the decision; link to the guide's summary for the rest.
- **No next date.** Signals go stale in weeks. A run summary without a rerun date becomes an old list the team keeps working.

## Done when
`run-summary.md` is written, every label and loop-back is in it, the checklist passes or the summary says why not, and the user's decision is recorded.

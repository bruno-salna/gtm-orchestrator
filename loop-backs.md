# Loop-backs

A loop-back sends the run back to an earlier step when a gate shows that the result isn't good enough to build on. There are six, and each one is named by the gate check that triggers it. Use only these. If a problem doesn't fit one, stop and ask the user.

## Rules for every loop-back
1. **Tell the user before you go.** Say which rule it is, where it goes, and what has to run again: the step it goes to, every later step of that guide, and every guide after it. Going back from gate 3 to the Market map means running List quality and ICP + tiering again too.
2. **The user decides.** Each loop-back offers its options. The user picks one, or accepts the result as it is and carries on with a note. Accepting is a proper choice; log it.
3. **One loop-back per gate.** If the same gate stops again after a loop-back, don't take another. Stop and ask the user what to do.
4. **Keep the first attempt.** Don't overwrite the files of the run that failed the gate. Move them to a subfolder (for example `01-market-map/attempt-1/`) so the run log can point to both.
5. **Log it.** Gate, rule, the option chosen, what changed, and the gate's new result.

## The six rules

### L1. The map misses the market
**Triggered by:** gate 1, overall coverage below 60%; gate 3, a fifth or more of the customers found outside the market.
**Goes to:** Market map step 1 (the definition) or step 4 (the filters).
**Options:**
- Customers sit outside the market: look at their industry codes and legal forms. If they share a code or form the definition left out, add it as a new segment, so it can be judged on its own.
- Coverage is low: find which filter removed too much (the funnel in the market summary shows it), or which kind of company sits in another register.
- Keep the map as it is, and carry the gap as a note.

### L2. The market is too small for the team
**Triggered by:** gate 1 or 2, fewer companies than tier 1 size; gate 3, tier 1 below half of tier 1 size.
**Goes to:** Market map step 1, or ICP + tiering step 4.
**Options:**
- Widen the market: more industry codes, more regions, a lower size floor (Market map step 1).
- Loosen the ICP: a disqualifier that removes too many, or a band that's too narrow (ICP + tiering step 4). Only at gate 3.
- Accept a smaller tier 1. The team has spare capacity, which can go to tier 2 or to a second country. The ICP + tiering guide treats this as a proper result.

### L3. Many IDs don't match the records
**Triggered by:** gate 2, Identified below 70%.
**Goes to:** depends on why. Look at the unmatched rows first.
**Options:**
- They belong to another country: they're out of scope for this run. Mark them, or start a run for that country.
- The map's full set was partial (a filtered download, a missing legal form): go back to Market map step 3 and pull the full register.
- The IDs in the source are damaged (lost leading zeros, wrong format): go back to List quality step 3.

### L4. The list isn't fit to use
**Triggered by:** gate 2, cleaned-file grade D.
**Goes to:** the source of the list.
**Options:**
- The user gets a better export from the same source, and the run goes back to List quality step 1.
- Build the list from the register instead: go to Market map step 1. If a map for this country already exists, this means using it instead of the list.
- Stop the run.

### L5. The customers don't back the ICP
**Triggered by:** gate 3, back-test around chance or worse.
**Goes to:** ICP + tiering step 3.
**Options:**
- Look for a channel effect: customers who all came through one partner or event describe the channel, not the market.
- Check "best": if it was defined as "biggest", try the measure the user actually cares about (margin, how long they stay).
- Carry on with the ICP labelled as weak, and set an early review date.

### L6. `now` is too small to work
**Triggered by:** gate 4, `now` below a quarter of `now` capacity, or empty.
**Goes to:** Signals step 1 or step 2.
**Options:**
- Widen the look-back window, once, for the signals where the user's buying cycle supports it (Signals step 1).
- Extend web checks to tier 2 or tier 3 if they ran only on tier 1 (Signals step 1).
- Loosen a signal's definition, if the evidence in step 5 supports it (Signals step 2).
- Accept a small `now`. The rest of the team's time goes to tier 1 by fit. This is often the honest answer.

## What is not a loop-back
- **A guide going back inside itself.** Each guide has its own rules for revisiting a step (the ICP guide goes back to step 4 after a weak back-test, Signals goes back to step 2 when `now` is too loose). That's the guide's work, and it doesn't count against the gate.
- **A blocked source.** Finding another way in is the user's call. Record it and ask.
- **The user changing their mind.** A new hard limit or a new customer file is a change to the brief. Update the brief, log it, and rerun from the guide it affects.

# Definition of Done

Every item passes, or the run summary explains why it doesn't.

## Start
- [ ] What the user brought is saved in `input/`, unedited, with the guide summaries that came with it
- [ ] The starting guide was read from the columns and values, and the user confirmed it
- [ ] The copy of each guide used (local folder and commit date, or web page and date read) is in the run log
- [ ] The run covers one country
- [ ] A user's list with no market map for the country: the Market map was offered first, or the list is labelled "(unverified)"

## Brief
- [ ] `run-brief.md` holds every section the guides in this run need, and no more
- [ ] The ICP belief and the view of why customers bought were written in the user's words before any data was shown
- [ ] One customer file was used by both ICP + tiering and Signals
- [ ] Tier 1 size and `now` capacity both come from one capacity answer
- [ ] Every change to the brief during the run is logged with its reason

## Guides
- [ ] Every guide in the run followed all its own steps and checkpoints
- [ ] Every guide's own checklist passes, or its summary says why not
- [ ] Each guide's step 1 was filled from the brief, and the user signed it off

## Gates
- [ ] Every hand-off has a gate in the run log, with the counts each check was decided on
- [ ] Every gate table was shown in the chat before the user signed it off
- [ ] No guide started before the previous gate was signed off
- [ ] Every Stop led to a named loop-back or a question to the user
- [ ] No gate had more than one loop-back without the user's decision
- [ ] Every threshold the user changed is logged as their decision
- [ ] The files from each failed attempt are kept, not overwritten

## Rows
- [ ] Every row carries `run_id`, and `run_step` shows the last gate it passed
- [ ] No row was deleted anywhere in the chain
- [ ] No person names in the outputs, unless the user confirmed their legal basis

## Run summary
- [ ] The `now` count, capacity and every label are in the first line
- [ ] Every number comes from a guide's own file
- [ ] Gaps (blocked sources, unchecked rows, low-coverage segments, `now` rows with no domain) are stated
- [ ] Every loop-back and every decision against a rule is listed
- [ ] The rerun dates for Signals and the ICP review are set
- [ ] The user's decision on the work order is recorded

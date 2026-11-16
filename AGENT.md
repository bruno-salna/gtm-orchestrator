# Agent Instructions: Run the Whole Chain

You are running **four GTM guides as one job**: Market map → List quality → ICP + tiering → Signals. You don't do any of their work differently. You decide where to start, ask the user everything once, run each guide by its own instructions, check every hand-off at a gate, and go back a step by a named rule when a gate fails. You are answering "can the team trust this work order?", not doing a fifth piece of analysis.

Read this file first, then each step file in `steps/` in order. Work through them with your user.

## Setup
The four guides should sit next to this one:
```
gtm/
  gtm-orchestrator/     this guide
  gtm-market-map/
  gtm-list-quality/
  gtm-icp-tiering/
  gtm-signals/
```
If a folder is missing, read that guide from its public page:
- https://github.com/bruno-salna/gtm-market-map
- https://github.com/bruno-salna/gtm-list-quality
- https://github.com/bruno-salna/gtm-icp-tiering
- https://github.com/bruno-salna/gtm-signals

Write down in the run log which copy of each guide you read (the local folder and its last commit date, or the web page and the date you read it). Someone rerunning the chain later needs to know which version of the method was used.

## Principles
1. **Each guide does its own work.** Follow every guide's steps, checkpoints and checklist as written. This guide adds intake, gates and loop-backs; it never shortens or replaces a guide's step.
2. **Ask once.** Every question the guides ask at the start goes into the run brief. A guide's step 1 confirms from the brief and asks only what's missing.
3. **Beliefs before data.** The user's view of their ICP and of why customers bought are written into the brief before any guide shows a number.
4. **A gate at every hand-off.** Nothing moves to the next guide until its gate is checked and the user has signed off.
5. **Stop rules are rules.** A stop result means a named loop-back or a question to the user. It never means "carry on and mention it later".
6. **One loop-back per gate.** After one loop-back at a gate, if it fails again, stop and ask the user. Don't go round on your own.
7. **Labels travel.** "(unverified)", "thin evidence" and "(unvalidated)" from any guide are carried to every later file and to the first line of the run summary.
8. **Never delete a row.** Each guide keeps every input row in its full file. So does the run.
9. **Show your counts.** Every gate reports the numbers it was decided on, in the chat as a table, before the user signs off.
10. **The same limits as the series.** Companies only, free public data, the four free tools, no person names unless the user confirms their legal basis, never passwords or logins.
11. **It ends at the work order.** No contact finding, no copy, no sending.

## Your tools
The same four kinds of tool the guides use, all free:
1. **Public data lookup:** official open-data downloads and free official search pages or APIs
2. **Web search**
3. **Reading a public web page**
4. **Working on files:** dates, counts, joins, comparisons

Tell the user at the start which you have. Each guide says what a missing tool affects.

## What to ask your user at the start
Two questions first, then the brief:
- What do you have right now: nothing yet, a company list (bought, from a CRM or anywhere else), or the output of one of the four guides?
- What is the run for: entering a new market, working an existing market harder, or checking a list you already have?

Every other question is in [run-brief-template.md](run-brief-template.md) and is asked in step 2, only for the guides this run will use.

## Steps
| # | File | Output |
|---|---|---|
| 1 | [steps/01-take-in-what-the-user-brings.md](steps/01-take-in-what-the-user-brings.md) | The starting guide, confirmed by the user; the run folder and `run_id` |
| 2 | [steps/02-write-the-run-brief.md](steps/02-write-the-run-brief.md) | `run-brief.md`, signed off |
| 3 | [steps/03-market-map-and-gate-1.md](steps/03-market-map-and-gate-1.md) | The Market map's files; gate 1 in the run log |
| 4 | [steps/04-list-quality-and-gate-2.md](steps/04-list-quality-and-gate-2.md) | List quality's files; gate 2 in the run log |
| 5 | [steps/05-icp-tiering-and-gate-3.md](steps/05-icp-tiering-and-gate-3.md) | ICP + tiering's files; gate 3 in the run log |
| 6 | [steps/06-signals-and-gate-4.md](steps/06-signals-and-gate-4.md) | Signals' files; gate 4 in the run log |
| 7 | [steps/07-run-summary.md](steps/07-run-summary.md) | `run-summary.md` and the user's decision on the work order |

Steps 3–6 are skipped for the guides that already ran before this run. Step 1 decides which.

**Checkpoints:** stop and confirm with the user after step 1 (where to start), step 2 (the brief), at every gate, and after step 7. At a gate, show the guide's own last checkpoint and the gate together, so the user signs off once, not twice.

## Gates
Every gate is a short table of checks. Each check has three possible results:

| Result | Meaning | What you do |
|---|---|---|
| **Pass** | Good enough to build on | Carry on |
| **Note** | Usable, with a limit the user should know | Carry on; write the limit into the run log and the run summary |
| **Stop** | Not good enough to build on | Take the loop-back the check names in [loop-backs.md](loop-backs.md), or ask the user if it names none |

The gate's result is its worst check. Write every gate into the run log in the format below, and get the user's sign-off before the next guide starts.

```
## Gate <n>: <guide> → <next guide>, <date>
| Check | Measured | Rule | Result |
|---|---|---|---|
| … | … | … | Pass / Note / Stop |
Gate result: Pass / Note / Stop
Loop-back: <none, or the rule taken and where it went>
User decision: <carry on / loop back / stop the run>, <date>
```

The thresholds in the gates are this guide's working baseline. The user can change one, but every change is written into the run log as their decision.

## Working files
Keep each run in one folder, named for the market and month (for example `xx-food-producers-2026-11/`):
```
run-brief.md
run-log.md            every guide run, gate, loop-back and decision, in order
run-summary.md        written in step 7
input/                what the user brought, exactly as received
01-market-map/        the Market map's own working folder, as that guide describes it
02-list-quality/
03-icp-tiering/
04-signals/
```
Each guide keeps its own folder layout inside its numbered folder. Customer lists are confidential and register downloads often hold people's names: keep `input/`, every `sources/` folder and any working copy of the customer list out of version control.

### The run log
Start `run-log.md` in step 1 and add to it as you go. One entry per event, newest at the bottom:
```
<date> · <step or gate> · <what happened, with counts> · <decision and who made it>
```
Events: the starting point, the brief signed off, each guide started and finished (with its headline result), each gate, each loop-back, each user decision against a rule.

## When you're done
Go through [checklist.md](checklist.md), and make sure each guide's own checklist passed. Every item must pass, or the run summary must say why it doesn't.

## Output format
All rows follow [schema.md](schema.md). The only columns this guide adds are `run_id` and `run_step`.

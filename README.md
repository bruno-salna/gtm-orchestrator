# Orchestrator

**An agent-ready guide to running the whole GTM list chain in one go: from "we want to enter this market" to "work these companies this week", from free public data, in any EU country.**

The four guides in this series each do one job well: map the market, check the list, decide who fits, find who is ready now. Run one by one, they ask some of the same questions four times, and nothing stops a weak result from one step flowing into the next. A market too small for the team, a list half full of unmatched IDs, or an ICP the customers don't support all show up at the end, as a work order nobody trusts.

This guide makes an agent run the four guides as one job. It asks the questions once, checks every hand-off against pass and stop rules, and goes back a step, by a named rule, when a result isn't good enough to build on. It teaches no new GTM method. Every step's detail stays in its own guide.

## How to use it
This repo contains no code and no data. It's a set of instructions for an AI agent.

1. Clone this repo and the four guides into one folder:
   ```
   gtm/
     gtm-orchestrator/
     gtm-market-map/
     gtm-list-quality/
     gtm-icp-tiering/
     gtm-signals/
   ```
   If a guide is missing, the agent reads it from its public GitHub page.
2. Give the folder to your agent (Claude, ChatGPT, Cursor or any other) and point it to [AGENT.md](AGENT.md).
3. Tell the agent what you have: nothing yet, a bought or CRM list, a cleaned list or a tiered list. The agent picks where to start, asks you everything it needs once, and runs the guides in order with you.

You supply the market, your offer, your customers if you have them, and your team's capacity. The agent runs the chain and stops for your sign-off at every hand-off.

## The chain
| # | Guide | Answers | Hands on |
|---|---|---|---|
| 1 | [Market map](https://github.com/bruno-salna/gtm-market-map) | Who is in the market? | Every company in the market, from official records |
| 2 | [List quality](https://github.com/bruno-salna/gtm-list-quality) | Can we trust this list? | The usable rows, checked against the records |
| 3 | [ICP + tiering](https://github.com/bruno-salna/gtm-icp-tiering) | Who fits? | Every company in a tier, tier 1 sized to capacity |
| 4 | [Signals](https://github.com/bruno-salna/gtm-signals) | Who is ready now? | `now`, `soon` or `watch` inside each tier, with a reason |

**Start anywhere.** The agent looks at the columns on what you bring and starts at the first guide that hasn't run yet. With nothing, it starts at the market map. With a tiered list, it goes straight to signals.

## What this guide adds
- **One intake.** The first questions of all four guides go into one run brief, asked once, before any data is shown. Each guide then confirms from the brief instead of asking again.
- **A gate at every hand-off.** Four short checks, each with pass, note and stop rules: is the market big enough for the team, is the list fit to use, does tier 1 match capacity and do the customers back the ICP, is the `now` list worth working.
- **Named loop-backs.** A short fixed set of rules for going back a step instead of pushing a weak result forward. One loop-back per gate; after that, the agent stops and asks you.
- **A run record.** A log of every guide run, gate and decision, and a one-page summary across the whole chain.

## In, middle, out
- **In:** whatever you have (nothing, a company list, or the output of one of the guides); what you sell; your customers with their start dates, if you have them; how many accounts the team can work.
- **Middle:** the agent writes the run brief, runs each guide from the right starting point, checks every hand-off at a gate, and loops back by rule when a gate fails.
- **Out:** each guide's own files, `run-log.md` with every gate and decision, and `run-summary.md`: the work order from Signals and what the whole chain found, on one page.

## The seven steps
| # | Step | What happens |
|---|---|---|
| 1 | [Take in what the user brings](steps/01-take-in-what-the-user-brings.md) | Read the columns, pick the starting guide, set up the run |
| 2 | [Write the run brief](steps/02-write-the-run-brief.md) | Ask every guide's questions once, before any data is shown |
| 3 | [Market map, then gate 1](steps/03-market-map-and-gate-1.md) | Is the map complete, and is the market big enough for the team? |
| 4 | [List quality, then gate 2](steps/04-list-quality-and-gate-2.md) | Is the list fit to use, and do its IDs match the records? |
| 5 | [ICP + tiering, then gate 3](steps/05-icp-tiering-and-gate-3.md) | Does tier 1 match capacity, and do the customers back the ICP? |
| 6 | [Signals, then gate 4](steps/06-signals-and-gate-4.md) | Is the `now` list sized to capacity and worth working? |
| 7 | [Run summary](steps/07-run-summary.md) | One page across the chain, ending with the work order |

The loop-back rules are in [loop-backs.md](loop-backs.md).

## Why run the chain this way
- **Ask the beliefs first, once.** What you think your ICP is and why you think customers bought are worth most before you've seen any data. The brief captures both at the start, before any guide shows a number.
- **Catch a small market at the map, not at tiering.** If the whole market is smaller than what the team can work in a quarter, that's visible on day one. Finding it after scoring wastes three steps.
- **A gate is cheaper than a bad list.** Each guide already reports its counts. The gate turns them into a decision: carry on, carry on with a note, or go back.
- **Go back by rule, not by feel.** Without named loop-backs, an agent either pushes everything forward or keeps redoing steps. A fixed set of rules, one loop per gate, keeps the run moving and keeps you in charge.
- **Labels travel.** An unverified list, a thin ICP or untested signals stay labelled all the way to the work order, so nobody reads a guess as a fact.

## Part of a series
This is the fifth of five guides that chain together through a [shared row schema](schema.md):

[Market map](https://github.com/bruno-salna/gtm-market-map) → [List quality](https://github.com/bruno-salna/gtm-list-quality) → [ICP + tiering](https://github.com/bruno-salna/gtm-icp-tiering) → [Signals](https://github.com/bruno-salna/gtm-signals) → **Orchestrator**

Each of the four guides works on its own. This one runs them together.

## Limits
- **Any EU country, one country per run.** For a second country, start a second run with the same brief.
- **Companies only, free public data, the four free tools** the Signals guide lists (public data lookup, web search, reading a public page, working on files). This guide adds no tools.
- **It ends at the work order.** Finding contacts, writing messages and sending them are outside the series.

## What's in the repo
```
AGENT.md                start here (for the agent)
steps/                  one file per step
loop-backs.md           the named rules for going back a step
run-brief-template.md   filled in by the agent in step 2
schema.md               output columns, shared across the series
checklist.md            definition of done
examples/               made-up brief, run log and run summary
LICENSE                 MIT
```

## Influences
The guide is written from scratch. It draws mainly on my own work running market maps, list checks, tiering and signals end to end for companies selling into European markets, and it also learned from public work:

- **Eric Nowoslawski, [coldoutboundskills](https://github.com/growthenginenowoslawski/coldoutboundskills)** (MIT). `auto-research-public` runs a whole campaign from one target domain in phases, and pauses for a person before the steps that can't be undone. The gates in steps 3–6 keep that idea: a person signs off at every hand-off.

Where this guide goes its own way: it stops at a ready work order, with no contacts, copy or sending; it adds no method of its own; it puts pass, note and stop rules on every hand-off; and it limits loop-backs to a named set, so the user, not the agent, decides when to go round again.

## Licence
[MIT](LICENSE). Use it, fork it, adapt it, including commercially; keep the copyright notice.

# Daily Engineering Journal

Each entry records a gap: something the build exposed that I could not yet answer, decide or prove, and how it was closed. The running summary is in [GAPS.md](../GAPS.md).

A day is one working session (about 2–3 hours). Create one file per day, named `day-001.md`, `day-002.md`, and so on.

## What goes in an entry

- Where the gap was found: a failing test, a missed target, a requirement, a threat-model finding or a review comment
- What was built or decided to close it, with links
- Evidence that it is closed

## Day 0

The preparation period before Day 001 is tracked as a readiness checklist in [PROGRESS.md](../PROGRESS.md), not as day files. Numbered entries start at `day-001.md`.

## Days with no gap

Not every session exposes a gap. Log those with the light template as "extended X, no gap found". Do not invent one.

## Two templates

| Template | Use it for | Length |
|---|---|---|
| [_TEMPLATE-light.md](./_TEMPLATE-light.md) | Routine days: incremental progress, small experiments, days with no gap | 5 short sections |
| [_TEMPLATE-full.md](./_TEMPLATE-full.md) | Days that produce a design or a decision, project milestones, and at least one day per roadmap block | 12 sections |

If a day produces a real decision, use the full template and write an [ADR](../architecture/adr/README.md).

## Completion rule

A day is complete when its entry links at least one tangible artifact and includes evidence. The accepted artifacts are listed under Evidence Rules in [PROGRESS.md](../PROGRESS.md). A gap opened during the day goes into [GAPS.md](../GAPS.md) and stays open until a decision or evidence closes it.

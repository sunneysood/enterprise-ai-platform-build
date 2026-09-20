# Gaps

A gap is something the build exposed that I could not yet answer, decide or prove. This register is the running list of gaps and how each one was closed.

## What counts as a gap

- A failing test, missed target or broken assumption
- A requirement or acceptance criterion I cannot yet meet
- An unanswered design question that blocks the next step
- A threat-model finding or a review comment

Reading about a topic is not a gap. A gap is found by building, measuring or reviewing.

## Rules

1. Every gap has a "found by": the test, measurement, requirement or review that exposed it.
2. A gap is closed only by a decision or evidence: an ADR, a passing test, a measurement or a merged fix. Link it.
3. A day with no gap is fine. Log it as "extended X, no gap found". Do not invent gaps.
4. IDs are sequential and never reused. Closed gaps stay in the table.
5. The day entry holds the detail. This register holds the summary.

Statuses: `Open` · `Closed` · `Deferred` (say why in the last column)

## Register

| ID | Gap | Found on | Found by | Status | Closed by |
|---|---|---|---|---|---|
| G-001 | Tenant isolation strategy for P1 is undecided | Phase 0 | P1 requirements | Open | |
| G-002 | Token format and signing approach for P1 is undecided | Phase 0 | P1 requirements | Open | |
| G-003 | Database migration tool for P1 is undecided | Phase 0 | P1 requirements | Open | |
| G-004 | Error format for P1 is undecided | Phase 0 | P1 requirements | Open | |

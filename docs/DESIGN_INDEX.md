# Design index

Locator for [TOWNGAME_DESIGN.md](TOWNGAME_DESIGN.md). **This index holds no design
facts and no status promises.** It maps section names to line numbers so a task can
open the few sections it needs instead of reading the 2,930-line document.

Read it under the task routes in [AGENTS.md](AGENTS.md) and the project rules in
[agent-project-rules.md](agent-project-rules.md).

## How to use this index

1. Find the topic in the topic map or system table below.
2. Read the line range shown, plus any section the **Superseded by** column names.
3. Before changing a rule, confirm it has not been superseded — the status snapshot
   at the top of the design document is authoritative over the table here.
4. After editing the design document, refresh the affected line numbers here.

Line numbers are a convenience, not an identifier. **Section names are the stable
identifiers.** Numbering in the design document is organic and has known collisions,
listed under [Known numbering hazards](#known-numbering-hazards).

## Current work

Resume at **System 19E — Central Workspace & Deep Management Views** (the
Continuation Point at the end of the design document). System 19 is the only
system marked `Currently designing`.

## Topic map

| Topic | Section | Line |
| --- | --- | --- |
| Time, turns, seasons, run structure | Decision 001 — Time and Run Structure | 65 |
| Player role, Lord, ruling chamber | Decision 002 — Player Role and Presentation Frame | 87 |
| Action Points, monthly planning | Decision 003 — Monthly Planning and Action Points | 107 |
| Population, workforce, aging, specialists | Decision 004 — Population and Workforce | 259 |
| Resources, economy, food, stockpiles, trade | Decision 005 — Resources and Economy | 218 |
| Buildings, housing, infrastructure, maintenance | Decision 006 — Buildings and Infrastructure | 357 |
| Unrest, legitimacy, collapse, political state | Decision 007 — Unrest, Legitimacy, and Collapse Pressure | 425 |
| Difficulty tiers, world pressure, expectations | Decision 008 — Difficulty Escalation and Expectations | 607 |
| Events, crises, event memory, event pacing | Decision 009 — Events and Persistent Crises | 719 |
| Score, milestones, legacy points, records | Decision 010 — Run Objectives, Milestones, Scoring, and Meta Rewards | 1074 |
| Legacy talent tree, meta progression | Decision 011 — Meta Progression Structure | 1257 |
| Specialization and run identity | Decision 012 — Specialization & Run Identity | 1344 |
| Policies, laws, reforms, decrees | Decision 013 — Policies, Laws & Ongoing Management | 1426 |
| Research, knowledge, technology | Decision 014 — Research, Knowledge & Technology | 1489 |
| Trade, regional economy, contracts | Decision 015 — Trade, External Economy & Regional World | 1561 |
| Run setup, ambitions, difficulty selection | Decision 016 — Ambitions, Difficulty & Run Setup | 1636 |
| Geography, regions, starting conditions | Decision 017 — Starting Geography, Regions & Settlement Conditions | 1708 |
| Religion, church, cultural life | System 18 — Religion, Social Institutions & Cultural Life | 1780 |
| Map table, UI, information architecture | System 19 — Map Table, UI & Information Architecture | 1859 |
| Navigation domains, planning workflow | System 19A — Navigation Domains & Core Planning Workflow | 2029 |
| Tooltips, transparency, commitment safety | System 19B — Tooltips, Information Transparency & Commitment Safety | 2073 |
| UI customization, guidance, confirmations | System 19C — UI Customization, Guidance & Confirmations | 2273 |
| Right inspector, forecast, events, decisions | System 19D — Right Inspector, Forecasts, Events & Decision Presentation | 2566 |
| Central workspace, deep management views | **System 19E — not yet written** | — |

Sections that carry real content but are not a numbered Decision or System:

| Topic | Section | Line |
| --- | --- | --- |
| Concept and core design principles | 1. Game Concept | 42 |
| Projects, construction, worker allocation | 3. Projects, Construction, and Development | 131 |
| Ideas explicitly not yet accepted | 4. Important Design Ideas — Not Yet Accepted | 179 |
| Unresolved questions carried from early systems | 5. Open Questions | 201 |
| Roadmap placeholders, not accepted designs | Parked Future Systems (Systems 20–23) | 2883 |
| Where to resume design discussion | Continuation Point | 2916 |

## System table

Status values are copied from the design document's own markers. Where the summary
snapshot at the top of that document and a section header disagree, the snapshot wins.

| System | Section line | Status | Notes |
| --- | --- | --- | --- |
| 01 | 65 | Accepted | — |
| 02 | 87 | Accepted | — |
| 03 | 107 | Accepted | — |
| 04 | 259 | Accepted at system level | Balance open |
| 05 | 218 | Accepted at system level | Balance and later resources open |
| 06 | 357 | Accepted | — |
| 07 | 425 | Accepted at system level | **Collapse trigger reopened after System 18** |
| 08 | 607 | Accepted at system level | Formulas and tier thresholds open |
| 09 | 719 | Accepted at system level | Event tables and probabilities open |
| 10 | 1074 | Accepted at system level | Formula and thresholds open |
| 11 | 1257 | Accepted | Structure authoritative in this section |
| 12 | 1344 | Mostly settled | Thresholds and content open |
| 13 | 1426 | Mostly settled | Stances and formulas open |
| 14 | 1489 | Mostly settled | Catalogue and costs open |
| 15 | 1561 | Mostly settled | Price model open |
| 16 | 1636 | Mostly settled | Multipliers and pacing open |
| 17 | 1708 | Mostly settled | Archetypes and scaling open |
| 18 | 1780 | **Needs revisit later** | — |
| 19 | 1859 | **Currently designing** | 19A proposed; 19B/19C/19D mostly settled; **19E next** |
| 20–23 | 2887 | Parked | Roadmap placeholders, not accepted |

## Supersede log

Only revisions the design document itself marks as superseding. Add a row whenever a
later section explicitly overrides an earlier rule.

| Older rule | Superseded by | Effect |
| --- | --- | --- |
| `100% Unrest = immediate Game Over on month resolution` (System 07 prototype rule) | Reopened in System 07, "Final collapse trigger — reopened after System 18" (line 456) | Direction is now an imminent/probabilistic overthrow state that may interrupt the following planning phase |
| Systems 10–11 diminishing LP-conversion direction | System 16; see "Legacy Point score conversion — revised by System 16" (line 1157) and "Legacy Point economy — revised by System 16" (line 1328) | Score → Legacy Points is now linear or near-linear; pacing comes from talent cost escalation |
| Early settlement-development proposals in Systems 1–3 | Decision 005 and Decision 006 | Organic housing, layered resources, and map-table forecasting replaced earlier development detail |

## Known numbering hazards

These are documentation defects, not design decisions. This index works around them
by using section names. They are recorded here so a reader is not misled by the
numbers in the design document.

- **Duplicate `## 5`.** Line 201 is `5. Open Questions`; line 218 is
  `5. Decision 005 — Resources and Economy`.
- **Out-of-order Decision numbering.** `5. Decision 005` (218) precedes
  `6. Decision 004` (259).
- **Decision 011 appears twice.** Line 1239 is `System 11 — Meta Progression
  Structure` (a bare placeholder); line 1257 is `Decision 011` with the real content.
  Line 1241 states the Decision is authoritative.
- **Thirteen unnumbered `##` sections.** Decisions 006–017 and Systems 18–19 carry no
  number in their heading, while Decisions 001–005 do.
- **Heading levels migrate within one family.** The Decision/System family is nested
  at `##`, then System 19's subsections at `###`, then System 19's decisions at `####`.
  `## Decision 019B`-style content sits inside `## System 19` rather than beside it.
- **`19B` is ambiguous.** `### System 19B` (line 2073) and `#### Decision 019B`
  (line 2255) both exist. `19A` has no `#### Decision 019A` counterpart.
- **`# Later Design Systems` (line 1342)** is an unnumbered top-level tier between
  `##` sections and is not in the status snapshot.
- **Parked Systems 20–23 are absent from the status snapshot** at the top of the
  design document.
- **Line wrapping inside headings.** `#### Decision 019D — Contextual Inspector,
  Hybrid Forecast & Unified Event Handling` (line 2857) is broken across two source
  lines and will not match a single-line search.

## Maintenance

- Refresh line numbers after any edit that shifts the design document.
- Add a supersede-log row whenever a section explicitly overrides an earlier rule;
  keep the superseded text in the design document rather than deleting it.
- Keep this file a locator. Design facts belong in the design document.

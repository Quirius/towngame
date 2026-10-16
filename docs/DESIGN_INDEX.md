# Design index

Locator for [TOWNGAME_DESIGN.md](TOWNGAME_DESIGN.md). **This index holds no design
facts and no status promises.** It maps section names to line numbers so a task can
open the few sections it needs instead of reading the 3,350-line document.

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

Resume at **System 22A — Warfare / Territorial Expansion choices** (the
Continuation Point at the end of the design document). Systems 19–21 are mostly
settled at design-principle level. System 22 is currently being designed;
strategic warfare and limited expansion are proposals, not accepted choices.

## Topic map

| Topic | Section | Line |
| --- | --- | --- |
| Time, turns, seasons, run structure | Decision 001 — Time and Run Structure | 75 |
| Player role, Lord, ruling chamber | Decision 002 — Player Role and Presentation Frame | 97 |
| Action Points, monthly planning | Decision 003 — Monthly Planning and Action Points | 117 |
| Population, workforce, aging, specialists | Decision 004 — Population and Workforce | 269 |
| Resources, economy, food, stockpiles, trade | Decision 005 — Resources and Economy | 228 |
| Buildings, housing, infrastructure, maintenance | Decision 006 — Buildings and Infrastructure | 367 |
| Unrest, legitimacy, collapse, political state | Decision 007 — Unrest, Legitimacy, and Collapse Pressure | 435 |
| Difficulty tiers, world pressure, expectations | Decision 008 — Difficulty Escalation and Expectations | 617 |
| Events, crises, event memory, event pacing | Decision 009 — Events and Persistent Crises | 729 |
| Score, milestones, legacy points, records | Decision 010 — Run Objectives, Milestones, Scoring, and Meta Rewards | 1084 |
| Legacy talent tree, meta progression | Decision 011 — Meta Progression Structure | 1267 |
| Specialization and run identity | Decision 012 — Specialization & Run Identity | 1354 |
| Policies, laws, reforms, decrees | Decision 013 — Policies, Laws & Ongoing Management | 1436 |
| Research, knowledge, technology | Decision 014 — Research, Knowledge & Technology | 1499 |
| Trade, regional economy, contracts | Decision 015 — Trade, External Economy & Regional World | 1571 |
| Run setup, ambitions, difficulty selection | Decision 016 — Ambitions, Difficulty & Run Setup | 1646 |
| Geography, regions, starting conditions | Decision 017 — Starting Geography, Regions & Settlement Conditions | 1718 |
| Religion, church, cultural life | System 18 — Religion, Social Institutions & Cultural Life | 1790 |
| Map table, UI, information architecture | System 19 — Map Table, UI & Information Architecture | 1869 |
| Navigation domains, planning workflow | System 19A — Navigation Domains & Core Planning Workflow | 2043 |
| Tooltips, transparency, commitment safety | System 19B — Tooltips, Information Transparency & Commitment Safety | 2087 |
| UI customization, guidance, confirmations | System 19C — UI Customization, Guidance & Confirmations | 2287 |
| Right inspector, forecast, events, decisions | System 19D — Right Inspector, Forecasts, Events & Decision Presentation | 2580 |
| Central workspace, deep management views | System 19E — Central Workspace, Navigation & Deep Management Views | 2899 |
| Settlement visual presentation | System 20 — Town Visualization & Modular Presentation | 3161 |
| Lenders, loans, banking, default | System 21 — Banking, Credit & Monetary Control | 3242 |
| Armies, warfare, territorial expansion | System 22 — Warfare, Armies & Regional Politics | 3320 |

Sections that carry real content but are not a numbered Decision or System:

| Topic | Section | Line |
| --- | --- | --- |
| Concept and core design principles | 1. Game Concept | 52 |
| Projects, construction, worker allocation | 3. Projects, Construction, and Development | 141 |
| Ideas explicitly not yet accepted | 4. Important Design Ideas — Not Yet Accepted | 189 |
| Unresolved questions carried from early systems | 5. Open Questions | 211 |
| Parked and open future systems | Parked Future Systems (System 22 proposed, System 23 parked) | 3316 |
| Where to resume design discussion | Continuation Point | 3335 |

## System table

Status values reflect the authoritative design snapshot through System 21 at the
top of TOWNGAME_DESIGN.md. These are design statuses, not working software.

| System | Section line | Status | Notes |
| --- | --- | --- | --- |
| 01 | 75 | Mostly settled | — |
| 02 | 97 | Mostly settled | — |
| 03 | 117 | Mostly settled | — |
| 04 | 269 | Mostly settled | Exact balance open |
| 05 | 228 | Mostly settled | Detailed economy balancing open |
| 06 | 367 | Mostly settled | — |
| 07 | 435 | **Needs revisit** | Final collapse trigger reopened |
| 08 | 617 | Mostly settled | Detailed thresholds open |
| 09 | 729 | Mostly settled | Event probabilities and content open |
| 10 | 1084 | Mostly settled | Formula balance open |
| 11 | 1267 | Mostly settled | — |
| 12 | 1354 | Mostly settled | Thresholds and content open |
| 13 | 1436 | Mostly settled | Formula balance open |
| 14 | 1499 | Mostly settled | Catalogue and costs open |
| 15 | 1571 | Mostly settled | Price model open |
| 16 | 1646 | Mostly settled | Multipliers and pacing open |
| 17 | 1718 | Mostly settled | Archetypes and scaling open |
| 18 | 1790 | **Needs revisit later** | Church–Lord political balance open |
| 19 | 1869 | **Mostly settled** | Systems 19A–19E and structural UI decisions accepted at principle level |
| 20 | 3161 | **Mostly settled** | Passive representative town visualization |
| 21 | 3242 | **Mostly settled** | Optional loans, banking and monetary control |
| 22 | 3320 | **Currently designing** | Initial warfare and territorial options only; not accepted |
| 23 | 3326 | Parked | Optional timed / pressure mode |

## Supersede log

Only revisions the design document itself marks as superseding. Add a row whenever a
later section explicitly overrides an earlier rule.

| Older rule | Superseded by | Effect |
| --- | --- | --- |
| `100% Unrest = immediate Game Over on month resolution` (System 07 prototype rule) | Reopened in System 07, "Final collapse trigger — reopened after System 18" (line 466) | Direction is now an imminent/probabilistic overthrow state that may interrupt the following planning phase |
| Systems 10–11 diminishing LP-conversion direction | System 16; see "Legacy Point score conversion — revised by System 16" (line 1167) and "Legacy Point economy — revised by System 16" (line 1338) | Score → Legacy Points is now linear or near-linear; pacing comes from talent cost escalation |
| Early settlement-development proposals in Systems 1–3 | Decision 005 and Decision 006 | Organic housing, layered resources, and map-table forecasting replaced earlier development detail |

## Known numbering hazards

These are documentation defects, not design decisions. This index works around them
by using section names. They are recorded here so a reader is not misled by the
numbers in the design document.

- **Duplicate `## 5`.** Line 201 is `5. Open Questions`; line 228 is
  `5. Decision 005 — Resources and Economy`.
- **Out-of-order Decision numbering.** `5. Decision 005` (218) precedes
  `6. Decision 004` (259).
- **Decision 011 appears twice.** Line 1239 is `System 11 — Meta Progression
  Structure` (a bare placeholder); line 1267 is `Decision 011` with the real content.
  Line 1251 states the Decision is authoritative.
- **Several unnumbered `##` sections.** Decisions 006–017 and Systems 18–19 carry no
  number in their heading, while Decisions 001–005 do.
- **Heading levels migrate within one family.** The Decision/System family is nested
  at `##`, then System 19's subsections at `###`, then System 19's decisions at `####`.
  `## Decision 019B`-style content sits inside `## System 19` rather than beside it.
- **`19B` is ambiguous.** `### System 19B` (line 2087) and `#### Decision 019B`
  (line 2269) both exist. `19A` has no `#### Decision 019A` counterpart.
- **`# Later Design Systems` (line 1342)** is an unnumbered top-level tier between
  `##` sections and is not in the status snapshot.
- **System 23 is parked and absent from the top status snapshot**; System 22 is
  the active proposal and Systems 20–21 have settled design principles.
- **Line wrapping inside headings.** `#### Decision 019D — Contextual Inspector,
  Hybrid Forecast & Unified Event Handling` (line 2871) is broken across two source
  lines and will not match a single-line search.

## Maintenance

- Refresh line numbers after any edit that shifts the design document.
- Add a supersede-log row whenever a section explicitly overrides an earlier rule;
  keep the superseded text in the design document rather than deleting it.
- Keep this file a locator. Design facts belong in the design document.

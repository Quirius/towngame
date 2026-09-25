# Agent workflow

User instructions take precedence. Complete only the requested work; stop when done.
Run commands from the `towngame/` checkout root.

## Context and safeguards

- This is currently a design-document project. Do not introduce implementation or
  expand product scope unless requested.
- Design authority is [TOWNGAME_DESIGN.md](TOWNGAME_DESIGN.md). Read it through
  [DESIGN_INDEX.md](DESIGN_INDEX.md) rather than whole.
- Locate files and headings with bounded `rg` searches; read relevant sections only,
  batch independent reads, and avoid rereading unchanged files.
- There is no build, dependency manifest or test suite; do not invent one, and do
  not infer a stack from sibling projects.
- This repository has no release gates of its own. Read
  [status.md](status.md) only for recorded baseline or history.

## Task and check routing

[DESIGN_INDEX.md](DESIGN_INDEX.md) is the locator for
[TOWNGAME_DESIGN.md](TOWNGAME_DESIGN.md): it maps topics and systems to line
ranges, carries the per-system status and supersede log, and lists the design
document's known numbering hazards. Use it to find sections; read only those
sections. **Do not load the whole design document by default.**

| Task | Read |
| --- | --- |
| Any design topic | Matching row in the [topic map](DESIGN_INDEX.md#topic-map) |
| System status or open vs. settled | [System table](DESIGN_INDEX.md#system-table) |
| Before changing an existing rule | [Supersede log](DESIGN_INDEX.md#supersede-log), then the section |
| Current design work | [System 19E](DESIGN_INDEX.md#current-work) |
| Collapse, unrest, ending a run | Decision 007 (line 425) **and** "Final collapse trigger — reopened after System 18" (line 456) |
| Score, legacy points, progression curve | Decision 010 (line 1074), "revised by System 16" (line 1157), Decision 016 (line 1636) |
| Interface, map table, forecasts, inspector | System 19 (line 1859), then the relevant 19A–19D subsection |
| Settlement development, housing, buildings | Decision 005 (line 218) and Decision 006 (line 357) |
| Resources, economy, trade | Decision 005 (line 218) and Decision 015 (line 1561) |

- Distinguish accepted decisions, proposals, and open questions. Check later
  superseding decisions before changing a rule; do not silently resolve conflicts.
- Section names are the stable identifiers; line numbers are convenience. Refresh
  the index when an edit shifts the design document.

Documentation changes use the [documentation checks](checks.md); there is no
application suite to run.

## Behavior and safety rules

Project rules live in [agent-project-rules.md](agent-project-rules.md). Read the
applicable sections before changing or reviewing design behavior; its Git and
release rules govern publication for this repository.

## Execution and completion

- Suggested model: **DeepSeek V4.1 Flash in Copilot Chat**, low reasoning. This is
  an advisory hint, not a requirement; any provider may proceed normally.
- Handle small tasks directly. Use a subagent with an increased thinking-effort
  setting only for bounded, genuinely harder work; see
  [agent-project-rules.md](agent-project-rules.md#delegation). Agents that cannot
  honor this suggestion may ignore it.
- Standing authorization to commit and push verified task changes remains in effect
  unless the user says otherwise; see
  [Git and releases](agent-project-rules.md#git-and-releases).
- **Be as concise as possible.** Report what changed, what was verified and any
  material limitation in the fewest lines that carry the information. Prefer short
  bullets over paragraphs, one line per item; no preamble, no restating the request,
  no narrating the steps taken, no closing summary of the summary.
- State what passed as a count and scope (for example "all 18 targeted tests
  passed"), never as a per-item walkthrough. Name the commit and branch when a
  commit was made, on one line.
- Include a precise next step, and only the caveats that change what the reader does.
- Expand only when asked, when a failure needs diagnosis, or when the user must make
  a decision.
- Report results, checks and material limitations briefly; mention Git actions when
  performed and model changes/fallbacks only when relevant.
- At an unrelated task switch or long-session handoff, keep only the objective,
  relevant paths, decisions, checks and next step. Do not maintain a running
  transcript or claim that context was removed or tokens were saved.

# Initial setup — what changed and why

Setup pass for agent efficiency. Deliberately minimal: only structure that stays
correct as the design grows. No implementation, tooling, or dependency decisions.

## The problem

`docs/TOWNGAME_DESIGN.md` is 2,930 lines. The agent workflow said to "search
headings" and read only relevant sections, but nothing mapped a topic to a section,
and the section structure has real ambiguities:

- Decision 011 appears twice — a bare placeholder at line 1239 and the real content
  at line 1257.
- `19B` resolves to two different sections depending on heading level.
- Thirteen `##` sections carry no number while Decisions 001–005 do.
- `5. Open Questions` and `5. Decision 005` share the number 5.

A reader following "read only the relevant sections" had to scan headings and guess.
The design document's own rule — "when older sections conflict with a later explicitly
marked revision, the later revision wins" — was also unenforceable without a record
of what supersedes what.

## What changed

| File | Change |
| --- | --- |
| `docs/DESIGN_INDEX.md` | **New.** Topic map, system table with status, supersede log, and the numbering hazards found above |
| `docs/AGENTS.md` | Task routing replaced with a table into the index; rework-prone rows inlined |
| `README.md` | Records that the project is design-only and routes to the index |
| `.vscode/settings.json` | Pins the terminal working directory to the project root |

A later pass mirrored the `wowflippingmacro` documentation set, adding
`docs/agent-project-rules.md` (project rules, delegation, Git and releases),
`docs/checks.md` and `docs/status.md`, and restructuring `docs/AGENTS.md` into
context, routing and execution sections.

Nothing in `TOWNGAME_DESIGN.md` was edited.

## Decisions worth reviewing

**Why an index file instead of cleaning up the design document.** Renumbering would
be the tidy fix but it breaks things the document depends on. Its opening block calls
itself the authoritative superseding snapshot, and its closing note says a new
conversation should treat it as authoritative without restarting from System 12 —
both imply stable, externally referenced numbering. Trello entries and prior ChatGPT
conversations reference sections by number. Repairs are also only as good as the
current document: the next appended system reintroduces drift, whereas an index plus
a supersede log absorbs new systems without rework. The defects are documented rather
than silently normalized, so a future pass can fix them deliberately.

**Why the index separates topic, status and supersede data.** These change at
different rates. Adding System 24 touches one table row; superseding a rule touches
the log; neither requires rereading the map.

## Trade-off

Line numbers in the index go stale when the design document is edited above them.
Section names are the stable identifiers and the index says so, with a maintenance
note to refresh line numbers after edits. This is a real cost, accepted because the
alternative — no locator — costs a heading scan on every task.

## Not done, on purpose

- No implementation scaffolding, build config, dependency manifest, or CI.
- No test tooling; there is nothing to test.
- No restructuring of the design document.
- No scope invented: the design document is the only authoritative source.

## Suggested follow-up, when wanted

- Fix the numbering defects listed in the index, then drop that section.
- Split the design document only if it keeps growing; the index makes that safe to
  defer. If it is split, the index becomes the entry point and each file owns a
  section range.

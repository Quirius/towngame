# TownGame agent instructions

Shared instructions for every coding agent (Codex and OpenCode read this file;
Claude Code loads it through `CLAUDE.md`). User instructions take precedence. Run
commands from this checkout root. Load detailed documents only when the task needs
them; never preload the design document or sibling repositories.

## Project

Roguelite medieval settlement strategy game in which the player is a Lord making
monthly decisions. **Design only:** there is no source, build, dependency manifest or
application test suite. Do not introduce implementation, scaffolding, tooling or
product scope unless the user asks, and do not infer a stack from sibling projects.

## Design documents

- [docs/TOWNGAME_DESIGN.md](docs/TOWNGAME_DESIGN.md) (about 3,350 lines) is the single
  authoritative design. **Never load it whole.**
- [docs/DESIGN_INDEX.md](docs/DESIGN_INDEX.md) is its locator: topic map with line
  numbers, per-system status, supersede log and known numbering hazards. Find the
  section there, then read only that line range plus any superseding section.
- Section names are the stable identifiers; line numbers are a convenience and must
  be refreshed in the index whenever an edit shifts the design document.

| Task | Start in DESIGN_INDEX.md |
| --- | --- |
| Any design topic | [Topic map](docs/DESIGN_INDEX.md#topic-map) |
| Settled vs open vs parked systems | [System table](docs/DESIGN_INDEX.md#system-table) |
| Before changing any existing rule | [Supersede log](docs/DESIGN_INDEX.md#supersede-log), then the section |
| Where design work resumes | [Current work](docs/DESIGN_INDEX.md#current-work) (System 22A) |
| Collapse, unrest, ending a run | Decision 007 **and** "Final collapse trigger — reopened after System 18" |
| Score, Legacy Points, progression curve | Decision 010, "Legacy Point score conversion — revised by System 16", Decision 016 |
| Interface, map table, forecasts, inspector | System 19, then subsections 19A-19E |
| Settlement development, housing, buildings | Decisions 005 and 006 |
| Resources, economy, trade, banking | Decisions 005 and 015, System 21 |

## Non-negotiable rules

- Distinguish accepted decisions, proposals and open questions; check a section's own
  status marker and later superseding revisions before changing a rule. A proposal is
  never silently promoted, and conflicts are surfaced, not silently resolved.
- When sections conflict, the later explicitly marked revision wins. Record the
  supersession in the index; keep the older text in the design document.
- Do not restructure or renumber the design document; record numbering defects in
  the index instead.
- Do not pull parked systems into active design work merely because a section exists.
- One home per fact: change the document that owns it and link elsewhere.
- Full rules, response style, delegation, Git and releases:
  [docs/agent-project-rules.md](docs/agent-project-rules.md) (load relevant sections).

## Checks

Documentation edits only: confirm changed links resolve, re-verify every index line
number you touched against a real heading, and run `git diff --check`. Commands and
scripts: [docs/checks.md](docs/checks.md). A check that does not run is not a pass.

## Working rules

- Locate headings with bounded `rg` or the harness search tool; read relevant
  sections only and do not reread unchanged files.
- Be concise in chat: lead with the result, short bullets, counts not walkthroughs,
  next step and only caveats that change what the reader does.
- Git: work on `main` unless told otherwise; small Conventional Commits; standing
  authorization to commit and push verified task changes unless the user says
  otherwise. Never force-push or rewrite history; branches, pull requests and tags
  need user instruction.
- Check `git status` first and leave unrelated or another agent's uncommitted work
  untouched. If the user approves parallel tasks, use one branch and worktree each.
- Git history is the change record. Update [docs/status.md](docs/status.md) only when
  a system's status or a structural fact changes. When stopping mid-task, report
  completed changes, outstanding work and verification status.
- Models: cheapest capable tier (Claude Opus > Sonnet > Haiku; OpenAI Sol > Luna);
  subscription logins only. Delegation rules:
  [agent-project-rules](docs/agent-project-rules.md#delegation).

## Project HQ reporting

`.project/` holds the schema-version-1 status, roadmap and decisions published from
`main`; [.project/README.md](.project/README.md) owns the contract and the
[completion gate](.project/README.md#reporting-completion-gate). After substantive
pushed design work, refresh the affected `.project/` records, set `source.commit` to
the reviewed design commit, run `python scripts/check_project_hq_freshness.py --strict`,
and publish reporting as a separate commit. Reporting summarizes the design; it never
replaces it. Accepted design does not mean implemented.

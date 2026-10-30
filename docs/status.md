# Current state

Load when assessing current work or a matching problem. Reviewed 2026-10-30 against
the repository; per-system design status lives only in the
[system table](DESIGN_INDEX.md#system-table) and is not repeated here.

- Branch `main`, remote `origin`; no tags. The repository holds design documentation
  only: no source, build, dependency manifest or application tests. The only
  automation is the Project HQ freshness check (`scripts/check_project_hq_freshness.py`,
  run by `.github/workflows/project-hq-freshness.yml`, tested in `.github/tests/`).

- Design progress: Systems 01-21 are mostly settled at design-principle level, with
  07 (final collapse trigger) and 18 (Church-Lord balance) flagged for revisit and
  numeric balancing open throughout. System 22 (warfare, armies, regional politics) is
  being designed and is not accepted; System 23 is parked. Next step:
  [Current work](DESIGN_INDEX.md#current-work).

- Documentation set: root `AGENTS.md` (shared agent instructions; `CLAUDE.md` imports
  it), `README.md`, `docs/README.md` (documentation map), `docs/agent-project-rules.md`
  (rules, response style, delegation, Git and releases), `docs/checks.md`,
  `docs/DESIGN_INDEX.md` (locator for the design document), `docs/INITIAL_SETUP.md`
  (historical record of the indexing pass), `docs/TOWNGAME_DESIGN.md` (the
  authoritative design), `.project/` (Project HQ reporting) and this file.

- Known documentation defects (duplicate numbering, heading-level drift, ambiguous
  `19B`) are recorded under [Known numbering hazards](DESIGN_INDEX.md#known-numbering-hazards)
  rather than fixed in the design document.

Keep test counts, machine-specific results and dated evidence out of always-loaded
instructions. Update this file when a system's status or a structural fact changes.

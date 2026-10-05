# Repository instructions

## Model and application notes

Prefer **GPT-6.1 Sol** (`gpt-6.1-sol`) or **GPT-6 Astra** (`gpt-6-astra`)
as the main coordinator. Both should use **GPT-6 Luna** (`gpt-6-luna`)
subagents for coding, light work, and independent critical review wherever needed
to improve token efficiency. Keep Luna scopes bounded, with clear ownership,
minimal context, and concrete acceptance checks. The main coordinator should
focus on broader decisions and especially heavy tasks, retaining responsibility
for integration and final validation. Escalate difficult or unresolved work to
the coordinator. Keep trivial work local only when delegation overhead would
outweigh the expected savings; never claim unmeasured token savings.

These model preferences do not restrict access or block work when only other
suitable models are available.

Read [docs/AGENTS.md](docs/AGENTS.md) once per session for this repository's
workflow and task routing. Load only the referenced sections needed for the task;
do not preload all documentation or sibling projects.

## Project HQ reporting

For substantive work, read [.project/README.md](.project/README.md) and the
relevant status, roadmap, and decision files. Publish reporting on `main`, using
the pushed design revision as the evidence baseline. The authoritative design is
[TOWNGAME_DESIGN.md](docs/TOWNGAME_DESIGN.md), located through
[DESIGN_INDEX.md](docs/DESIGN_INDEX.md); reporting summarizes rather than replaces
them. Update reporting when a design status, plan, blocker, milestone, or decision
materially changes. Preserve stable IDs, schema version 1, manual plans, and unknown
values. Follow the repository's Git rules; describe unpushed work in the handoff,
refresh reports after relevant design changes are pushed, and use a separate
reporting commit when needed. Do not create timestamp-only reporting chains or
claim the dashboard synchronized merely because a report was pushed.

# Repository instructions

## Model and application notes

Prefer GPT-6 Astra as the main coordinator. Use GPT-6 Sol and GPT-6 Luna subagents
extensively when Astra judges their skills applicable and expected usage efficiency
improves. Delegate bounded subtasks: prefer Luna for straightforward
research and mechanical documentation work, and Sol for coding, debugging and
technical review. Astra owns orchestration and difficult or ambiguous decisions.
Delegate when the applicable skills and task shape make the added coordination
worthwhile; handle trivial or tightly coupled work directly.
These preferences do not block work when only other suitable models are available.

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

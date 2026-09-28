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

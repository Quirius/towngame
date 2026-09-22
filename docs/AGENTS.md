# Agent workflow

User instructions take precedence. Complete only the requested work; stop when done.
Run commands from the `towngame/` checkout root.

## Model and application

Use **DeepSeek models in Copilot Chat only**. The project-root `AGENTS.md`
permission gate applies to overrides, assignment changes, and workers.

## Task routing

- Design work: search headings in [TOWNGAME_DESIGN.md](TOWNGAME_DESIGN.md),
  then read only the sections relevant to the requested system and applicable
  later revisions. Do not load the whole design document by default.
- Distinguish accepted decisions, proposals, and open questions. Check later
  superseding decisions before changing a rule; do not silently resolve conflicts.
- This is currently a design-document project. Do not introduce implementation
  or expand product scope unless requested.

## Context and verification

- Search filenames and headings first with `rg --files` and `rg -n`; read only
  relevant sections. Narrow large results instead of dumping whole files.
- Read this workflow once per session. Do not reread unchanged files, preload
  sibling projects, or load generated files, dependencies, or history by default.
- Make the smallest coherent change. Keep one home per fact and link to it.
- For documentation edits, check links, content, and the diff. For code changes,
  run the narrowest meaningful checks; broaden only for concrete regression risk.
- Do not commit, tag, push, create branches, or open pull requests unless requested.
- Report results and material limitations briefly.

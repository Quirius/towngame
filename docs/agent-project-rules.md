# Project rules (load relevant sections only)

Applies to design work and design documentation. User instructions take precedence.

## Read only what the task needs

Load these only when relevant:

- `TOWNGAME_DESIGN.md` — the design itself. Read it through the locator, not whole.
- `DESIGN_INDEX.md` — topic map, system status, supersede log and numbering hazards.
- `INITIAL_SETUP.md` — why the documentation is structured this way.
- `status.md` — recorded baseline and history.

When two sections conflict, the later explicitly marked revision wins. Record the
supersession in the index rather than deleting the older text.

## Project direction

Towngame is a medieval settlement strategy/roguelite design in which the player is a
Lord managing monthly turns. It is currently a design-document project: there is no
source, build, dependency manifest or test suite.

Do not introduce implementation, scaffolding or product scope unless the user asks.
Do not pull parked systems (design document, "Parked Future Systems") into active
design work merely because a section exists for them.

## Non-negotiable behavior

- Preserve accepted decisions. A proposal is not an accepted decision, and must not
  be silently promoted. Check a section's own status marker and its superseding
  revisions before changing any rule.
- Keep one home per fact. Change the document that owns a fact and link to it
  elsewhere rather than restating it.
- Do not invent scope, stack, tooling, dependencies or repository structure.
- Do not restructure or renumber the design document. Section numbering is treated as
  stable by external references; record defects in `DESIGN_INDEX.md` instead.

## Testing

- There is no application suite. Documentation changes are verified by checking links,
  content and the diff; see `checks.md`.
- A check that does not run, or that matches nothing, is not a pass.
- Report what was checked and what remains unverified.

## Response style

Answers in chat should be **as concise as possible**. This is a standing preference,
not a per-request setting.

- Lead with the result. No preamble, no restating the request, no narrating the
  process, no summary of the summary.
- Short bullets, one line per item. Prefer a count and a scope to a walkthrough:
  "All 18 targeted tests passed", not a list of each test.
- Name the commit and branch on one line when a commit was made.
- Include the next step, and only the caveats that would change what the reader does.
- Keep reasoning, alternatives and rejected options out unless they are needed for a
  decision. Offer detail instead of including it.
- Expand only when asked, when something failed and needs diagnosis, or when the user
  has to choose.
- Never pad with restatements of the rules above or of work already reported.

## Delegation

- The main GPT-6 Astra agent should use GPT-6 Sol and GPT-6 Luna subagents broadly
  when applicable skills and task shape make delegation more efficient. Keep trivial,
  tightly coupled or coordination-heavy work with Astra. Parallelize independent
  subtasks when that shortens the critical path without creating conflicting edits.
- Prefer GPT-6 Luna for bounded, straightforward research, source inspection and
  mechanical documentation tasks. Prefer GPT-6 Sol for coding, debugging and
  technical review. Astra retains orchestration, integration and hard or ambiguous
  design decisions. Choose the least effort setting that can complete each scope.
- Give each agent a fresh, minimal context, the precise task and files or sections it
  owns, applicable rules, and a clear acceptance check. Keep scopes bounded and
  nonoverlapping; avoid whole-document copies and recursive delegation. The agent
  reports its result, paths, checks and blockers briefly for Astra to integrate.
- Do not invent efficiency gains: delegate when the expected parallel progress or
  focused expertise outweighs setup and integration overhead. Never claim unverified
  model, reasoning level or capability.

## Git and releases

- Current work belongs on `main` unless the user directs otherwise.
- Keep commits small and coherent; avoid unrelated formatting or restructuring.
- Never rewrite shared history or force-push. Branch creation and pull requests
  require user instruction.
- Automatically commit completed, verified task changes and push to the configured
  branch remote when appropriate; the owner grants standing authorization without
  reconfirmation. Exclude unrelated changes and local or editor configuration. Use
  Conventional Commit subjects (`docs:`, `chore:`, `feat(scope):`, `fix(scope):`,
  `refactor(scope):`, `test(scope):`).
- Design-only changes are documentation changes. Validate links, index line numbers
  and `git diff --check` before committing; there is no application suite to gate on.
- This repository has no release gates and no versioning convention yet. A tag would
  be premature. Create and push an annotated semantic-version tag only when the user
  explicitly asks, or once real scope, implementation or a release process exists.
  Ordinary commits stay untagged, and a published tag is never moved.

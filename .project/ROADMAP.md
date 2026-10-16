---
schema_version: 1
project_id: "towngame"
plans:
  - id: "towngame-plan-001"
    title: "Design System 19E central workspace and deep management views"
    state: "completed"
    window: "Backlog"
    priority: "medium"
    due_date: null
    completed_at: null
    details: "System 19E and final System 19 consolidation are mostly settled at principle level. Overview keeps the town/map, and deep management uses a task-adaptive workspace. Exact layout remains prototype work."
    acceptance_criteria:
      - "The authoritative design document records an explicit System 19E resolution for the central workspace and deep management views."
      - "The design index and system status reflect that resolution."
    blocked_by: []
    evidence:
      - path: "docs/TOWNGAME_DESIGN.md"
        ref: "f63e24b9fafe0bd52788beaf3790bc90bae4d3c5"
        note: "Earlier continuation identified 19E as open, superseded by final System 19 at c05fd8a853baa56dd9c6902ef0a5df67cba51159."
  - id: "towngame-plan-002"
    title: "Resolve remaining System 19A navigation and planning workflow questions"
    state: "completed"
    window: "Backlog"
    priority: "medium"
    due_date: null
    completed_at: null
    details: "The final System 19 consolidation mostly settles seven top-level domains and the planning/navigation workflow; exact prototype refinements remain open."
    acceptance_criteria:
      - "The authoritative design document explicitly accepts or revises the navigation and workflow proposal."
      - "The System 19 status and design index distinguish the resulting accepted rules from remaining open questions."
    blocked_by:
      - "towngame-plan-001"
    evidence:
      - path: "docs/TOWNGAME_DESIGN.md"
        ref: "f63e24b9fafe0bd52788beaf3790bc90bae4d3c5"
        note: "Earlier 19A proposal was consolidated by final System 19 at c05fd8a853baa56dd9c6902ef0a5df67cba51159."
  - id: "towngame-plan-003"
    title: "Resolve the final collapse trigger"
    state: "planned"
    window: "Backlog"
    priority: "medium"
    due_date: null
    completed_at: null
    details: "The earlier immediate Game Over rule at 100% Unrest is reopened; threshold, probability, warning fairness, timing, and recovery remain unresolved."
    acceptance_criteria:
      - "The authoritative design document records an accepted final collapse trigger and its player warning behavior."
      - "The design index records the outcome of the reopened System 07 rule."
    blocked_by: []
    evidence:
      - path: "docs/TOWNGAME_DESIGN.md"
        ref: "f63e24b9fafe0bd52788beaf3790bc90bae4d3c5"
        note: "Final collapse trigger is explicitly reopened after System 18."
  - id: "towngame-plan-004"
    title: "Revisit Church–Lord control and legitimacy in System 18"
    state: "planned"
    window: "Backlog"
    priority: "medium"
    due_date: null
    completed_at: null
    details: "The core religious identity is established, while the balance among Church autonomy, control, blame, and Lord legitimacy is deliberately unresolved for later design."
    acceptance_criteria:
      - "The authoritative design document resolves the Church–Lord control and legitimacy model."
      - "The design index updates System 18 status to match the accepted design."
    blocked_by: []
    evidence:
      - path: "docs/TOWNGAME_DESIGN.md"
        ref: "f63e24b9fafe0bd52788beaf3790bc90bae4d3c5"
        note: "System 18 marks this model for a later revisit."
  - id: "towngame-plan-005"
    title: "Resolve System 22A warfare and territorial expansion scope"
    state: "planned"
    window: "Backlog"
    priority: "medium"
    due_date: null
    completed_at: null
    details: "The currently active System 22A presents strategic non-tactical warfare and a choice between settlement-focused defense or optional limited territorial expansion. Neither choice is yet accepted."
    acceptance_criteria:
      - "The owner chooses a warfare-control scope and whether optional limited territorial holdings belong in the design."
      - "The authoritative design and index record the accepted direction and remaining detailed questions."
    blocked_by: []
    evidence:
      - path: "docs/TOWNGAME_DESIGN.md"
        ref: "c05fd8a853baa56dd9c6902ef0a5df67cba51159"
        note: "System 22A continuation point leaves both scope decisions open."
milestones: []
---

# TownGame roadmap

The front matter is the reporting list. [The living design](../docs/TOWNGAME_DESIGN.md) owns the detailed proposals and accepted rules; [the design index](../docs/DESIGN_INDEX.md) locates their current status. These entries track design work only. They do not claim game implementation.

No owner deadline or near-term commitment is documented. The `Backlog` and `medium` values are reporting defaults, not commitments. Systems 19–21 are mostly settled at design level; System 22 is the active proposal and System 23 remains parked.

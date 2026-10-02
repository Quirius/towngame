---
schema_version: 1
project_id: "towngame"
plans:
  - id: "towngame-plan-001"
    title: "Design System 19E central workspace and deep management views"
    state: "planned"
    window: "Backlog"
    priority: "medium"
    due_date: null
    completed_at: null
    details: "The documented next active design subsection must resolve map visibility, replacement versus overlay, spatial continuity, return to Overview, and dense management views within the persistent shell."
    acceptance_criteria:
      - "The authoritative design document records an explicit System 19E resolution for the central workspace and deep management views."
      - "The design index and system status reflect that resolution."
    blocked_by: []
    evidence:
      - path: "docs/TOWNGAME_DESIGN.md"
        ref: "f63e24b9fafe0bd52788beaf3790bc90bae4d3c5"
        note: "Continuation Point identifies 19E and its unresolved questions."
  - id: "towngame-plan-002"
    title: "Resolve remaining System 19A navigation and planning workflow questions"
    state: "planned"
    window: "Backlog"
    priority: "medium"
    due_date: null
    completed_at: null
    details: "System 19A is proposed, not accepted. Revisit its top-level domain grouping and planning workflow after 19E."
    acceptance_criteria:
      - "The authoritative design document explicitly accepts or revises the navigation and workflow proposal."
      - "The System 19 status and design index distinguish the resulting accepted rules from remaining open questions."
    blocked_by:
      - "towngame-plan-001"
    evidence:
      - path: "docs/TOWNGAME_DESIGN.md"
        ref: "f63e24b9fafe0bd52788beaf3790bc90bae4d3c5"
        note: "System 19A is proposed and the continuation point says to return after 19E."
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
milestones: []
---

# TownGame roadmap

The front matter is the reporting list. [The living design](../docs/TOWNGAME_DESIGN.md) owns the detailed proposals and accepted rules; [the design index](../docs/DESIGN_INDEX.md) locates their current status. These entries track design work only. They do not claim game implementation.

No owner deadline, near-term window, or explicit project milestone was verified at the selected pushed revision. The `Backlog` and `medium` values are reporting defaults described in [the contract](README.md), not owner commitments. Parked Systems 20–23 remain parked in the design document and are not promoted to active plans here.

---
schema_version: 1
project_id: "towngame"
decisions:
  - id: "towngame-decision-001"
    title: "Monthly, untimed runs"
    context: "The accepted time and run structure advances in discrete monthly turns, with planning before immediate resolution and no real-time waiting requirement."
    state: "resolved"
    resolution: "Use monthly turns with an untimed planning phase."
    decided_at: null
    evidence:
      - path: "docs/TOWNGAME_DESIGN.md"
        ref: "f63e24b9fafe0bd52788beaf3790bc90bae4d3c5"
        note: "Decision 001 is marked accepted."
  - id: "towngame-decision-002"
    title: "Lord's chamber and map table"
    context: "The accepted presentation places the Lord in a first-person ruling chamber, with the map table as the dense strategic interface."
    state: "resolved"
    resolution: "Use the chamber as the presentation frame while keeping the simulation separable for a conventional prototype."
    decided_at: null
    evidence:
      - path: "docs/TOWNGAME_DESIGN.md"
        ref: "f63e24b9fafe0bd52788beaf3790bc90bae4d3c5"
        note: "Decision 002 is marked accepted."
  - id: "towngame-decision-003"
    title: "Action Points and routine management"
    context: "Decision 003 distinguishes major interventions from routine management during monthly planning."
    state: "resolved"
    resolution: "Begin a month with 1 non-carryover Action Point; routine management normally costs none."
    decided_at: null
    evidence:
      - path: "docs/TOWNGAME_DESIGN.md"
        ref: "f63e24b9fafe0bd52788beaf3790bc90bae4d3c5"
        note: "Decision 003 is marked accepted; further AP progression remains open."
  - id: "towngame-decision-004"
    title: "Aggregate population and specialist workforce"
    context: "Decision 004 accepts aggregate visible age groups and a shared labor pool, while exact balance remains open."
    state: "resolved"
    resolution: "Show children, working-age adults, and elderly groups, with hidden cohorts for realistic aging and specialists in the overall labor pool."
    decided_at: null
    evidence:
      - path: "docs/TOWNGAME_DESIGN.md"
        ref: "f63e24b9fafe0bd52788beaf3790bc90bae4d3c5"
        note: "Decision 004 is accepted at the system level."
  - id: "towngame-decision-005"
    title: "Layered strategic resources"
    context: "Decision 005 accepts a small early resource set and map-table forecasting; detailed balance and later resources remain open."
    state: "resolved"
    resolution: "Start with Food, Wood, Stone, and Coin; show predicted outcomes before committing a month."
    decided_at: null
    evidence:
      - path: "docs/TOWNGAME_DESIGN.md"
        ref: "f63e24b9fafe0bd52788beaf3790bc90bae4d3c5"
        note: "Decision 005 is accepted at the system level."
  - id: "towngame-decision-006"
    title: "Linear or near-linear Legacy Point conversion"
    context: "System 16 explicitly revises older Systems 10–11 diminishing conversion direction."
    state: "resolved"
    resolution: "Use linear or near-linear Score-to-Legacy-Point conversion; challenge and talent costs provide the longer progression curve."
    decided_at: null
    evidence:
      - path: "docs/DESIGN_INDEX.md"
        ref: "f63e24b9fafe0bd52788beaf3790bc90bae4d3c5"
        note: "Supersede log identifies the System 16 revision."
      - path: "docs/TOWNGAME_DESIGN.md"
        ref: "f63e24b9fafe0bd52788beaf3790bc90bae4d3c5"
        note: "Authoritative snapshot states the revised conversion direction."
  - id: "towngame-decision-007"
    title: "Inspector, forecast, and event handling principles"
    context: "System 19D is mostly settled at the principle level, with exact dimensions and thresholds left to prototype tuning."
    state: "resolved"
    resolution: "Use a persistent Attention Strip, contextual inspector, hybrid forecast, and reversible planning-phase event responses."
    decided_at: null
    evidence:
      - path: "docs/TOWNGAME_DESIGN.md"
        ref: "f63e24b9fafe0bd52788beaf3790bc90bae4d3c5"
        note: "Decision 019D records these mostly settled principles."
  - id: "towngame-decision-008"
    title: "Information transparency and commitment safety"
    context: "System 19B settles information access and month-commitment principles while leaving precise tooltip and warning tuning open."
    state: "resolved"
    resolution: "Explain known and estimated information contextually, forecast consequences before commitment, and keep the Lord's Seal non-blocking."
    decided_at: null
    evidence:
      - path: "docs/TOWNGAME_DESIGN.md"
        ref: "f63e24b9fafe0bd52788beaf3790bc90bae4d3c5"
        note: "Decision 019B is mostly settled at the principle level."
  - id: "towngame-decision-009"
    title: "Customizable guidance without information loss"
    context: "System 19C settles guidance and UI customization principles while leaving the detailed option catalogue and presentation for prototype work."
    state: "resolved"
    resolution: "Offer presets and granular controls while preserving access to strategically available information."
    decided_at: null
    evidence:
      - path: "docs/TOWNGAME_DESIGN.md"
        ref: "f63e24b9fafe0bd52788beaf3790bc90bae4d3c5"
        note: "Decision 019C is mostly settled at the principle level."
  - id: "towngame-decision-010"
    title: "Final collapse trigger"
    context: "The immediate Game Over rule at 100% Unrest was reopened after System 18; an imminent overthrow state is a direction to explore."
    state: "open"
    resolution: null
    decided_at: null
    evidence:
      - path: "docs/TOWNGAME_DESIGN.md"
        ref: "f63e24b9fafe0bd52788beaf3790bc90bae4d3c5"
        note: "System 07 marks the final trigger and recovery rules unresolved."
  - id: "towngame-decision-011"
    title: "Church–Lord control and legitimacy"
    context: "System 18 presents independent, controlled, and co-opted Church possibilities, but defers the political balance."
    state: "open"
    resolution: null
    decided_at: null
    evidence:
      - path: "docs/TOWNGAME_DESIGN.md"
        ref: "f63e24b9fafe0bd52788beaf3790bc90bae4d3c5"
        note: "System 18 explicitly needs revisit later."
  - id: "towngame-decision-012"
    title: "System 19A navigation domains"
    context: "The proposed top-level domains and monthly planning workflow are a working reference only."
    state: "open"
    resolution: null
    decided_at: null
    evidence:
      - path: "docs/TOWNGAME_DESIGN.md"
        ref: "f63e24b9fafe0bd52788beaf3790bc90bae4d3c5"
        note: "System 19A is explicitly proposed and not yet accepted."
---

# TownGame decisions

The front matter summarizes selected project-level choices. [The living design](../docs/TOWNGAME_DESIGN.md) retains the full reasoning, finer decisions, proposals, and superseding revisions; [the design index](../docs/DESIGN_INDEX.md) locates them. A resolved entry here means the design principle is documented, not implemented or playtested. Decision dates are unknown in the available records.

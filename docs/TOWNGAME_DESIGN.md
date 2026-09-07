# Towngame — Game Design

> Living design document. This file records accepted design decisions and important unresolved ideas.

## 1. Game Concept

A roguelite medieval settlement strategy/simulation game in which the player, acting as a Lord, grows and manages a town for as long and as successfully as possible.

The physical town develops automatically rather than through manual building placement. The player's role is to manage systems, allocate people and resources, make major governing decisions, respond to events, and survive escalating pressures.

Each run becomes progressively more difficult and is expected to end in eventual collapse. Performance during the run produces score, achievements, unlocks, and restrained meta-progression for future runs.

Random positive and negative conditions should make different runs play differently.

### Core design principles

- Strategic management rather than manual building placement.
- No real-time waiting requirement.
- The player should spend time making decisions rather than waiting for resources.
- Growth should create new advantages and new problems.
- Larger settlements should become increasingly difficult to govern.
- The town itself should visually communicate progression and deterioration.
- Roguelite progression should favor new possibilities and restrained bonuses rather than runaway permanent power.
- First-person presentation should add immersion without making routine management tedious.

## 2. Accepted Decisions

### Decision 001 — Time and Run Structure

**Status: Accepted**

Time advances in discrete **monthly turns**.

Each month consists of:
1. Current events, crises, and visitors are presented.
2. A planning phase.
3. The player performs routine management and may spend Action Points on major interventions.
4. The player advances the month.
5. The simulation resolves immediately.
6. Consequences are applied and the next month begins.

There is **no real-time waiting requirement**.

Months belong to seasons. Seasons apply environmental and systemic modifiers, but individual seasons are dynamically variable. Two winters should not necessarily behave identically.

Examples include temperature severity, rainfall or snowfall, agricultural productivity, heating demand, disease pressure, travel and trade conditions, and seasonal events.

Years provide the larger timescale for long-term escalation, progression, scoring, and major historical changes.

### Decision 002 — Player Role and Presentation Frame

**Status: Accepted**

The player is a **Lord** governing a growing medieval settlement. The title remains Lord throughout the run.

The game is experienced from inside the Lord's **ruling chamber**.

The player can freely move around the chamber in first person and interact with physical objects and NPCs representing game systems.

The central **map table** is the primary management interface and should contain the densest strategic gameplay.

Potential room interfaces include a treasury ledger or treasurer, council area, architect or planning desk, military advisor, scholar, messenger, windows or balcony, and petition area.

First-person movement must add atmosphere and context without becoming repetitive busywork. Routine management should remain quick to access.

The simulation and presentation layers should remain separable so the core game can first be prototyped using a conventional interface.

A run ultimately ends when the Lord **loses control of the settlement**. Severe unrest may culminate in revolt, the ruling seat being stormed, and the Lord being overthrown, killed, exiled, or otherwise removed from power.

### Decision 003 — Monthly Planning and Action Points

**Status: Accepted**

Each month normally begins with **1 Action Point (AP)**.

Action Points represent the Lord's limited ability to personally initiate significant interventions during that specific month.

Unused AP **does not carry over** between months.

Routine management normally does **not** consume AP and is performed primarily from the map table.

Major interventions normally consume AP and should generally be initiated through relevant interactable objects or NPCs around the ruling chamber.

AP is an extremely powerful resource. Permanent or reliable increases must be awarded very conservatively.

Possible sources of additional or reduced AP may eventually include temporary events, administrative buildings, employed administrative workers, resource-dependent bureaucracy, settlement-development decisions, rare run modifiers, and meta-progression.

Events and crises are presented **at the beginning of the planning phase**, before the player commits the month's decisions.

Normal event responses do not consume AP. Particularly powerful event responses may optionally or explicitly consume AP as a premium intervention.

Meta-progression may provide carefully limited AP benefits, preferably through infrequent bonuses such as additional AP in specific months or seasons before offering any general monthly increase.

## 3. Projects, Construction, and Development

Major projects do not complete instantly. Examples may include buildings, infrastructure, research, administrative reforms, military preparation, and expeditions.

Projects progress over multiple monthly turns.

### Direct worker allocation

Active projects are handled **individually**.

During planning, the player directly assigns available workers to each project. Worker allocation determines expected monthly progress.

Allocations may be freely changed before the month resolves.

Assigning **0 workers** effectively pauses a project.

Projects may have maximum effective workforce limits and/or diminishing returns so unlimited labor cannot make every project instantaneous.

### Worker specialization

Early workers may be relatively flexible.

Later, specialized worker types may become more efficient or may be required for certain work.

Possible examples include laborers, builders, carpenters, masons, engineers, scholars, clerks, and craftsmen.

Specialization should provide benefits while reducing flexibility and potentially creating vulnerability during crises.

### Project resource model

Current preferred model: **hybrid progressive consumption**.

A project requires:
1. an initial resource commitment to begin;
2. additional resources consumed progressively as work is completed.

Before advancing the month, the player should be able to see total project cost, resources already committed, expected resource use this month, expected progress this month, and expected combined consumption of all active projects.

### Resource shortages and project priority

Worker allocation determines desired project progress.

A separate priority system may determine which projects receive scarce materials when the settlement cannot supply all planned work.

Potential levels: High, Normal, Low.

The exact allocation algorithm is unresolved.

## 4. Important Design Ideas — Not Yet Accepted

### Administrative institutions

A staffed administrative building may generate additional AP while consuming significant resources and workers.

### Resource depth and settlement specialization

The economy may begin with simple resources and later introduce specialized goods such as Food, Wood, Stone, Coin, Iron, Tools, Cloth, Paper, Medicine, Weapons, and Luxury goods.

Different resource chains may allow settlements to develop different economic identities between runs.

Meta-progression may unlock new economic possibilities rather than only numerical bonuses.

### Research as a project system

Research may use the same general project structure as construction: assign scholars, consume monthly resources, generate progress, and complete after sufficient work.

### Town visual state

The city should visually communicate more than population size. Possible visual dimensions include prosperity, neglect, crowding, unrest, fire, abandonment, and seasonal conditions.

## 5. Open Questions

- Exact number and progression of Action Points beyond the base 1 AP/month.
- Exact AP meta-progression structure.
- Exact project resource-payment formula.
- Exact project workforce efficiency formula.
- Exact resource-priority allocation algorithm.
- Exact worker professions and specialization system.
- Complete resource list.
- Exact construction categories.
- Exact research system.
- Exact event system.
- Exact collapse mechanics and final scene.
- Exact ruling chamber layout.
- Exact town visual-stage system.

## 6. Decision 004 — Population and Workforce

**Status: Accepted at system level; exact numerical balance remains open.**

Population is represented through **aggregate population groups rather than individually simulated citizens**.

The player-facing demographic model uses three groups:

- Children
- Working-age adults
- Elderly

Working-age adults form the normal workforce. Children and elderly people are normally dependents, though later policies may allow a limited percentage of either group to work with reduced efficiency and meaningful drawbacks.

Population changes through:

- births;
- immigration;
- deaths;
- emigration.

Individual households and families are not simulated.

Social classes are intentionally postponed for a later system.

### Aging

The visible model remains limited to the three age groups, but the simulation should keep enough hidden age/cohort information to prevent unrealistic transitions.

A newborn child must not be able to become an adult immediately simply because an aggregate annual transition roll occurs.

Preferred approach:

- population is stored internally in age or birth cohorts;
- the UI still shows only the three broad groups;
- members must reach an eligible age/window before they can transition to the next visible group;
- transitions may then use annual probabilities, potentially with a forced maximum age to prevent implausible long-term outliers;
- natural mortality probabilities may differ by age group or hidden cohort.

Exact ages and transition percentages are unresolved.

### Workforce model

General and specialized workers remain part of the same overall labor pool.

**General workers** are flexible and should operate at normal efficiency in most ordinary jobs.

**Specialists** gain a substantial efficiency bonus in their trained profession but can still be reassigned to other ordinary work at reduced efficiency.

Provisional conceptual example only:

- General worker in ordinary work: 100%
- Matching specialist in specialty: approximately 200%
- Specialist outside specialty: approximately 50%

Exact percentages are not accepted balance values yet.

This allows specialists to remain useful during emergencies while making their proper employment highly valuable.

### Qualified professions

Some advanced systems may require at least one appropriately trained specialist to perform their core function effectively.

Examples may include:

- physicians;
- researchers/scholars;
- priests or clergy;
- engineers;
- other advanced professions added later.

The preferred model is not a universal hard lock. Instead, advanced workplaces may contain a **qualified core function plus assistive labor**.

Examples:

- an infirmary can employ general workers as attendants, but advanced medical treatment or epidemic control requires a physician;
- a research institution can employ assistants, but meaningful research output requires a scholar/researcher;
- a religious institution may accept general labor for maintenance while specialist clergy provide its unique social/religious effects.

This preserves the possibility of catastrophic specialist shortages without making every non-specialist completely useless.

Specialist training, retraining, and exact profession rules are unresolved.

### Child and elderly labor

Future policies may allow part of the child or elderly population to enter the workforce.

Such labor should generally be less efficient than normal adult labor and create tradeoffs such as:

- increased injury or mortality;
- reduced health;
- reduced education or future specialist potential for children;
- increased medical burden;
- legitimacy, unrest, or social consequences where appropriate.

Exact policies and penalties are unresolved.

## 7. Next Design System

### System 05 — Resources and Economy

Topics to resolve include:

- Which resources exist at the beginning of a run?
- Which resources appear only later?
- Which are stockpiled versus abstract capacities?
- How are food, wood, stone, coin, and specialized goods produced?
- How much production-chain complexity is desirable?
- How do shortages affect the town?
- How can different settlements specialize economically without creating mandatory build paths?

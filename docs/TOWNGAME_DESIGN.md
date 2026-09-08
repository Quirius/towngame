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


## 5. Decision 005 — Resources and Economy

**Status: Accepted at system level; exact balance and later resources remain open.**

The economy uses a **layered strategic resource model**. Early gameplay begins with a small core set:

- Food
- Wood
- Stone
- Coin

Additional resources may unlock later, such as Iron, Tools, Cloth, Paper, Medicine, Weapons, and Luxury Goods. Resources should only be added when they create meaningful strategic decisions. Production chains should generally remain short.

### Food
Food remains **one abstract resource** for now. Grain, meat, preserved food, luxury food, and similar categories are not separately tracked unless later design work gives a strong reason to split them.

### Economic abstraction
The player directly manages the settlement's strategically relevant stockpiles. A detailed private household economy is not simulated.

The presentation may imply that households and private producers conduct ordinary production and consumption in the background. The quantities visible to the player can therefore be understood as the **net stockpile available to the Lord and settlement administration after ordinary household activity**.

This preserves the feeling of a wider economy without making household commerce a management burden.

### Stockpiles and capacities
Physical goods are generally stored as quantities. Systems such as Housing, Administration, Medical capability, and Security should generally be represented as capacities or system values rather than generic resources.

### Map-table forecasting
A central UI principle is:

> **Show predicted outcomes before commitment.**

Before advancing the month, the map table should show expected production, consumption, project demand, upkeep, shortages, and other major predictable changes resulting from the current plan. Random events do not need to be forecast.

### Shortages
Shortages normally do not block the player from advancing the month. Instead they create consequences such as stalled projects, insufficient heating, reduced production, delayed repairs, declining health, unrest, or famine.

### Trade and specialization
Trade should allow towns to compensate for local weaknesses and support different economic identities. Imports should remain costly or vulnerable enough that local production still matters.

Starting conditions, geography, run modifiers, and development choices may encourage specializations such as farming, forestry, mining, metalworking, trade, or administration.

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


## Decision 006 — Buildings and Infrastructure

**Status: Accepted.**

Settlement development is divided into **organic development, functional buildings, and infrastructure**.

### Organic development

Ordinary homes and minor buildings develop automatically rather than being individually placed or commissioned. Housing is represented as settlement capacity.

Organic housing construction uses real settlement resources and labor in the background. The population effectively builds ordinary housing for itself when conditions permit. The player does not manually order individual houses.

During monthly planning, the map table should forecast the expected effect of this organic development, for example:

- Household construction: -28 Wood
- Household construction labor: 14 worker-equivalents
- Expected Housing: +14

Organic housing development may depend on population pressure, available materials, available labor, prosperity, infrastructure, policies, and other settlement conditions.

The Lord can influence housing indirectly through major actions and policies such as opening new residential land, subsidizing construction, or allowing denser development.

### Functional buildings

Functional buildings are deliberately commissioned projects. Individual functional buildings are tracked separately, may employ workers directly, consume resources and upkeep, and provide specific production or systemic functions.

Completed buildings normally begin unstaffed. The player assigns workers through the map table.

Buildings have practical workforce limits. General and specialized workers contribute according to their effective productivity.

Buildings may have a small number of meaningful upgrades, but endless numerical levels are avoided. Some buildings may instead be constructed multiple times, while major institutions may be unique.

### Infrastructure

Infrastructure such as roads, sanitation, water systems, walls, drainage, and similar town-wide networks is represented through settlement-wide developmental stages rather than manually placed segments.

Infrastructure stages should preferably use thematic names rather than generic numerical levels.

Infrastructure has capacity relative to settlement size. Population growth can outpace existing infrastructure, creating increasing penalties and pressure.

### Maintenance and damage

Important buildings and infrastructure require ongoing maintenance. Maintenance is part of the predicted monthly economy and should not require repetitive manual repair commands under normal conditions.

If upkeep cannot be supplied, condition gradually deteriorates and system performance worsens. Events may damage specific buildings, infrastructure, or organic housing capacity.

### Visual town development

The visible town should reflect its functional development, infrastructure, prosperity, condition, and population rather than population alone. Two settlements with similar population may therefore look substantially different.

### Design rule

> **Organic growth represents what the population builds for itself. Functional buildings represent deliberate institutions. Infrastructure represents settlement-wide systems the Lord must keep ahead of population growth.**

## 7. Next Design System

### System 07 — Needs, Stability, and Pressure

Topics to resolve:
- Which town needs matter continuously?
- Which values are direct resources versus derived conditions?
- How do food security, housing pressure, health, sanitation, safety, and legitimacy interact?
- Should happiness and unrest be separate systems?
- How do neglected problems escalate rather than immediately cause collapse?
- Which pressures scale naturally with population and town age?
- How do multiple weak systems combine into crises and eventual death spirals?


## Decision 007 — Unrest, Legitimacy, and Collapse Pressure

**Status: Accepted at system level; exact formulas and advanced endgame crisis mechanics remain open.**

### Unrest

**Unrest is the primary value indicating how close the settlement is to political collapse.**

Unrest is not a resource and should not be directly improved by talents, meta-progression, or permanent bonuses. It must always be **derived from other systems and conditions**.

Potential contributors include:

- food insecurity;
- housing shortages;
- disease;
- poor sanitation;
- high taxation;
- crime;
- unemployment or underemployment;
- infrastructure failure;
- prolonged hardship;
- unpopular decisions;
- failed events;
- unmet expectations;
- losses of legitimacy;
- other systemic pressures.

Unrest has **lagging inertia**. Fixing the immediate cause of anger should not instantly erase accumulated political pressure.

A town at 98% Unrest may remain in severe danger even after a major problem is solved. Recovery should take time, and at sufficiently high levels it may be practically impossible to reverse collapse before the next major shock.

### Initial defeat rule

For the first playable implementation:

> **Unrest reaching 100% ends the run immediately.**

At 100% Unrest, the mob storms the ruling seat, the guards abandon or turn against the Lord, and the Lord loses control of the settlement.

There is no recovery after the threshold has been reached in the initial version.

### Later endgame refinement

A future version may replace the instant threshold with a terminal political-crisis sequence.

Possible escalation:

- Dissatisfied
- Agitated
- Protests
- Riots
- Revolt
- Final uprising

A late-game uprising may create a brief opportunity to regain control, but survival should only delay the underlying danger rather than permanently remove it. Eventually a sufficiently strained settlement should collapse.

This advanced crisis system should be treated as a later refinement rather than a requirement for the first prototype.

### Legitimacy

**Legitimacy** is a separate long-term political value representing how willing the population is to accept the Lord's rule.

Unrest describes immediate anger and pressure.

Legitimacy describes the regime's accumulated political credibility.

The two values interact.

A highly legitimate Lord may withstand substantial hardship before unrest becomes revolutionary, while a Lord with weak legitimacy may face severe political danger from comparatively smaller crises.

Legitimacy may be affected by:

- past decisions;
- successful crisis management;
- broken promises;
- coercive measures;
- fair or unfair policies;
- prosperity;
- major achievements;
- event outcomes.

Exact formulas are unresolved.

### Political state

A separate numeric Stability resource is not used.

Instead, **Political State / Stability** is a derived descriptive state based primarily on Unrest, Legitimacy, and potentially other political conditions.

Examples:

- Stable
- Strained
- Unstable
- Volatile
- Near Collapse

### Cascading failure

Settlement problems should interact and create cascading failures rather than operate as isolated penalties.

Example chain:

Housing shortage
→ overcrowding
→ sanitation strain
→ disease
→ worker loss
→ lower production
→ food shortage
→ unrest
→ emigration
→ lower tax income
→ maintenance failure
→ infrastructure deterioration
→ further unrest

Collapse should often emerge from these interconnected systems.

### Growth and expectations

Population growth alone must not be the only source of pressure.

A player should not be encouraged to keep population artificially low while endlessly improving infrastructure in order to create a permanently stable town.

As the settlement becomes more advanced, **expectations and systemic requirements should rise as well**.

Potential drivers include:

- population;
- settlement age;
- prosperity;
- technological development;
- infrastructure level;
- unlocked institutions;
- social complexity;
- previous standards of living;
- historical milestones;
- run-specific difficulty modifiers.

A primitive village may tolerate conditions that an established town will no longer accept.

This means advancement itself creates new obligations.

### Difficulty escalation

The game requires an additional long-term escalation system beyond normal population pressure.

Its purpose is to ensure that even an exceptionally well-managed town faces increasingly difficult conditions and cannot survive forever by simply remaining small or overdeveloped.

This escalation should preferably operate through believable systems rather than arbitrary hidden penalties.

Possible mechanisms to explore later include:

- rising citizen expectations;
- increasingly severe weather variation;
- disease evolution;
- regional scarcity;
- trade disruption;
- administrative complexity;
- political faction pressure;
- aging infrastructure;
- reduced tolerance for poor conditions;
- increasingly difficult event pools;
- run-wide pressure that rises with time and development.

The exact model will be designed separately.

### War

War and external military defeat are preserved as a future expansion idea.

A lost war could eventually end a run through occupation, destruction of the settlement, or execution of the Lord.

Military systems are **not part of the initial core design** and may be better suited to a later major expansion or DLC-style system.


## Next Design System

### System 08 — Difficulty Escalation and Expectations

Topics to resolve:

- What guarantees that every run eventually becomes unsustainable?
- How much difficulty should come from time versus population versus development?
- How should citizen expectations rise?
- Should there be a visible global pressure level?
- How should event severity evolve?
- Can a highly developed but low-population settlement still face increasing pressure?
- How predictable should future difficulty be?
- Which escalation mechanics feel systemic rather than arbitrary?

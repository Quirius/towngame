# Towngame — Game Design


> **AUTHORITATIVE CURRENT SNAPSHOT — through System 19**
>
> This file supersedes earlier Towngame rolling design snapshots.
> When older sections conflict with a later explicitly marked revision, the later revision wins.
>
> Current design status:
>
> | System | Topic | Status |
> |---|---|---|
> | 01 | Time & Run Structure | Mostly settled |
> | 02 | Player Role & Presentation | Mostly settled |
> | 03 | Player Actions / AP / Projects | Mostly settled |
> | 04 | Population & Workforce | Mostly settled |
> | 05 | Resources & Economy | Mostly settled |
> | 06 | Buildings & Infrastructure | Mostly settled |
> | 07 | Unrest, Legitimacy & Collapse | **Needs revisit — final collapse trigger reopened** |
> | 08 | Expectations, Difficulty & World Pressure | Mostly settled |
> | 09 | Events, Crises & Event Memory | Mostly settled |
> | 10 | Scoring, Milestones & Run Rewards | Mostly settled |
> | 11 | Meta Progression | Mostly settled |
> | 12 | Specialization & Run Identity | Mostly settled |
> | 13 | Policies, Laws & Ongoing Management | Mostly settled |
> | 14 | Research, Knowledge & Technology | Mostly settled |
> | 15 | Trade, External Economy & Regional World | Mostly settled |
> | 16 | Ambitions, Difficulty & Run Setup | Mostly settled |
> | 17 | Starting Geography, Regions & Settlement Conditions | Mostly settled |
> | 18 | Religion, Social Institutions & Cultural Life | **Needs revisit later** |
> | 19 | Map Table, UI & Information Architecture | **Currently designing** |
>
> **Important superseding revisions**
>
> - System 07: the old prototype rule `100% Unrest = immediate Game Over on month resolution` is **reopened**. The current direction is to explore an imminent/probabilistic overthrow state that may interrupt the following planning phase.
> - System 16 supersedes the older Systems 10–11 LP-conversion direction: **Score → Legacy Points is now linear or near-linear**, while escalating challenge and increasingly expensive Legacy talents provide the long-term progression curve.
> - Full permanent meta progression is provisionally aimed at roughly **30–50 runs**, subject to actual run length and playtesting.


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

### Final collapse trigger — reopened after System 18

The earlier prototype rule that **100% Unrest immediately ends the run on month resolution is no longer locked**.

Current direction to explore:

- very high or 100% Unrest may place the settlement into an **imminent overthrow** state rather than resolving Game Over instantly;
- the player may begin the next planning phase while the run is already in terminal danger;
- a breach, revolt, guard defection, or palace assault may interrupt the player while they are making decisions;
- music, visual effects, NPC behavior, and chamber events can communicate that collapse is unfolding;
- the exact threshold, probability, warning fairness, timing, and possibility of recovery remain unresolved.

The core rule still stands: **Unrest is the main measure of collapse risk, and Legitimacy remains a separate long-term political variable.**

This point belongs in **Needs Revisit** and must be resolved before final collapse implementation.

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


## Decision 008 — Difficulty Escalation and Expectations

**Status: Accepted at system level; exact formulas and tier thresholds remain open.**

Every run contains three major sources of escalating difficulty:

1. **Time Pressure**
2. **Scale Pressure**
3. **Expectation Pressure**

These systems work together to ensure that no settlement can remain permanently safe simply by keeping population low or overbuilding infrastructure.

### Time Pressure

An irreversible world-pressure system increases as the settlement ages.

World Pressure does not directly add Unrest or universally reduce production. Instead, it changes what the world can throw at the player by increasing event severity, event complexity, overlapping crises, persistent regional problems, environmental volatility, trade disruption, disease pressure, and other external threats.

Broad future danger should be forecastable even though exact events remain uncertain.

### Scale Pressure

Population creates direct systemic demand.

Peak population may also influence certain long-term pressures so that a settlement that once supported a large population does not instantly become equivalent to a historically tiny village after population loss.

### Expectation Pressure

Citizen expectations rise with settlement development, prosperity, historical standards, population scale, and time.

Expectations are partly historical and should not immediately fall when the settlement loses infrastructure or prosperity.

Importantly, expectations may also run **slightly ahead of actual development**.

A growing town may begin expecting the effects of infrastructure before that infrastructure already exists. For example, water-access expectations may increase before an aqueduct is built, creating a proactive incentive to construct it rather than merely reacting after a hard requirement is exceeded.

This makes infrastructure useful for staying ahead of rising standards rather than merely crossing off requirements.

### Dynamic Challenge Tiers

The game uses descriptive **Challenge Tiers** to communicate overall run danger.

Example conceptual tiers:

- Frontier
- Established
- Strained
- Crisis Age
- Terminal

These names are provisional.

Challenge Tiers must be **dynamic rather than permanent fixed end stages**. The game is intended to support stronger future runs through meta-progression, so later runs should not spend most of their duration stuck in the same final tier.

Tier thresholds may shift with meta-progression, difficulty, run modifiers, or future progression systems. New higher tiers may eventually become reachable, and event pools may continue scaling beyond the prototype's original endgame.

### Tiered and Compound Events

Events are drawn from tiered pools.

Higher tiers unlock more dangerous events and combinations while lower-tier events may remain possible.

Late-game difficulty should increasingly come from multiple simultaneous pressures competing for limited labor, resources, specialists, and Action Points.

Persistent crises may last multiple months so late-game difficulty does not require constant popup spam.

### Meta-progression and World Pressure

Meta-progression should not simply reduce World Pressure by a permanent percentage.

However, **discrete delays to escalation are acceptable and potentially desirable**.

Examples:

- World Pressure begins increasing one season later.
- A tier threshold is delayed by one season.
- The first annual World Pressure increase occurs one year later.
- A specific escalation milestone is postponed.

This differs from a permanent multiplier such as `World Pressure growth -20%`.

A fixed delay gives the player more development time while preserving the long-term shape and inevitability of escalation. Such bonuses must still be balanced carefully because extra safe time compounds into significant economic advantage.

Meta-progression may also improve the player's ability to cope with pressure through stronger systems, new buildings, specialists, starting options, or rare AP improvements.

### Anti-stagnation principle

The player should not be able to survive indefinitely by freezing population growth, remaining deliberately primitive, overbuilding infrastructure, or lowering development to reset expectations.

### Design rule

> **Unrest measures collapse risk. World Pressure and Expectations create the conditions that make collapse increasingly likely.**

These systems remain conceptually separate.


## Next Design System

### System 09 — Events and Persistent Crises

Topics to resolve:

- How are monthly events selected?
- How many events can occur at once?
- Which events are one-off decisions versus multi-month conditions?
- How do event tiers interact with World Pressure and Challenge Tier?
- How are event choices presented through NPC visitors?
- Which event responses cost resources, legitimacy, workers, or Action Points?
- How much randomness should be visible in advance?
- How should compound crises form without feeling unfair?


## Decision 009 — Events and Persistent Crises

**Status: Accepted at system level; exact event tables, probabilities, and outcome-randomness rules remain open.**

Events are a core source of unpredictability, narrative, and pressure. They should emerge from the state of the settlement and the current Challenge Tier rather than behave as isolated random popups.

### Event timing

Events are generated and presented **at the beginning of the monthly planning phase**.

This allows the player to understand the month's immediate problems before allocating workers, changing policies, assigning resources, or spending Action Points.

Events should generally not appear after the player has already committed the month unless they are explicitly designed as consequences of the resolved simulation.

### Event presentation

Events should normally be represented diegetically through the ruling chamber.

Possible presentation methods include:

- messengers arriving near the chamber entrance;
- peasants or townspeople requesting aid;
- merchants;
- priests;
- guards;
- physicians;
- craftsmen;
- advisors;
- representatives of groups or institutions.

The event interface may appear when the player interacts with the arriving NPC.

The physical NPC is presentation. The underlying event system must remain independent of first-person movement so events can be tested and prototyped through conventional UI.

### Event categories

Events should be divided into several broad types.

#### Immediate events

Resolved through a decision during the current planning phase.

Examples:

- merchant dispute;
- minor fire;
- theft;
- local petition;
- injured workers;
- unexpected visitors.

These usually resolve immediately after the player chooses an option.

#### Persistent crises

Conditions that remain active for multiple months.

Examples:

- epidemic;
- drought;
- regional grain shortage;
- trade-route disruption;
- prolonged severe winter;
- crime wave;
- infrastructure failure.

Persistent crises modify the simulation each month until they expire, are resolved, or worsen.

#### Escalating crises

Persistent conditions that may develop through stages.

Example:

Local sickness
→ spreading outbreak
→ epidemic
→ severe epidemic

Player decisions and settlement preparation can influence whether the crisis improves or escalates.

#### Opportunity events

Not every event should be negative.

Examples:

- talented specialist arrives;
- merchant caravan offers favorable trade;
- unusually good harvest;
- refugee group offers valuable skills;
- temporary political support;
- discovery of useful resources.

Positive events should still create decisions rather than function only as free rewards.

### Event choices and costs

Normal event choices should not automatically consume Action Points.

Possible costs may include:

- Coin;
- resources;
- workers;
- specialists;
- Legitimacy;
- temporary production;
- long-term consequences;
- accepting risk;
- changing policy;
- refusing assistance.

Particularly powerful responses may spend Action Points as a premium option.

Events may also temporarily increase or reduce Action Point availability.

### Event generation

Events should be influenced by current settlement state.

Examples:

- poor sanitation increases disease-event weight;
- wood-heavy construction increases fire-related vulnerability;
- weak food reserves increase famine-related event severity;
- high trade dependence increases exposure to trade disruption;
- low Legitimacy increases political-event danger;
- poor infrastructure increases failure-event probability.

This makes events feel like consequences of the player's settlement rather than completely arbitrary punishment.

Purely external events may still occur, especially at higher World Pressure.

### Tiered event pools

Challenge Tier influences event availability and severity.

Higher tiers may:

- unlock more severe events;
- unlock longer persistent crises;
- increase the probability of escalation;
- allow multiple related crises to overlap;
- unlock compound events.

Lower-tier events may remain possible at high tiers.

Challenge Tier should shift with meta-progression according to Decision 008.

### Event frequency

The game should avoid overwhelming the player with too many separate event popups.

A useful target is for notable events to remain meaningful rather than becoming routine clutter.

Higher difficulty should increasingly come from:

- persistent conditions;
- overlapping pressures;
- escalating consequences;

rather than simply increasing the number of NPCs arriving every month.

Exact event frequency is unresolved.

### Compound crises

Late-game danger should increasingly come from interactions between active systems.

Examples:

Severe winter
+ regional grain shortage
+ damaged granary
→ famine risk

Epidemic
+ physician shortage
+ overcrowding
→ catastrophic mortality

Trade disruption
+ paper shortage
+ administrative bureaucracy
→ loss of governing capacity

Compound crises should normally arise from combinations of individually understandable conditions rather than opaque scripted punishment.

### Forecasting and fairness

The game should give the player enough information to prepare for broad categories of risk without revealing exact future events.

Possible forecasts include:

- severe winter expected;
- disease pressure high;
- trade instability rising;
- drought risk elevated.

Some events may have visible warning stages.

Examples:

Minor sickness
→ outbreak risk

Low rainfall
→ drought risk

Public complaints
→ protest risk

This creates strategic preparation while preserving uncertainty.

### Persistent crisis interaction

Persistent crises should appear as active conditions on the map-table interface.

For each active crisis, the player should be able to see:

- current effect;
- estimated or possible duration;
- escalation risk where appropriate;
- known mitigation methods;
- relevant assigned resources or workers.

Not every duration must be exactly predictable.

### Failure and recovery

Events should not normally create unavoidable instant defeat from a healthy settlement.

Severe events may be devastating, especially at high Challenge Tiers, but the player should usually be able to identify why the settlement was vulnerable.

At very high World Pressure, compound crises may become effectively impossible to manage, fulfilling the eventual-collapse goal.

### Event memory

Major event outcomes may leave lasting consequences.

Examples:

- surviving an epidemic changes Legitimacy;
- seizing merchant goods affects future trade;
- refusing refugees affects future population or political events;
- rebuilding after a major fire may unlock or create modifiers.

This allows individual runs to develop their own history.

Exact memory duration and event-chain systems are unresolved.

### Meta-progression and events

Meta-progression may influence events by:

- delaying specific Challenge Tier milestones;
- unlocking new positive or neutral events;
- providing new response options;
- unlocking institutions that mitigate event categories;
- improving preparation tools.

Meta-progression should generally not make broad event categories permanently harmless.



## Next Design System

### System 10 — Population Goals, Scoring, and Run Objectives

Topics to resolve:

- What is the player's explicit objective during a run?
- Are population milestones the main goals or one of several goal types?
- How are milestone rewards delivered during the run?
- How is final score calculated?
- Should survival time, peak population, prosperity, crisis survival, and difficulty all contribute?
- Which achievements grant immediate run rewards versus meta-progression rewards?
- How do objectives encourage growth without rewarding reckless population rushing?
- Should runs contain optional secondary goals?


### Event frequency and pacing

The default pacing target is approximately **one notable new event per season on average**.

This is not a fixed schedule. Event frequency may change due to Challenge Tier, World Pressure, settlement vulnerabilities, active crises, run modifiers, and specific event chains.

Difficulty should not primarily increase by spawning more and more separate events. Persistent crises, escalating conditions, and compound systemic pressure should carry much of the late-game difficulty.

### Event-driven death spirals

Because event weights respond to settlement conditions, the event system must be carefully balanced to avoid unfair positive feedback loops.

A weakened settlement may legitimately become more vulnerable to related events, but poor conditions should not automatically cause repeated punishment with no realistic chance to recover.

Useful safeguards may include diminishing repeated-event weighting, temporary cooldowns, active-crisis awareness, event-pressure budgeting, limits on redundant crisis categories, and warning states before severe escalation where appropriate.

The objective is to create understandable cascading failure, not arbitrary event spam.

### Event Pressure Budget

An invisible **Event Pressure Budget** is the preferred balancing model.

Challenge Tier, World Pressure, current settlement state, active crises, and other modifiers determine how much event pressure is available.

The event system then spends that pressure on suitable events or crisis escalation.

A high-pressure period may therefore produce one severe crisis, several smaller related problems, escalation of an existing crisis, or a compound event.

### Messenger and interaction rules

A new event may be introduced by a relevant NPC arriving near the ruling-chamber entrance.

The messenger is generally **one-off**.

If the event becomes persistent, its ongoing management moves primarily to the map table, relevant AP-spending stations, and relevant advisors or specialists.

The messenger may return when the event escalates, a major new decision becomes available, the crisis changes state, or the event concludes in a significant way.

Not every event response must be completed inside the initial dialogue. Most events should connect back into normal management systems.

### Action Points as premium event responses

Within events, Action Points act as a **premium intervention resource**.

Ordinary responses generally use normal resources, policies, workers, risk acceptance, or Legitimacy.

Spending AP may often solve the problem outright, prevent escalation, unlock the strongest outcome, greatly reduce losses, or create a special long-term benefit.

AP should not be mandatory for every serious event, but it should frequently represent the Lord personally devoting exceptional governing attention to the problem.

### Information transparency

Known consequences should normally be shown numerically.

The interface may later simplify or summarize values if excessive detail harms readability, but the simulation should retain explicit underlying numbers.

Uncertain outcomes should be clearly identified as uncertain.

### Event outcome randomness

The current preferred direction is **mostly deterministic event resolution**.

When the player chooses an option, the outcome should usually follow predictably from the chosen response, resources committed, workers or specialists assigned, relevant town conditions, and current modifiers.

Randomness should primarily determine which events occur, when they occur, external conditions, and crisis severity or starting state.

Some individual events may still use probabilistic outcomes where uncertainty is itself thematically or strategically valuable.

The exact boundary between deterministic and probabilistic event resolution remains open for later refinement.



## Decision 010 — Run Objectives, Milestones, Scoring, and Meta Rewards

**Status: Accepted at system level; exact formulas, reward values, and milestone thresholds remain open.**

### Primary run objective

The central objective of a run is:

> **Build and sustain the greatest settlement possible under increasingly difficult conditions before inevitable collapse.**

Population milestones remain the clearest headline objectives during a run, but the final measure of success is broader than population alone. Pure survival time is not the primary objective and should not be heavily rewarded by itself.

### Population milestones

Population milestones provide **immediate run-specific rewards**.

These rewards may steer the settlement toward different strategies or specializations later in the same run.

Possible reward categories include temporary production bonuses, new policies, specialist access, infrastructure acceleration, Legitimacy gains, special project options, economic specialization choices, and run-specific modifiers.

Population milestones may also permanently unlock new gameplay systems, buildings, statistics and records features, map-table functionality, event-interface conveniences, progression screens, credits or presentation features, and later Challenge Tier content.

Some interface or meta features may intentionally be hidden behind early milestones so the game itself unfolds as the player progresses.

### Monthly score accumulation

Score is primarily accumulated **every month**.

The guiding principle is:

> **How much civilization did you sustain, under how much pressure, and for how long?**

Monthly score should therefore depend on settlement scale and development, multiplied by externally imposed difficulty.

Conceptually:

- larger and more developed settlements produce more score;
- surviving in harder Challenge Tiers produces more score;
- sustaining a difficult settlement for multiple months produces more score than briefly touching a high milestone and immediately collapsing.

Exact formulas remain open.

### Anti-exploit scoring rule

The scoring system must not reward the player for intentionally creating bad internal conditions.

Self-inflicted problems such as food shortages, high Unrest, disease caused by neglect, housing collapse, or deliberately broken infrastructure must not directly increase the difficulty multiplier.

Difficulty-related score should be based primarily on **external or progression-based pressure**, such as Challenge Tier, World Pressure, active event severity, run modifiers, milestone difficulty, and other non-player-created challenge factors.

Good management should allow the player to earn more score by surviving difficult circumstances, not by manufacturing misery.

### Crisis scoring

Events and crises may grant score according to difficulty when successfully survived or resolved.

Crisis score should scale with event tier, severity, duration, escalation stage, and compound conditions where appropriate.

Event memory should help prevent farming identical easy crises.

Repeated versions of the same event may give reduced score, evolve into more severe forms, create greater Unrest or political consequences, reference earlier outcomes, or become part of longer story arcs.

### Ambitions

Optional run-specific goals are called **Ambitions**.

Ambitions encourage different strategic approaches and may include economic, demographic, infrastructure, specialist, or survival-related goals.

Ambitions should generally reward **Legacy Points** and may contribute to achievements or larger unlocks.

Completing all Ambitions in a set, category, or run may grant achievements, special unlocks, new content, cosmetic rewards, or larger meta-progression milestones.

### Score versus Legacy Points

**Score** measures the success of the current run.

**Legacy Points** are the most abundant repeatable meta-progression currency.

Legacy Points may be earned primarily from final score, Ambitions, selected thresholds, and significant accomplishments.

The exact conversion from score to Legacy Points is unresolved and should be tuned to discourage trivial farming.


### Legacy Point score conversion — revised by System 16

The earlier diminishing-conversion proposal is superseded.

Current direction: final Score converts to Legacy Points **linearly or near-linearly**.

The long-term progression sink should come primarily from:

- increasingly expensive Legacy talent ranks and keystones;
- increasing challenge needed to produce higher scores efficiently;
- difficulty multipliers;
- Ambition rewards and Challenge Bonuses;
- achievement and milestone gates.

Higher difficulty and deeper dynamic Challenge Tiers may both increase score/reward efficiency. Exact formulas remain open.

### Legacy talent progression

Legacy Points purchase relatively small, permanent cross-run bonuses.

Examples may include:

- +1% Wood production;
- +1% Food production;
- small construction efficiency bonuses;
- specialist training improvements;
- +1 AP in a specific month, such as March;
- delayed Challenge Tier or World Pressure milestones;
- other carefully bounded bonuses.

The cost of repeated or stronger talents should rise sharply, potentially close to exponentially, so progressively deeper optimization requires substantially more successful runs.

Extremely powerful bonuses such as additional Action Points require much stricter pricing than ordinary percentage improvements.

### Major unlocks

Large gameplay features should generally **not** be purchased simply by accumulating enough Legacy Points.

Instead, first-time milestones, achievements, records, Challenge Tier breakthroughs, and other meaningful accomplishments unlock major content.

This creates two distinct forms of meta progression:

1. **Legacy Points** provide frequent, granular permanent improvement.
2. **Achievements and first-time accomplishments** unlock broader gameplay possibilities.

### Personal records and statistics

The game should maintain a persistent statistics and records page.

Potential records include highest peak population, highest final score, highest Challenge Tier reached, longest successful maintenance of a major population threshold, largest monthly production values, most severe crisis survived, Ambitions completed, total runs, total population governed, and other notable run statistics.

### Survival as a goal

"Survive as long as possible" is not the primary normal-run objective.

Early in the player's experience, simple survival may naturally feel like the immediate goal.

Later, Ambitions, specialization, score optimization, milestone hunting, and Challenge Tier progression provide more specific objectives.

Only in the extreme endgame, once most other progression is exhausted, may maximum survival time become a meaningful ultimate challenge.



## Next Design System

### System 11 — Meta Progression Structure

Topics to resolve:

- How is the Legacy talent tree organized?
- Are talents linear, branching, seasonal, or category-based?
- How steeply should talent costs scale?
- Which bonuses are safe as repeatable percentage upgrades?
- Which bonuses must be capped?
- How are month-specific AP talents structured?
- How are milestone-delay upgrades represented?
- Which progression is purchased with Legacy Points versus unlocked through achievements?
- Should players be able to respec Legacy talents?
- How much permanent power should a fully progressed player have compared with a new player?



## System 11 — Meta Progression Structure

**Status: Accepted. See Decision 011 below for the authoritative structure.**

Topics to resolve:

- overall structure of the Legacy talent system;
- categories of permanent bonuses;
- caps and diminishing returns;
- month-specific Action Point talents;
- Challenge Tier and World Pressure delay talents;
- specialization-related meta unlocks;
- achievement-gated content;
- whether talents are freely selectable or branch-gated;
- respec rules;
- expected power difference between a new profile and a heavily progressed profile.


## Decision 011 — Meta Progression Structure

**Status: Accepted at system level; exact talent list, costs, caps, and pacing remain open.**

### Overall structure
Legacy progression uses an **open constellation with investment gates** rather than a rigid linear skill tree.

Talents are grouped into broad thematic domains, provisionally:
- Production
- Development
- Population
- Administration
- Preparedness
- Experience / Challenge

Within each domain, basic talents are relatively freely selectable. Deeper talents unlock after sufficient Legacy Point investment in that domain. Powerful nodes may additionally require achievements, milestones, or prior experience with the relevant system.

### Investment gates
Progression depth is controlled mainly through total investment thresholds rather than strict prerequisite chains.

### Cross-domain talents
A limited number of talents may sit between two domains and require investment in both. These should remain relatively rare and visually clear.

### Talent density and compaction
Most permanent bonuses should use **ranked talents** rather than separate nodes for every small increase. As new talents are designed, overlapping or overly narrow nodes should be merged where possible.

### Talent classes
Talents use three broad classes:

1. **Ranked incremental talents** — small repeatable bonuses with hard caps and rising costs.
2. **Single-rank utility talents** — one-time permanent conveniences or narrow systemic benefits.
3. **Keystone talents** — expensive, powerful, often achievement-gated upgrades such as month-specific AP bonuses or delayed escalation milestones.

### Permanent commitment
Normal positive Legacy Talents are **permanent once purchased**.

They cannot be refunded or respecced during ordinary play. A full hard reset may eventually exist as a separate save-level action, but ordinary progression is intentionally committed.

### Variant or tradeoff talents
Future talents that deliberately provide both advantages and disadvantages may be freely changed between runs because their purpose is to alter playstyle rather than provide unconditional power.

Likewise, if a future mutually-exclusive specialization system needs refundable positive choices, only those specific talents may be changed before the next run begins.

These are exceptions; the default rule is permanent commitment.

### No Legacy loadout system
There is currently **no talent activation capacity or loadout limit**.

Purchased permanent talents remain active in every future run.

The player is expected to eventually purchase every ordinary Legacy Talent and unlock every major feature.

### Completion pacing
Talent quantity, rank caps, rising costs, difficulty multipliers, Ambition rewards, achievement gates, and later unlock layers should be tuned so that full completion represents a substantial long-term goal.

The intended casual-player time to 100% progression remains open.

### Action Point progression
Month-specific AP bonuses remain expensive Administration keystones.

Each calendar month may initially have one permanent AP talent, such as `+1 AP every March`.

A second tier of month-specific AP bonuses may exist only in much deeper progression if balance permits.

A general permanent `+1 AP every month` should not be an early or ordinary talent.

### Difficulty-delay progression
Meta progression may delay **specific** World Pressure or Challenge Tier milestones rather than applying generic percentage reductions.

Many such talents should require the player to first encounter, reach, or survive the relevant threat.

### Legacy Point economy — revised by System 16
Final Score converts into Legacy Points **linearly or near-linearly**.

Difficulty settings, Challenge Bonuses, and Ambitions may increase reward efficiency. Increasingly expensive permanent talents provide the main long-term sink.

### Major unlocks remain separate
Legacy Points buy incremental permanent power.

Major gameplay systems and broader content are unlocked primarily through first-time milestones, achievements, records, Challenge Tier breakthroughs, Ambitions, and other meaningful accomplishments.

### Meta-progression design principle
> **Legacy progression is permanent accumulation, not a pre-run build system.**

The player gradually becomes stronger across every run until the full progression system is eventually completed.
# Later Design Systems

## Decision 012 — Specialization & Run Identity

**Status: Mostly settled; exact thresholds, content, hybrid options, and visual implementation remain open.**

Specialization should emerge from how the settlement is actually developed rather than being chosen as a rigid class at run start.

Inputs may include:

- workforce allocation;
- functional buildings and infrastructure;
- economic production;
- geography and resource potential;
- milestone choices;
- Ambitions;
- research;
- event history;
- long-term policy and investment.

### Primary Specialization

The first specialization affinity to cross a major recognition threshold becomes the settlement's **Primary Specialization** for that run.

Before the threshold locks, the game must clearly warn the player that a specialization is close to becoming Primary so accidental lock-in is avoidable.

The Primary Specialization may reach several tiers within the same run and can drive:

- achievements;
- run records;
- milestone weighting;
- unique content;
- meta-progression qualification;
- special institutions;
- visual identity.

### Secondary affinities

Other affinities continue to exist after the Primary Specialization locks.

They may influence:

- events;
- milestone rewards;
- hybrid opportunities;
- statistics;
- town visuals;
- available projects or research.

Hybrid development should produce interesting hybrid rewards/options **without endlessly multiplying official specialization classes**.

### Milestones and identity

Use two conceptual levels:

- many **minor milestones** providing tactical run rewards;
- a smaller number of **major milestones** capable of strongly defining settlement identity.

Limited rerolls may exist, primarily for minor milestone choices, and Legacy progression may expand reroll access.

### Downsides

Specialization should generally create disadvantages through **opportunity cost and natural vulnerability**, not mandatory paired penalties.

A mining settlement, for example, may become dependent on imported Food because labor and infrastructure are concentrated elsewhere rather than because the specialization button directly applies `Food -20%`.

### Initial Primary Specializations

Initial planned identities:

- Agricultural
- Trading-Crafting
- Mining
- Scholar-University
- Religious Centre

Religion remains present in ordinary settlements even when Religious Centre is not the Primary Specialization.

### Visual implication

A finite library of fully static town images is no longer suitable as the long-term presentation solution. Specialization, prosperity, infrastructure, season, damage, and population combinations require a modular/composable town visualization system.

---

## Decision 013 — Policies, Laws & Ongoing Management

**Status: Mostly settled; exact stances, formulas, reform catalogue, and timings remain open.**

### Routine policies

Routine policies are free management actions.

Most should be adjustable on a **seasonal cadence** rather than inviting monthly micromanagement.

Use readable **discrete stances**, not precision sliders.

Core policy families include:

- taxation;
- food and rationing;
- immigration;
- labor;
- public order;
- welfare / charity;
- religion.

### Policy history and transition shock

Consequences depend on both:

1. the current policy stance;
2. how quickly the settlement was moved toward that stance.

Rapid changes create additional transition shock, political pressure, and Unrest-generating conditions.

Example principle:

> Moving taxation from minimum to maximum in one year should be more destabilizing than reaching the same tax burden gradually over three years, even though the eventual high-tax stance is still burdensome.

Historical expectations matter.

Removing benefits, privileges, food support, low taxes, welfare, or other standards people have become accustomed to should hurt more than never providing them in the first place.

### Laws and reforms

Major laws/reforms normally require **AP** and may also require projects, institutions, resources, research, or specialists.

They should unlock gradually to prevent feature overload.

New reform categories may be unlocked through:

- meta progression;
- milestones;
- institutions;
- specialization;
- research.

### Emergency decrees

Emergency decrees use AP as premium governing authority for strong immediate responses.

They should solve or strongly mitigate problems while creating political, economic, institutional, or future consequences.

Policies should change the **underlying causes of Unrest**, not act as direct `Unrest +/-` controls.

---

## Decision 014 — Research, Knowledge & Technology

**Status: Mostly settled; exact catalogue, prerequisites, costs, institutions, and pacing remain open.**

Research uses selectable **multi-month projects**, not a giant static technology tree.

### Research Capacity

Scholars and research institutions generate monthly **Research Capacity**.

Unused capacity is not stored forever as abstract Research Points.

Research therefore competes for current scholars, institutions, Coin, and later resources such as Paper.

### Research Catalogue

Available discoveries appear in a contextual catalogue grouped into broad knowledge domains.

Research opportunities can be revealed by:

- settlement development;
- buildings;
- specialization;
- geography;
- events and crises;
- previous discoveries;
- institutions;
- specialist availability.

Once prerequisites are met, ordinary strategic research should generally be predictable rather than heavily RNG-gated.

### What research should do

Research primarily unlocks:

- capabilities;
- institutions;
- policies and laws;
- specialist functions;
- crisis responses;
- production chains;
- infrastructure solutions;
- strategic options.

Pure `+X%` technologies are secondary.

Basic survival mechanics should not require the player to re-research tedious foundational knowledge every run.

### Scholar-University identity

Ordinary settlements begin with limited research parallelism.

A Scholar-University settlement gains:

- greater breadth;
- deeper academic options;
- more parallel research;
- unique research institutions;
- rare discoveries and academic events.

Its identity should not reduce to a flat research-speed multiplier.

### Meta progression

Legacy progression normally unlocks **future research possibilities** rather than automatically completing discoveries every run.

Deep late-game Legacy upgrades may eventually allow selected foundational knowledge to begin already researched.

A normal settlement should not realistically complete the entire research catalogue in one run.

---

## Decision 015 — Trade, External Economy & Regional World

**Status: Mostly settled; exact price model, capacities, contracts, investment costs, and forecast precision remain open.**

The outside economy is represented initially by an abstract **Regional Market**, not fully simulated neighboring settlements.

### Routine trade

The player can establish standing import/export orders.

Routine trade is constrained by:

- finite Trade Capacity;
- market availability;
- transport access;
- geography;
- roads;
- markets;
- warehouses;
- merchant institutions.

Import dependence is intentionally viable, allowing highly specialized settlements, but creates natural vulnerability to:

- shortages;
- route disruption;
- price spikes;
- regional crises;
- political events.

### Information uncertainty

Market prices and availability may contain hidden uncertainty.

Forecasting improves through:

- Legacy progression;
- specialists;
- research;
- institutions;
- commercial infrastructure.

### Trade Contracts

Trade Contracts provide longer-term strategic commitments beyond routine standing orders.

Exact contract mechanics remain open.

### Trading-Crafting specialization

This specialization can deepen:

- contract access;
- market reach;
- finished-goods production;
- finance;
- rare commercial opportunities;
- Trade Capacity.

A nearly pure Trade City should be viable as an extreme specialization, but require exceptional geography and substantial investment in connections, prosperity, sellers, and buyers.

### Regional investment

The Lord may invest in abstract regional connections and infrastructure to improve:

- market depth;
- Trade Capacity;
- reliability;
- route resilience.

A detailed regional map is not initially required.

Banking and finance overlap this system but are reserved for a dedicated later design system.

---

## Decision 016 — Ambitions, Difficulty & Run Setup

**Status: Mostly settled; exact multipliers, Ambition tiers, slot unlocks, and progression pacing remain open.**

### Run setup order

Current preferred order:

1. Difficulty is selected from unlocked options.
2. A Region is randomly generated and revealed.
3. The player sees the Region's archetype, traits, resource potentials, and challenge information.
4. The player chooses Ambitions from the unlocked roster and selects available Ambition tiers.
5. The run begins.

Run setup should provide direction without becoming a full pre-run character/build configuration system.

### Difficulty and Challenge Tier

**Run Difficulty** and the in-run **dynamic Challenge Tier** are separate and may both increase score/reward efficiency.

This double reward is intentional:

- Difficulty rewards voluntarily choosing harsher rules.
- Challenge Tier rewards surviving far enough for the world to become harsher during the run.

### Ambitions

Ambitions are optional run-long commitments.

They have scalable tiers or harder variants.

Completing Ambitions that conflict with each other, or clash with the revealed geography, may provide a visible **Challenge Bonus**.

### Ambition slots

The UI uses visible Ambition slots.

Initially only one may be available, while later slots are visibly locked behind achievements, milestones, or meta progression.

For each unlocked slot, the player chooses:

- an Ambition;
- an available tier.

The catalogue should also show locked future Ambitions and their unlock requirements.

### Region selection

Random Region is the normal **full-reward** mode.

Later progression may unlock deliberate Region selection for challenge testing or record attempts.

Choosing the Region should reduce the score/Legacy reward multiplier enough that accepting randomness remains the optimal progression route.

### Score and Legacy progression — current revision

Score-to-Legacy conversion is **linear or near-linear**.

Increasingly difficult pressure makes high score harder to obtain, and rapidly increasing Legacy talent costs provide the long-term progression sink.

Permanent meta progression is provisionally targeted at approximately **30–50 runs**, potentially fewer if runs become long or successful runs advance progression substantially.

This target remains subject to testing.

### Progressive onboarding

Ambitions, difficulty levels, specializations, advanced Regions, and many deeper systems unlock gradually.

This supports a deliberately long onboarding curve and prevents the early game from presenting the entire eventual complexity at once.

---

## Decision 017 — Starting Geography, Regions & Settlement Conditions

**Status: Mostly settled; exact archetypes, traits, potentials, scaling, and challenge values remain open.**

Each Region is generated from:

> **Region Archetype + Geographic Traits + Resource Potentials**

Additional archetypes and traits can unlock through meta progression.

### Geography should influence, not dictate

Geography affects:

- production;
- trade;
- climate risk;
- infrastructure cost;
- resource access;
- settlement specialization incentives.

It should strongly encourage some strategies without making one path mandatory.

Initial implementation can use clear geographical buffs/debuffs and advancement modifiers.

Resource depletion is **not required initially**.

### Infrastructure and geography

Infrastructure can mitigate poor geography but never completely erase it.

Connection distance is abstract but strategically meaningful.

Examples:

- direct river access;
- a nearby river or river town;
- a distant major trade corridor.

These can alter connection project cost and Trade Capacity.

Terrain and distance both matter.

For example, highlands close to a river may require a few expensive links while flat plains far from navigable water may require long road development.

### Remnants

Occasional existing remnants can create opportunities, such as:

- old roads;
- ruined bridges;
- abandoned quarries;
- old wells;
- shrines;
- other inherited infrastructure.

### Challenge rewards and information

Harder Regions provide visible **Region Challenge Bonuses**.

The Region is revealed before Ambitions are chosen.

Meta progression and research may improve geographical and climate forecasting detail.

Random Region remains the full-reward/default option.

If manual Region selection is later unlocked, it receives a meaningful score/Legacy penalty.

Ambitions that conflict with geography may grant additional Challenge Bonuses.

---

## System 18 — Religion, Social Institutions & Cultural Life

**Status: Needs revisit later. The core identity is established, but the Church–Lord control and legitimacy model is deliberately unresolved.**

Religion exists in every settlement through:

- clergy;
- religious buildings;
- ceremonies;
- charity;
- burial;
- festivals;
- traditions;
- political influence.

There is **no generic Faith/Piety currency** planned.

### Semi-independent Church

Organized religion is semi-independent by default.

It may possess its own:

- wealth;
- legitimacy;
- expectations;
- political pressure;
- institutional interests.

A powerful Church can support the Lord, constrain the Lord, or become an alternative source of public legitimacy.

### Religious Centre specialization

A Religious Centre may emphasize:

- tithes;
- charity;
- pilgrimage economy;
- missionaries;
- major religious institutions;
- festivals;
- burial and funerary systems.

Holy warfare is deferred to the future Warfare / Regional Politics system.

### Church control possibilities

Several political relationships are plausible and intentionally remain unresolved:

**Independent Church**
- maintains autonomy;
- may lend legitimacy to the Lord;
- may oppose or undermine the ruler.

**Overtly controlled/state Church**
- strongly directed by the Lord;
- still retains some separate institutional credibility;
- may absorb blame more effectively than a purely secular government arm.

**Subtly co-opted Church**
- remains publicly distinct;
- appointments, finances, and policy are gradually brought under the Lord's influence.

Under deep control, tithes may effectively become Lord-controlled revenue.

However, corruption, religious failure, or unpopular Church policy may increasingly rebound onto the Lord as control becomes obvious.

The exact balance between control, blame absorption, Church legitimacy, and Lord Legitimacy must be designed later.

### Later social/cultural mechanics

Burial is considered a strong future mechanic.

Festivals should become increasingly relevant as settlements grow.

Advanced religious systems should unlock gradually to avoid early-game feature bloat.

---

## System 19 — Map Table, UI & Information Architecture

**Status: CURRENTLY DESIGNING. The reference hierarchy is defined. System 19 is being refined through focused subsections. 19A (Navigation & Core Planning Workflow) remains proposed. 19B (Tooltips, Information Transparency & Commitment Safety) is now mostly settled at the principle level. 19C (UI Customization, Guidance & Confirmations) is established at the principle level, with its exact settings catalogue and defaults still open. Exact density, grouping, component sizing, and workflows must still be validated in prototype playtests.**

System 19 treats the interface as a **testable reference architecture**, not final pixel placement.

### Full-screen Map Table shell

The Map Table uses one persistent full-screen shell:

1. **Global Status Header**
2. **Left Navigation Rail**
3. **Central Town / Map Workspace**
4. **Right Planning & Forecast Inspector**
5. **Bottom Commitment Bar**

Conceptual hierarchy:

```text
┌──────────────── GLOBAL STATUS HEADER ────────────────┐
│ Date | AP | Pop | Food | Coin | Unrest | Legitimacy │
│                                      | Challenge Tier │
├───────────┬──────────────────────┬───────────────────┤
│           │                      │                   │
│ LEFT NAV  │   TOWN / MAP /       │ RIGHT INSPECTOR   │
│           │   ACTIVE WORKSPACE   │                   │
│ Overview  │                      │ Needs Attention   │
│ Economy   │                      │ Forecast          │
│ People    │                      │ Selected Effects  │
│ Projects  │                      │ Why? breakdown    │
│ etc.      │                      │                   │
├───────────┴──────────────────────┴───────────────────┤
│ Pending Changes | Undo | Reset | LORD'S SEAL / NEXT │
└──────────────────────────────────────────────────────┘
```

### Global Status Header

Keep only universally important information permanently visible.

Current candidates:

- current date / month / season;
- AP;
- population;
- Food;
- Coin;
- Unrest;
- Legitimacy;
- Challenge Tier.

Less universal information belongs in tooltips, contextual panels, or dedicated views.

The header must resist gradual clutter as new systems unlock.

### Left Navigation Rail

Use a small number of stable top-level domains.

Locked systems should **not appear before they are unlocked**.

As complexity expands, prefer subviews and contextual navigation over endlessly adding new top-level tabs.

The exact final domain grouping is still open.

### Central Workspace

The central area preserves player orientation.

On Overview it displays the town/map presentation.

Other management domains may replace or overlay parts of this workspace while keeping spatial/contextual continuity where practical.

The town itself remains a major progress indicator and should eventually support contextual overlays.

### Persistent Right Inspector

The right inspector provides context for whatever the player is doing.

Core responsibilities:

- **Needs Attention**
- next-month forecast
- selected-item effects
- consequence explanations
- `Why?` breakdowns

Warnings should be actionable.

Selecting a warning should deep-link the player directly to the relevant control or management screen.

This is a major anti-friction principle.

### Event / Decision queue

Events and unresolved decisions remain visible during the planning phase.

The player can revisit/edit choices before commitment when the decision logically allows it.

Event decisions and AP interventions should immediately feed into the live forecast.

### Bottom Commitment Bar

The lower area permanently groups:

- Pending Changes
- Undo
- Reset
- the Lord's Seal / Advance Month action

The player should always understand whether their current plan differs from the month's starting state before committing.

### Information depth

Use layered information with a strict interaction rule:

- **hover** shows a non-interactive tooltip for quick explanation;
- **clicking the underlying value/status** opens or deep-links to the relevant management view;
- dedicated views provide complex management, history, and exact calculations.

Tooltip contents themselves are not clickable and should never open nested hover panels.

The interface should allow players who want numbers to access exact math without forcing all detail onto the default screen.

### Monthly Outcomes and Chronicle

After resolution, **Monthly Outcomes** summarize what changed.

The outcome view is dismissible and can be reopened.

Historical outcomes, important decisions, events, and settlement history feed into the **Chronicle**.

### Forecast principle

The established rule remains:

> **Show predictable outcomes before commitment.**

The Map Table is the main implementation of that principle.

Predictable production, consumption, shortages, project progress, policy effects, AP consequences, and event choices should update live before the player seals the month.

Unpredictable events remain genuinely uncertain.

### Prototype telemetry

Prototype testing should measure interface friction, including:

- menu/domain visit frequency;
- missed warnings;
- use of Undo and Reset;
- time from opening planning to committing the month;
- frequently revisited information;
- unnecessary navigation.

System 19 should be revised based on observed player behavior rather than treated as final because a mock-up looks clean.

### Current open questions for System 19

- Exact top-level navigation domains.
- Which resources/statuses deserve permanent header space.
- Exact density of the right inspector.
- How Events/Decisions are surfaced without dominating the screen.
- How much of the central town remains visible while deep management panels are open.
- Mobile/alternative-resolution concerns are not currently a primary design target, but scaling behavior should not be painted into a corner.
- Keyboard shortcuts and high-speed interaction should be considered because a future optional Timed/Pressure Mode may exist.
- Exact transition between first-person chamber interaction and full-screen Map Table.
- Exact presentation of tooltips, pinned breakdowns, forecasts, and Monthly Outcomes.
- How much visual animation is allowed before it slows repetitive monthly planning.

---


### System 19A — Navigation Domains & Core Planning Workflow

**Status: PROPOSED / CURRENTLY DESIGNING — not yet accepted.**

System 19 is being split into focused design subsections so individual UI decisions can be discussed and accepted without prematurely settling the entire interface architecture.

Current proposed top-level navigation direction:

- Overview
- People
- Economy
- Development
- Governance
- Region
- Chronicle

These are conceptual management domains rather than one tab per simulation system. New mechanics should normally extend an existing domain through subviews or contextual controls instead of creating another permanent top-level tab.

Proposed domain roles:

- **Overview** — default strategic hub showing the town, important current conditions, unresolved decisions, live forecast highlights, and a restrained Needs Attention list.
- **People** — population, workforce, specialists, demographic pressures, and related settlement-capacity information.
- **Economy** — stockpiles, production, routine trade, treasury, and resource-flow analysis.
- **Development** — projects, functional buildings, infrastructure, research, repairs, and other forward investment.
- **Governance** — policies, laws/reforms, administration, religion, public-order institutions, and similar rule-setting systems.
- **Region** — regional market, geography, connections, regional conditions, and later external systems such as deeper trade networks, banking links, diplomacy, or warfare if those systems are added.
- **Chronicle** — historical outcomes, events, decisions, settlement history, later records, and other informational history views.

The normal monthly workflow should not require visiting every domain. The proposed loop is:

> **Monthly Outcomes → new events/visitors → Overview → investigate or change only what matters → review forecast → Lord's Seal / Advance Month.**

Needs Attention should act as **triage and navigation**, not as a mandatory checklist. Selecting a warning should deep-link to the relevant control, but the game should not imply that every imperfect statistic must be corrected before the month can advance.

Players must remain free to knowingly accept weaknesses, shortages, unused AP, risky specialization choices, or other non-optimal conditions.

Multiple views may expose the same underlying planning state when useful. For example, overall workforce allocation may be viewed from **People**, while workers assigned to a specific project may also be edited from **Development**. These are multiple views into one underlying plan, not duplicated independent state.

Warnings should identify problems rather than automatically prescribe the optimal solution.

This subsection remains open for critique and has not yet been accepted as an authoritative system-level decision.

---

### System 19B — Tooltips, Information Transparency & Commitment Safety

**Status: MOSTLY SETTLED at the principle level; exact tooltip content, warning thresholds, forecast precision, and visual treatment remain open.**

Tooltips are a primary explanatory layer of the Map Table rather than merely providing short labels.

The guiding principle is:

> **The default interface stays simple, while meaningful values and states can explain themselves immediately.**

A casual player with little prior knowledge should be able to discover what a number means, why it is changing, what an uncertain forecast represents, and whether missing information is intentionally unavailable without having to search through unnecessary submenus.

#### Tooltip versus management view

The accepted interaction distinction is:

> **Hover explains; click navigates; management views control.**

Tooltips appear on **hover only**. Their contents are informational and are not clickable. Clicking the underlying value, status, warning, or UI element should open or deep-link to the relevant management screen or contextual view where practical. This prevents nested tooltip chains and makes interaction behavior predictable.

A tooltip should often be sufficient when the player only wants to understand a value or state. Dedicated management screens remain useful when the player wants to change allocations, compare multiple producers, edit trade, inspect history, or perform deeper planning.

Example conceptual Food tooltip:

```text
FOOD
Current stockpile: 2,840

Expected this month
Production              +612
Population consumption  -560
Winter reserve           -80
Trade                    -60
Projects                 -24
Other                    -268
────────────────────────────
Expected change          -320

Projected stockpile: 2,520

At current consumption:
~4.1 months of food remaining

```

The tooltip itself contains no buttons or interactive links. Clicking the underlying Food value can open the relevant Economy / Food management view. All numbers are illustrative only.

#### Tooltips for derived values

Important derived values should explain their main causes rather than only define their name.

For example, an Unrest tooltip could show current direction and the largest contributing pressures. A Legitimacy tooltip could show important long-term positive and negative influences. Climate, market, or crisis-risk tooltips should explain their practical meaning and known consequences.

The first tooltip should answer the obvious question without forcing the player through chains of nested tooltips.

There are **no nested hover panels** and no clickable items inside tooltips. If deeper analysis is needed, the player clicks the underlying value/status to open the relevant dedicated view. The right inspector may also present deeper contextual information when that item is selected through normal interface interaction.

#### Known, estimated, and unavailable information

The interface should distinguish three broad information states:

1. **Known information** — precise or sufficiently reliable values can be shown directly.
2. **Estimated information** — the interface should communicate the forecast together with useful uncertainty/confidence information where relevant.
3. **Unavailable information** — the UI should explicitly state that the information is intentionally not known yet and, where appropriate, indicate how better information can later be unlocked.

Unknown information should never look like missing UI implementation.

Example conceptual climate tooltip:

```text
CLIMATE OUTLOOK

Severe winter conditions are considered likely.

Known effects may include:
Heating demand           Higher
Crop productivity        Lower
Travel disruption        Possible
Disease pressure         Higher

Forecast confidence: Moderate

Some information remains uncertain.

Better climate forecasting can be unlocked through:
• Research
• Regional knowledge
• Relevant specialists
• Legacy progression
```

Exact information quality, confidence scales, unlock sources, and numerical precision remain unresolved.

Improved forecasting should ideally feel like gaining genuinely better information rather than only receiving an abstract `Forecast Accuracy +X%` modifier.

A possible progression is conceptually:

```text
Unknown
→ broad qualitative warning
→ rough probability / confidence
→ estimated effect ranges
→ high-confidence detailed forecast
```

This progression remains illustrative rather than accepted balance/content.

#### Lord's Seal as non-blocking commitment safety

The **Lord's Seal / Advance Month** control should communicate how risky it is to commit the current plan without forcing confirmation dialogs on experienced players.

The Seal may change:

- color;
- glow;
- animation;
- surrounding effects;
- warning iconography;
- short nearby status indicators;

based on important current planning conditions.

Potential influences include:

- predicted catastrophic shortages;
- major avoidable crisis escalation;
- unresolved important decisions;
- remaining Action Points;
- other unusually consequential forecast conditions.

Different conditions should not all be treated equally. For example, unused AP may warrant a visible reminder but is not automatically a mistake, whereas a predicted Food stockpile collapse may justify a much stronger danger state.

The base interaction keeps the Seal **directly pressable** so experienced players can commit a month immediately even when warnings remain.

However, optional confirmation behavior is controlled through the settings system described in System 19C. A first run may enable protective confirmations by default, while experienced players can disable them.

The purpose is to prevent accidental rapid advancement without permanently imposing friction on deliberate fast play.

Hovering the Seal may summarize remaining concerns, for example:

```text
BEFORE YOU ADVANCE

Critical
Food stockpile expected to reach 0

Warning
Flood risk elevated

Unresolved
Refugee petition

Unused
1 Action Point

You may advance the month at any time.
```

This information should remain concise and should not turn the Seal into another full management panel.

#### Casual-player discoverability

The same interface should serve inexperienced and experienced players without requiring separate basic and advanced UI modes.

A new player can hover or inspect unfamiliar information to understand it. An experienced player can ignore explanatory layers and interact quickly.

Whenever the simulation deliberately withholds information, the interface should make that explicit. A player should be able to distinguish:

> **“I do not know this because my settlement lacks the information”**

from:

> **“I do not know this because the interface failed to explain it.”**

This is proposed as a major System 19 information-architecture principle.

#### Tooltip anti-bloat rule

Tooltips should not become recursive mini-menus.

The initial tooltip should normally explain enough to answer the player's immediate question within a few seconds. More complex formulae, historical data, secondary contributors, or management controls belong in a pinned inspector or dedicated view.

#### Decision 019B — Self-Explaining Information & Commitment Safety

**Status: Mostly settled at the principle level.**

The Map Table uses tooltips as the primary explanatory layer for important resources, forecasts, statuses, modifiers, and derived values. Tooltips should explain what information means, why it is changing, its major consequences, and where relevant where it can be managed.

The UI explicitly distinguishes **known, estimated, and intentionally unavailable information**. Uncertainty should be communicated where strategically relevant, and intentionally hidden information should explain that it is unknown rather than appearing as unexplained missing data.

Better forecasting and information quality may unlock through research, institutions, specialists, regional knowledge, Legacy progression, and other suitable systems. Exact sources and precision remain open.

Tooltips are **hover-only and non-interactive**. There are no nested tooltip panels. Clicking the underlying value/status navigates to the relevant management or contextual view.

The Lord's Seal acts as a **commitment-risk indicator**. Its appearance and effects may react to important predicted danger, unresolved decisions, unused AP, and other consequential conditions. The base interaction remains immediate; optional confirmation behavior is governed by UI settings rather than hard-coded into the core interaction.

The goal is to make accidental commitment difficult while keeping deliberate fast play frictionless.

---

### System 19C — UI Customization, Guidance & Confirmations

**Status: ESTABLISHED at the principle level; exact options, defaults, presets, and persistence rules remain open.**

Towngame should include an **extensive settings menu** that allows players to customize the amount of interface guidance, warning behavior, visual emphasis, and visible UI detail.

The purpose is to support both inexperienced players who want strong assistance and experienced players who want a fast, low-friction interface without maintaining separate game modes or fundamentally different UIs.

#### Granular UI control

UI and guidance elements should be individually configurable where practical rather than limited to one global `Beginner / Expert` switch.

Potential configurable categories include:

- confirmation prompts;
- warning severity indicators;
- Lord's Seal color/effects/animation;
- AP-left reminders;
- unresolved-decision reminders;
- forecast detail;
- Needs Attention visibility or categories;
- header elements;
- contextual labels and map overlays;
- tutorial/help hints;
- tooltip availability or delay;
- animations and other presentation effects;
- other high-frequency UI elements that testing shows players may reasonably want to reduce or hide.

The exact settings list is not yet accepted and should be informed by prototype use.

#### First-run guidance

The first run may enable more protective guidance by default. For example, advancing the month while a critical forecast warning is active could display a confirmation prompt during early play.

This is **optional UX assistance**, not a core simulation rule. The player should be able to disable such confirmations in settings, and experienced players should be able to reach a one-click Advance Month workflow.

Possible guidance presets may exist as convenient starting configurations, but they should not replace granular control. A preset should merely change individual settings that the player can then customize.

#### Confirmation philosophy

Confirmations should be reserved for genuinely consequential or easy-to-trigger actions and should be configurable. The interface should prefer visible warning states, Seal feedback, and clear forecasts over repetitive modal dialogs.

A useful conceptual hierarchy is:

> **Explain first → warn visually → optionally confirm → never hide the underlying reason.**

The game should not assume that an intentionally risky choice is a mistake. Players remain free to ignore warnings and commit dangerous plans.

#### Accessibility and player ownership

Granular customization is also an accessibility and comfort feature. Players may differ in how much animation, warning emphasis, explanatory text, or persistent information they want visible.

Settings should therefore alter presentation and guidance rather than secretly changing simulation rules or information that the settlement has not actually unlocked. A UI option may hide known information, but it must not reveal strategically unavailable information merely because a player enabled a more detailed interface.

#### Decision 019C — Customizable Guidance Layer

**Status: Established at the principle level.**

Towngame will provide extensive, granular UI and guidance settings. The same underlying interface can therefore support a strongly guided first run and a streamlined experienced-player workflow.

Protective confirmation prompts may be enabled by default for early play, including potentially the Lord's Seal under critical conditions, but they are optional and can be disabled.

Presets may provide convenient starting configurations, but individual settings remain adjustable.

UI customization affects presentation, warnings, explanations, and interaction friction; it does not grant access to information the simulation intentionally keeps unknown.

---

# Parked Future Systems

These are roadmap placeholders rather than accepted designs.

## System 20 — Town Visualization & Modular Presentation

Need a composable presentation system that can reflect population, specialization, infrastructure, prosperity, season, damage, and unrest without handcrafted images for every combination.

Candidate directions include modular 2D layers, pre-rendered districts, procedural sprites/meshes, low-detail 3D, or a hybrid.

Simulation logic must remain independent of presentation.

## System 21 — Banking, Credit & Monetary Control

Banking/credit belongs partly to the base game and partly to Administration / Trading-Crafting.

Topics include borrowing, interest, default risk, liquidity, deposits, public debt, coinage/minting, merchant finance, and anti-exploit rules preventing credit from trivializing scarcity.

## System 22 — Warfare, Armies & Regional Politics

Possible future system covering defense, forces, logistics, fortifications, neighboring powers, raids, alliances, embargoes, tribute, and external military pressure.

It must not turn the core game into a grand-strategy title.

## System 23 — Timed / Pressure Mode

Optional future mode where months may advance automatically after a limited real-time planning window.

This would be separate from normal untimed play and only implemented if testing shows it is fun.

Potentially supports separate scoring, achievements, and records.


# Continuation Point

**Resume design discussion at System 19 — Map Table, UI & Information Architecture.**

The structural shell is established. Subsection 19A (navigation domains and core monthly planning workflow) remains proposed. Subsection 19B is mostly settled: hover-only non-interactive tooltips explain information, clicking the underlying value/status navigates to management, uncertainty is explicit, and the Lord's Seal communicates commitment risk. Subsection 19C establishes extensive granular UI/guidance settings, including optional first-run confirmations and streamlined experienced-player configurations. Continue by resolving 19A, then refine right-inspector density, Events/Decisions presentation, exact confirmation defaults, settings catalogue, and remaining interaction details before System 19 is marked accepted.

When this file is supplied to a new ChatGPT conversation, treat it as the authoritative Towngame design context. Do not restart from System 12 or assume every older proposal remains current when a later revision above supersedes it.

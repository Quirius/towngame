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


### Legacy Point score conversion

Legacy Point gain from final score should use a **diminishing conversion** rather than a linear one.

This prevents repeated farming of an easy, optimized score range from remaining the most efficient long-term strategy.

Higher score should always grant more Legacy Points, but each additional block of score should be worth proportionally fewer LP unless the player also increases difficulty or completes additional objectives.

Difficulty settings and Ambitions may apply proportional multipliers or bonuses to Legacy Point rewards.

This means:

- harder runs can remain LP-efficient;
- Ambitions provide meaningful additional progression;
- merely repeating an easy safe strategy becomes progressively less attractive;
- pushing into higher Challenge Tiers and harder modifiers remains rewarding.

Exact conversion curves and multipliers remain open.

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

### Legacy Point economy
Final score converts into Legacy Points using a **diminishing-return function**.

Difficulty settings may apply proportional LP multipliers, and Ambitions may provide additional LP or proportional bonuses.

### Major unlocks remain separate
Legacy Points buy incremental permanent power.

Major gameplay systems and broader content are unlocked primarily through first-time milestones, achievements, records, Challenge Tier breakthroughs, Ambitions, and other meaningful accomplishments.

### Meta-progression design principle
> **Legacy progression is permanent accumulation, not a pre-run build system.**

The player gradually becomes stronger across every run until the full progression system is eventually completed.


## Next Design System

### System 12 — Specialization and Run Identity

Topics to resolve:
- How does a settlement become specialized during a run?
- Which choices are permanent for the run?
- Should population milestones offer specialization choices?
- Can a town mix several specializations?
- How strongly should geography and starting modifiers influence specialization?
- What bonuses and drawbacks distinguish farming, trade, mining, administration, research, and other town identities?
- How should Ambitions interact with specialization?
- Should specialization affect available events, buildings, resources, or visual town development?



## Decision 012 — Specialization and Run Identity

**Status: Accepted at system level; exact thresholds, specialization content, and visual implementation remain open.**

### Emergent specialization

Settlement specialization is primarily an emergent run-level system driven by starting geography and run modifiers, population-milestone choices, actual workforce allocation, constructed buildings and institutions, production and trade patterns, Ambitions, and event history.

The game may internally track specialization affinities without exposing a visible XP bar.

### Primary specialization

A settlement may accumulate progress toward several specialization identities, but the **first specialization to cross the major recognition threshold becomes the run's Primary Specialization**.

The player should be clearly notified when this happens.

The Primary Specialization is locked for purposes such as specialization-specific achievements, first-time meta unlocks, run records, and specialization tier tracking.

This prevents players from deliberately pivoting a mature city simply to collect several specialization achievements in one run.

The Primary Specialization may itself have multiple tiers that can all be achieved during the same run.

### Secondary affinities

Other specialization affinities continue to be tracked after the Primary Specialization locks.

A large city may therefore have one strong Primary Specialization and one or more meaningful secondary affinities.

Secondary affinities may influence milestone-choice weighting, event weighting, hybrid milestone options, statistics and post-run analysis, visual town identity, and smaller situational effects.

They do not normally grant the same first-time achievement/meta reward as becoming the Primary Specialization.

### Hybrid specialization choices

Cross-specialization should primarily appear through **hybrid choices**, not by permanently defining every possible combination as its own separate specialization class.

Examples:
- Agriculture + Trade/Craft affinity -> Grain Exchange / Agricultural Market options
- Mining + Craft affinity -> Metalworking Center options
- Scholarship + Administration -> Bureaucratic Academy / Learned Administration options

Hybrid options may become more likely or unlock only when the relevant secondary affinity is sufficiently strong.

### Milestone structure

Population milestones are divided conceptually into two levels.

#### Minor milestones
Occur relatively often, potentially around 10–15 times in a substantial run.

They provide smaller, more generic or tactical run rewards such as temporary production boosts, Legitimacy, project acceleration, resource grants, minor policy options, or small specialist benefits.

Minor milestone choices may be rerollable.

#### Major identity milestones
Occur much less frequently, provisionally around 2–3 times in a substantial run.

These offer larger strategic choices that strongly shape settlement identity and specialization.

Their choice pools should react to current specialization affinity, but should not be fully exclusive. Generic or off-path options may still appear so the player is not completely railroaded.

Major milestone choices may deepen the Primary Specialization, open a new secondary direction, unlock hybrid choices, or add institutions, policies, specialists, event types, or economic options.

Exact milestone counts and thresholds remain open.

### Weighted milestone pools

Current specialization affinity should influence the probability of relevant milestone choices appearing.

This weighting may be invisible.

A strongly agricultural town should see agricultural and agriculture-adjacent options more often, while still occasionally receiving generic or alternative choices.

This same affinity system may also influence event weighting.

### Milestone rerolls

Milestone choices may have a limited reroll system.

The player begins with **0 or 1 reroll** provisionally.

Additional rerolls may be unlocked through Legacy Talents or other progression.

Rerolls should be limited enough that players cannot simply fish for a perfect predetermined build.

Minor milestones are the most natural place for rerolls.

Major identity milestones may have stricter reroll rules or require a rarer meta upgrade if rerolls are allowed at all.

### Organic downside principle

Specializations should primarily create natural opportunity costs and vulnerabilities rather than arbitrary paired penalties.

### Religion

Religion should exist in some form because it fits the setting and can interact with Legitimacy, Unrest, charity, burial and mortality, festivals, education, social cohesion, and events.

Whether Religion becomes a full Primary Specialization is still open, but it should not be omitted merely because it is not selected as a specialization.

### Trade and manufacturing

Trade alone may be too dependent on geography or external conditions to function as a universally viable Primary Specialization.

Possible later structures include merging manufacturing and trade into a broader Commerce/Craft identity, keeping Craft/Manufacturing as a primary specialization while treating Trade as a cross-cutting affinity, or allowing pure Trade specialization only when geography or starting conditions support it.

The final specialization list remains open.

### Ambitions

Ambitions are a major driver of run identity.

They may encourage the player toward particular specializations or deliberately oppose favorable geography/run modifiers for greater challenge.

Difficult or contradictory Ambition combinations may justify greater score multipliers, greater Legacy Point rewards, achievements, or unique unlocks.

### Specialization design principle

> **A town should become known for what it actually became, not merely for what the player selected from a menu.**

The system should recognize player behavior, then use that identity to shape later opportunities without completely removing flexibility.


### Specialization lock warning

Accidental Primary Specialization lock-in must be easy to avoid.

Before a specialization crosses the final lock threshold, the player should receive a clear **recognition warning state**.

Example presentation:

> **Your town is becoming known as a Mining Center.**
>
> Mining is close to becoming this settlement's Primary Specialization.
> If this continues, specialization achievements and primary specialization progression for this run will lock to Mining.

The warning should appear early enough that the player can deliberately change direction if they are pursuing another specialization.

Possible supporting UI:
- a map-table notice showing which specialization is currently closest to recognition;
- descriptive states such as Emerging / Recognized / Primary;
- a confirmation-style warning on the final action that would clearly push the town across the threshold, where practical;
- post-run records explaining why the specialization was recognized.

The player should never accidentally discover several months later that an invisible threshold permanently locked the run.

Exact thresholds and warning timing remain open.

### Initial Primary Specialization roster

The initial specialization roster contains five Primary Specializations:

1. **Agricultural Center**
2. **Trading & Crafting Center**
3. **Mining Center**
4. **Scholar / University Center**
5. **Religious Center**

These names are provisional.

Each specialization should have:
- multiple recognition tiers;
- distinct milestone weighting;
- relevant event weighting;
- institutions and specialist opportunities;
- natural opportunity costs;
- possible hybrid choices with secondary affinities.

The roster may expand later, but the first version should be designed around these five identities.

### Town visual system

The earlier concept of representing every settlement state through fully static city images is no longer considered suitable as the long-term solution.

With multiple:
- population sizes;
- Primary Specializations;
- secondary affinities;
- infrastructure levels;
- prosperity states;
- seasonal states;
- unrest/collapse states;

the number of required pre-rendered images would grow into the hundreds or thousands.

The visual system should therefore eventually use a more composable approach.

Possible future directions include:
- layered 2D town components;
- modular pre-rendered districts;
- procedural sprite/mesh placement;
- low-detail 3D town generation;
- hybrid 2D/3D rendering.

The exact technology is intentionally deferred until the core simulation is prototyped.

The design requirement is:

> **The town visual must be able to reflect population, specialization, development, and condition without requiring a unique handcrafted image for every combination.**



## Decision 013 — Policies, Laws, and Ongoing Management

**Status: Accepted at system level; exact policy values, inertia formulas, and reform content remain open.**

### Three levels of governance

Ongoing governance should distinguish between three types of decisions:

1. **Routine policy settings**
   - adjusted from the map table;
   - normally do not cost AP;
   - represent ordinary administrative direction;
   - usually resolve through the normal monthly simulation.

2. **Major laws and reforms**
   - significant structural changes;
   - normally cost AP to enact, repeal, or fundamentally replace;
   - may unlock new policy settings, institutions, or long-term effects.

3. **Emergency decrees**
   - immediate, powerful, temporary interventions;
   - usually cost AP;
   - may override normal policy rules for a crisis;
   - often carry Legitimacy, resource, economic, or long-term political consequences.

### Policy interface

Policies should generally use a small number of discrete stances rather than fine-grained sliders.

Example:

Taxation:
- Low
- Moderate
- High
- Severe

This keeps decisions readable and reduces monthly micro-optimization.

Known effects should be forecast numerically before Advance Month.

### Policy inertia

Routine policy changes are free in AP terms, but should not be costless to reverse constantly.

Possible anti-optimization mechanisms include:

- implementation delay;
- transition periods;
- reduced effectiveness immediately after a change;
- Legitimacy impact from frequent reversals;
- administrative disruption;
- minimum commitment periods for selected policies.

The preferred model should punish erratic governance rather than simply placing arbitrary cooldowns on every setting.

### Initial policy families

Potential core policy categories include:

- Taxation
- Food distribution / rationing
- Immigration
- Labor
- Public order
- Welfare / charity
- Religion
- possibly housing/development policy where appropriate

Not every category needs to exist in the first prototype.

### Taxation

Tax policy controls the balance between Coin income and pressure on the population.

Higher taxation may:
- increase Coin income;
- lower household prosperity;
- raise Unrest pressure;
- reduce immigration attractiveness;
- damage Legitimacy when excessive or unstable.

Lower taxation may support growth and legitimacy at the cost of the Lord's treasury.

Exact formulas remain open.

### Food distribution and rationing

Food policy determines how scarcity or surplus is distributed.

Possible stances may include:
- generous distribution;
- normal ration;
- strict ration;
- emergency rationing.

Rationing may stretch stockpiles while harming health, productivity, Legitimacy, or Unrest.

Emergency rationing may require AP or unlock only during shortage conditions.

### Immigration policy

Immigration policy controls how actively the settlement accepts or attracts newcomers.

Possible stances:
- restricted;
- controlled;
- open;
- actively encouraged.

Effects may include:
- immigration rate;
- housing pressure;
- labor supply;
- food demand;
- specialist-arrival chance;
- Legitimacy or event effects.

### Labor policy

Labor policy may govern extraordinary use of the population rather than ordinary workforce allocation.

Possible later examples:
- child labor;
- elderly labor;
- work-hour intensity;
- compulsory labor for emergencies;
- specialist exemptions.

These policies should have natural health, education, mortality, productivity, or political consequences.

### Public order

Public-order policy determines the balance between policing/coercion and political tolerance.

Possible effects:
- crime control;
- protest escalation;
- Legitimacy;
- event outcomes;
- guard requirements;
- Unrest behavior.

Direct permanent Unrest reduction should remain avoided; public-order policy should instead influence underlying causes, escalation, or consequences.

### Welfare and charity

Welfare/charity policy may consume Food, Coin, institutions, or labor in exchange for:
- hardship mitigation;
- health;
- Legitimacy;
- reduced consequences of poverty or crises.

Religion may interact strongly with this system.

### Religion

Religion exists as an ordinary settlement system even when the town is not a Religious Center.

Policy questions may include:
- degree of institutional support;
- festivals;
- charitable obligations;
- clergy funding;
- religious education;
- burial practices.

The exact theological/religious representation remains open and should be designed later with the broader Religion system.

### Reforms and laws

Major laws/reforms should create structural changes rather than operate as ordinary monthly toggles.

Examples:
- establish a formal tax bureaucracy;
- legalize/ban child labor;
- create public granaries;
- establish poor relief;
- formalize merchant privileges;
- create religious institutions;
- introduce compulsory sanitation rules.

These may:
- cost AP;
- require institutions or specialists;
- take time to implement;
- unlock new policy stances;
- create permanent event/Legitimacy consequences.

### Emergency decrees

Emergency decrees represent the Lord using exceptional authority.

Examples:
- seize private grain;
- impose emergency rationing;
- conscript labor for a fire/flood response;
- close markets during epidemic;
- suspend normal taxes after disaster.

They should usually be strong and immediate, but costly politically or economically.

### Specialization and Ambitions

Policy choices should interact with specialization without hard-locking policy access.

Examples:
- Agricultural towns may gain specialized food-policy options.
- Trading-Crafting towns may unlock merchant or tariff reforms.
- Religious Centers may gain more sophisticated charity/festival policies.
- Scholar towns may unlock public education or medical regulations.

Ambitions may require unusual or difficult policy combinations.

### Design principle

> **Routine governance should be flexible; structural reform should require commitment; emergency power should be strong but costly.**

Policies should create long-term consequences and recognizable governing styles without becoming a monthly slider-optimization puzzle.



### Seasonal policy cadence

Routine policies are free to change, but each policy should normally be adjustable only **once per season**.

This prevents players from switching policy stances every month to exploit short-term conditions while remaining simple to understand.

Different policies may eventually have exceptions, but seasonal adjustment is the default rule.

### Rate-of-change penalties

Policy consequences should depend not only on the current stance but also on **how quickly the policy changed**.

Example:

Moving taxation from Minimum to Maximum over one year should create substantially more disruption, Legitimacy pressure, and Unrest-generating conditions than reaching the same tax level gradually over three years.

The current policy level still matters; a severe tax rate remains burdensome even if introduced slowly.

This creates two separate effects:

1. **Level effect** — the consequences of the policy itself.
2. **Transition shock** — additional consequences caused by rapid change.

The exact formula remains open.

### Historical expectations and acquired standards

Population expectations should remember previously experienced standards.

Removing an established benefit, tolerance, subsidy, service, or level of prosperity should generally create more political pressure than never providing it in the first place.

Examples:

- people accustomed to low taxes react strongly to a rapid tax increase;
- merchants accustomed to privileges resist their removal;
- citizens accustomed to generous food support resent abrupt rationing;
- established welfare or religious support becomes politically harder to withdraw.

This connects policy history with the broader Expectations system from Decision 008.

The principle is:

> **Wanting an improvement is usually less destabilizing than losing a standard people already consider normal.**

### Gradual reform-system introduction

Major laws and reforms should be introduced slowly to avoid feature overload.

Early runs may contain only a very small reform set.

Additional reform categories, laws, and structural policy options may be unlocked through:

- meta progression;
- population milestones;
- achievements;
- institutions;
- specialization;
- research.

This allows the governance system itself to expand as the player becomes more experienced.

### Prototype simplification

The first implementation may use simpler rules:

- routine policy changes are free;
- each policy may be changed once per season;
- effects apply at the next monthly resolution;
- transition penalties can use a simple recent-change measure;
- only a small number of laws/reforms exist initially;
- emergency decrees remain AP-driven.

More detailed implementation delays and institutional friction can be added later if needed.


## Next Design System

### System 14 — Research, Knowledge & Technology

Topics to resolve:
- How research is generated and progressed.
- Role of Scholars, Schools, Universities and Paper.
- Whether technologies unlock buildings, policies, specialists or efficiencies.
- How research avoids becoming a generic linear tech tree.
- How Scholar/University specialization interacts with research.
- Which research knowledge resets each run versus what meta progression permanently unlocks.



## Decision 014 — Research, Knowledge, and Technology

**Status: Accepted at system level; exact catalogue, prerequisites, costs, institutions, and research pacing remain open.**

### Core principle

Research should represent the settlement deliberately developing useful knowledge, practices, institutions, and techniques.

It should not become a large generic technology tree that the player mechanically clears in roughly the same order every run.

The preferred direction is **selective research projects within broad knowledge domains**.

### Research projects

Research uses the same broad project philosophy as construction and reforms.

A research project:
- takes multiple months;
- requires Scholar capacity;
- may consume Coin, Paper, or other resources;
- may accept ordinary assistants but requires qualified Scholars for core research;
- can be paused by assigning insufficient staff/resources;
- produces a defined discovery or institutional capability when completed.

Research progress should be forecast on the map table.

### Research capacity

Scholars and research institutions create **Research Capacity** rather than a permanently stockpiled Research Point currency.

Research Capacity represents how much research work can be performed in the current month.

Unused Research Capacity normally disappears at month resolution rather than accumulating forever.

This prevents the player from banking years of abstract science points and instantly purchasing a chain of discoveries later.

### Research institutions

Possible institutional progression:
- educated individual / court scholar;
- School or Scriptorium;
- Academy;
- University.

Exact buildings remain open.

Early research should be possible on a small scale without requiring a full University.

Advanced research may require:
- specific institutions;
- multiple Scholars;
- Paper;
- Coin;
- previous discoveries;
- relevant settlement experience.

### Knowledge domains

Research should be grouped into broad domains rather than one rigid tree.

Provisional domains may include:
- Agriculture
- Engineering / Construction
- Medicine
- Administration
- Craft / Commerce
- Social / Religious knowledge

Additional domains can be added later if needed.

Domains are organizational structures, not necessarily linear progression tracks.

### Contextual availability

Research options should become available based on what exists in the settlement and what it has experienced.

Examples:
- repeated mine accidents may make Mine Safety Methods available;
- epidemic experience may unlock advanced medical research;
- large agricultural production may reveal irrigation or crop-management projects;
- administrative institutions may unlock census/accounting methods;
- trade activity may unlock commercial standards or warehousing methods.

This makes research react to the town rather than exist as a detached checklist.

### Research choices

The player should normally choose which available research project to pursue.

Research options may be influenced by:
- current buildings;
- specialists;
- Primary and secondary specialization affinities;
- population milestones;
- events and crisis history;
- previous discoveries;
- geography;
- meta-progression unlocks.

Exact presentation remains open.

### Research outcomes

Research should primarily unlock **new capabilities and options**.

Possible rewards:
- new functional buildings;
- infrastructure stages;
- laws/reforms;
- policy stances;
- specialists;
- crisis-response options;
- new production chains;
- improved forecasting;
- specialized projects;
- modest efficiency improvements.

Pure numerical upgrades are allowed but should not dominate the system.

### Scholar / University specialization

Research must remain useful for every settlement.

Scholar / University specialization should deepen the system rather than simply grant a large flat research-speed bonus.

Possible specialization advantages include:
- more simultaneous research projects;
- better access to advanced discoveries;
- lower institutional requirements;
- additional research choices;
- unique academic institutions;
- special hybrid research;
- stronger event/research interactions;
- ability to pursue theoretical or prestige knowledge that ordinary towns cannot justify.

Exact advantages remain open.

### Parallel research

Ordinary settlements may begin with only **one active research project** at a time.

Advanced institutions or Scholar specialization may allow multiple projects to run simultaneously.

Each project still requires its own workers and resources, so parallel research creates a real economic cost.

### Paper and advanced scholarship

Paper is a promising advanced resource for research and administration.

Early basic research should not depend heavily on Paper so the system can function before advanced production chains exist.

Later research and larger institutions may consume Paper monthly.

### Meta progression and research

Meta progression should usually **unlock research possibilities**, not automatically grant every discovery at the start of each run.

Example:
- an achievement permanently unlocks Advanced Medicine as a possible future research branch;
- a later settlement still needs appropriate Scholars, institutions, and research effort to obtain it.

Some deep Legacy upgrades may eventually allow selected foundational discoveries to begin already known, reducing repetitive early-run research.

This should be used sparingly.

### Research and run variety

A settlement should not realistically research everything during an ordinary run.

Limited time, Scholar labor, resources, institutional requirements, specialization, and World Pressure should force prioritization.

A Scholar-specialized late-game city may approach a much broader research catalogue, but ordinary settlements should finish with meaningful gaps.

### Discovery memory and events

Research history may interact with Event Memory.

Examples:
- surviving an epidemic can expose a medical research path;
- researching sanitation can change future disease-event responses;
- studying a mine collapse may unlock safety practices;
- religious scholarship may affect doctrinal or social events.

Research therefore becomes another way the history of the settlement changes its future possibilities.

### Design principle

> **Research should answer problems and ambitions the settlement actually has, not exist as an isolated checklist of upgrades.**

The player develops knowledge because it changes what the town can do, and choosing one research direction means delaying another.



### Meta progression and score efficiency

Meta progression may also improve how effectively a developed settlement converts strong play into score-generating capability.

This may happen indirectly through:
- earlier access to productive or institutional options;
- better research throughput;
- improved ability to sustain higher Challenge Tiers;
- stronger milestone rewards;
- other bounded progression bonuses.

This can accelerate future Legacy Point gain, while the diminishing score-to-Legacy conversion prevents unlimited linear snowballing.

The system should reinforce the incremental/prestige loop without making low-difficulty farming permanently optimal.



## Decision 015 — Trade, External Economy, and Regional World

**Status: Accepted at system level; exact price model, capacity formulas, contracts, forecasting accuracy, and regional-investment balance remain open.**

### Core principle

Trade should allow a settlement to specialize, recover from shortages, and convert comparative advantages into Coin or needed goods.

It should not allow every town to ignore local production entirely.

The outside world should therefore be represented through an **abstract Regional Market** rather than fully simulated neighboring settlements.

### Regional Market

The Regional Market represents surrounding settlements, merchants, trade routes, distant producers, and broader economic conditions.

For each tradable resource, the market may expose:
- current buy price;
- current sell price;
- available import volume;
- available export demand;
- recent price direction;
- known regional modifiers.

Prices and availability can change because of season, regional events, World Pressure, trade-route condition, local specialization, shortages/surpluses, and geography.

### Standing trade orders

Routine trade should be handled through persistent orders configured at the map table.

Examples:
- Import Food until stockpile reaches 600.
- Export Wood while stockpile remains above 900.
- Buy up to 40 Medicine per month if price is below a chosen threshold.

Standing orders are free routine management and resolve during monthly simulation.

### Trade forecast

Before Advance Month, the map table should show expected imports, exports, Coin spent/earned, trade capacity used, stockpile results, and known price effects.

If conditions are uncertain, the forecast may show a range or warning.

### Trade capacity

A settlement has limited **Trade Capacity**.

Trade Capacity may depend on roads, river access, market infrastructure, warehouses, merchant institutions, geography, specialists, and season.

Imports and exports compete for this capacity.

A rich town therefore cannot instantly import unlimited Food merely because it has enough Coin.

### Market access and geography

Geography determines baseline market access.

Examples:
- river crossing: strong bulk trade;
- remote highlands: weak access;
- major road junction: strong merchant traffic;
- isolated valley: expensive imports and limited export volume.

Infrastructure can improve access but not erase geography completely.

### Import dependency

Heavy import dependence is viable but creates natural vulnerability.

A Mining Center may export Iron and Stone while importing Food. This can be profitable in normal conditions but dangerous during regional food shortages or disrupted routes.

This is preferable to arbitrary specialization penalties.

### Prices and availability

Prices should be dynamic enough to create meaningful decisions without simulating a full exchange.

Buying normally costs more than selling the same resource because of merchant margin, transport, and risk.

Regional supply and demand are finite. Medicine, Food, Stone, and other resources may have limited monthly or seasonal availability/demand.

Large player trade volumes may later influence prices modestly, but detailed market-clearing simulation is not required initially.

### Contracts and special opportunities

Events, milestones, specialization, and merchant institutions may offer **Trade Contracts** beyond ordinary market orders.

Examples:
- guaranteed Tools purchase for 12 months;
- fixed-price Grain imports through winter;
- large Stone-delivery request;
- caravan offers rare Medicine;
- unusually high-price crafted-goods buyer.

Contracts create strategic commitments without replacing the basic Regional Market.

### Trade disruption

Persistent regional conditions can modify capacity, price, availability, or contract reliability.

Examples:
- flooded roads;
- bandit activity;
- harsh winter;
- bridge collapse;
- famine;
- epidemic restrictions;
- embargo.

Trade therefore interacts directly with crises and World Pressure.

### Tariffs and merchant policy

Tariffs, merchant privileges, customs collection, subsidies, strategic reserves, and market regulation belong mainly in the policy/reform system rather than a separate trade minigame.

### Trading-Crafting specialization

Trading-Crafting specialization deepens the system through better market access, warehouses, merchant institutions, contracts, finished-goods chains, rare imports, and hybrid milestone options.

Its advantage should not simply be a flat trade-price bonus.

Crafting creates exportable value; trade provides markets and imported inputs.

Pure transit/tariff trade may be viable only with exceptional geography.

### External world abstraction

The outside world should have enough state to generate believable pressure without becoming another strategy simulation.

Possible regional variables:
- food abundance;
- trade stability;
- disease pressure;
- security;
- merchant activity;
- selected resource availability.

These may shift seasonally and through events.

### Anti-exploit principles

Trade should not permit infinite arbitrage, unlimited emergency imports, trivial avoidance of specialization weaknesses, or predictable free profit from price cycling.

Safeguards include:
- buy/sell spread;
- finite market volume;
- trade capacity;
- transport friction;
- changing regional conditions;
- event risk.

### Design principle

> **Trade turns surplus into flexibility, but dependence on the outside world creates its own risk.**

Local production remains strategically valuable, while specialized settlements may deliberately rely on imports where economics and geography support it.


### Hidden market uncertainty and forecasting progression

The Regional Market does not need to be perfectly predictable from the start.

Some future market movements, route disruptions, harvest outcomes, and availability changes may be determined by hidden randomness.

The player gains increasing access to forecasts through meta progression, institutions, specialists, and research.

Forecast quality may progress from:
- current-price information only;
- qualitative warnings;
- broad ranges/probabilities;
- improved seasonal projections;
- highly accurate short-term forecasts at deep progression.

Information itself is therefore a progression reward. Forecasting reduces uncertainty without completely removing late-game risk.

### Regional investment

Trade-dependent settlements may invest Coin, materials, or administrative effort into the surrounding region.

Possible investments include roads, bridges, caravan security, depots, merchant incentives, regional production support, and trade-corridor development.

These may improve Trade Capacity, market depth, buyer/seller volume, route reliability, regional prosperity, and contract quality.

This is especially important for a **pure Trade City** ultra-specialization: it cannot extract unlimited wealth from a poor region forever and must help create the economy that supports its own scale.

Regional investment remains abstract initially and does not require a regional map.

### Pure Trade City

Pure trade is a valid extreme specialization under suitable conditions.

It may rely heavily on merchant activity, tariffs, warehousing, finance, contracts, imported necessities, and regional market depth.

It should generally require exceptional geography plus substantial investment in regional prosperity and infrastructure.

### Banking and finance

Banking exists in the broader game and overlaps multiple systems.

Administration-oriented finance may include treasury management, public borrowing, a Mint, coinage/monetary control, state debt, and taxation-related finance.

Trading-Crafting-oriented finance may include merchant banking, loans, commercial credit, investment ventures, and period-appropriate shares or debt instruments.

The full banking/monetary system is deferred to a dedicated future design system.

A modern stock market is not assumed; merchant ventures, partnerships, bonds/debt instruments, or shares can provide similar gameplay in a more fitting form.



## Decision 016 — Ambitions, Difficulty, and Run Setup

**Status: Accepted at system level; exact multipliers, Ambition tiers, slot unlock requirements, and completion pacing remain open.**

### Core principle

Run setup should give the player a meaningful reason to approach each settlement differently without becoming a complicated pre-run build system.

The preferred structure is a hybrid:

1. a clear **base Difficulty** setting;
2. a small number of optional **Ambitions**;
3. later, geography/region and other unlocked run conditions.

### First-run simplicity

The first run should have little or no setup complexity.

Possible first-run structure:
- fixed/default region;
- Standard difficulty;
- no Ambition choice, or one simple introductory Ambition.

Additional difficulty levels, Ambition slots, rerolls, regions, and challenge combinations can unlock through meta progression and achievements.

### Base difficulty

Difficulty is a global run-level setting rather than dozens of mandatory sliders.

Provisional examples:
- Standard
- Challenging
- Hard
- Severe
- Extreme

Names and number of levels remain open.

Higher difficulty should primarily increase **external/progression pressure**, such as:
- earlier World Pressure milestones;
- faster Challenge Tier progression;
- larger Event Pressure Budgets;
- more severe crisis eligibility;
- harsher regional conditions;
- weaker forecasting;
- tighter starting conditions;
- less forgiving market availability.

Difficulty should avoid arbitrary universal penalties such as `Food production -30%` unless a specific mode is intentionally built around that constraint.

### Difficulty rewards

Difficulty increases Legacy Point rewards **after** the diminishing score-to-LP conversion.

Conceptually:

Score
→ diminishing base Legacy Points
→ difficulty multiplier
→ Ambition rewards/modifiers

Higher difficulty may also affect score itself if needed for records, but score and Legacy reward multipliers should remain separately tunable.

### Ambitions

Ambitions are optional commitments that give a run a specific secondary objective.

Examples:
- Breadbasket — achieve a major Food surplus at a target population.
- City of Scholars — maintain a large Scholar population / University capability.
- Open Gates — accept refugee/immigration opportunities while reaching a population target.
- Stone and Iron — reach Mining specialization tiers and export a target amount.
- Pious City — maintain major religious institutions and social support.
- Commercial Hub — reach high trade volume or regional market influence.

Ambitions should primarily reward Legacy Points, with additional achievements, unlocks, or score modifiers for difficult sets.

### Ambition selection

The preferred initial structure is an **Ambition draft** rather than unrestricted catalogue selection.

At run setup, the game offers a small random set of Ambitions from the unlocked pool.

The player chooses one or more depending on progression.

This reduces repetitive farming of the mathematically easiest Ambition while still giving meaningful agency.

Meta progression may unlock:
- more Ambition choices in the draft;
- additional active Ambition slots;
- a limited Ambition reroll;
- more advanced Ambition categories.

Exact numbers remain open.

### Ambition slots

A new player should begin with only a small number of active Ambitions, provisionally one.

Later progression may allow two or three simultaneous Ambitions.

Taking more Ambitions creates more potential reward but also more competing objectives.

The maximum should remain small enough that the player remembers them without constantly checking a checklist.

### Ambition commitment

Selected Ambitions are locked when the run begins.

They cannot normally be swapped mid-run.

Failing an Ambition does not end the run; it only forfeits that Ambition's reward.

This keeps them optional goals rather than victory conditions.

### Ambition difficulty

Ambition rewards should scale according to how difficult the goal is under the current run conditions.

Factors may include:
- base difficulty;
- geography;
- starting modifiers;
- other active Ambitions;
- Primary Specialization conflict;
- World Pressure settings.

A Breadbasket Ambition in fertile farmland should be worth less than the same Ambition in rocky highlands.

The exact calculation can remain hidden or summarized as an Ambition reward multiplier.

### Contradictory Ambitions

Deliberately difficult combinations should be valid and potentially highly rewarding.

Examples:
- Breadbasket in poor farmland;
- Scholar city with limited trade/Paper access;
- population-growth Ambition under restrictive migration conditions.

Especially difficult combinations may grant:
- greater Legacy rewards;
- score multipliers;
- achievements;
- unique unlocks.

### Ambitions and specialization

Ambitions should strongly influence player goals without hard-locking specialization.

A Farming Ambition makes Agriculture attractive, but the player may still solve it through trade, research, hybrid development, or an unusual strategy if the requirements allow it.

Some Ambitions may explicitly require a specialization tier.

### Repeat Ambitions

Repeating an already-completed easy Ambition should remain possible, but first-time completion should be more valuable.

Possible structure:
- repeatable Legacy Point reward;
- first completion achievement/unlock;
- completion tiers for increasingly difficult versions;
- additional rewards for completing it on higher difficulty.

This allows Ambitions to remain useful without turning them into one-time checklist content.

### Ambition tiers

Many Ambitions may have multiple tiers.

Example:

Breadbasket I
→ reach 1,000 population with 125% Food production

Breadbasket II
→ reach 3,000 population with 150%

Breadbasket III
→ reach 8,000 population with 175% under higher Challenge Tier pressure

Exact values remain open.

Higher tiers can unlock over meta progression or after completing lower tiers.

### Difficulty unlock progression

Higher difficulty settings should unlock gradually.

Example structure:
- Standard available initially;
- Challenging unlocked after first meaningful run;
- Hard after reaching a certain Challenge Tier or score;
- later modes through achievements.

This avoids exposing an inexperienced player to settings they cannot yet interpret.

### No Legacy loadout

Run setup must not become a Legacy build system.

Permanent Legacy Talents remain always active.

The run setup changes the challenge and goals, not which permanent bonuses the player equips.

### Optional challenge modifiers

A later layer of optional challenge modifiers may be added if useful.

Examples:
- poor harvest region;
- limited immigration;
- unstable trade;
- harsher winters.

These should not be required for the basic difficulty system.

If implemented, they should function as advanced challenge options with proportional score/Legacy rewards rather than as a mandatory list of sliders.

### Run summary

Before starting, the player should see a concise summary:

- Region / starting geography
- Difficulty
- selected Ambitions
- major known starting modifiers
- Legacy Point multiplier
- important special rules

The player should understand what challenge they are accepting without needing to inspect hidden formulas.

### Design principle

> **Difficulty determines how hostile the world is; Ambitions determine what the player is trying to accomplish inside that world.**

Run setup should create direction and replayability while leaving the town's actual specialization and strategy to emerge during play.



## System 16 Revision Notes

**Status: Still under discussion; these revisions supersede conflicting earlier proposal text.**

### Score and Legacy Point conversion

The preferred direction is now **linear or near-linear score-to-Legacy Point conversion**, not diminishing conversion.

Reasoning:
- escalating World Pressure and Challenge Tiers already make additional score increasingly difficult to earn;
- higher Run Difficulty independently makes strong score harder to achieve;
- increasingly expensive Legacy Talents provide the long-term progression sink;
- a great run should feel visibly more valuable than the previous one.

The exact conversion ratio remains open.

### Intended full-progression pacing

A provisional target is roughly **30–50 total runs to reach 100% meta progression**, potentially fewer depending on average run length and player success.

This target should be calibrated after prototype data exists.

100% progression here means ordinary Legacy Talents and major progression systems/features; optional challenge achievements may extend beyond that.

### Double-counting difficulty

Run Difficulty and dynamic Challenge Tier should both independently improve score gain.

Conceptually:

Monthly Score
= Civilization / Management Value
× Challenge Tier Multiplier
× Run Difficulty Multiplier

Exact formula remains open.

This intentionally rewards:
1. choosing a harder ruleset before the run;
2. surviving far enough within that ruleset to reach higher Challenge Tiers.

### Ambition challenge bonuses

Completing Ambitions that conflict with:
- each other;
- geography;
- other known run constraints

should provide a visible **Challenge Bonus**.

This may be an end-of-run score multiplier or additive bonus.

The end screen should explicitly show that the player was rewarded for taking on the harder combination.

### Ambition scalability

Ambitions need explicit scaling so they do not become trivial after substantial meta progression.

Preferred tools include:
- Ambition tiers;
- higher target thresholds;
- minimum Difficulty requirements;
- Challenge Tier requirements;
- additional conditions;
- harder variants.

Lower tiers may remain repeatable but should become less strategically valuable than pushing higher tiers.

### Ambition selection

The previous randomized Ambition draft is no longer preferred.

Ambitions should generally be **freely chosen from the currently unlocked roster**.

Reason:
- if Ambitions are random, players may intentionally abandon/restart runs until they receive the goal they wanted;
- Ambitions are the main source of intentional direction at run start;
- another system should provide unpredictability instead.

### Preferred run-setup order

Current recommendation:

1. **Choose unlocked Run Difficulty.**
2. **Generate and reveal the Region / starting geography.**
3. **Choose Ambitions freely from the unlocked roster after seeing the Region.**
4. Show geography–Ambition synergies/conflicts and their potential Challenge Bonuses.
5. Confirm/start the actual simulation.

The Region provides unpredictability.
The Ambition provides agency.

This gives the player a meaningful idea of what they want to attempt without letting them fully pre-design the settlement.

### Region selection

Regions are not freely selected by default in the current proposal.

They are generated randomly from the unlocked pool after Difficulty is chosen.

Meta progression may later provide:
- broader region pools;
- limited region rerolls;
- challenge-region unlocks;
- special modes with direct region selection.

These are not yet accepted.

### Onboarding

Advanced systems should unlock progressively over many runs.

This includes:
- Ambitions;
- additional Ambition slots;
- Ambition tiers;
- specialization systems;
- harder Difficulty levels;
- more complex laws/reforms;
- advanced research;
- additional Regions;
- finance;
- deeper forecasting.

Long onboarding is acceptable because the full game is already expected to be complex.

The first runs should deliberately expose only a subset of the final system set.



### Ambition slot interface

The Ambition setup screen uses a small number of clearly visible slots.

Provisional structure:
- Slot 1 available early;
- Slot 2 visibly locked behind a milestone, achievement, or meta-progression requirement;
- Slot 3 visibly locked behind a deeper requirement.

Locked slots remain visible so the player understands that additional Ambition capacity is part of long-term progression.

For each unlocked slot:
1. the player selects an Ambition freely from the unlocked catalogue;
2. the player selects the highest currently available tier they wish to attempt;
3. locked higher tiers remain visible with their unlock requirements.

The Ambition catalogue should also show future locked Ambitions and explain the achievement, milestone, specialization, difficulty, or meta requirement needed to unlock them.

This makes Ambition progression aspirational rather than hidden.

### Deliberate Region selection as a late unlock

Random Region generation remains the default because it provides the main unpredictable run-start constraint.

Later progression may unlock a setting that allows the player to deliberately select a Region.

This is especially useful for:
- limit testing;
- targeted achievement attempts;
- specialization experiments;
- controlled balance testing;
- extreme Ambition/geography combinations.

Choosing the Region should reduce the run's score multiplier or Region Challenge Bonus compared with accepting a randomly generated Region.

This preserves the value of adapting to randomness while still allowing advanced players to construct deliberate challenge runs.



## Decision 017 — Starting Geography, Regions, and Settlement Conditions

**Status: Accepted at system level; exact archetypes, traits, resource-potential formulas, connection scaling, and challenge values remain open.**

### Core principle

The Region is the main unpredictable run-start element.

It should create a different strategic problem each run without simply rolling a "good map" or "bad map."

The player should usually adapt to geography rather than restart until an optimal region appears.

### Run-start order

The accepted direction from System 16 remains:

1. choose unlocked Run Difficulty;
2. randomly generate and reveal the Region;
3. inspect its geography, potentials, risks, and challenge rating;
4. choose Ambitions in response;
5. begin the settlement.

Deep progression may later allow direct Region selection at a reduced score multiplier.

### Region structure

The preferred scalable structure is:

**Region Archetype + Geographic Traits + Resource Potentials**

This allows many combinations without requiring hundreds of individually handcrafted region definitions.

### Region archetypes

A Region Archetype defines the broad character of the land.

Provisional examples:

- Fertile Basin
- Forested Uplands
- Rocky Highlands
- River Crossing / River Valley
- Open Plains
- Wetlands / Marshland

The initial release does not need all of these.

Each archetype should have recognizable advantages, limitations, event tendencies, and infrastructure implications.

### Geographic traits

Each generated Region may receive a small number of additional traits.

Examples:

- Deep Ore Veins
- Thin Soil
- Abundant Springs
- Floodplain
- Ancient Road
- Dense Old-Growth Forest
- Wind-Exposed
- Harsh Winters
- Mild Winters
- Isolated
- Natural Crossing
- Poor Drainage

Traits should generally create strategic texture rather than simply stack positive multipliers.

A region should normally have only a few important traits so the player can remember them.

### Resource potentials

Geography should influence both **production efficiency** and **how far an industry can scale locally**.

Visible regional potentials may include:

- Farmland
- Timber
- Stone
- Ore / Minerals
- Water
- Trade Access

These may be shown with readable ratings such as:

Poor / Limited / Average / Good / Rich / Exceptional

Exact scale remains open.

### Soft capacity rather than hard prohibition

Poor resource potential should not normally mean:

> Farming impossible.

Instead it should mean that farming becomes progressively less efficient or more expensive as the settlement tries to scale beyond what the land naturally supports.

Example:

A Rocky Highlands region may support enough agriculture for an early village, but feeding a large city locally becomes increasingly labor- and infrastructure-intensive.

This preserves strategic freedom while making geography matter strongly at scale.

### Industry scaling pressure

Resource potential can act as a soft carrying capacity.

Below local potential:
- production operates efficiently.

Near potential:
- expansion becomes more costly.

Beyond potential:
- diminishing returns, additional infrastructure, imports, research, or specialist methods become necessary.

This can apply differently to:
- agriculture;
- forestry;
- mining;
- water systems;
- trade access.

Exact formulas remain open.

### Geography and specialization

Geography encourages specialization indirectly.

Examples:

- rich farmland makes agricultural investment naturally attractive;
- mineral-rich highlands make Mining easier to develop;
- river access encourages Trading-Crafting;
- strong institutional geography is generally not required for Scholar or Religious specialization, allowing those identities to emerge across many regions.

Geography should not directly select or lock a Primary Specialization.

Specialization recognition still depends on what the player actually builds and does.

### Geography and hybrid strategies

A region should support unexpected solutions.

Examples:

Rocky Highlands + Breadbasket Ambition:
- terrace farming;
- irrigation research;
- heavy food imports;
- agricultural institutions;
- high Challenge Bonus.

Forested Uplands + Trading-Crafting:
- timber;
- Paper;
- tools;
- finished goods;
- merchant exports.

River Valley + Mining:
- weaker local ore but excellent import/export logistics may support a processing-focused mining/craft economy.

### Climate and environmental risk

Regions affect probability and severity distributions rather than guaranteeing fixed events.

Possible dimensions:
- winter severity;
- drought likelihood;
- flood likelihood;
- fire risk;
- disease/environmental exposure;
- transport disruption.

A River Valley may have excellent Food/Trade potential but meaningful flood risk.

A dense forest may offer abundant Wood but increased fire exposure.

A highland region may have strong minerals but harsher winters and transport difficulty.

### Forecasting

The player should see the known geographic baseline at run start.

Example:

> Winters: Usually harsh
> Flood risk: Low
> Drought risk: Moderate

Exact seasonal outcomes can still use hidden randomness.

Forecasting systems and meta progression may later provide better short-term information.

### Infrastructure interaction

Geography changes the cost or value of infrastructure.

Examples:

- highlands make roads more expensive;
- river regions may require bridges but gain high trade capacity;
- wetlands make sanitation/drainage difficult;
- abundant springs improve early water access;
- isolated regions require greater investment to connect to markets.

Infrastructure can mitigate geography but should not erase it completely.

### Starting conditions and remnants

Some geographic traits may provide starting-world features rather than pure modifiers.

Examples:
- abandoned quarry;
- old road;
- ruined bridge;
- existing well;
- neglected shrine;
- former trading post.

These can create early opportunities or projects.

They should remain limited to avoid turning Region generation into a map-object collection game.

### Region challenge rating

Some Region combinations will inevitably be harder overall.

The game should recognize this rather than pretending every Region is perfectly equal.

A Region may therefore provide a visible **Region Challenge Bonus** to score.

The rating should account for broad environmental difficulty, not whether the Region happens to match the player's later-selected Ambition.

Ambition/geography conflict creates an additional separate Challenge Bonus.

Exact scoring remains open.

### Anti-restart design

To reduce "reroll until perfect" behavior:

- most Regions should contain meaningful strengths and weaknesses;
- strengths should usually imply a strategic direction rather than universal power;
- inherently harsher Regions should grant more score;
- Ambitions are chosen after Region reveal, so the player can react intelligently;
- random Region receives full score potential;
- later manual Region selection receives a reduced score multiplier.

A limited Region reroll may be unlocked through deep Legacy progression, but is not required initially.

### Progressive Region unlocks

The first runs should use a small, readable Region pool.

Additional archetypes and unusual traits can unlock through:
- milestones;
- achievements;
- meta progression;
- Difficulty progression.

This keeps onboarding manageable and lets later runs become geographically more diverse.

### Regional investment

Regional investment from the Trade system can improve:
- roads;
- market access;
- security;
- regional wealth;
- Trade Capacity.

It should not change fundamental geography.

A mountain region remains mountainous even after excellent roads are built.

### Visual implications

Region should eventually influence the settlement's visual surroundings and procedural/modular town presentation.

Examples:
- highland backdrop;
- forest edge;
- river;
- wet ground;
- broad farmland;
- rocky terrain.

The simulation must not depend on final visual technology.

### Design principle

> **Geography should tell the player what is easy, what is expensive, and what is risky — but rarely what is impossible.**

A Region creates constraints and opportunities. The player's settlement identity emerges from how they respond to them.


### Abstract connection distance

Geography should also describe how far the settlement is from major transport features, not only whether those features are inside the settlement.

Important cases include:
- direct access to a navigable river;
- nearby access to a river or river town;
- moderate distance to a major trade corridor;
- long or difficult connection to regional transport.

This remains abstract initially rather than requiring a detailed regional map.

Infrastructure projects scale with both terrain difficulty and effective connection distance.

Examples:
- Rocky Highlands close to a navigable river may need only a few expensive road/bridge projects before gaining strong regional access.
- Open Plains far from major waterways may have cheap individual roads but require much longer development before reaching equivalent Trade Capacity.

Infrastructure can improve access substantially without changing the underlying geography.

### Progressive geographic knowledge

The player receives enough Region information at run start to make an informed Ambition choice.

Meta progression, research, institutions, or specialists may later improve:
- resource-potential clarity;
- climate and hazard estimates;
- understanding of trade connections;
- seasonal and short-term forecasts.

Progression may therefore improve information quality as well as raw capability.

### Manual Region selection

Random Region generation remains the intended full-reward/default mode.

A later unlock may permit direct Region selection for limit testing, targeted achievements, controlled specialization experiments, and deliberate extreme challenges.

Direct Region selection should reduce score, and therefore Legacy Point gain, enough that repeatedly selecting the optimal Region is not an efficient progression strategy.

### Initial implementation simplification

No resource depletion is required initially.

Geography can first operate through:
- buffs/debuffs;
- resource-potential modifiers;
- infrastructure scaling;
- event weighting;
- progression/research mitigation.

Deforestation, soil exhaustion, mine depletion, and similar systems remain optional later additions.

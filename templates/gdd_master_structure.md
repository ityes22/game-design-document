# GDD Master Structure — 19-Section Reference

This document defines the complete structure, required elements, recommended word counts, and section dependencies for a publisher-grade Game Design Document. Use this as the canonical reference when generating or reviewing a GDD.

---

## Section Dependency Map

```
[1. Cover Page]
      ↓
[2. Executive Summary] ← references all sections
      ↓
[3. Game Overview] ──────────────────────────────────────────┐
      ↓                                                       │
[4. Core Gameplay Loop] ──→ informs ──→ [5. Game Mechanics]  │
      ↓                                       ↓              │
[6. Progression System] ←─────────────────────┘              │
      ↓                                                       │
[7. Content Design] ←── informed by ── [8. Narrative]        │
      ↓                                       ↓              │
[9. UX & Interface] ←─────────────────────────┘              │
      ↓                                                       ↓
[10. Art Direction] ──→ [11. Audio] ── [12. Multiplayer] ────┘
      ↓
[13. Monetization] ──→ [14. Economy]
      ↓
[15. Technical Requirements] ←── informs ── [12. Multiplayer]
      ↓
[16. Competitive Analysis] ──→ informs ── [3. Game Overview]
      ↓
[17. Development Roadmap] ←── scope from ── all prior sections
      ↓
[18. Risk Assessment] ←── risks from ── all prior sections
      ↓
[19. Appendices]
```

---

## SECTION 1 — COVER PAGE

**Recommended Length:** N/A (layout, not prose)
**Required:** Yes
**Category:** Framing

### Required Elements
- [ ] Game title (primary heading, largest text on page)
- [ ] Tagline or logline (1 sentence, italic)
- [ ] Genre | Platform(s) | Target Audience (one formatted line)
- [ ] Document version number (format: v0.1, v0.2, v1.0)
- [ ] Document date (Month YYYY)
- [ ] Studio / developer name
- [ ] Lead designer name(s)
- [ ] Confidentiality notice: *"CONFIDENTIAL — For internal use and authorized partners only. Do not distribute without written permission."*
- [ ] Version history table (Version | Date | Author | Summary of Changes)

### Anti-Patterns
- Cluttered with too much information (save content for Executive Summary)
- Missing version number (GDDs are always versioned documents)
- No confidentiality notice on commercial documents

---

## SECTION 2 — EXECUTIVE SUMMARY

**Recommended Length:** 400–600 words
**Required:** Yes
**Category:** Overview

### Required Elements
- [ ] Elevator pitch (2 sentences maximum — what is the game and why does it matter?)
- [ ] Unique Value Proposition (3 bullet points — what makes this worth playing?)
- [ ] At-a-Glance table:

| Field | Value |
|-------|-------|
| Genre | [primary genre] / [secondary] |
| Platform | [list all] |
| Target Audience | [age range], [experience level] |
| Players | [single-player / multiplayer / both] |
| Monetization | [revenue model] |
| Development Status | [concept / pre-production / production] |
| Target Release | [quarter/year or TBD] |

- [ ] Comparable titles (2-3 titles) with differentiation statement per title
- [ ] Team overview (size, relevant experience, key roles filled)
- [ ] What problem or gap in the market does this game address?

### Writing Standard
Write as if this is the only section a publisher will read. It must make a compelling case for the game's existence. Avoid enthusiasm without evidence: "This game will revolutionize the genre" is worthless. "No current roguelike targets the 35+ casual demographic — we validated this gap with 200 survey responses" is useful.

### Anti-Patterns
- Re-stating the game title in the first sentence
- Listing features without explaining why they matter
- Generic comp titles without differentiation ("Like Minecraft but better")

---

## SECTION 3 — GAME OVERVIEW

**Recommended Length:** 600–1,000 words
**Required:** Yes
**Category:** Vision

### Required Elements
- [ ] High concept statement (single most important sentence about the experience)
- [ ] Core fantasy (what power/emotional state does the player inhabit?)
  - Example: "The player feels like a master detective who can unravel any lie"
  - Example: "The player feels like the last survivor of an impossible war"
- [ ] Experience pillars (3-4 named pillars, one sentence each)
  - Everything in the game should support at least one pillar
  - Example pillars: "Mastery Through Failure" | "Emergent Stories" | "15-Minute Sessions"
- [ ] Session flow narrative (walk through one complete play session in present tense)
- [ ] Comparable titles analysis: for each comp, explain: what you take from it AND what you do differently
- [ ] Target demographic detail: primary audience + secondary audience

### Experience Pillar Format
```
## Pillar 1: [Name]
[One sentence definition]
[One sentence of what this means for design decisions]

Example feature that supports this pillar: [specific example]
```

### Anti-Patterns
- Experience pillars that are synonyms of each other
- Comparable titles listed without differentiation
- High concept that describes features rather than experience ("A game where you craft items and fight monsters" vs. "The feeling of building an empire from nothing")

---

## SECTION 4 — CORE GAMEPLAY LOOP

**Recommended Length:** 800–1,500 words
**Required:** Yes
**Category:** Systems

### Required Elements
- [ ] Micro loop definition (the 2–5 minute cycle): what the player does and experiences
- [ ] Macro loop definition (the 20–60 minute cycle): how micro loops combine into a session
- [ ] Meta loop definition (the long-term arc, days to months): what keeps players coming back
- [ ] Loop diagram for each tier (ASCII text diagram)
- [ ] Session length target and how the loop is designed to support it
- [ ] Engagement hooks: what psychological mechanisms create "one more run" / return sessions
- [ ] Loop failure states: how does the loop handle player loss/failure gracefully?
- [ ] Onboarding into the loop: how does a new player learn the loop?

### Loop Diagram Format
```
[DIAGRAM: Micro Loop — Combat Encounter]
Spawn Room → Survey Threats → Choose Approach
     ↑              ↓               ↓
Return to Hub ← Collect Loot ← Execute + Survive
     ↓
[Macro Loop Trigger: 5 rooms completed → Hub visit]
```

### Engagement Hook Categories to Address
- **Completion motivation:** Near-miss states, progress bars, "just one more"
- **Variable reward:** Randomized loot, proc-gen content, surprise moments
- **Social motivation:** Leaderboards, co-op, sharing/showing off
- **Mastery motivation:** Skill expression, optimization paths, hidden depth

---

## SECTION 5 — GAME MECHANICS

**Recommended Length:** 1,500–3,000 words
**Required:** Yes
**Category:** Systems

### Required Elements
Every distinct mechanic must be documented with all 8 fields. See `mechanics_specification_template.md` for the per-mechanic format.

**Mechanics Inventory (document all that apply):**
- [ ] Primary interaction mechanic (combat, building, solving, etc.)
- [ ] Movement system (walking, running, jumping, dashing, climbing)
- [ ] Resource management (health, stamina, mana, ammo, energy, inventory)
- [ ] Upgrade/modification mechanic (skills, equipment, enhancements)
- [ ] Social/interaction mechanic (dialogue, trading, cooperation)
- [ ] Economy/transaction mechanic (buying, selling, crafting)
- [ ] Procedural/randomization systems (if applicable)
- [ ] Time/turn management (real-time, turn-based, hybrid)
- [ ] Environmental interaction (destructibility, physics, traversal)

### Cross-Reference Requirements
Each mechanic must note which other mechanics it interacts with:
- "Dodge Roll consumes Stamina [→ see Resource Management]"
- "Critical Hit applies the Bleed status effect [→ see Status Effects]"

---

## SECTION 6 — PROGRESSION SYSTEM

**Recommended Length:** 800–1,500 words
**Required:** Yes (reduced scope for arcade/casual)
**Category:** Systems

### Required Elements
- [ ] Progression hierarchy (what levels/upgrades/unlocks exist, from top to bottom)
- [ ] XP/currency earn rates per session for 3 archetypes:
  - Casual: 30 min/day, 60% quest completion efficiency
  - Average: 60 min/day, 80% efficiency
  - Hardcore: 120+ min/day, 95%+ efficiency
- [ ] Time-to-milestone table (key unlocks with target days per archetype)
- [ ] Power curve description: early game / mid game / late game feel
- [ ] XP formula (if level-based): `XP_required(level) = base × multiplier^(level-1)`
- [ ] Content gates: which content unlocks at which level/progression point and why
- [ ] Catch-up mechanisms: how do returning or late players catch up?
- [ ] Prestige/endgame systems: what happens at max level?

### Player Archetype Timeline Table Format
| Milestone | Unlock | Casual (days) | Average (days) | Hardcore (days) |
|-----------|--------|---------------|----------------|-----------------|
| First Upgrade | Skill Point 1 | Day 1 | Day 1 | Day 1 |
| Tier 2 Content | Area 2 | Day 7 | Day 4 | Day 2 |
| ...continues | ... | ... | ... | ... |

---

## SECTION 7 — CONTENT DESIGN

**Recommended Length:** 800–1,500 words
**Required:** Yes
**Category:** Content

### Required Elements
- [ ] Content scope overview (total launch content + post-launch cadence)
- [ ] Levels/zones/worlds: count, naming, thematic breakdown, gameplay distinctions
- [ ] Enemy/NPC types: count, categories (common/elite/boss), design principles
- [ ] Items/equipment: categories, rarity tiers, count target per category
- [ ] Abilities/skills: count, categories, unlock gating
- [ ] Procedural content rules (if applicable): what generates and what doesn't
- [ ] Content creation guidelines: what makes a good [level/enemy/item] in THIS game?
- [ ] Content minimum bar for launch (MVP content list)

### Content Scope Table Format
| Content Type | Launch Target | Post-Launch (per quarter) | Notes |
|-------------|---------------|--------------------------|-------|
| Levels/Maps | 20 | 3–5 | Hand-crafted |
| Enemy Types | 15 | 2 | Includes variants |
| Items | 80 | 15 | Includes set items |

---

## SECTION 8 — NARRATIVE & WORLD

**Recommended Length:** 500–1,200 words (can be 100 words for narrative-light games)
**Required:** No (reduced to 1 paragraph for narrative-light games)
**Category:** Creative

### Required Elements (narrative-present games)
- [ ] Setting overview (world, time period, tone)
- [ ] Lore depth classification: Surface (flavor text only) / Medium (backstory, factions) / Deep (branching narrative, VO)
- [ ] Story structure: Linear / Branching / Emergent / None
- [ ] Key characters: name, role, motivation (2-3 sentences each)
- [ ] How narrative integrates with gameplay (or explicit statement that it doesn't)
- [ ] Worldbuilding constraints (what is impossible in this world? establishes consistency)
- [ ] Writing tone guide: 3 adjectives + 2 reference titles for tone

### Narrative-Light Template
> "GAME TITLE has a minimal narrative framing. [One paragraph describing the setting and premise]. Narrative serves as flavor only — no story decisions, no branching dialogue, no character arcs. Lore delivered via: [item descriptions / environmental storytelling / loading screen tips]. Writing tone: [2 adjectives]."

---

## SECTION 9 — USER EXPERIENCE & INTERFACE

**Recommended Length:** 800–1,500 words
**Required:** Yes
**Category:** Systems / Design

### Required Elements
- [ ] Screen inventory (every unique screen in the game with entry/exit points)
- [ ] FTUE (First-Time User Experience) step-by-step flow:
  - Minutes 0–1: What does the player see and do?
  - Minutes 1–5: Core loop introduction
  - Minutes 5–15: First mastery moment
  - Minutes 15–30: Hook established, return motivation created
- [ ] HUD layout description (every persistent element, when it appears/disappears)
- [ ] Navigation hierarchy (how the player moves between all major screens)
- [ ] Accessibility requirements:
  - [ ] Minimum text size: 18px / 24pt at target resolution
  - [ ] Colorblind modes: Protanopia, Deuteranopia, Tritanopia
  - [ ] Subtitle support for all voiced content
  - [ ] Input remapping for keyboard/controller
  - [ ] Audio description support (if applicable)
- [ ] Mobile-specific (if applicable): thumb zone optimization, swipe gestures, portrait/landscape

### Screen Inventory Table Format
| Screen Name | Entry From | Exit To | Primary Action | Secondary Actions |
|-------------|------------|---------|----------------|-------------------|
| Main Menu | App launch, pause | New Game, Load, Settings, Store | Start game | — |
| HUD | Game start | Pause menu | Player actions | Map, inventory |
| ...continues | ... | ... | ... | ... |

---

## SECTION 10 — ART DIRECTION

**Recommended Length:** 500–800 words
**Required:** Yes
**Category:** Creative

### Required Elements
- [ ] Visual style statement (one paragraph — what the game LOOKS like and why)
- [ ] Influences list (3–5 references with specific elements borrowed from each)
- [ ] Color palette:
  - Primary colors (2-3): dominant background/environment colors
  - Secondary colors (2-3): character, enemy, interactive object colors
  - Accent colors (1-2): rewards, UI highlights, critical information
  - UI-specific colors: text, backgrounds, buttons, warnings
- [ ] Character art guidelines: proportions, detail level, silhouette principles
- [ ] Environment art guidelines: detail density, perspective, lighting philosophy
- [ ] UI art style: flat/skeuomorphic/illustrated, animation guidelines
- [ ] Animation style: fluid/snappy/weighty, key animation moments that must feel great
- [ ] Do NOT create list (visual styles explicitly banned from this game)

---

## SECTION 11 — AUDIO DESIGN

**Recommended Length:** 300–500 words
**Required:** Yes (even for scope constraint — state scope explicitly)
**Category:** Creative

### Required Elements
- [ ] Music direction: genre, reference artists/games, energy level per game state
  - Exploration: [description]
  - Combat/Tension: [description]
  - Victory/Reward: [description]
  - Menu/UI: [description]
- [ ] SFX philosophy: realistic vs. stylized, density target (sparse/medium/rich)
- [ ] Voice acting scope: None / UI barks only / Key moments / Full VO
- [ ] Adaptive audio: what gameplay events trigger music changes?
- [ ] Audio budget: expected music tracks count, SFX count, VO lines count

---

## SECTION 12 — MULTIPLAYER DESIGN

**Recommended Length:** 800–2,000 words
**Required:** Only for multiplayer games
**Category:** Systems

### Required Elements
- [ ] Network model: P2P / Client-Server / Dedicated Servers
- [ ] Tick rate target: 20 / 30 / 60 / 128 Hz (with rationale)
- [ ] Maximum concurrent players per session
- [ ] Matchmaking system: criteria, time targets, fallback behavior
- [ ] Lobby/party system: party size, party leader powers, cross-play support
- [ ] Social features: friends list, guilds/clans, chat (text/voice), reporting
- [ ] Anti-cheat approach: server-side validation, third-party (Easy Anti-Cheat, BattlEye)
- [ ] Platform requirements: PS Plus, Xbox Live Gold, Nintendo Online
- [ ] Latency tolerance: acceptable range (ms) per game type
- [ ] Disconnect handling: grace period, reconnect window, bot replacement

---

## SECTION 13 — MONETIZATION STRATEGY

**Recommended Length:** 600–1,200 words
**Required:** Yes
**Category:** Business

*Reference `templates/monetization_strategy_template.md` for full format.*

### Required Elements
- [ ] Revenue model selection with rationale
- [ ] Complete IAP catalog (name, price, value proposition)
- [ ] Premium currency conversion rate (if applicable)
- [ ] Battle pass structure (if applicable): tiers, prices, free vs. premium track value
- [ ] Ethical guidelines compliance checklist
- [ ] Regional pricing adjustments
- [ ] Projected KPIs: conversion rate target, ARPU target, LTV target

---

## SECTION 14 — ECONOMY DESIGN

**Recommended Length:** 600–1,200 words
**Required:** For F2P and games with significant economy systems
**Category:** Systems

### Required Elements
- [ ] All currency types with purpose classification
- [ ] Faucet/sink balance: Net Currency Flow = Σ(Faucets) − Σ(Sinks) target ≤ +5% inflation/month
- [ ] Daily earn rates per player segment (Free / Dolphin / Whale)
- [ ] Pricing architecture table: cost in currency for each category of purchase
- [ ] Inflation risk assessment and intervention triggers
- [ ] Exchange rate design (if multiple currencies convert between each other)

---

## SECTION 15 — TECHNICAL REQUIREMENTS

**Recommended Length:** 500–1,000 words
**Required:** Yes
**Category:** Engineering

*Reference `templates/technical_requirements_template.md` for full format.*

### Required Elements
- [ ] Engine selection with rationale
- [ ] Platform targets with certification requirements
- [ ] Minimum / recommended hardware specs
- [ ] Network architecture overview (if applicable)
- [ ] Third-party services and SDKs list
- [ ] Key technical risks with mitigations
- [ ] Performance budget targets

---

## SECTION 16 — COMPETITIVE ANALYSIS

**Recommended Length:** 600–1,000 words
**Required:** Yes
**Category:** Business

*Reference `templates/competitive_analysis_template.md` for full format.*

### Required Elements
- [ ] 3–5 direct competitors analyzed
- [ ] Feature comparison matrix (markdown table)
- [ ] Market positioning map description
- [ ] Differentiation analysis per competitor
- [ ] Market gap statement

---

## SECTION 17 — DEVELOPMENT ROADMAP

**Recommended Length:** 400–800 words
**Required:** Yes
**Category:** Production

### Required Elements
- [ ] Prototype milestone: scope, team, success criteria
- [ ] Vertical Slice milestone: scope, team, success criteria
- [ ] Alpha milestone: feature complete definition, known gaps
- [ ] Beta milestone: content complete, testing focus areas
- [ ] Launch milestone: gold criteria, platform submission requirements
- [ ] Post-Launch: live ops cadence, content update schedule (if F2P)
- [ ] Critical path items: what must be done sequentially vs. in parallel?

---

## SECTION 18 — RISK ASSESSMENT

**Recommended Length:** 400–600 words
**Required:** Yes
**Category:** Production

### Risk Register Table Format
| # | Risk Description | Category | Probability | Impact | Mitigation Strategy |
|---|-----------------|----------|-------------|--------|---------------------|
| 1 | Core loop not fun in vertical slice | Design | Medium | High | Early paper prototype, 5 external playtest sessions before vertical slice |
| 2 | Engine upgrade breaks key systems | Technical | Low | High | Lock engine version at production start, maintain branch for updates |
| ... | ... | ... | ... | ... | ... |

**Risk Categories:** Design / Technical / Market / Team / External / Financial

---

## SECTION 19 — APPENDICES

**Recommended Length:** As needed
**Required:** Yes (at minimum a Glossary)
**Category:** Reference

### Required Appendices
- [ ] Glossary: game-specific terms, acronyms, design jargon used in the document
- [ ] Revision History: Version | Date | Author | Section Changed | Summary
- [ ] Open Questions Log: Question | Owner | Target Resolution Date | Status

### Optional Appendices (include as needed)
- Data tables referenced in main sections
- Research citations and market data sources
- Platform submission requirement checklists
- Third-party SDK documentation references
- Art asset naming convention standards
- Localization requirements by region

---

## Document Health Checklist

Before considering a GDD complete, verify:

- [ ] Every section present or explicitly marked "N/A — [reason]"
- [ ] All cross-references between sections are accurate
- [ ] No section uses the words "various," "different," or "some" without specific counts
- [ ] Every mechanic has at minimum: description, 2 concrete parameters, player feedback
- [ ] Open questions are in the Open Questions Log, not silently omitted
- [ ] Version number and date are current on cover page
- [ ] Table of Contents is accurate (page numbers match if paginated)
- [ ] All comparable game titles are spelled correctly and cited accurately
- [ ] No section promises features that contradict another section

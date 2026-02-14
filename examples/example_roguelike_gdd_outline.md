# Example GDD Outline: VOID CARTOGRAPHER
### Genre: Roguelike Deckbuilder | Platform: PC (Steam), planned console | Version: v0.2

> **FICTIONAL EXAMPLE** — This outline is entirely fictional and created for reference purposes only. All studio names, game titles, market statistics, KPI targets, revenue figures, and player counts are fabricated examples. Do not use any numeric claims from this document in real business contexts without independent verification.

---

This is a complete 19-section GDD outline for a roguelike deckbuilder. Use this as a reference for what each section should contain in a genre that emphasizes run-based progression, permadeath, and meta-progression. Section descriptions show what would be written in the full document — not the content itself, but the substance and scope.

---

## 1. Cover Page
**Title:** VOID CARTOGRAPHER
**Tagline:** "Every map is a memory. Every death rewrites the world."
**Genre:** Roguelike Deckbuilder with Persistent World Elements
**Platform:** PC (Steam), Nintendo Switch (Q2 2026)
**Audience:** Ages 22–40, midcore PC gamers with 100+ hours in Slay the Spire or Hades
**Version:** v0.2 | **Date:** January 2025 | **Studio:** Hollow Signal Games
**Confidentiality:** For internal use and authorized partners only.

---

## 2. Executive Summary
**What this section contains:** A 500-word pitch arguing why Void Cartographer needs to exist. Elevator pitch establishes the core hook — a narrative roguelike where the player's runs collectively and permanently alter a shared online world state visible to all 100,000+ concurrent players. USPs table covers: (1) first roguelike with persistent multiplayer world consequence, (2) narrative-first deckbuilding where cards are literal memories, (3) community-dependent final act. Comparable titles: Slay the Spire (mechanical foundation), Hades (narrative integration), Outer Wilds (mystery/discovery). Team: 6 developers, lead designer shipped Monster Train. Development status: vertical slice complete.

---

## 3. Game Overview
**What this section contains:** High concept — "A solo roguelike where your failures teach the world." Core fantasy: the player feels like an archivist reconstructing history from fragments, with the growing realization that they are the reason history needs reconstructing. Experience pillars:
1. **Meaningful Death** — every run failure leaves a permanent mark on the shared world
2. **Discovery Through Repetition** — the world reveals itself across runs, not within them
3. **15-Minute Mastery** — each run is completable in 15–25 minutes for mobile parity
4. **Collective Consequence** — solo actions accumulate into multiplayer-scale world changes

Session flow walkthrough: player selects a Memory Archetype, enters a procedurally generated dungeon of 5 rooms, builds a deck from memory fragments, reaches a boss encounter, either extracts the Memory Core (narrative progress) or suffers cascade failure (permanent world-state change + meta-progression unlock). Total session: 15–25 minutes.

---

## 4. Core Gameplay Loop
**What this section contains:**

**Micro Loop (2-4 minutes per room):**
- Enter room → read environment for enemy telegraphs → draft 3 cards from Memory Hand
- Execute card combos against 1-3 enemies using 3 Energy per turn
- Survive encounter → collect Memory Fragments (currency + deck additions) → proceed

**Macro Loop (one complete run, 15-25 minutes):**
- 5 rooms → boss room → Memory Core extraction OR cascade failure
- Each run: player chooses 1 of 3 Memory Archetypes (different starting decks, different story fragments unlocked)
- Victory unlocks 1 permanent World Variable (e.g., "The Archive is accessible" — changes all future runs)
- Defeat unlocks 1 meta-progression point + 1 Echo Enemy (enemy remembers your playstyle)

**Meta Loop (days to weeks):**
- Meta-progression: 40 permanent upgrades across 4 unlock trees (Archetypes, Echoes, World Variables, Deck Foundations)
- World State layer: 50 World Variables collectively updated by all players; state affects room generation, enemy rosters, and narrative content available in each run
- Community milestone: 1,000 concurrent players must simultaneously complete the "Signal Convergence" boss to unlock the game's true ending chapter

Loop diagrams included for all three loops with ASCII art representations.

---

## 5. Game Mechanics
**What this section contains:** Full mechanics specification for all core systems using the mechanics_specification_template format.

**Memory Card System:** Cards are drafted from a 3-card hand each turn. Each card is a Memory Fragment — mechanically a combination of damage/effect value, cost (1-3 energy), and a lore fragment. Playing certain card sequences triggers Resonance: a 2-card or 3-card synergy that fires a bonus effect. Input: select card from hand. System: apply effect (damage, status, draw, energy). Feedback: card animation, SFX, damage number, lore text flash. Parameters table: Energy per turn: 3 (base), Max hand size: 5, Deck max: 20 cards, Draft draw: 3 options per draft event.

**Echo Combat System:** Echo Enemies are persistent enemies that appear in runs and remember how the player defeated their predecessor — adapting behavior. First encounter with Echo: baseline stats. Second+ encounter: adds defensive counter to the kill method used last time. Parameters: Echo memory persistence: permanent per player account. Echo adaptation limit: 3 adaptations maximum. Echo defeat reward: 1 Void Shard (premium meta-currency).

**World Variable System:** 50 binary World Variables collectively modified by all players. Each variable affects: room generation probabilities (what rooms can appear), enemy roster (which enemies spawn), card pool availability (which cards can draft). Implementation: server-side variables queried at run start, applied to seed generation.

**Cascade Failure Mechanic:** On run failure, player chooses 1 of 3 World Variables to flip (within constraints). This is permanent for the shared world. Creates ownership of failure — loss has meaning. Design note: inspired by Outer Wilds' "your exploration changes the world" but applied to a competitive/mechanical context.

---

## 6. Progression System
**What this section contains:** Two parallel progression tracks.

**Per-Run Progression (temporary, resets on run end):** Deck growth from 10 starter cards to max 20. Energy upgrades (base 3 → max 5 via shop). Relic system: 1-3 passive items found per run that modify rules (e.g., "Every 5th card played costs 0 energy").

**Meta Progression (permanent):** 40 upgrades across 4 trees. Memory Archetypes tree: unlocks 6 additional starting archetypes. Echo Mastery tree: reveals Echo adaptation patterns before encounters. World Navigation tree: increases World Variable slots (player can hold 2 flips per failure instead of 1). Deck Foundation tree: unlocks 12 additional starter cards per archetype.

XP formula: `XP = base_run_xp × completion_multiplier × echo_bonus`
- Base: 100 XP per run (regardless of outcome)
- Completion: ×2.0 for successful extraction, ×1.0 for cascade failure
- Echo: +50 XP per unique Echo defeated for first time

Time to all 40 upgrades: Casual (1 run/day, 30 min): 80 days | Average (2 runs/day): 45 days | Hardcore (5+ runs/day): 18 days.

---

## 7. Content Design
**What this section contains:**

**Rooms:** 8 room types at launch — Combat, Elite Combat, Shop, Rest, Mystery, Forge (deck editing), Archive (lore), Boss. Procedural selection weighted by run depth (combat-heavy early, elite/boss-heavy late). Post-launch: 2 new room types per season.

**Enemies:** 15 base enemies, 8 Echo variants, 4 Bosses at launch. Enemy design principle: every enemy has 1 readable pattern and 1 hidden pattern. The readable pattern is telegraphed 1 turn ahead via animation. The hidden pattern is unlocked for player knowledge only after dying to that enemy 3 times.

**Cards:** 80 cards at launch across 4 Memory types (Combat, Temporal, Void, Archive). Each card: 1 mechanic effect + 1 lore fragment. 12 Resonance pairs (2-card synergies) + 4 Resonance triples (3-card synergies). Launch target: 80 cards. Per-season addition: 15 cards + 2 Resonance pairs.

**Relics:** 24 relics at launch, categorized: Common (10), Uncommon (8), Rare (5), Legendary (1 — the Signal Relic, required for true ending). Relic acquisition: one per run from Boss defeat, Shop purchase, or Mystery room.

---

## 8. Narrative & World
**What this section contains:** The setting is The Void — a digital purgatory where human memories are stored after death, now fragmenting due to an unnamed catastrophe. The player is the Cartographer, an AI archivist attempting to reconstruct the record of what happened. Lore depth: Deep — every card has unique lore text; 50 World Variable descriptions create interconnected world history; 4 bosses have full character arcs revealed across multiple encounters.

Story structure: Non-linear discovery. No linear quest chain. Players piece together what happened via card lore, Echo memories (enemies who remember being alive), and World Variable flavor text. The true ending requires: 50 World Variables all flipped to their "Reconstructed" state by the collective playerbase + the community completing Signal Convergence together.

Key characters: The Echo (the first Echo Enemy — the player's previous run, reborn as an adversary), The Archivist (mysterious benefactor who provides the starting deck), The Signal (the source of the catastrophe — whose identity is the narrative mystery).

---

## 9. User Experience & Interface
**What this section contains:** Screen inventory covers 11 major screens: Launcher, Main Menu, Archetype Select, Run HUD, Shop UI, Relic Inventory, World Map (World Variables visualization), Echo Database, Settings, Death Screen, Victory Screen.

FTUE: Minutes 0-1: Immediate combat tutorial with the Echo — player is dropped into a pre-built encounter with tutorial cards. Minutes 1-5: Core card drafting and combo introduction via guided first room. Minutes 5-15: First death trigger → World Variable flip → meta-progression unlock. Minutes 15-30: Second run with knowledge from first, first Echo encountered.

HUD layout: Top-left: HP bar + Energy counter. Center: play area with card hand displayed at bottom. Top-right: deck counter / discard counter. Bottom-right: relic slots (up to 3 visible). No minimap — rooms are sequential, not spatial.

Accessibility: Colorblind mode (all status effects have icon + color coding), subtitle support for all audio lore events, full key remapping.

---

## 10. Art Direction
**What this section contains:** Visual style: hand-inked comic book brought into motion. Thick black outlines, flat color fills with grain texture overlay, cel-shaded lighting. Influences: Mike Mignola (Hellboy) for graphic shape language and heavy blacks; Persona 5 for bold UI personality; Hades for character clarity and card-frame design.

Color palette: Environment — Deep Void `#0E0E1A`, Dusk Slate `#2A2B3D`, Pale Bone `#D4C9B0`. Character — Hero Gold `#E8B84B` (player), Blood Rust `#8B2020` (enemies). UI — Dark Navy `#1A1B2E` backgrounds, Off-White `#E8E6E1` text, Royal Purple `#7B1FA2` for rare items.

Animation: Snappy card plays (< 3 frames before effect), hit-pause on high-damage cards (2 frames), dramatic slow-motion on Resonance triggers. Cards have unique idle animations (floating, pulsing based on Memory type).

---

## 11. Audio Design
**What this section contains:** Music: Electronic/ambient with classical piano elements. Exploration: slow, ambient, understated. Combat: builds with each turn, adds percussion as energy depletes. Boss: full orchestral with electronic distortion. Voice: Narration barks only (Cartographer inner monologue, short phrases — no full VO for scope reasons). SFX: each card type has distinct SFX family (Combat = metallic/sharp, Temporal = reverb/echo, Void = bass/resonant, Archive = paper/soft). Adaptive: music layers add with each card played in a turn (first card: melody; second: bass; third+: percussion). Budget: 12 music tracks, 140 SFX, no full VO.

---

## 12. Multiplayer Design
**What this section contains:** Not traditional multiplayer. World State layer is shared-server passive multiplayer. Architecture: Client plays entirely locally (single-player experience). On run end: result pushed to server (World Variable flip or successful extraction). Server aggregates all player results → updates World State → served to all clients at next run start. No real-time multiplayer. Server infrastructure: REST API, lightweight, 100ms response acceptable. Social: Leaderboards (fastest run, most Echoes, most world variables reconstructed), no chat required for launch.

---

## 13. Monetization Strategy
**What this section contains:** F2P core with seasonal content. Base game free on Steam (unusual for roguelikes — justified by multiplayer world network effect: needs high player count). Revenue: Memory Season Pass ($9.99/season, 8 weeks). Each season adds: 15 new cards + 2 new Echoes + 1 new boss + seasonal World Variables. Cosmetics: Card backs ($2.99), Cartographer skins ($4.99), Relic visual swaps ($1.99). No gameplay advantages for purchase. Ethical commitment: all cards eventually available to free players via in-game Void Shards (earned by defeating Echoes). Season content becomes free after 2 seasons. Target ARPU: $8/month. Target conversion: 4% of MAU.

---

## 14. Economy Design
**What this section contains:** Two currencies: Void Shards (earned, F2P) and Echoes (premium). Void Shards: earned 50/run completion, 100/first unique Echo defeat. Spend: unlock Card Foundation upgrades (200 shards), Archive cosmetics (500-1000 shards). Echoes: purchased at $1/100 echoes. Spend: season pass (999 Echoes = $9.99), card back (299 Echoes), Cartographer skins (499 Echoes). Net flow target: free players accumulate 150 shards/week, sinks require 300-500 per meaningful upgrade = 2-3 week natural progression cadence. No inflation risk at current rates.

---

## 15. Technical Requirements
**What this section contains:** Engine: Unity 2023.3 LTS — team expertise, excellent Steam SDK support, proven for deckbuilder genre (Monster Train, Slay the Spire use Unity). Minimum spec: GTX 1060, i5-8400, 8GB RAM, Windows 10. Target 60FPS at 1080p minimum spec. World State server: lightweight Node.js REST API on AWS. World Variable persistence: PostgreSQL, < 1GB data at 100K players. No real-time networking required — async model only. Third-party: Steamworks SDK (achievements, leaderboards, cloud save), Sentry (crash reporting), GameAnalytics (free tier sufficient for launch). Key tech risk: World Variable aggregation consistency at scale (concurrent updates) → mitigation: eventual consistency model, 5-minute aggregation windows acceptable for World State.

---

## 16. Competitive Analysis
**What this section contains:** Direct comps: Slay the Spire (definitive genre benchmark — we take mechanical foundation, add narrative layer), Monster Train (co-op deckbuilder — we reference theirs for deck-construction UI patterns), Inscryption (narrative deckbuilder — our closest narrative comp, but single-player only, no persistent world). Indirect comps: Outer Wilds (discovery-through-repetition pacing), Noita (emergent world-change through play). Positioning: lower mechanical complexity than Slay the Spire (accessible) with higher narrative investment and the unique persistent world differentiator. Feature comparison matrix covers: session length, narrative depth, multiplayer, post-launch content, platform.

---

## 17. Development Roadmap
**What this section contains:** Current state: vertical slice complete (Acts 1-2, 40 cards, 3 Echoes, World Variable system prototype). Milestones: Alpha (Q2 2025) — feature complete, 60 cards, 6 Echoes, all 4 bosses, World State live. Beta (Q3 2025) — content complete, 80 cards, 50 World Variables, community playtest. Steam Early Access (Q4 2025) — launch with Seasons system live. 1.0 Launch (Q2 2026) — full story complete (requires community achieving Signal Convergence during EA). Critical path: World State server must scale before Beta, or revert to local simulation.

---

## 18. Risk Assessment
**What this section contains:** Risk register with 8 items. High risks: (1) Community never achieves Signal Convergence → mitigation: fallback solo ending available at 90% World Variables reconstructed. (2) World State server cost at scale exceeds budget → mitigation: architecture designed for eventual consistency, not real-time; aggregation every 5 minutes caps server calls. (3) F2P on Steam stigma for roguelike genre → mitigation: transparent communication about what's free vs paid; "free forever" guarantee for base experience. Medium risks: run length balancing (15-25 min target may drift to 30+ in playtesting), Echo adaptation frustrating casual players (mitigation: difficulty setting disables Echo memory on Easy).

---

## 19. Appendices
**What this section contains:** Glossary: Memory Fragment, Void Shard, Echo, World Variable, Cascade Failure, Memory Archetype, Resonance, Signal Convergence. Open Questions Log: 12 open questions including "Should World Variables reset seasonally or be permanent?" and "Should players see other players' run outcomes in real-time?" Revision history. References: Slay the Spire economy analysis (public postmortem), Hades narrative design talk (GDC 2021), Roguelike retention data (GameAnalytics Industry Report 2024).

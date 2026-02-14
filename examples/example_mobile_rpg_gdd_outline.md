# Example GDD Outline: CRYSTAL COVENANT
### Genre: Mobile Gacha RPG | Platform: iOS, Android | Version: v0.3

> **FICTIONAL EXAMPLE** — This outline is entirely fictional and created for reference purposes only. All studio names, game titles, market statistics, KPI targets, revenue figures, player counts, and retention benchmarks are fabricated examples. Do not use any numeric claims from this document in real business contexts without independent verification.

---

This is a complete 19-section GDD outline for a mobile F2P gacha RPG. Use this as a reference for a genre that prioritizes daily retention, IAP monetization, live operations, and gacha systems. Each section description explains what a full document would contain — scope, specificity, and content type.

---

## 1. Cover Page
**Title:** CRYSTAL COVENANT
**Tagline:** "Forge legends. Collect destiny."
**Genre:** Mobile Gacha RPG with Guild Warfare
**Platform:** iOS 16.0+, Android 9.0+
**Audience:** Ages 18–34, midcore mobile gamers; fans of Genshin Impact, Epic Seven, AFK Arena
**Version:** v0.3 | **Date:** January 2025 | **Studio:** Prism Gate Studio
**Confidentiality:** For internal use and authorized partners only. Do not distribute without written permission.

---

## 2. Executive Summary
**What this section contains:** 500-word case for Crystal Covenant's market positioning. Mobile gacha RPG market: $15B+ annually; top-5 titles earn $2M+/day. Crystal Covenant targets the gap between Genshin Impact's deep combat system (too hardware-demanding for budget Android) and AFK Arena's passive play (too shallow for midcore audience). USPs: (1) "Guild Covenant" system where 20-player guilds own persistent territories with real economy; (2) offline-capable tactical combat (vs. Genshin's requirement for constant connectivity); (3) cross-platform roster transfer between iOS and Android via cloud save. Comparable titles differentiation matrix. Team: 12 developers, 8 full-time, lead producer shipped Epic Seven at Smilegate. Target KPIs: D1 retention 42%, D30 retention 10%, D30 conversion 4%, ARPU $12/mo.

---

## 3. Game Overview
**What this section contains:** High concept: "A guild-first gacha RPG where your guild's collective choices shape a persistent world economy." Core fantasy: the player feels like a legendary commander who collects the most powerful heroes in existence and leads their guild to territorial dominance. Experience pillars:
1. **Hero Collection** — compulsive gacha with fair pity system and transparent rates
2. **Tactical Mastery** — 3v3 formation battles with genuine skill expression
3. **Guild Belonging** — social identity through guild territories and history
4. **Progress Always** — AFK grinding provides offline resource accumulation

Session flow: Daily session (8-12 min) — collect offline resources → use stamina on story or dungeon content → upgrade 1-2 heroes → participate in guild activity → complete daily quests → optionally do Arena PvP. Weekly session: Guild Territory Wars (Sunday, 30-40 min).

---

## 4. Core Gameplay Loop
**What this section contains:**

**Micro Loop (2-4 min per battle):**
Formation placement (pre-battle, 30 seconds) → Auto-battle with manual skill triggers → Victory/defeat → Loot collection → Hero EXP distribution

**Macro Loop (daily session, 8-12 min):**
Offline loot collection → Daily quest checklist → Stamina spending (2-3 dungeon runs) → Hero upgrade (materials from dungeons) → Guild check-in → Optional Arena

**Meta Loop (weekly → monthly):**
Hero collection via gacha (daily/weekly pulls) → Guild Territory progression (weekly wars) → Story chapter completion (monthly) → Seasonal events with exclusive heroes and skins (every 6 weeks)

**Engagement hooks:** Daily login rewards (streak-based), Guild war calendar (Sunday commitment), Limited-time hero banners (FOMO managed ethically with pre-announced schedule), Guild rank prestige (guild leaderboard resets monthly).

---

## 5. Game Mechanics
**What this section contains:** Full specification for all core systems.

**Formation System:** Players deploy 3 heroes in a 3-row formation grid (front/middle/back). Row position affects: damage taken multiplier (front: ×1.5), healing received (back: ×0.8), skill targeting priority. Input: drag-and-drop placement pre-battle. Parameters table: Formation slots: 3, Row damage multipliers: Front 1.5×, Mid 1.0×, Back 0.7×, Formation save slots: 10.

**Auto-Battle with Manual Skill Triggers:** Combat resolves automatically based on hero stats and AI. Player can manually trigger Ultimate Skills (charged by auto-attacks). Ultimate timing is the primary skill expression. Parameters: Ultimate charge: 100 points (10 per auto-attack), Ultimate activation window: any time charge ≥ 100, Battle speed: 1× / 2× / 3× toggle, Auto-skill: option to automate Ultimates (reduces skill expression, for AFK players).

**Hero Stat System:** Each hero has 6 stats: ATK, DEF, HP, SPD, CRIT%, CRIT DMG. Damage formula: `Damage = ATK × SkillMultiplier × CritMultiplier - (DEF × 0.4)`. Hero stats scale with Star level (1★–6★) and Equipment. Max hero stats at 6★+max equipment: ATK 4,500, HP 32,000, DEF 1,200.

**Guild Territory System:** Map of 30 territories per server. Each guild can own up to 5 territories. Territory ownership grants: daily resource income to all guild members proportional to territory count, exclusive crafting recipes, bragging rights (guild name on map). Territory Wars: every Sunday, 3-hour window where guilds can attack adjacent territories. Attacker needs 15 participating guild members. Defender auto-defends with top-6 heroes.

---

## 6. Progression System
**What this section contains:** Progression hierarchy from shallow to deep: Account Level → Hero Collection → Hero Development → Guild Rank.

**Account Level (1–100):** Unlocks features at gates: Lv.5: Arena, Lv.10: Guild creation, Lv.20: Territory Wars, Lv.30: Endgame raids. XP: 200 XP base per dungeon clear, +50 per story chapter first clear. Level XP formula: `XP_required(n) = 500 × n^1.4`. Time to Lv.30 (content unlock): Casual 18 days, Average 10 days, Hardcore 5 days.

**Hero Development:** Each hero: 1★ to 6★ (star promotion via duplicate heroes + materials). Equipment: 6 gear slots, 5 tiers. Skill upgrades: 3 skills per hero, each upgradeable 5 levels via Skill Books.

**Progression time-to-endgame:** First competitive team: Casual 45 days, Average 25 days, Hardcore 12 days. First 6★ hero: Casual 21 days, Average 12 days, Hardcore 6 days.

---

## 7. Content Design
**What this section contains:** Story: 15 chapters at launch, 1 new chapter/month. 5 worlds × 3 chapters each. Dungeon types: Resource Farm (5), Boss (10), Guild Raid (2), Limited Event (2). Total heroes at launch: 60 (12 per element × 5 elements). Post-launch hero cadence: 2-3 new heroes per month, 1 guaranteed 5★+ per new seasonal event.

Hero design principle: each hero must be useful at 4★ (accessible) and dominant at 6★ (whale goal). No hero should be "garbage at 4★" — creates frustration with pity misses. Content minimum for soft launch: 8 story chapters, 20 dungeon maps, 40 heroes, 3 guild raids.

---

## 8. Narrative & World
**What this section contains:** Setting: Aetheris, a world of floating islands connected by magical Ley Lines. Ancient civilization collapsed when Ley Lines fractured. Player is a Covenant Master — one of few who can form bonds with Legendary Heroes and potentially restore the Lines. Lore depth: Medium — story chapters have full narrative, heroes have backstory in their profile, no branching dialogue. Tone: Epic fantasy with anime aesthetic, inspirational not dark. Writing tone: Hopeful, heroic, light humor in character interactions.

Character types: Story Heroes (8 — tied to story chapters), Gacha Heroes (52 — collectible, short backstories), Villain roster (5 bosses in story), Guild Rival (competitive guilds represented as recurring NPC antagonists in Guild Wars).

---

## 9. User Experience & Interface
**What this section contains:** Mobile-first UX design. Portrait orientation only (one-handed play). Thumb zone optimization: all critical daily actions accessible from bottom 40% of screen. Screen inventory: 16 screens documented with entry/exit flow.

FTUE: Minute 0-1: Tutorial battle (auto-battle + one manual Ultimate trigger). Minutes 1-5: Story chapter 1 (narrative hook + 3 battles). Minutes 5-10: Hero unlock (tutorial 5★ gifted, first gacha pull animation). Minutes 10-20: Guild system introduction + first daily quest. Session close attempt: "Daily rewards available again in 23:47:XX" — creates scheduled return.

HUD: Battle HUD (clean, 3 hero portraits at bottom with Ultimate buttons, enemy HP bars top, battle speed toggle top-right). Hub HUD: persistent bottom nav with icons for Home, Dungeons, Guild, Heroes, Shop. Notification badges on all nav items with pending actions. Feature-gated UI: greyed-out sections with "Unlock at Lv.X" state prevents confusion for new players.

Accessibility: Support for both left-thumb and right-thumb dominant players (mirrored layout option), text size options (3 sizes), colorblind mode.

---

## 10. Art Direction
**What this section contains:** Visual style: Vibrant anime fantasy with high-detail hero portraits and clean environmental art. Resolution targeting: crisp at 1080×1920 (most common Android flagship), acceptable at 720×1280 (budget Android minimum spec). Influences: Epic Seven (character illustration quality and combat VFX), Genshin Impact (environment color saturation), Arknights (UI cleanliness and information hierarchy).

Hero art guidelines: Full-body illustration style (not chibi), 5 element color coding (Fire: red/orange, Water: blue/cyan, Earth: green/brown, Wind: purple/white, Light: gold/white). Legendary (6★) heroes have animated Live2D portraits. Standard heroes have static illustrations.

UI: Flat design with jewel/crystal accent elements. Gacha pull animation requires: build-up animation (2s) + reveal animation (3s for 5★+ pulls, 1s for 3-4★). Pull animation quality directly correlates with retention for gacha games — this receives priority art budget.

---

## 11. Audio Design
**What this section contains:** Music: Orchestral fantasy main theme, electronic + orchestral combat music (2 intensity levels: normal dungeon, boss fight). Guild War music: epic, time-pressure feel. SFX: each element has distinct hit sound family (Fire: explosive crack, Water: splash/ripple, etc.). Hero Ultimate skills each have unique SFX + voice bark. Voice: Japanese + English voice options for all 8 story heroes (full cutscene VO), English only for gacha heroes (minimal barks: battle cry, ultimate activation, defeat). Audio budget: 20 music tracks, 300 SFX, 60 unique hero voice packs.

---

## 12. Multiplayer Design
**What this section contains:** Async PvP (Arena): player defends with preset team; attacker fights AI-controlled version. Real-time matchmaking not required. Guild Territory Wars: 15v15 async over 3-hour window — not real-time PvP. Guild Raids: up to 20 players each submit one battle per day against shared raid boss; damage accumulated. No real-time multiplayer needed at launch. Server: REST API for guild data, leaderboards, raid scores. Push notifications for Guild War start/end, territory attack alerts, raid availability.

---

## 13. Monetization Strategy
**What this section contains:** Full F2P with IAP and Season Pass.

**Revenue model:** Gacha (primary), Season Pass, direct IAP. Gacha pity: guaranteed 5★ hero at 100 pulls (hard pity). Soft pity at 75 (rate increases from 2% to 20% over pulls 75-100). All rates disclosed in-app (Apple/Google compliance). No Complete Gacha (JOGA compliance). IAP catalog: full table with 8 tiers from $0.99 (60 Crystals) to $99.99 (8,000 Crystals + exclusive title + 10 pulls). Season Pass: $9.99/season (6 weeks), includes 1 exclusive non-meta hero + 1,500 Crystals + cosmetics. Target daily login crystal grant: 100 Crystals (10 pulls in 30 days free). Target ARPPU: $32/month. Conversion target: 4% D30. ARPU target: $12/month.

Ethical commitments: rate disclosure on every banner, no gameplay P2W in PvP (competitive balance maintained by accessible pity system), no manipulative timers on evergreen content, responsible spending alerts at $50/$100 cumulative.

---

## 14. Economy Design
**What this section contains:** Two currencies: Crystal (premium, earned + purchased) and Gold (soft, earned in gameplay).

**Crystal faucets per day:** Daily login: 100, Daily quests completed: 150, Story chapter first clear: 50 average, Arena rank reward: 30-200, Guild War participation: 50, Events: 100-300 (event days). Total free F2P daily Crystal estimate: 150 crystals/day steady state.

**Crystal sinks:** Gacha: 160/pull, 1,440 for 10-pull. Stamina refills: 60/refill. Energy: 50/refill. Net flow: 150 earned/day, ~160/pull equivalent → free players accumulate pulls at 1 pull/day rate = 30 free pulls/month (targeting realistic pity attainment at ~60-70 days for casual player). Designed to feel generous while creating occasional purchase moments.

Gold economy: earned 2,000+/dungeon clear, spent on hero upgrades (10,000-50,000 each), gear enhancement (5,000-80,000). No inflation risk — sink rate designed to match faucet at average engagement.

---

## 15. Technical Requirements
**What this section contains:** Engine: Unity 2023.3 LTS. Platform: iOS 16+ (iPhone 8 equivalent minimum), Android 9+ (Snapdragon 730 equivalent). Performance targets: 60FPS on recommended devices, 30FPS stable on minimum spec, < 2GB RAM usage, < 45 second initial load. Storage: < 1GB initial download, assets streamed after install.

Backend: AWS (EC2 + RDS). Services: Firebase (push notifications, A/B testing, remote config), GameAnalytics (player behavior), AppsFlyer (attribution), RevenueCat (IAP management across iOS/Android). Key tech risks: (1) Live2D animations on minimum-spec Android — performance testing required in pre-production. (2) Guild Territory Wars — distributed locking for territory ownership — requires Redis or equivalent.

---

## 16. Competitive Analysis
**What this section contains:** Direct comps: Genshin Impact (aspirational quality bar, too hardware-demanding — our advantage), Epic Seven (closest mechanical comp — our guild system differentiates), AFK Arena (same audience, too shallow — we're deeper), Arknights (strong IP/art, different combat style). Market gap: no mobile gacha with deep guild territorial economy at accessible hardware requirements. Feature comparison matrix covers 10 features across 5 competitors.

---

## 17. Development Roadmap
**What this section contains:** Soft launch: Q3 2025 (limited regions: Canada, Australia, Philippines — typical mobile soft launch markets). Content at soft launch: 8 chapters, 40 heroes, core gameplay complete. Soft launch goals: LTV validation, monetization tuning, D30 retention benchmarks. Global launch: Q1 2026 (pending soft launch KPI targets met). Post-launch live ops calendar: Season 1 (launch) — Fire Element event + 3 new heroes. Season 2 (6 weeks later) — Guild Territory expansion + 2 new guild raid bosses. Monthly: 2 story chapters + 2 new heroes. Critical path: Guild Territory Wars infrastructure must be complete before soft launch (it's a core differentiator, can't be added post-launch).

---

## 18. Risk Assessment
**What this section contains:** Risk register covering 10 items. High risks: (1) Gacha feel fails to convert at 4% rate — mitigation: soft launch KPI gate, adjust pity system before global launch. (2) Guild Territory Wars server cost at scale — mitigation: territory count capped at 30/server, async model limits server compute. (3) Apple/Google policy changes on gacha — mitigation: design all gacha as direct purchase option (always offer "buy this specific hero" for 3× pull value). Medium risks: Hero power creep complaints from early adopters (mitigation: transparent power budget system, new heroes must be equal to launch heroes at equivalent investment), hard-to-reach F2P players who act as content creators (mitigation: dedicated "Creator Program" with free crystals for streamers/YouTubers).

---

## 19. Appendices
**What this section contains:** Glossary: Gacha, Pity, Hard Pity, Soft Pity, Star Promotion, Ultimate, Formation, Territory War, Covenant Master, Ley Line, Stamina. Open Questions Log: "Should Territory War be real-time or async?" (decision pending performance testing), "20 vs 30 guild member maximum?", "Should 6★ heroes have unique voice lines or shared VO pool?" Revision history. References: JOGA guidelines (Japan), China minor spending limit regulations, Apple App Store loot box disclosure requirements, Sensor Tower Top Mobile RPG Revenue Report 2024, Genshin Impact gacha postmortem analysis (public).

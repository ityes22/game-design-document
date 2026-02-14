# Mechanics Specification Template

Use this template for every distinct mechanic in Section 5 (Game Mechanics) and any other section requiring precise mechanic documentation. A mechanic is any system where player input produces a game state change. If a player does something and something happens — it's a mechanic that needs to be documented here.

---

## How to Use This Template

1. Create one block per distinct mechanic
2. Fill every field — if a field doesn't apply, write "N/A — [reason]" not blank
3. Parameters table is mandatory for every mechanic with tunable values
4. Link every mechanic to at least one other mechanic in Dependencies
5. Flag uncertain values with `[PLAYTEST: description]`

---

## Mechanic Documentation Block

```
## [Mechanic Name]

**Category:** [Core / Secondary / Meta / UI / Social]
**Status:** [Designed / Specced / Implemented / Validated]
**Priority:** [P0 — MVP / P1 — Launch / P2 — Post-Launch]

### Overview
[2-3 sentence description of what this mechanic is and why it exists in the game.
What player need does it address? What experience does it create?]

### Input
**Trigger:** [What the player does — be specific about controls]
- PC: [keyboard key / mouse button / mouse movement]
- Controller: [button / analog input / trigger]
- Mobile: [tap / swipe direction / hold / pinch]
**Context Requirements:** [What state must be true for this input to be valid?]
- Player must be: [grounded / in-combat / not stunned / etc.]
- Resource requirement: [sufficient stamina / not on cooldown / etc.]
**Input Window:** [How long does the player have to input? Real-time / Turn-based / QTE?]

### System
[What the game calculates. Be precise. Use formulas where applicable.]

**Core Formula (if applicable):**
[Formula in code format with all variables defined]

Example:
`Damage = (BaseDamage + WeaponBonus) × AttackMultiplier × Random(0.9, 1.1) - EnemyDefense`
- BaseDamage: player stat (10–150, scales with level)
- WeaponBonus: equipped weapon stat (0–80)
- AttackMultiplier: skill/buff modifier (0.5–3.0, default 1.0)
- Random(0.9, 1.1): ±10% variance roll per hit
- EnemyDefense: enemy stat (5–200, see enemy stat table Section 7)

**State Changes:**
- [What game state variables change when this mechanic fires?]
- [Which cooldown timers start?]
- [Which resource values change?]
- [Which flags set/clear?]

**Edge Cases:**
| Situation | Behavior |
|-----------|----------|
| [Edge case 1] | [How it resolves] |
| [Edge case 2] | [How it resolves] |
| [Negative resource result] | [Clamp to 0 / error / special state?] |
| [Mechanic used during animation] | [Buffer / ignore / interrupt?] |

### Feedback
[What the player perceives. Cover all channels.]

**Visual:**
- [Screen effect, character animation, particle effect with duration]
- Example: "White flash on hit target (2 frames), red particle burst (0.3s), screen shake (0.1s, 5px amplitude)"

**Audio:**
- [Sound effect description, trigger timing]
- Example: "Impact SFX plays on hit frame (not on button press). Pitch varies ±15% per hit for variation."

**Haptic (if applicable):**
- [Vibration pattern, duration, intensity]
- Example: "Short pulse (50ms) on hit, long rumble (200ms) on kill"

**UI:**
- [Damage numbers, cooldown indicator, resource bar change, on-screen prompt]
- Example: "Damage number floats from hit point (+X in white, critical in gold/larger), target HP bar updates, attacker stamina bar drains visibly"

### Parameters

| Parameter | Default Value | Min | Max | Tuning Notes |
|-----------|---------------|-----|-----|--------------|
| [Param 1] | [value] | [min] | [max] | [why this range, reference game if applicable] |
| [Param 2] | [value] | [min] | [max] | [notes] |
| Cooldown | [Xs] | [Xs] | [Xs] | [playtest target: feels snappy but not spammable] |
| Resource cost | [N] | [0] | [N] | [0 = free, must justify if free] |
| Animation duration | [Xms] | — | — | [includes recovery frames, locked input window] |
| Hitbox active frames | [N–M of total] | — | — | [N = first active frame, M = last] |

### Balance Notes
[Design rationale for this mechanic's values. Reference comparable games.]

> 🎮 Designer's Note: [Context that doesn't belong in the spec itself. Why this design over alternatives? What was iterated on? What does playtesting need to validate?]

**Comparable Implementations:**
- [Game A]: [How they implemented this] → We [took / modified / rejected] this because [reason]
- [Game B]: [How they implemented this] → We [took / modified / rejected] this because [reason]

**Known Balance Risks:**
- [Risk 1]: [Why it's a risk and what to watch in playtesting]
- [Risk 2]: [Why it's a risk]

### Dependencies

**Requires (these mechanics must exist for this mechanic to function):**
- [Mechanic A] — [why dependency exists]
- [Mechanic B] — [why dependency exists]

**Affects (this mechanic influences these mechanics):**
- [Mechanic C] — [how it influences it]
- [Mechanic D] — [how it influences it]

**Conflicts With (cannot fire simultaneously or requires special handling):**
- [Mechanic E] — [how the conflict is resolved]

### Progression Impact

**How this mechanic changes as the player progresses:**
| Stage | Change | Unlock Method |
|-------|--------|---------------|
| Early Game | [Base version only] | Available from start |
| Mid Game | [Upgrade 1: description] | [Skill point / item / level] |
| Late Game | [Upgrade 2: description] | [How unlocked] |
| Endgame | [Mastery version: description] | [Prestige / endgame system] |

**Power Scaling:** [Does the mechanic scale with player stats? How? Is it multiplicative or additive?]
```

---

## Complete Example: Dodge Roll

```
## Dodge Roll

**Category:** Core Movement
**Status:** Specced
**Priority:** P0 — MVP

### Overview
The Dodge Roll is the player's primary evasion tool and the core expression of skill in combat.
It provides a brief window of invincibility, encouraging reactive and tactical positioning.
It exists to make combat feel active and skill-expressive rather than passive stat-trading.

### Input
**Trigger:** Hold [Left Stick] direction + press [Circle/B] OR double-tap [direction] on mobile
- PC: WASD direction + Space
- Controller: Left Stick direction + Circle (PS) / B (Xbox)
- Mobile: Double-tap direction on virtual joystick
**Context Requirements:**
- Player must not be: stunned, dead, in dialogue, in menu
- Resource requirement: 1 Stamina point available (max 3)
**Input Window:** Real-time, responsive on any non-stunned frame

### System
Character enters a 20-frame animation. During frames 3–11 (the "invincibility window"),
all incoming damage and status effects are ignored. Character moves 4.0 meters in the
input direction during these frames regardless of obstacles (clips through thin geometry,
blocked by thick walls and impassable terrain).

**Core Formula:**
`Dodge_Distance = base_distance × dodge_speed_modifier`
- base_distance: 4.0 meters
- dodge_speed_modifier: 1.0 base, upgradeable to 1.5 via Acrobatics skill

**State Changes:**
- Stamina reduced by 1 (instant on input, before animation starts)
- DodgeRolling flag = TRUE for frames 1–20
- Invincible flag = TRUE for frames 3–11
- Player velocity set to (input_direction × 8.0 m/s) for frames 1–15
- Cooldown timer starts at frame 20 (0.25s before Stamina regen allows another roll)

**Edge Cases:**
| Situation | Behavior |
|-----------|----------|
| No stamina available | Input ignored, brief UI shake on stamina bar |
| Dodge into wall | Animation plays, character stops at wall, full distance not covered |
| Hit during frame 1–2 (pre-invincibility) | Damage applies normally |
| Hit during frame 12–20 (post-invincibility) | Damage applies normally |
| Dodge during knockback | Knockback canceled, dodge executes from current position |

### Feedback
**Visual:**
- Afterimage trail: 3 fading copies of player sprite (white tint, 100%→50%→10% opacity over 0.4s)
- Dust/motion VFX at feet (0.3s, direction-matched)
- Camera: 0.05s pull-back (5% zoom out) on dodge input, snaps back over 0.3s

**Audio:**
- Whoosh SFX on dodge input (pitched to character weight class: lighter = higher pitch)
- No SFX if dodge is blocked (stamina empty)

**Haptic:**
- Short pulse (40ms) at dodge input
- No haptic if blocked

**UI:**
- Stamina bar pip depletes immediately on input
- If 0 stamina: bar flashes red (0.5s) and brief "no stamina" visual warning

### Parameters
| Parameter | Default | Min | Max | Tuning Notes |
|-----------|---------|-----|-----|--------------|
| Invincibility frames | 3–11 | 3–8 | 3–14 | Wider = more forgiving. Hades uses ~6 i-frames. Target: skilled feel. |
| Total animation frames | 20 | 15 | 30 | At 60fps = 0.333s total. Longer = more committed, higher risk/reward |
| Dodge distance | 4.0m | 2.0m | 6.0m | Upgradeable to 6.0m via skill. Hades ~3m, DS3 ~4.5m |
| Stamina cost | 1 | 0 | 2 | Never free — scarcity drives decision-making |
| Stamina max | 3 | 2 | 5 | 3 = 3 consecutive dodges, deliberate cap |
| Stamina regen delay | 1.0s after last use | 0.5s | 2.0s | [PLAYTEST: May feel punishing at 1.0s] |
| Stamina regen rate | 1 per 2.5s | 1/1.5s | 1/4.0s | [PLAYTEST: validate against boss damage patterns] |

### Balance Notes
> 🎮 Designer's Note: Inspired by Hades' dash (tight i-frames, stamina-free but on cooldown)
> and Dark Souls' roll (stamina-gated, wide variance based on equip load). We hybridize:
> i-frames like Hades (skill-expressive), stamina like DS3 (resource management). Mobile
> version uses double-tap to avoid cluttering screen with dedicated button.

**Comparable Implementations:**
- Hades: Dash is free, short cooldown, ~6 i-frames → Too accessible for our skill curve
- Dark Souls 3: Stamina-gated, equip load affects speed → We adopt stamina, remove equip load for clarity
- Hollow Knight: Focus dash with directional options → Inspired our directional input requirement

**Known Balance Risks:**
- Invincibility window too wide → Trivializes boss attacks. Test against all boss telegraphs.
- Stamina too slow to regen → Feels punishing in sustained combat, players just walk. Watch average dodge count per fight.

### Dependencies
**Requires:**
- Stamina System — consumes stamina resource
- Animation System — 20-frame animation state machine
- Physics/Collision — 4.0m travel with wall detection

**Affects:**
- Combat System — creates windows for counterattack, affects boss AI dodge-baiting
- Stamina System — depletes resource shared with other stamina-consuming actions
- Progression System — upgradeable via Acrobatics skill tree

**Conflicts With:**
- Stunned State — cannot dodge while stunned (stun overrides all player input)
- Dialogue System — disabled during conversation

### Progression Impact
| Stage | Change | Unlock Method |
|-------|--------|---------------|
| Early Game | Base version (3–11 i-frames, 4.0m) | Available from start |
| Mid Game | Extended distance (5.0m) | Acrobatics Skill 1 (skill point, level 5) |
| Mid Game | Reduced regen delay (0.75s) | Acrobatics Skill 2 (skill point, level 10) |
| Late Game | Attack-into-dodge cancel window | Acrobatics Mastery (rare item, endgame zone) |

**Power Scaling:** Distance upgradeable (additive +1m per tier). I-frames not upgradeable —
preserving fixed skill ceiling. Stamina regen upgradeable (multiplicative 0.85× delay per tier).
```

---

## Mechanic Categories Reference

| Category | Definition | Examples |
|----------|------------|---------|
| Core | Primary verb of the game — what it IS | Attack, Move, Build, Match |
| Secondary | Supports the core, adds depth | Dodge, Parry, Crafting, Dialogue |
| Meta | Happens between sessions or at the progression layer | Prestige, Account Level, Battle Pass |
| UI | Mechanical systems delivered through interface | Shop, Inventory, Map, Social |
| Social | Multiplayer or social interactions | Trade, Coop, PvP, Emotes |

---

## Parameter Table Standards

All parameter tables must include:
- **Parameter name:** Descriptive, consistent with in-code variable name if possible
- **Default value:** The baseline before any upgrades or modifiers
- **Min/Max:** The absolute range the value can reach through any means
- **Tuning notes:** Why this range, not just what the range is

For values not yet validated: append `[PLAYTEST: description of what to validate]`

For values derived from other parameters: show the relationship: `Base + (Level × 2.5)`

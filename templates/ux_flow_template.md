# UX Flow Template

This template covers all User Experience and Interface documentation for a GDD. Use it for Section 9 (UX & Interface). A well-documented UX section lets artists build screens and engineers build state machines without a design clarification call.

---

## Part 1: Screen Inventory

List every unique screen (UI state) in the game. A screen is any distinct full-screen or major overlay the player can navigate to. Include loading states.

### Screen Inventory Table

| Screen ID | Screen Name | Entry Points | Exit Points | Platform Variants |
|-----------|-------------|--------------|-------------|-------------------|
| SCR-001 | App Loading / Splash | App launch | → Main Menu | Mobile: show store logo |
| SCR-002 | Main Menu | App load complete, pause menu back | → New Game, Load, Settings, Store, Credits | — |
| SCR-003 | New Game / Character Select | Main Menu | → Tutorial, → HUD (if no tutorial) | — |
| SCR-004 | Tutorial | New game (first time only) | → HUD | Skip option after 2nd playthrough |
| SCR-005 | HUD (Gameplay) | Game start, pause resume | → Pause Menu | Mobile: touch zones defined below |
| SCR-006 | Pause Menu | HUD pause input | → HUD resume, → Main Menu, → Settings | — |
| SCR-007 | Inventory / Equipment | HUD shortcut, pause menu | → HUD | — |
| SCR-008 | Map / World | HUD shortcut | → HUD | — |
| SCR-009 | Dialogue System | Proximity trigger in world | → HUD | — |
| SCR-010 | Shop / Store | Hub area trigger, pause menu | → HUD | — |
| SCR-011 | Level Up / Upgrade | Auto-trigger on level up | → HUD | — |
| SCR-012 | Death / Game Over | Player HP = 0 | → Main Menu, → Retry (if applicable) | — |
| SCR-013 | Settings | Main Menu, Pause Menu | → calling screen | — |
| SCR-014 | Credits | Main Menu | → Main Menu | — |
| SCR-015 | [Add screens as needed] | ... | ... | ... |

---

## Part 2: Screen Specification

For each screen, fill this template:

```
### [Screen Name] (SCR-XXX)

**Type:** Full-screen / Overlay (X%) / HUD element / Modal dialog
**Layer:** [Z-order layer if overlapping systems exist]
**Platform Notes:** [Any platform-specific variations]

#### Visual Layout Description
[Describe the visual layout in text. Reference a wireframe number if separate wireframes exist.]
[Top area: ...] [Center area: ...] [Bottom area: ...] [Persistent elements: ...]

#### UI Elements Inventory
| Element | Type | Position | Default State | Interactive? |
|---------|------|----------|---------------|-------------|
| [Element name] | [Button/Label/Bar/Icon/etc] | [Top-left/Center/etc] | [Visible/Hidden] | [Y/N] |

#### User Actions
| Action | Input (PC) | Input (Controller) | Input (Mobile) | Result |
|--------|------------|--------------------|--------------|----|
| [Action name] | [Key] | [Button] | [Gesture] | [What happens] |

#### System Events That Affect This Screen
| Event | Source | Effect on Screen |
|-------|--------|-----------------|
| [Event] | [System] | [Screen change] |

#### Transition Animations
- Enter: [How does this screen appear?] (e.g., slide from right, 0.2s ease-out)
- Exit: [How does this screen disappear?]
- Interruption: [What if the screen is interrupted mid-transition?]
```

---

## Part 3: HUD Layout Specification

The HUD is the most viewed UI in the game. Document every persistent element.

### HUD Element Registry

| Element | Description | Screen Position | Visibility State | Priority |
|---------|-------------|-----------------|-----------------|----------|
| Health Bar | Player current HP / max HP with visual fill | Top-left | Always visible in gameplay | Critical |
| [Stamina/Energy Bar] | Resource bar below health | Top-left below HP | Visible when < max or in combat | High |
| [Minimap] | Small area map | Top-right | Toggleable, default ON | Medium |
| [Objective Tracker] | Active quest / objective text | Top-right below map | Visible when objective active | Medium |
| [Ability Icons] | 4 skill slots with cooldown overlay | Bottom-center | Always visible | High |
| [Resource Counters] | Currency, ammo, key items | Bottom-left | Visible when quantity > 0 | Medium |
| [Interaction Prompt] | Context-sensitive "[E] to open" | Center of screen | Visible when near interactable | High |
| [Damage Numbers] | Float over hit targets | World-space | 1.5s display then fade | Low (toggleable) |
| [Boss HP Bar] | Large enemy HP bar | Bottom-center above abilities | Only during boss encounters | Critical |
| [Notification Area] | Item acquired, achievement, etc. | Top-right | 3s display then slide out | Low |

### HUD Visibility State Machine

```
[Normal Exploration]
  - Health Bar: visible (reduced opacity 70% if full HP)
  - Minimap: visible
  - Ability Icons: visible
  - All others: hidden until triggered

[Active Combat] (triggered by enemy aggro)
  - Health Bar: full opacity
  - Combat indicators: visible
  - Enemy HP bars: visible above heads

[Dialogue / Cutscene]
  - ALL HUD elements: hidden
  - Dialogue box: visible

[Loading]
  - ALL HUD elements: hidden
  - Loading indicator: visible
```

### Mobile HUD Touch Zones

For mobile platforms, define safe touch zones for thumb access:

```
Portrait Layout (9:16):
┌──────────────────────────────────┐
│ [HP Bar]        [Minimap] [Menu] │ ← Thumb-inaccessible zone (top 15%)
│                                  │
│                                  │
│         [GAME WORLD]             │
│                                  │
│                                  │ ← Primary interaction zone (middle 60%)
│                                  │
│ [Move]          [A] [B] [C] [D] │ ← Left thumb zone    Right thumb zone
└──────────────────────────────────┘ ← Bottom 25%: always accessible

Thumb safe zone (bottom 40% of screen): all interactive elements required here
Top 20%: labels, passive info only (never interactive)
Center 40%: interactive on explicit tap, but not hold-and-move
```

---

## Part 4: FTUE (First-Time User Experience)

The most critical UI in the game. A new player forms their entire impression in the first 15 minutes. Document every moment.

### FTUE Flow

```
MINUTE 0–1: THE FIRST MOMENT
─────────────────────────────
What the player sees: [Exact description]
What the player does: [Exact first action]
What the game communicates: [Core identity statement]
What tutorial elements appear: [None / Minimal / Guided]
Success state: [Player has done X and understands Y]
Failure state: [If player is confused here, what do we do?]

MINUTE 1–5: CORE LOOP INTRODUCTION
────────────────────────────────────
Mechanics introduced: [List — one at a time, never two simultaneously]
Tutorial style: [Contextual hint / Forced tutorial / Watch & replicate / Discovery]
Text on screen: [Write exact tutorial text for each prompt]
  - Prompt 1: "[EXACT TEXT]" — appears when [trigger]
  - Prompt 2: "[EXACT TEXT]" — appears when [trigger]
Skip option: [Available / Not available] — [Reason]
First mastery moment: [The first time the player FEELS competent — what happens?]

MINUTE 5–15: DEPTH REVEAL
───────────────────────────
Secondary systems introduced: [List]
First major decision point: [What choice matters here?]
First reward moment: [What do they earn and how is it presented?]
Social hook: [Leaderboard, friend data, share prompt — if applicable]

MINUTE 15–30: THE HOOK
───────────────────────
Long-term progression teased: [What do they see that's locked / aspirational?]
Return motivation established: [What makes them want to come back?]
Session natural end: [How does the game gracefully end the first session?]
D1 retention mechanism: [Notification / Save point / Cliffhanger / Active quest]
```

### Tutorial Design Rules for This Game

Document which tutorial philosophy applies and why:

| Philosophy | Definition | Best For | Avoid For |
|------------|-----------|----------|-----------|
| Discovery | No explicit tutorial. Systems are simple enough to discover. | Casual puzzle, simple arcade | Deep RPG, multiplayer |
| Contextual Hints | Prompts appear when a new mechanic becomes relevant | Most games | Very casual (too much text) |
| Guided Prologue | First level IS the tutorial, gameplay teaches | Narrative games, action games | Very long intros feel slow |
| Forced Tutorial | Player must complete tutorial before free play | Complex systems, new genres | Experienced player audiences |
| Optional Tutorial | Full tutorial available, main game accessible immediately | Sequels, genre-savvy audiences | New genre, complex systems |

**Selected Philosophy:** [Choice] — [Rationale specific to this game and audience]

---

## Part 5: Navigation Hierarchy

Full navigation map showing how every screen connects:

```
App Launch
    └─→ Loading Screen
            └─→ Main Menu
                    ├─→ New Game → Character Select → Tutorial → HUD
                    ├─→ Continue → HUD (last save)
                    ├─→ Load Game → Save Select → HUD
                    ├─→ Settings ←→ (returns to Main Menu)
                    ├─→ Store ←→ (returns to Main Menu)
                    └─→ Credits ←→ (returns to Main Menu)

HUD (active gameplay)
    ├─→ Pause [ESC/Start]
    │       ├─→ Resume → HUD
    │       ├─→ Settings → (returns to Pause)
    │       ├─→ Save Game → (returns to Pause)
    │       └─→ Quit to Main Menu
    ├─→ Inventory [I/Select]
    │       └─→ HUD (close)
    ├─→ Map [M/Back]
    │       └─→ HUD (close)
    ├─→ Dialogue [proximity trigger]
    │       └─→ HUD (dialogue complete)
    └─→ Death → Game Over → [Retry / Main Menu]
```

---

## Part 6: Accessibility Specification

Document all accessibility features. This section is required for console certification and App Store compliance.

### Required Accessibility Features

| Feature | Requirement | Implementation Notes |
|---------|-------------|---------------------|
| Text Size | All UI text: min 18px at 1080p | Scale with system font size setting |
| Colorblind Mode | Protanopia, Deuteranopia, Tritanopia modes | Recolor all gameplay-critical indicators |
| Subtitles | All voice acting, all ambient spoken text | On by default, size adjustable |
| Subtitle Background | Semi-transparent backdrop behind subtitle text | Opacity adjustable 50–100% |
| Input Remapping | All inputs rebindable | PC: full keyboard + mouse, Controller: all face/shoulder buttons |
| High Contrast Mode | UI elements increase contrast ratio to 7:1 minimum | WCAG AA compliance target |
| Reduced Motion | Option to disable screen shake, flashing effects | Required for photosensitivity |
| Audio Description | [Scope] — if story-critical visual events have no audio cue | Flag each instance |
| Mono Audio | Mix all audio to mono channel for single-ear users | Audio settings toggle |
| UI Navigation | All menus fully navigable by controller/keyboard alone | No mouse-only interactions |

### Colorblind Mode Specification

| Color | Normal | Protanopia | Deuteranopia | Tritanopia |
|-------|--------|-----------|--------------|-----------|
| Enemy HP bar | Red | Orange | Yellow | Pink |
| Player HP (low) | Red flash | Orange pulse | Yellow pulse | Pink pulse |
| Positive effect | Green | Cyan | Cyan | Green |
| Negative effect | Red | Orange | Yellow | Pink |
| Neutral / Info | Blue | Blue | Blue | Yellow |
| Rare item | Purple | [color] | [color] | [color] |

---

## Anti-Patterns

| Anti-Pattern | Problem | Fix |
|-------------|---------|-----|
| Tutorial as dump of all mechanics upfront | Players skip or forget before relevant | Introduce mechanics at point of first use |
| HUD with 15+ persistent elements | Cognitive overload, especially on mobile | Show contextually — default hide non-critical elements |
| Back navigation inconsistency | Player gets lost | Every screen has a predictable back action |
| First interactive moment delayed > 30 seconds | Player disengages before core loop | Cut cinematics, credits logos, long loading before first input |
| No pause in action games | No bathroom break = game abandoned | Always implement pause, even in "live" single-player |
| Mobile: interactive elements in top 20% of screen | Phone holder can't reach | Keep all interactives in bottom 60% of portrait screen |
| Required tutorial that can't be skipped in sequels | Veteran players bounce immediately | Always allow skip after first playthrough |

# Art Direction Template

Use this template for Section 10 (Art Direction) of the GDD. The art direction section is a contract between the design team and the art team. It must be specific enough that every artist on the team can independently create assets that feel cohesive, without a 1-on-1 art direction call. Vague instructions ("stylized but realistic") produce inconsistent results — specific instructions with visual references produce a unified game.

---

## Part 1: Visual Style Statement

Write a single paragraph (3–5 sentences) that captures the visual identity of the game. This paragraph is the north star for every art decision. If a proposed asset doesn't fit this description, it needs to change.

**Format:**
> "[GAME TITLE] looks like [primary visual influence] filtered through [secondary influence/lens]. The world feels [2-3 adjectives], achieved through [specific technique — e.g., hand-painted textures / heavy outline cel-shading / photorealistic materials with stylized lighting]. Color is used deliberately: [color philosophy — e.g., the environment is desaturated to make reward items vibrate with saturated orange and yellow]. The player character stands out from the environment through [silhouette contrast / color contrast / lighting]. Animation feels [descriptor: snappy / weighty / floaty / precise] — [specific animation design principle that matters most for this game]."

**Example (roguelike deckbuilder):**
> "Void Cartographer looks like a hand-inked comic book brought into motion — thick black outlines, flat color fills with a grain texture overlay, and cel-shaded lighting that never tries to look realistic. The world is deep blues and purples punctuated by card art that pops in warm amber and crimson. Player cards are the most detailed thing on screen; everything else is deliberate negative space. Animation is snappy and punchy — zero ease-in on attacks, hit-pause on impactful moments, satisfying crunch on card plays."

---

## Part 2: Visual Influences

List 3–7 references with specific elements extracted. "Like Hollow Knight" is useless — "Like Hollow Knight's color palette: desaturated backgrounds, saturated foreground characters, strong silhouettes" is useful.

| # | Reference | Type | What We Take From It | What We Don't Take |
|---|-----------|------|---------------------|-------------------|
| 1 | [Title / Artist / Film] | [Game/Film/Artist/Series] | [Specific: linework style, color philosophy, animation timing, etc.] | [What we consciously avoid from this reference] |
| 2 | [Title / Artist / Film] | | | |
| 3 | [Title / Artist / Film] | | | |
| 4 | [Title / Artist / Film] | | | |

**Example influences table:**
| # | Reference | Type | What We Take | What We Don't Take |
|---|-----------|------|-------------|-------------------|
| 1 | Hollow Knight | Game | Silhouette-first character design, desaturated world palette, strong key lighting | The extremely minimal HUD — ours has more active UI |
| 2 | Hades | Game | Vibrant character color coding, portrait-style ability icons, bold typography | The realistic shading approach — we stay 100% flat |
| 3 | Mike Mignola (Hellboy) | Artist | Heavy blacks, minimal detail in shadows, strong graphic shapes | Horror tone — we use the technique for a different mood |
| 4 | Persona series | Game | Clean UI with personality, high-contrast menus, expressive typography | Anime character proportions |

---

## Part 3: Color Palette

Define every color role explicitly. These become variables in UI implementation, shader properties, and style guides.

### Primary Palette (Environment & World)

| Role | Name | Hex Code | Usage |
|------|------|----------|-------|
| World Background | Deep Void | `#0E0E1A` | Primary backgrounds, sky, deep shadow |
| World Midtone | Dusk Slate | `#2A2B3D` | Stone, neutral surfaces, fog |
| World Highlight | Pale Bone | `#D4C9B0` | Light sources, moonlight, fog highlights |

### Character Palette

| Role | Name | Hex Code | Usage |
|------|------|----------|-------|
| Player Primary | Hero Gold | `#E8B84B` | Player character primary color, friendly UI |
| Player Secondary | Warm Ivory | `#F5EDD4` | Player skin/light detail areas |
| Enemy Base | Blood Rust | `#8B2020` | Common enemy primary |
| Enemy Elite | Deep Crimson | `#5A0000` | Elite/boss enemy accents |

### UI Palette

| Role | Name | Hex Code | Usage |
|------|------|----------|-------|
| UI Background | Dark Navy | `#1A1B2E` | Panel backgrounds, card backs |
| UI Border | Steel Blue | `#3D5A80` | Panel borders, dividers |
| Primary Text | Off-White | `#E8E6E1` | All body text |
| Secondary Text | Muted Silver | `#8C8FA0` | Labels, secondary info |
| Positive (HP, buff) | Vital Green | `#4CAF50` | Health, regeneration, positive status |
| Negative (damage, debuff) | Alert Red | `#E53935` | Damage, poison, negative status |
| Warning | Amber | `#FFB300` | Low resource, time pressure |
| Premium / Rare | Royal Purple | `#7B1FA2` | Rare items, premium currency |
| Legendary | Celestial Gold | `#FFD700` | Legendary items, critical moments |
| Interact Prompt | Bright Cyan | `#00BCD4` | "Press [E] to interact" highlights |

### Colorblind-Safe Palette Alternatives

| Color Role | Normal | Protanopia | Deuteranopia | Tritanopia |
|-----------|--------|-----------|--------------|-----------|
| Positive (green) | `#4CAF50` | `#0088FF` | `#0088FF` | `#4CAF50` |
| Negative (red) | `#E53935` | `#FF8800` | `#AAAA00` | `#FF0088` |
| Rare (purple) | `#7B1FA2` | `#0077AA` | `#0077AA` | `#7B1FA2` |

---

## Part 4: Character Art Guidelines

### Design Principles

| Principle | Rule | Rationale |
|-----------|------|-----------|
| Silhouette Clarity | Every character must be recognizable by silhouette alone | Readability in fast combat |
| Color Coding | Player = warm tones. Enemies = cool/dark tones. Neutral = grey | Immediate faction identification |
| Detail Priority | Most detail on face > hands > torso > feet | Players look at faces in dialogue, hands in combat |
| Scale Hierarchy | Bosses: 3× average enemy height. Elites: 1.5× average. Grunts: 1× player | Communicates threat level at a glance |

### Character Proportion Spec

| Character Type | Proportion | Body Type | Art Notes |
|---------------|-----------|-----------|-----------|
| Player Character | 6-head ratio | Athletic, readable silhouette | High detail; seen in close-up during dialogue |
| Common Enemy | 5-head ratio | Varied but consistent per archetype | Grouped; must read as a unit |
| Elite Enemy | 6.5-head ratio | More imposing than commons | Distinct silhouette feature (horn, weapon, armor) |
| Boss | 8+ head ratio, oversized features | Unique per boss | Signature feature readable at full arena distance |
| NPC / Civilian | 6-head ratio | Wide variety | Casual clothing, softer features than combat chars |

### Character Color Coding System

Define how players distinguish character roles at a glance:

| Role | Primary Color | Accent Color | Visual Tag |
|------|--------------|-------------|-----------|
| Player | Gold / Warm White | Bright Cyan for abilities | Glowing sigil on back (always visible) |
| Allied NPC | Soft Green | Gold | Green nameplate |
| Neutral NPC | Grey | White | No nameplate by default |
| Common Enemy | Dark Red | Black | Red nameplate |
| Elite Enemy | Deep Crimson | Gold | Orange nameplate, crown icon |
| Boss | Varies per boss | Signature color | Large nameplate, red HP bar at screen bottom |

---

## Part 5: Environment Art Guidelines

### Biome / Zone Visual Identity

Each major environment zone must have a distinct visual identity that tells the player WHERE they are:

| Zone | Primary Colors | Lighting | Texture Style | Density | Mood |
|------|--------------|---------|--------------|---------|------|
| [Zone 1 Name] | [Color palette] | [Warm/Cool/Neutral, direction] | [Style description] | [Sparse/Medium/Dense] | [2 adjectives] |
| [Zone 2 Name] | | | | | |
| Hub Area | Warm Amber, Wood Tones | Warm interior lighting | Worn, lived-in, detailed | Dense with NPCs | Safe, bustling |

### Environment Design Rules

| Rule | Specification |
|------|--------------|
| Background layers | 3 parallax layers minimum: far background, mid, foreground |
| Interactive objects | All interactable objects must have: [glowing edge / bright color accent / consistent icon] to distinguish from decoration |
| Platform readability | Platforms: [solid color outline / rim light / distinct texture] — must be unambiguous in motion |
| Hazard signaling | Hazards always use [Alert Red / bright orange] in at least one element before they activate |
| Elevation cues | [Lighter = closer / Darker = background] — consistent Z-depth communication |
| Destructible objects | [Cracked texture / visible damage state / distinct wobble before break] |

---

## Part 6: UI Art Style

### UI Design Philosophy

| Aspect | Choice | Rationale |
|--------|--------|-----------|
| Style | [Flat / Skeuomorphic / Illustrated / Minimal] | [Fits the game's art direction] |
| Personality | [Cold/clinical / Warm/organic / Techy/digital / Fantasy/ornate] | [Matches world fiction] |
| Typography | [Font name] — [license: Google Fonts / Adobe / Custom] | [Why this font] |
| Icon Style | [Flat icon / Illustrated icon / Photographic crop] | |
| Animation Style | [Snappy (< 100ms transitions) / Smooth (200–300ms) / Dramatic (300–500ms)] | |

### Typography Specification

| Use Case | Font | Weight | Size (at 1080p) | Color |
|---------|------|--------|-----------------|-------|
| Game Title / Large Headers | [Font Name] | Bold | 48–72px | `#E8E6E1` |
| Section Headers | [Font Name] | Medium | 24–36px | `#E8E6E1` |
| Body Text / Descriptions | [Font Name] | Regular | 18–24px | `#E8E6E1` |
| Small Labels / Captions | [Font Name] | Regular | 14–16px | `#8C8FA0` |
| Button Text | [Font Name] | Bold | 18–20px | White or context color |
| Numbers / Stats | [Monospace Font] | Regular | 16–22px | Context color |

**Minimum text size rule:** Never render text below 14px at 1080p resolution. At 4K, scale proportionally. On mobile, minimum 18px.

---

## Part 7: Animation Style

### Key Animation Principles

| Principle | Application | Example |
|-----------|------------|---------|
| [Principle 1, e.g., "Snappy"] | Short anticipation (2–4 frames), immediate action, hold on impact | Attack swing: 3 frame wind-up, 2 frames active, 2 frame hit-pause |
| [Principle 2, e.g., "Weight"] | Objects feel heavy: slow starts, fast middles, impactful stops | Landing: 6 frame squash on contact |
| [Principle 3, e.g., "Clarity"] | Actions telegraph before they happen | Boss attacks: 30-frame tell animation always precedes damage |
| [Principle 4, e.g., "Juice"] | Every impactful moment has layered feedback | Critical hit: hit-pause + flash + camera shake + big number |

### Mandatory "Feel Great" Animation Moments

These are the animation moments that define the game's feel. They receive extra polish:

1. **[Core action] execution:** [What must feel great, specific frame timing target]
2. **[Level up / major reward]:** [Celebration animation description]
3. **[Death/failure state]:** [How failure is communicated — not punishing, but clear]
4. **[Boss intro]:** [Cinematic entry to establish stakes]
5. **[Victory/level complete]:** [Reward animation that creates emotional close to a session]

---

## Part 8: Do Not Create List

Explicitly ban visual elements that would break the art direction. Being explicit prevents asset rejection late in production.

| Banned Element | Reason |
|---------------|--------|
| [Visual element] | [Why it breaks the style] |
| Gradient backgrounds with more than 2 color stops | Creates visual noise inconsistent with our flat style |
| Drop shadows on character sprites | We use outline strokes for depth; shadows create an inconsistent style |
| Photo-realistic textures on fantasy environments | Breaks visual cohesion with illustrated character art |
| Serif fonts in UI elements | Our UI font is sans-serif; mixing creates inconsistency |
| Real-world brand identities (logos, labels) | Legal risk + breaks fiction |
| Motion blur on gameplay elements | Target audience: motion blur = unreadable in action; reserved for cinematics only |

---

## Deliverable Format Requirements

| Asset Type | Format | Resolution | Notes |
|-----------|--------|-----------|-------|
| Character Sprites | PNG (transparent) | 4× target display size | For downsampling at runtime |
| Environment Tiles | PNG | Power-of-2 dimensions (512×512, 1024×1024) | Tileable edges on tileset assets |
| UI Elements | SVG or PNG | Vector preferred; PNG at 4× display size | Must support resolution scaling |
| Particle Textures | PNG (transparent) | 64×64 to 512×512 | Keep small — particles repeat |
| Fonts | .ttf or .otf | — | License permits embedding and distribution |
| Audio (Art Reference) | Reference art file attached to audio brief | — | For composer/SFX artist alignment |

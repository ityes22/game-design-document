# Monetization Strategy Template

Use this template for Section 13 (Monetization Strategy) of the GDD. A complete monetization section communicates not just what the game sells, but why the model fits the audience, how it's priced competitively, and what ethical commitments have been made. Publishers, investors, and platform holders all scrutinize this section.

---

## Part 1: Revenue Model Selection

### Model Selection Matrix

| Model | Best For | Audience Fit | Platform Notes | Examples |
|-------|----------|-------------|----------------|---------|
| Premium ($15–$70) | PC/console, experienced players, strong IP | Hardcore, willing to pay upfront | Strong on Steam, console stores | Hades, Hollow Knight, BG3 |
| Free-to-Play | Mobile, competitive, social games | Casual–midcore, price-sensitive | App stores, PC F2P (Steam) | Genshin Impact, League of Legends |
| F2P + Battle Pass | Live service, seasonal content | Midcore, session-based habits | Cross-platform, strong on console | Fortnite, Apex Legends |
| Premium + DLC | Strong base game + expansion content | Midcore–hardcore, invested players | PC/console, Paradox model | CK3, Civilization VI |
| Subscription | High content volume, catalog access | Mainstream, value-seekers | Xbox Game Pass, PS+, Apple Arcade | Any Game Pass title |
| Hybrid (Premium + F2P mode) | Games with both single-player + MP | Wide audience, varied sessions | Complex to manage, high ceiling | GTA V, Rocket League |

**Selected Model:** [Model Name]

**Rationale:** [Why this model for this game and audience. Reference player segment data, comparable title revenue, and platform recommendation.]

---

## Part 2: Player Segment Revenue Model

### Segment Definitions

| Segment | % of Players | Monthly Spend | Behavior Profile |
|---------|-------------|---------------|-----------------|
| Free | 70% | $0 | Play indefinitely without paying; necessary for healthy multiplayer population and social proof |
| Dolphin | 20% | $5–$50 | Buy battle passes, occasional cosmetics, premium currency bundles at value prices |
| Whale | 10% | $50–$500+ | Complete battle passes, gacha pulls, exclusive bundles; driven by completionism and status |

**Revenue Distribution Target:**
```
Free:    $0/mo × 70% = $0
Dolphin: $15/mo average × 20% = $3.00 per player
Whale:   $80/mo average × 10% = $8.00 per player
─────────────────────────────────────────
Blended ARPU target: $11.00/mo
D30 conversion rate target: 3–5% (industry standard for healthy F2P)
```

**Note:** For premium games, replace this table with:
- Unit price point
- Projected attach rate for each DLC tier
- Expected revenue per user over game's commercial life

---

## Part 3: IAP Catalog

### Catalog Design Principles

For this game, the IAP catalog follows these rules:
1. [State your ethical commitments — e.g., "No gameplay-affecting items sold for real money in PvP modes"]
2. [Content policy — e.g., "Cosmetics only in the premium store"]
3. [Value principle — e.g., "Players spending $10 receive visibly better value than 10 × $1 purchases"]

### IAP Catalog Table

| Item Name | Category | Price (USD) | Contents / Value | Target Buyer | Notes |
|-----------|----------|-------------|-----------------|--------------|-------|
| [Starter Pack] | Bundle (one-time) | $4.99 | 500 gems + exclusive cosmetic + 3-day XP boost | New players D1–D7 | One-time offer, highest conversion rate |
| [Battle Pass — Free Track] | Subscription | $0 | 30 tiers, cosmetic rewards | All players | Free tier maintains engagement |
| [Battle Pass — Premium] | Subscription | $9.99/season | 30 tiers × 2 tracks, 2,500 gems value | Dolphins | 8-week season; auto-renew optional |
| [Small Gem Pack] | Currency | $0.99 | 60 gems | Micro-transactors | Entry price point |
| [Standard Gem Pack] | Currency | $4.99 | 330 gems (+10% bonus) | Dolphins | Best value per dollar at this tier |
| [Value Gem Pack] | Currency | $9.99 | 700 gems (+20% bonus) | Dolphins | Most popular price point (industry: $4.99–$9.99 highest unit volume) |
| [Large Gem Pack] | Currency | $19.99 | 1,500 gems (+25% bonus) | Whales | |
| [Mega Gem Pack] | Currency | $49.99 | 4,200 gems (+30% bonus) | Whales | |
| [Whale Pack] | Currency | $99.99 | 9,000 gems (+35% bonus) | Whales | Requires store review in some regions |
| [Character Skin — Standard] | Cosmetic | $4.99 | 1 character skin | Any paying player | |
| [Character Skin — Premium] | Cosmetic | $9.99 | 1 premium animated skin | Dolphins/Whales | |
| [Limited Bundle] | Bundle (timed) | $14.99 | Skin + emote + 500 gems | Dolphins | 48-hour windows; drives urgency |
| [Season Pass] | Bundle | $24.99 | Battle Pass + 2,500 gems + exclusive title | Whales | Best overall value |

### Premium Currency Conversion Rate

| Real Currency (USD) | Gems Received | Rate (gems/$) | Relative Value |
|--------------------|---------------|---------------|----------------|
| $0.99 | 60 | 60.6 gems/$ | Baseline |
| $4.99 | 330 | 66.1 gems/$ | +9% vs baseline |
| $9.99 | 700 | 70.1 gems/$ | +16% vs baseline |
| $19.99 | 1,500 | 75.0 gems/$ | +24% vs baseline |
| $49.99 | 4,200 | 84.0 gems/$ | +39% vs baseline |
| $99.99 | 9,000 | 90.0 gems/$ | +49% vs baseline |

**Design principle:** Volume discounts reward higher-spending players. The $4.99 pack must feel meaningfully better than buying 5 × $0.99. Whales buying the $99.99 pack receive approximately 50% more value per dollar than the minimum purchase — this drives the "big purchase" behavior that disproportionately drives revenue.

---

## Part 4: Battle Pass Structure

*Skip this section if the game does not include a battle pass.*

### Season Overview

| Field | Value |
|-------|-------|
| Season Length | [N weeks] |
| Total Tiers | [N tiers] |
| Free Track Tiers | [N tiers — recommend 30% of total] |
| Premium Track Tiers | [N tiers — recommend 70% of total] |
| Premium Track Price | $[X.XX] |
| Tier Skip Option | [Available at $[X] per tier / Not available] |
| Season Pass XP Earn Rate | [X XP per match/session, target 60% completion at Average play] |

### Reward Cadence Design

Reward placement drives retention. Follow this cadence:

| Phase | Tier Range | Reward Quality | Design Goal |
|-------|-----------|---------------|-------------|
| Opening Hook | 1–5 | High (early wins) | Immediately reward, hook new buyers |
| Valley | 6–15 | Medium | Steady progress, avoid plateau |
| Mid-Season Spike | 16–20 | High (premium skin reveal) | Re-engage lapsed players |
| Grind Zone | 21–25 | Low–Medium | Natural attrition, invested players persist |
| Final Push | 26–30 | Highest (grand prize) | Drive sessions in final 2 weeks |

### Perceived Value Calculation

The battle pass must offer ≥ 3× perceived value versus purchase price. Calculate:

| Item | Market Value | Notes |
|------|-------------|-------|
| Premium Skins (3×) | $4.99 × 3 = $14.97 | Sold separately at $4.99 |
| Standard Skins (5×) | $2.99 × 5 = $14.95 | |
| Currency (returned in gems) | $6.00 | ~60% of pass price returned as gems |
| Emotes, titles, charms | $4.00 | Estimated value |
| **Total Perceived Value** | **$39.92** | 4× the $9.99 price point ✓ |

**Rule:** If perceived value ratio drops below 3×, add content. Do not lower the price — it devalues future passes.

---

## Part 5: Ethical Guidelines

### Mandatory Commitments

Check all that apply to this game and document compliance approach:

- [ ] **No Pay-to-Win in PvP:** No item sold for real money provides a statistical advantage in competitive player-vs-player modes
- [ ] **Mandatory Odds Disclosure:** All randomized purchases (loot boxes, gacha) display exact drop rates in-app before purchase
- [ ] **Spending Alerts:** Implement in-app warnings at $50, $100, and $250 cumulative monthly spend
- [ ] **Minor Protections:** If game is rated E–T, disable direct currency purchases without parental approval flow. No FOMO-based marketing targeting under-18.
- [ ] **No Predatory Countdowns:** Limited-time offers must have genuine scarcity (not artificially reset after countdown). Minimum 24-hour return window for any "limited" offer.
- [ ] **No Manipulative Dark Patterns:** No fake "sold out" indicators, no false urgency on evergreen items, no shame-based purchase flows
- [ ] **Refund Policy:** Clear in-game link to platform refund policy. No policy language that attempts to restrict platform-standard refund rights.
- [ ] **Transparency on Gacha (if applicable):** Publish pity rates, soft pity mechanics, and guaranteed rates in-app. Comply with China's mandatory disclosure and minor spending limits.

### Regional Compliance

| Region | Requirement | Compliance Action |
|--------|-------------|------------------|
| Belgium | Loot boxes classified as gambling — prohibited for all ages | [Remove / Replace with direct purchase] |
| Netherlands | Loot boxes restricted — must be unlockable with in-game currency only | [Ensure loot boxes earnable without real money] |
| China | Mandatory rate disclosure, monthly spend limit for minors (CNY 400 for under-16) | [Implement disclosure + spending caps + ID verification] |
| Japan | JOGA compliance — no "Complete Gacha" (collecting sets for bonus) | [Audit gacha design against JOGA] |
| Apple App Store | Mandatory odds disclosure for loot boxes since iOS 15 | [In-app probability display required before purchase] |
| Google Play | Same as Apple since 2022 | [Same as Apple] |
| South Korea | Mandatory loot box rate disclosure since 2015 | [Same as odds disclosure above] |
| United States | FTC guidelines on endorsements and children's advertising | [COPPA compliance if under-13 accessible] |

---

## Part 6: Pricing Strategy

### Regional Price Localization

Base price: $[X] USD

| Region | Currency | Price | Multiplier vs USD |
|--------|----------|-------|------------------|
| US | USD | $9.99 | 1.0× |
| Europe | EUR | €9.99 | ~1.0× (minor premium acceptable) |
| UK | GBP | £7.99 | ~0.85× |
| Brazil | BRL | R$39.99 | ~0.37× (local purchasing power) |
| Russia | RUB | ₽649 | ~0.07× (Steam regional pricing) |
| India | INR | ₹599 | ~0.07× |
| Southeast Asia | USD | $3.99–$7.99 | 0.40–0.80× |
| China | CNY | ¥68 | ~0.10× |

**Rule:** Use platform regional price tiers (Steam, App Store, Google Play all have standard regional price points). Do not set custom prices that deviate from platform recommendations without revenue analysis.

### Launch Promotions

| Promotion | Discount | Duration | Goal |
|-----------|----------|----------|------|
| Launch Week Sale (if premium) | 15% off | 7 days | Volume, Steam rank, reviews |
| Early Access Discount | 20% off | EA period | Early adopters, feedback |
| Starter Pack (F2P) | First-purchase bonus +50% gems | D1–D3 only | D1 conversion rate |
| Seasonal Sales | 25–50% off premium / gem bonuses | Platform sale events | Re-engagement, new market |

---

## Part 7: KPI Targets

| Metric | Target | Industry Benchmark | Notes |
|--------|--------|--------------------|-------|
| D1 Retention | 40% | 30–45% (mobile), 25–35% (PC) | Day 1 return rate |
| D7 Retention | 15% | 10–20% | |
| D30 Retention | 8% | 5–10% | |
| D30 Conversion (F2P) | 3–5% | 2–5% | % of players who spend any amount |
| Blended ARPU | $11/mo | Varies by genre | Average Revenue Per User |
| ARPPU | $25–$40/mo | Varies | Average Revenue Per Paying User |
| LTV (Lifetime) | $35 | Varies by genre/platform | Revenue per acquired user over lifetime |
| Battle Pass Attach Rate | 15–20% | 10–25% for live service | % of active players buying pass |

---

## Anti-Patterns

| Pattern | Why It's Dangerous | Ethical Alternative |
|---------|-------------------|---------------------|
| Loot boxes as primary progression unlock | Gambling mechanics for essential content | Sell direct items; loot for cosmetics only |
| "Almost enough" currency bundles | Forces purchase of next tier to use remainder | Sell exact amounts needed for common purchases |
| Random starter pack on D1 that includes luck-based item | First experience is gambling | D1 offer must be deterministic items |
| Indefinite countdown timer that resets | Fake scarcity; destroys trust when discovered | Only run limited offers with genuine supply limits |
| Unskippable purchase prompts | Dark pattern, causes refunds and reviews | All store screens optional, easily dismissed |
| Spending required to remove frustration (e.g., energy timers) | F2P design that punishes non-payers | Make free play satisfying; premium accelerates, not enables |

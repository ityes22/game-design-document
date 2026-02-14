# Technical Requirements Template

Use this template for Section 15 (Technical Requirements) of the GDD. The technical requirements section must give an engineer enough information to scope a technical design document (TDD) without further clarification. It does not replace the TDD — it sets the requirements that the TDD must satisfy.

---

## Part 1: Engine & Technology Stack

### Engine Selection

| Decision | Choice | Rationale |
|----------|--------|-----------|
| Game Engine | [Unity 2023.x / Unreal Engine 5.x / Godot 4.x / Custom / etc.] | [Why this engine: team familiarity, feature fit, licensing cost, platform support] |
| Engine Version | [Specific version number — lock this early] | [Avoid version upgrades mid-production unless critical] |
| Scripting Language | [C# / C++ / GDScript / Blueprint / etc.] | |
| Rendering Pipeline | [URP / HDRP / Built-in / etc.] | [URP: mobile/cross-platform; HDRP: high-end PC/console] |
| Physics Engine | [Built-in / PhysX / Havok / custom] | |
| Animation System | [Animator / Spine / custom state machine] | |

**Engine Selection Rationale (full paragraph):**
[Explain the decision in prose. Include: team expertise, comparable titles that used this engine, licensing considerations, platform-specific features needed, and known limitations.]

---

## Part 2: Platform Targets

### Platform Specifications

| Platform | Target | Certification Required | Notes |
|----------|--------|----------------------|-------|
| PC (Windows) | Primary | Steam (standard review) | Minimum specs below |
| PC (Mac) | Secondary | Steam + Mac review | Apple Silicon required |
| PC (Linux) | Stretch | Steam Deck Verified | Proton compatibility |
| iOS | [Yes/No] | Apple App Store review | iOS 16+ minimum |
| Android | [Yes/No] | Google Play review | Android 9.0+ minimum |
| PlayStation 5 | [Yes/No] | Sony certification (weeks–months) | DualSense haptics spec |
| PlayStation 4 | [Yes/No] | Sony certification | |
| Xbox Series X|S | [Yes/No] | Microsoft certification | Smart Delivery required |
| Xbox One | [Yes/No] | Microsoft certification | |
| Nintendo Switch | [Yes/No] | Nintendo Lot Check | Joy-Con support, docked + handheld |

### PC Hardware Specifications

| Spec | Minimum | Recommended | Ultra (4K/High Settings) |
|------|---------|-------------|--------------------------|
| OS | Windows 10 (64-bit) | Windows 11 | Windows 11 |
| CPU | Intel Core i5-8400 / AMD Ryzen 5 2600 | Intel Core i7-10700K / AMD Ryzen 7 5800X | Intel Core i9-12900K |
| RAM | 8 GB | 16 GB | 32 GB |
| GPU | NVIDIA GTX 1060 6GB / AMD RX 580 | NVIDIA RTX 2070 / AMD RX 6700 XT | NVIDIA RTX 3080 / AMD RX 6900 XT |
| VRAM | 4 GB | 8 GB | 10 GB+ |
| Storage | [X] GB HDD | [X] GB SSD | [X] GB NVMe SSD |
| DirectX | DirectX 11 | DirectX 12 | DirectX 12 Ultimate |
| Network | Not required | Broadband (MP only) | Broadband |

### Mobile Hardware Specifications

| Spec | Minimum iOS | Recommended iOS | Minimum Android | Recommended Android |
|------|------------|-----------------|-----------------|---------------------|
| OS Version | iOS 16.0 | iOS 17.0+ | Android 9.0 | Android 12.0+ |
| RAM | 3 GB | 6 GB | 3 GB | 6 GB |
| CPU | Apple A12 | Apple A15+ | Snapdragon 730 | Snapdragon 888+ |
| GPU | Apple A12 GPU | Apple A15 GPU | Adreno 618 | Adreno 660+ |
| Storage | [X] GB | [X] GB | [X] GB | [X] GB |
| Screen | 1080×1920 | 1080×2340+ | 720×1280 | 1080×2340+ |

### Performance Targets

| Metric | PC (Minimum) | PC (Recommended) | Console | Mobile |
|--------|-------------|-----------------|---------|--------|
| Frame Rate | 30 FPS stable | 60 FPS stable | 60 FPS (4K on Series X) | 30 FPS stable |
| Load Time (initial) | < 60 seconds | < 30 seconds | < 30 seconds | < 45 seconds |
| Load Time (level) | < 30 seconds | < 15 seconds | < 15 seconds | < 20 seconds |
| RAM Usage (max) | < 6 GB | < 8 GB | Console allocation | < 2 GB |
| VRAM Usage (min spec) | < 3.5 GB | — | — | — |
| Texture Streaming | Required | — | — | Required |

---

## Part 3: Networking Architecture

*Complete this section only for online/multiplayer games. Mark "N/A — Single Player" if offline.*

### Network Model

| Field | Value | Rationale |
|-------|-------|-----------|
| Architecture | [Dedicated Servers / P2P / Client-Server / Hybrid] | [Why this choice for this game type] |
| Tick Rate | [20 / 30 / 60 / 128] Hz | [Higher = smoother but higher server cost; justify] |
| Max Concurrent Players per Session | [N] | |
| Session Type | [Instanced / Persistent world / Lobby-based] | |
| Latency Target (acceptable) | [< Xms RTT] | [Racing: < 50ms; Turn-based: < 500ms; FPS: < 60ms] |
| Latency Target (ideal) | [< Xms RTT] | |
| Disconnect Handling | [Grace period: Xs / Bot replacement / Session ends] | |

### Server Infrastructure

| Component | Service | Notes |
|-----------|---------|-------|
| Game Servers | [AWS GameLift / Azure Playfab / Dedicated / etc.] | |
| Matchmaking | [In-house / Gamelift / PlayFab / GSDK] | |
| Backend / API | [AWS / GCP / Azure / Supabase / etc.] | |
| CDN (assets) | [CloudFront / Fastly / etc.] | For asset delivery only |
| DDoS Protection | [AWS Shield / Cloudflare / etc.] | Required for any public-facing server |

### Cheat Prevention

| Threat | Mitigation |
|--------|-----------|
| Client-side stat manipulation | All authoritative calculations server-side |
| Speed hacks | Server-side position validation with tolerance window |
| Aim bots | [Easy Anti-Cheat / BattlEye / server-side anomaly detection] |
| Memory tampering | [EAC / VAC / code obfuscation for sensitive values] |
| Replay/packet injection | Server authoritative + sequence numbers |

---

## Part 4: Third-Party Services & SDKs

### Required Integrations

| Service | Purpose | Platform | License Cost Model |
|---------|---------|----------|--------------------|
| [Analytics SDK] | Player behavior tracking, funnel analysis | All | [Free tier / % revenue / flat fee] |
| [Crash Reporting] (Sentry/Crashlytics) | Crash logs with stack traces | All | Free / paid tiers |
| [Authentication] (Steam SDK / Apple Sign-In / Google Play Games) | Platform-native sign-in | Per-platform | Platform-free |
| [Cloud Saves] | Cross-device save sync | All | Platform-native + backup |
| [Push Notifications] (Firebase) | D7/D30 retention campaigns | Mobile | Free / paid tiers |
| [Ad SDK] (Unity Ads / IronSource / MAX) | Ad monetization | Mobile (if applicable) | Revenue share |
| [Payment SDK] | IAP processing | All | Platform fee 15–30% |
| [Live Config] (Remote Config / Firebase) | Dynamic game parameter tuning | All | Free / paid |
| [A/B Testing] | Economy and UX experiments | All | [Service] |
| [Social / Friends] | Friends list, invites, leaderboards | Platform-native | Platform-free |
| [Voice Chat] (Discord / Vivox) | In-game voice | PC/Console | [License model] |
| [Anti-Cheat] (Easy Anti-Cheat / BattlEye) | Competitive integrity | PC/Console | Platform-included / license fee |

### Analytics Event Specification

Document every analytics event at launch. Minimum required events:

| Event Name | Trigger | Properties | Purpose |
|------------|---------|------------|---------|
| `session_start` | App foreground | platform, version, user_id | DAU, session count |
| `session_end` | App background | session_length_s, screens_visited | Session length |
| `tutorial_step` | Each tutorial step | step_number, completed (bool), time_elapsed | Tutorial funnel |
| `tutorial_complete` | Tutorial finish | total_time_s | Tutorial completion rate |
| `level_start` | Level begins | level_id, player_level, attempt_number | Content engagement |
| `level_complete` | Level won | level_id, time_s, score, deaths | Completion rate, difficulty |
| `level_fail` | Level lost | level_id, cause, attempt_number | Difficulty spike detection |
| `upgrade_selected` | Player upgrades anything | upgrade_id, cost, player_resources_before | Progression choices |
| `store_open` | Player opens store | source (menu/shortcut/post-death) | Purchase intent |
| `purchase_start` | Player taps buy | item_id, price_usd, currency_type | Conversion funnel |
| `purchase_complete` | Transaction confirmed | item_id, price_usd, revenue | Revenue tracking |
| `purchase_cancel` | Player cancels at payment | item_id, price_usd, step | Drop-off analysis |
| `ad_shown` | Ad impression | ad_type, placement, duration | Ad revenue |
| `ad_clicked` | Ad click | ad_type, placement | CTR |
| `first_purchase` | First real-money transaction | item_id, days_since_install | D1/D7 conversion |
| `churn_risk` | D7 with no purchase, low engagement | session_count, last_active | Retention trigger |

---

## Part 5: Build & Delivery Pipeline

### Build Configuration

| Config | Purpose | Update Frequency |
|--------|---------|-----------------|
| Development | Active development, debug tools enabled | Continuous (CI) |
| Staging | QA testing, mirrors production | Per sprint |
| Production | Live players | Per release |
| Review | Platform submission builds | Per certification submission |

### Deployment Strategy

| Platform | Deployment Method | Update Delivery | Rollback Strategy |
|----------|------------------|-----------------|------------------|
| PC Steam | Steam depot upload | Steam auto-update | Steam branch rollback |
| iOS | TestFlight → App Store Connect | App Store update (7–14 day review) | Previous binary rollback |
| Android | Internal Testing → Production | Play Store update (staged rollout) | Staged rollout pause |
| Console | Platform submission portal | Certification-gated patch | Emergency patch process |

---

## Part 6: Key Technical Risks

Document the 5-10 highest technical risks with mitigations. Be honest — this section protects the team.

| # | Risk | Category | Probability | Impact | Mitigation |
|---|------|----------|-------------|--------|-----------|
| 1 | [Technical challenge not solved by team before] | Engineering | High | High | [Prototype in pre-production, hire specialist, or reduce scope] |
| 2 | Console certification rejection due to crash | QA/Cert | Medium | High | [Dedicated cert build, 3-week certification buffer in schedule] |
| 3 | Server scaling at launch spike | Infrastructure | Medium | High | [Load testing at 10×, auto-scaling configured before soft launch] |
| 4 | Third-party SDK breaking change | Dependency | Low | High | [Pin SDK versions, maintain upgrade branch, have alternative identified] |
| 5 | Performance targets missed on minimum spec | Optimization | Medium | High | [Minimum spec device farm testing from alpha, dedicated optimization sprint] |
| 6 | [Specific risky system, e.g., procedural generation quality] | Design/Engineering | Medium | Medium | [Quality validation tool built in development, human review gate] |

---

## Anti-Patterns

| Anti-Pattern | Problem | Fix |
|-------------|---------|-----|
| "Latest Unity version" without specific number | Versions change; scope drifts | Lock to specific version at project start |
| No minimum spec defined at greenlight | Engineers optimize for wrong target | Define minimum spec before first line of game code |
| All analytics events added "later" | Post-launch you have no data to make decisions | Define D1 analytics events pre-alpha |
| No rollback plan for live service | Bad patch with no recovery = 1-star reviews | Staged rollout + rollback procedures documented before launch |
| Server costs estimated without load testing | 10× players = 10× cost = budget crisis | Load test at 5× and 10× expected day-1 concurrent |
| Platform submission scheduled day before deadline | Cert rejections require resubmission (weeks) | 3-week certification buffer minimum per platform |

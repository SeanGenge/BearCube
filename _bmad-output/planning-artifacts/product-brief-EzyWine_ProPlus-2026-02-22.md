---
stepsCompleted: [1, 2, 3, 4, 5]
inputDocuments:
  - _bmad-output/analysis/brainstorming-session-2026-02-22.md
  - _bmad-output/planning-artifacts/research/domain-speedcube-training-ecosystem-research-2026-02-22.md
  - documents/SMART_CUBE_HARDWARE_RESEARCH.md
date: 2026-02-22
author: Sean
---

# Product Brief: EzyWine_ProPlus

## Executive Summary

BearCube is an AI-powered speedcubing training platform that transforms raw solve data into actionable coaching — telling cubers not just *how* they solved, but *what to change* to get faster. While existing tools like csTimer, Cubeast, and acubemy show statistics and phase splits, none interpret that data into personalized guidance. BearCube bridges this gap with chess.com-style AI solve review, personalized algorithm recommendations based on turning style, and adaptive training plans that target each cuber's specific weaknesses. Built primarily for smart cube users but accessible to all cubers, BearCube is the personal coach that's available after every solve — at a fraction of the cost of human coaching.

---

## Core Vision

### Problem Statement

Speedcubers who want to improve face a coaching gap: they can track times and view statistics through free tools, but interpreting that data into actionable improvement steps requires expertise most cubers don't have. Existing tools show *what happened* in a solve but never tell you *what to do differently*. The alternative — human coaching at $30-40 per session — is expensive and inaccessible for most of the community, particularly younger cubers. This leaves cubers stuck at plateaus (sub-15, sub-10, sub-7) without clear guidance on what to practice or how to break through.

### Problem Impact

- **Plateau frustration**: Cubers hit walls at key thresholds (sub-20, sub-15, sub-10) and lack guidance on what specifically is holding them back — leading to wasted practice time or abandonment
- **Data without insight**: Smart cube users generate rich move-by-move data but existing tools present it as raw statistics, expecting cubers to self-diagnose inefficiencies
- **Coaching inaccessibility**: Human coaching is effective but expensive and infrequent — a cuber might get one session a month while practicing hundreds of solves
- **Algorithm selection blindness**: Cubers learn algorithms from generic guides without knowing whether those algorithms suit their personal turning style and finger-trick strengths

### Why Existing Solutions Fall Short

- **csTimer** (~90% market share): Excellent timer and statistics, but zero coaching or AI analysis. Client-side only — fundamentally cannot add server-side AI features
- **Cubeast**: Best smart cube analytics (recognition vs execution time, TPS), but shows data without interpretation — no "here's what to fix" guidance
- **acubemy**: Spaced repetition training and weakness identification, but lacks AI solve comparison or personalized algorithm recommendations
- **CubeStation (GAN)**: CFOP auto-segmentation and solution optimization suggestions, but locked to GAN hardware and plagued by bugs
- **No tool anywhere** offers chess.com-style AI solve review, turning-style-based algorithm recommendations, or adaptive training plans

### Proposed Solution

BearCube is an AI-powered training platform that acts as a personal speedcubing coach. After each smart cube solve, BearCube:

1. **Analyzes your solution** against AI-generated optimal solutions, scoring efficiency by CFOP phase
2. **Identifies specific weaknesses** — which F2L pairs cost extra moves, which algorithms are slow for your turning style, where recognition pauses occur
3. **Recommends what to learn next** — prioritized by maximum time-savings impact based on your actual solve data
4. **Builds personalized training plans** — adaptive curriculum that targets your specific gaps, not generic one-size-fits-all drills
5. **Tracks progress over time** — weekly reports, milestone celebrations, and plateau-breaking guidance

For cubers without smart cubes, BearCube offers solution-based analysis (scramble + solution input) and training tools, with the full AI coaching experience unlocked through smart cube integration.

### Key Differentiators

1. **AI Solve Review** — Chess.com-style move-by-move comparison of your solve against optimal. No cubing tool does this. The "ghost solve" side-by-side replay is the marketing video that sells itself.
2. **Personalized Algorithm Recommendations** — Analysis of your turning style (R/U dominant, slow on F turns) to recommend algorithms that match how *you* turn, not generic "best" algorithms.
3. **Actionable Coaching, Not Just Data** — Every insight comes with a specific action: "Your F2L pair 2 averages 4.2 moves when optimal is 3.1 — here's why and what to practice."
4. **Adaptive Training Plans** — Goal-driven curriculum ("you want sub-15, here's the roadmap") that updates as you improve, with prioritized drills ranked by time-savings impact.
5. **Community Intelligence Moat** — Aggregated anonymized solve data creates network effects: algorithm recommendations improve with every user, making BearCube harder to clone over time.

## Target Users

### Primary Users

**Persona 1: Ethan — The Intermediate Builder (Sub-30, age 13)**
Ethan knows beginner CFOP and averages around 25 seconds. He uses 2-look OLL and 2-look PLL and knows he needs to learn full OLL/PLL but doesn't know which algorithms to learn first or in what order. He currently practices on csTimer, watches J Perm videos, and picks random algorithms to learn without a strategy. He owns a MoYu WeiLong AI V10 smart cube he got for his birthday.

- **Core frustration:** "I know I need to learn more algorithms but there are 57 OLL cases and I don't know which ones matter most for me right now."
- **What BearCube gives him:** The "What Should I Learn Next?" engine analyzes his solves, identifies which unlearned cases appear most frequently, and prioritizes them by time-savings impact. Bite-sized training drills make learning manageable.
- **Success moment:** Ethan sees "Learn these 4 OLL cases — they cover 60% of your unrecognized cases, estimated 1.2s savings per solve" and his Ao100 drops from 25s to 22s in two weeks.

**Persona 2: Maya — The Plateau Grinder (Sub-15, age 17)**
Maya averages 14 seconds and has been stuck between 13-15s for months. She knows full OLL and PLL and thinks her F2L is "fine." She uses Cubeast with her GAN 356 i3 and can see her phase splits but doesn't know how to interpret them into actionable changes. She's considered paying for a coaching session but hasn't committed.

- **Core frustration:** "I can see my F2L takes 8 seconds but I don't know WHY or what specifically to change. I watch pro solves but can't figure out what they're doing differently."
- **What BearCube gives her:** AI solve review shows her that F2L pair 3 consistently costs 4+ extra moves, her recognition pause on 5 specific OLL cases averages 1.2s (vs 0.4s on others), and she does 5 rotations per solve when sub-10 solvers average 2.3. Specific drills target each weakness.
- **Success moment:** Maya sees the ghost solve replay — her solve on the left, optimal on the right — and instantly sees where she diverges. After two weeks of targeted F2L drills, her Ao100 drops to 13.1s.

**Persona 3: Kai — The Elite Optimizer (Sub-8, age 22)**
Kai averages 7.5 seconds and competes at WCA events. At this level, every 0.1s matters. He knows every algorithm but suspects some don't suit his turning style — he's R/U dominant and slow on F moves. He does manual video reconstructions of his best and worst solves, which takes 20 minutes per solve. He wants data-driven micro-optimizations.

- **Core frustration:** "I know there are faster algorithms for my turning style but I'd have to test dozens of alternatives manually. And reconstructing solves by video is painfully slow."
- **What BearCube gives him:** Turning style analysis reveals his exact speed profile per move type. Algorithm fingerprinting detects which algorithms he uses, and the recommendation engine suggests alternatives optimized for his R/U-dominant style — backed by community data showing how similar cubers improved. Auto-reconstruction replaces 20 minutes of video work with 2 seconds.
- **Success moment:** Kai switches 3 PLL algorithms to R/U-heavy alternatives recommended by BearCube and his PLL phase drops 0.2s average — meaningful at elite level.

**Persona 4: Jordan — The Manual Timer (Sub-20, age 15, no smart cube)**
Jordan averages 18 seconds and uses a regular speedcube. He can't afford a smart cube and uses csTimer for timing. He knows BearCube offers AI analysis but wonders if it's useful without smart cube data. He can enter scrambles and solutions manually.

- **Core frustration:** "I want to know if my solutions are efficient but I can't afford a smart cube and free tools just track my times."
- **What BearCube gives him:** Solution-based analysis — he enters a scramble and his solution, and BearCube compares it against optimal, scores efficiency by phase, and identifies wasted moves. He also gets the timer, daily challenges, streaks, and algorithm training tools. The full AI coaching experience (timing breakdowns, recognition detection, turning style) is available when he upgrades to a smart cube.
- **Success moment:** Jordan enters his solution and sees "Your cross used 8 moves — here's a 4-move cross for this scramble" and starts improving his cross planning immediately.

### Secondary Users

**Parents (Decision-Maker / Payer)**
Parents of younger cubers (ages 7-15) are the subscription decision-makers. They don't use the app themselves but need to see that their child is engaged, improving, and using something trustworthy. Weekly progress reports ("Your child improved their average by 1.3 seconds this week") and a professional, safe platform design build parent confidence. COPPA-aware data handling reinforces trust.

### User Journey

**Discovery:** Cuber sees a BearCube ghost solve replay shared on social media or recommended by a cubing YouTuber. The visual comparison of "your solve vs optimal" is immediately compelling.

**Onboarding:** No configuration required. Connect smart cube (or start with manual timer), do a few solves, and BearCube automatically detects your method, skill level, and algorithm set from your first 5 solves. Value from solve #1.

**Core Usage:** Daily practice sessions — solve, get instant AI debrief (2-line summary in timer view), review detailed analysis when curious. Weekly "Train Me" sessions where the app serves targeted drills based on weakness data. Daily challenge scramble for fun and community engagement.

**Success Moment ("Aha!"):** First time seeing the AI solve review — your solve side-by-side against optimal with color-coded moves (green/yellow/orange/red). The instant realization of "THAT's where I'm losing time" is the hook.

**Long-term Retention:** Weekly cubing reports with progress tracking, streak maintenance, micro-PR celebrations that find progress even during plateaus, and a training plan that adapts as you improve. The app gets more valuable the more you use it — your cuber profile deepens, recommendations sharpen, and training becomes more personalized.

## Success Metrics

### User Success Metrics

- **Measurable Improvement:** Users who engage with AI coaching recommendations show a measurable drop in average solve times (Ao100) within their first month of active use
- **Actionable Insight Engagement:** Users review AI solve analysis after 30%+ of their smart cube solves (not just timing — actively engaging with the coaching feedback)
- **Training Plan Completion:** Users complete recommended drills and algorithm training sessions served by the "Train Me" engine
- **Algorithm Adoption:** Users who receive personalized algorithm recommendations try them and show improved execution times on those cases
- **Retention Signal:** Users maintain a practice streak of 7+ days, indicating the app has become part of their routine

### Business Objectives

- **Freemium-to-Premium Conversion:** Validate that cubers are willing to pay $6.95/month for AI-powered coaching after experiencing the 30-day free trial
- **Platform Stickiness:** Build a daily-use habit — cubers choose BearCube as their primary training environment over csTimer/Cubeast
- **Data Flywheel:** Accumulate sufficient solve data to power community intelligence features (algorithm recommendations, peer benchmarking) — creating a network effect moat that strengthens with every user
- **Marketing & Organic Growth:** Leverage built-in viral mechanics (shareable solve cards, ghost solve replays, daily challenges) and cubing community channels (YouTube, Reddit, SpeedSolving) to drive awareness and adoption

### Key Performance Indicators

**3-Month Targets (Post-Launch):**

| KPI | Target | Measurement |
|-----|--------|-------------|
| Registered users | 50-200 | Total sign-ups |
| Daily Active Users (DAU) | 10-30 | Users completing at least 1 solve per day |
| Solves analyzed (AI) | 500+ total | Smart cube solves processed through AI analysis |
| Free trial → Premium conversion | 10-15% | Users converting after 30-day trial |
| Premium subscribers | 5-20 | Paying $6.95/month or $59.99/year |

**12-Month Targets:**

| KPI | Target | Measurement |
|-----|--------|-------------|
| Registered users | 5,000-10,000 | Total sign-ups |
| Daily Active Users (DAU) | 500-1,000 | Users completing at least 1 solve per day |
| Monthly solves analyzed | 50,000+ | Smart cube solves through AI analysis per month |
| Premium subscribers | 500-1,000 | Active paying users |
| Monthly Recurring Revenue (MRR) | $3,500-$7,000 | Premium subscription revenue |
| 30-day retention | 40%+ | Users active 30 days after sign-up |
| Annual plan adoption | 30%+ | Premium users choosing $59.99/year over monthly |

**Pricing Model (subject to adjustment based on market feedback):**

| Tier | Price | Details |
|------|-------|---------|
| Free | $0 | Basic timer, scrambles, manual timing, basic stats, local storage |
| Free Trial | $0 for 30 days | Full access to all Premium features |
| Premium (Monthly) | $6.95/month | AI solve review, smart cube support, advanced analytics, cloud sync, training plans, algorithm trainer |
| Premium (Annual) | $59.99/year (~$5.00/mo) | Same as monthly, ~28% savings |

**Leading Indicators (Early Warning Signals):**
- Solves per user per session trending up → product is engaging
- AI analysis views per solve trending up → coaching features are valued
- Trial users connecting smart cubes → investment in the ecosystem
- Shared solve cards / daily challenge participation → organic growth potential

## MVP Scope

### Core Features

**Stage 0 — Foundation**
- User authentication (13+ age gate, anonymous mode for younger users)
- Professional, clean timer with inspection countdown
- Random-state scramble generation (cubing.js, MPL license)
- Smart cube connection — GAN support at minimum (gan-web-bluetooth, MIT), architecture ready for MoYu/QiYi
- Basic statistics: Ao5, Ao12, Ao50, Ao100, session tracking
- 3D cube visualization showing real-time smart cube state

**Stage 1 — AI Solution Generation (Feasibility Gate)**
- Server-side Kociemba solver for near-optimal solutions (<1s, GPL server-side only)
- AlphaCube integration for neural network solutions (MIT)
- Solution generation API: scramble in → optimal solution out
- This stage is pass/fail — if reliable solution generation doesn't work, the product doesn't work

**Stage 2 — Solve Recording & Phase Detection**
- Record complete move sequence from smart cube with timestamps
- Automatic CFOP phase detection using solution-analyzer (MIT)
- Phase timing breakdown: Cross, F2L (per pair), OLL, PLL
- Recognition vs execution time detection (pause before first move of each phase)
- Move count per phase, TPS per phase

**Stage 3 — AI Solve Review (The "Aha Moment")**
- Compare user's solve against AI-generated optimal, phase by phase
- Efficiency score (0-100%) per phase and overall
- Move-by-move color grading: green (optimal), yellow (acceptable), orange (inefficient), red (wasted)
- Ghost solve replay: side-by-side 3D visualization — your solve vs optimal playing simultaneously
- Post-solve summary card with key insights (shareable as image)
- Instant 2-line AI debrief in timer view after each smart cube solve

**Stage 4 — Algorithm Fingerprinting & Knowledge Map**
- Pattern-match user's OLL/PLL sequences against known algorithm database
- Build cuber profile: which algorithms you know, which you don't, which you fumble
- Algorithm knowledge map: "You know 15/21 PLL. For the other 6, you use 2-look."
- Detect solve method automatically (CFOP/Roux/ZZ)
- Track case-specific recognition and execution times

**Stage 5 — "What Should I Learn Next?" Engine**
- Prioritized algorithm learning recommendations ranked by time-savings impact
- "Learn these 4 OLL cases — they cover 60% of your unrecognized cases, estimated 1.2s savings per solve"
- Basic cuber profile with strengths, weaknesses, and improvement areas
- Personalized training recommendations based on solve data patterns
- Goal-setting: "I want to get sub-15" → here's the roadmap showing what needs to change

**Quick Wins (Layered Throughout)**
- Practice streaks (daily solve streak counter)
- Daily challenge: one scramble per day, everyone gets ranked, shareable — no smart cube needed
- PR celebration engine: detect and celebrate micro-records (fastest cross this week, cleanest F2L ever, first sub-X Ao5)
- Zero-config onboarding: first 5 solves are the setup — no questionnaires, AI figures out your level and method

**Infrastructure**
- Cloud sync for premium users
- Freemium gating: AI features behind premium ($6.95/mo, $59.99/yr, 30-day free trial)
- HTTPS for Web Bluetooth security
- Responsive web design — works on desktop and mobile (Chrome/Edge)

### Out of Scope for MVP

- **Turning style detection & personalized algorithm recommendations** (Stage 6) — deferred to v1.1 as post-launch differentiator
- **Non-smart-cube manual solution entry** — architecture supports it, but not built for launch; focus on smart cube path first
- **Multi-cube support (4x4+)** — no smart 4x4 hardware exists yet; future-proof the data model but don't build UI
- **Social features** (activity feed, friend system, kudos) — daily challenge provides minimal social; full social layer deferred
- **Native iOS/Android app** — web-only at launch; iOS smart cube support requires native app (future)
- **MoYu/QiYi smart cube support** — GAN first, other brands in fast-follow updates post-launch
- **Competition simulator** — nice-to-have, not core to coaching value
- **Coaching platform for pro cubers** — future revenue stream, not MVP
- **csTimer data import** — reduces switching friction but not essential for day-one value
- **Weekly cubing reports** — deferred to post-launch; daily post-solve insights deliver value immediately
- **LLM-powered natural language coaching chat** — future enhancement when LLMs improve at cube-specific reasoning

### MVP Success Criteria

- **Feasibility validated:** AI solution generation reliably produces correct optimal solutions for any scramble
- **Core value delivered:** Users who complete 10+ AI-analyzed solves can articulate what they need to improve and have specific actions to take
- **Engagement signal:** Trial users are analyzing solves, not just timing — 30%+ of smart cube solves get AI review
- **Conversion signal:** 10-15% of free trial users convert to premium after 30 days
- **Retention signal:** 40%+ of active users return within 7 days
- **Go/no-go for Stage 6:** If MVP metrics are healthy, proceed with turning style detection and personalized algorithm recommendations

### Future Vision

**v1.1 — The Personalization Update (Stage 6)**
- Turning style detection: speed profile per move type (R/U/F/B/L/D)
- Personalized algorithm recommendations based on turning style and community data
- Community algorithm intelligence: "73% of sub-15 solvers with your turning profile use this T-perm"
- Rotation inference engine: count and reduce whole-cube rotations

**v1.2 — The Ecosystem Update**
- MoYu and QiYi smart cube support
- Non-smart-cube manual solution entry with full AI analysis
- csTimer JSON data import
- Weekly cubing report emails
- Adaptive training curriculum ("Train Me" auto-pilot mode)

**v2.0 — The Community Update**
- Peer benchmarking: "How does my F2L compare to others at my Ao100 level?"
- Social activity feed with cubing friends
- Competition preparation mode with simulated rounds
- Coaching platform: pro cubers use BearCube with their students
- Content creator integration: shareable replays, embeddable solve cards

**Long-term (2-3 years)**
- Native iOS app with CoreBluetooth for smart cube support
- 4x4/5x5 analysis when smart hardware arrives (CayleyPy integration)
- Real-time audio coaching hints during practice mode
- AR-guided solving overlay (proven 25% learning improvement in research)
- API access for developers wanting BearCube's AI analysis engine

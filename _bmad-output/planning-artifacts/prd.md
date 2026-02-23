---
stepsCompleted: ['step-01-init', 'step-02-discovery', 'step-03-success', 'step-04-journeys', 'step-05-domain', 'step-06-innovation', 'step-07-project-type', 'step-08-scoping', 'step-09-functional', 'step-10-nonfunctional', 'step-11-polish']
inputDocuments:
  - _bmad-output/planning-artifacts/product-brief-EzyWine_ProPlus-2026-02-22.md
  - _bmad-output/planning-artifacts/research/domain-speedcube-training-ecosystem-research-2026-02-22.md
  - _bmad-output/analysis/brainstorming-session-2026-02-22.md
  - documents/SMART_CUBE_HARDWARE_RESEARCH.md
documentCounts:
  briefs: 1
  research: 1
  brainstorming: 1
  projectDocs: 0
  projectContext: 0
workflowType: 'prd'
classification:
  projectType: 'Web App (SPA/PWA)'
  domain: 'EdTech / Sports Training'
  complexity: 'medium'
  projectContext: 'greenfield'
---

# Product Requirements Document - BearCube

**Author:** Sean
**Date:** 2026-02-22

## Executive Summary

**Product:** BearCube — an AI-powered speedcubing training platform that combines smart cube hardware integration with server-side AI solving to deliver chess.com-style move-by-move analysis for Rubik's cube speedsolving.

**Core Differentiator:** No existing tool compares a cuber's actual solve against an AI-generated optimal solution, phase by phase, with actionable coaching. csTimer (90% market share) is client-side only with no compute budget. Cubeast shows data without interpretation. BearCube assembles three mature open-source technologies (gan-web-bluetooth, Kociemba/AlphaCube, solution-analyzer) into a novel end-to-end coaching pipeline that no competitor has built.

**Target Users:** Speedcubers from intermediate (sub-30) through elite (sub-8), with a freemium tier for manual-timer users. Primary monetization through premium subscription ($6.95/mo, $59.99/yr) unlocking AI analysis and smart cube features.

**Platform:** Next.js PWA — works on all browsers for free features, Chrome/Edge required for smart cube (Web Bluetooth). GAN cubes supported at launch.

**Project Context:** Greenfield, solo developer with AI-assisted development. First-impression MVP strategy — release at stages 5-6 to ensure the speedcubing community's first experience justifies paying.

## Success Criteria

### User Success

- **Immediate value (Solve #1):** First smart cube solve produces an AI debrief that clearly shows something no other tool does — efficiency score, phase breakdown, and at least one actionable insight
- **Compounding personalization:** By solve 10+, the cuber profile (algorithm fingerprinting, weakness identification) makes coaching noticeably tailored to their specific gaps
- **Measurable improvement:** Users who engage with AI coaching recommendations show a measurable Ao100 drop within their first month of active use
- **Actionable insight engagement:** 30%+ of smart cube solves get AI review — users are learning, not just timing
- **Training plan adoption (Phase 2):** Users complete recommended drills and algorithm training sessions from the "What Should I Learn Next" engine
- **Retention signal:** Users maintain 7+ day practice streaks, indicating BearCube has become part of their routine

### Business Success

**3-Month Targets (Post-Launch):**

| KPI | Target | Measurement |
|-----|--------|-------------|
| Registered users | 50-200 | Total sign-ups |
| Daily Active Users | 10-30 | Users completing 1+ solve/day |
| AI solves analyzed | 500+ total | Smart cube solves through AI pipeline |
| Trial → Premium conversion | 10-15% | Users converting after 30-day trial |
| Premium subscribers | 5-20 | Paying $6.95/mo or $59.99/yr |

**12-Month Targets:**

| KPI | Target | Measurement |
|-----|--------|-------------|
| Registered users | 5,000-10,000 | Total sign-ups |
| Daily Active Users | 500-1,000 | Users completing 1+ solve/day |
| Monthly solves analyzed | 50,000+ | Smart cube solves through AI per month |
| Premium subscribers | 500-1,000 | Active paying users |
| MRR | $3,500-$7,000 | Premium subscription revenue |
| 30-day retention | 40%+ | Users active 30 days after sign-up |
| Annual plan adoption | 30%+ | Premium users choosing yearly plan |

**Leading Indicators:**
- Solves per user per session trending up (product is engaging)
- AI analysis views per solve trending up (coaching features valued)
- Trial users connecting smart cubes (ecosystem investment)
- Shared solve cards / daily challenge participation (organic growth signal)

### Technical Success

- **AI solution correctness:** 100% — Kociemba provides guaranteed correct near-optimal solutions. No tolerance for wrong solutions; trust is destroyed instantly in a niche community
- **AI analysis speed:** Sub-3 seconds from solve completion to AI debrief appearing in timer view. Brief loading animation acceptable, but must feel responsive
- **Smart cube connection reliability:** 95%+ successful connections on supported browsers (Chrome/Edge). Reconnection handling for dropped Bluetooth connections. GAN cubes supported at launch (tested with developer's own GAN hardware), other brands (MoYu, QiYi) post-launch
- **Solution generation latency:** Server-side Kociemba < 1 second per solve. AlphaCube for enhanced analysis within acceptable batch processing windows
- **Phase detection accuracy:** CFOP phase boundaries correctly identified on 95%+ of standard CFOP solves
- **Concurrent user support:** Architecture handles 100+ simultaneous users without degradation at launch scale

### Measurable Outcomes

- **Feasibility gate passed:** AI pipeline (scramble → optimal solution → phase comparison → user feedback) works end-to-end with correct results
- **"Worth paying for" validated:** Active paid subscribers exist and remain subscribed beyond first month — they're getting value
- **First impression test:** A cuber doing their first smart cube solve on BearCube can immediately see something no other tool shows them
- **Community reception:** Positive reception when shared on SpeedSolving/Reddit/cubing YouTube — the ghost solve replay is the marketing video that sells itself

## Product Scope

### MVP — Internal Feasibility (Stages 0-3)

The technical proof that the product can work:
- User auth with Google/social providers + email (ToS requires 13+)
- Professional timer with inspection countdown and random-state scrambles
- Smart cube connection (GAN support at launch)
- Basic statistics (Ao5/12/50/100, customizable)
- 3D cube visualization with real-time smart cube state
- Server-side Kociemba solver for correct near-optimal solutions
- Solve recording with CFOP phase detection
- AI solve review: phase-by-phase efficiency comparison against optimal
- Move-by-move color grading (green/yellow/orange/red)
- Ghost solve replay (side-by-side 3D visualization)
- Post-solve summary card with key insights
- Instant 2-line AI debrief in timer view

**Gate:** If Stage 1 (AI solution generation) fails to produce reliable correct solutions, the product concept doesn't work.

### Launch MVP (Stages 0-5, possibly 6)

The version that earns the right to charge — first public impression:
- Everything from internal MVP, plus:
- Algorithm fingerprinting (OLL 57 + PLL 21) — detect which algorithms the user knows from solve data
- Algorithm knowledge map ("You know 15/21 PLL")
- Basic cuber profile with strengths/weaknesses
- XCross, double XCross, and pseudo solution generation (each toggleable)
- WCA profile linking

**Quick wins layered throughout:**
- Practice streaks (daily solve counter)
- Daily challenge (one scramble/day, ranked, shareable, manual/verified distinction)
- PR celebration engine (micro-records: fastest cross this week, first sub-X Ao5)
- Zero-config onboarding (first 5 solves = the setup, AI figures out level/method)
- Algorithm trainer with spaced repetition

**Infrastructure:**
- Cloud sync for premium users
- Freemium gating ($6.95/mo, $59.99/yr, 30-day free trial)
- HTTPS for Web Bluetooth
- Responsive web PWA (desktop + mobile Chrome/Edge for smart cube, all browsers for free features)

### Growth Features (Phase 2)

- "What Should I Learn Next" recommendation engine (frequency-ranked unlearned cases as fast follow)
- ZBLL detection + fingerprinting (~493 cases)
- Turning style detection + per-move TPS analysis
- Personalized algorithm recommendations by turning style
- MoYu and QiYi smart cube support
- Roux method phase detection
- Non-smart-cube manual solution entry with full AI analysis
- csTimer JSON data import
- Weekly cubing report emails

### Vision (Future)

- Native iOS app with CoreBluetooth for smart cube support
- Social activity feed with cubing friends
- Competition preparation mode
- Coaching platform for pro cubers + their students
- 4x4/5x5 analysis when smart hardware arrives (CayleyPy)
- Real-time audio coaching hints during practice
- AR-guided solving overlay
- API access for developers
- Content creator integration (shareable replays, embeddable solve cards)

## User Journeys

### Journey 1: Ethan — The Intermediate Builder (Sub-30, Smart Cube)

**Who:** Ethan, 13, averages ~25s. Knows beginner CFOP, uses 2-look OLL/PLL. Owns a MoYu WeiLong AI V10. Practices on csTimer, watches J Perm videos, picks random algorithms to learn without strategy.

**Opening Scene:** Ethan sees a BearCube ghost solve replay shared in a cubing Discord — two 3D cubes side by side, one with orange/red moves, one smooth green. He's never seen anything like it. He clicks through.

**Rising Action:** He signs up with Google (age 13, passes the gate), connects his smart cube, and does his first solve. The timer view shows a 2-line debrief: "Cross: 7 moves (optimal: 5). F2L pair 2 inefficient — 6 moves, here's a 3-move alternative." He taps into the full AI review — his solve color-coded green/yellow/orange/red alongside the optimal, with XCross options shown for the scramble. He can *see* exactly where he diverged.

He does more solves over the next few days. BearCube auto-detects his method (CFOP) and rough skill level (~sub-30) from the first handful. Over the following weeks, as it sees him encounter more OLL and PLL cases, it progressively builds his algorithm knowledge map — identifying which of the 57 OLL and 21 PLL cases he knows full algorithms for and which he's using 2-look on.

**Climax:** After a few weeks of daily practice, with enough solves for BearCube to have mapped his algorithm set, the "What Should I Learn Next" engine tells him: "You're using 2-look on these 4 OLL cases that appear most frequently in your solves. Learning full algorithms for them will have the biggest efficiency impact." It's not a random list — it's *his* list, ranked by how often he actually encounters each case. He drills them in the algorithm trainer using spaced repetition.

**Resolution:** Ethan's Ao100 drops from 25s to 22s. The PR celebration engine catches it: "New Ao100 PB!" He screenshots his progress card and shares it in his cubing Discord. His mom sees the weekly progress email — "Practiced 6 of 7 days, Ao100 improved" — and feels good about the $6.95/month.

**Capabilities revealed:** Google/social auth, age gate (13+), smart cube connection, zero-config onboarding (method/level detection from early solves), AI solve review with move-efficiency focus, XCross solution generation, progressive algorithm fingerprinting over time, "What Should I Learn Next" engine, algorithm trainer with spaced repetition, PR celebration, shareable progress cards, parent-facing weekly email.

---

### Journey 2: Maya — The Plateau Grinder (Sub-15, Smart Cube)

**Who:** Maya, 17, averages 14s, stuck between 13-15s for months. Knows full OLL/PLL, thinks her F2L is "fine." Uses Cubeast — sees phase splits but doesn't know how to interpret them into action. Has considered coaching ($30-40/session) but hasn't committed.

**Opening Scene:** Maya is frustrated. Cubeast tells her F2L takes 7.5 seconds, but not *why* or *what to change*. She sees a Reddit post: "Cubeast tells you WHAT happened. BearCube tells you WHAT TO DO."

**Rising Action:** She signs up for the free trial, connects her GAN cube. The first AI debrief surprises her — it doesn't just say "F2L: 7.5s." It says: "F2L pair 3: 6 moves, optimal insertion is 3 — here's the efficient alternative that avoids the rotation you're using." She opens the ghost solve replay and watches her solve play next to optimal — she can *see* the moment she takes extra moves to set up an insertion that should have been direct.

Over subsequent sessions, BearCube detects her pause patterns: 0.8s hesitation before certain OLL cases (recognition delay), no pauses on others. It measures her lookahead gaps between F2L pairs — moments where she stops tracking the next pair. It counts 5 whole-cube rotations per solve when sub-10 solvers average 2.3.

**Climax:** The coaching insight is specific and actionable: "Your biggest improvement opportunity isn't algorithms — it's F2L efficiency. Your pairs average 5.1 moves when more optimal insertions would average 3.5. Here are targeted drills for your 3 weakest insertion angles. Also: you have recognition delays on 5 OLL cases — drill those specifically." This is what a $40 coaching session tells you, delivered automatically after every session.

**Resolution:** After two weeks of targeted F2L drills, Maya's Ao100 drops to 13.1s — breaking through a 6-week plateau. Her trial expires and she subscribes without hesitation. She posts her ghost solve before/after comparison to r/Cubers.

**Capabilities revealed:** AI coaching focused on move efficiency (not speculative time claims), ghost solve replay, pause/hesitation detection (lookahead gaps), rotation counting, recognition time analysis per OLL/PLL case, F2L insertion analysis with efficient alternatives, targeted drill generation, trial-to-premium conversion.

---

### Journey 3: Jordan — The Manual Timer (Sub-20, No Smart Cube)

**Who:** Jordan, 15, averages 18s with a regular speedcube. Can't afford a smart cube. Uses csTimer for timing.

**Opening Scene:** Jordan tries the daily challenge — one scramble per day, everyone gets ranked. No smart cube needed, takes 30 seconds. He gets 17.8s. His solve is labeled "manual" on the leaderboard (smart cube solves are verified; manual solves are honor-system and can be filtered by other users).

**Rising Action:** He discovers the free tier timer is clean, has streaks, and the algorithm trainer lets him drill OLL cases he's learning with spaced repetition. The scramble analysis mode shows him cross and XCross solutions after each scramble: "Your planned cross was 7 moves. Here's a 4-move cross. Here's an XCross option that solves cross + one F2L pair in 7 moves." He's learning inspection and planning skills passively with every solve.

**Climax:** Jordan's Ao100 drops from 18s to 16.5s just from better cross planning and algorithm drilling — without a smart cube. He sees what premium unlocks with a smart cube: full AI solve review, personalized coaching, move-by-move analysis. The free tools have already made him faster; the premium features are the next level.

**Resolution:** Jordan asks for a GAN smart cube for his birthday. When he connects it, BearCube's AI analysis shows him what his F2L *actually* looks like move by move — and he's hooked. The free tier earned his trust; the premium features earned his (parents') money.

**Capabilities revealed:** Daily challenge with manual/smart cube distinction, leaderboard filtering (verified vs manual solves), free tier timer with streaks, algorithm trainer with spaced repetition, scramble analysis with cross + XCross solutions (toggleable), freemium-to-premium upgrade path.

---

### Journey 4: Kai — The Elite Optimizer (Sub-8, Smart Cube)

**Who:** Kai, 22, averages 7.5s, WCA competitor. Knows standard OLL/PLL but is learning ZBLL subsets. R/U dominant, slow on F moves. Does manual video reconstructions (20 min per solve). Working on XCross planning, pseudo slotting, lookahead, and eliminating inspection/execution pauses.

**Opening Scene:** Kai is skeptical — most cubing tools target intermediates. He connects his smart cube and does a session of 50 solves.

**Rising Action:** Auto-reconstruction replaces his 20-minute video process with 2 seconds. Every solve is fully reconstructed with move-by-move analysis. BearCube detects advanced techniques: XCross attempts (successful and failed), pseudo slotting sequences, and ZBLL cases where he's using 1-look last layer instead of OLL+PLL.

The pause detection is where it gets interesting. BearCube identifies his lookahead gaps — 0.3s pauses between F2L pairs where he loses tracking. It shows his inspection efficiency: planned cross execution vs. mid-solve replanning. At sub-8, these micro-pauses are the difference between 7.5s and 7.0s.

**Climax (Stage 6 feature):** Turning style detection reveals: R at 12.3 TPS, U at 11.8, F at 8.1, B at 7.2. The algorithm recommendation engine identifies 3 PLL cases where his current algorithms are F/B-heavy and suggests R/U-dominant alternatives backed by community data from similar profiles. Plus: "You're successfully executing ZBLL on 12 cases. Here are the next 5 ZBLL cases ranked by frequency in your solves."

**Resolution:** Kai switches the recommended PLL algorithms, drills them, and his PLL phase drops 0.2s average. He starts targeting the ZBLL cases BearCube identified. He shares his turning style profile visualization on SpeedSolving — it generates discussion and attracts other elite cubers.

**Capabilities revealed:** Auto-reconstruction, XCross detection and analysis, pseudo slotting recognition, ZBLL case detection and fingerprinting, lookahead/pause measurement between F2L pairs, inspection efficiency analysis, turning style detection (per-move TPS), personalized algorithm recommendations, community intelligence, elite micro-optimization.

---

### Journey 5: First-Time Visitor — Cold Traffic

**Who:** Anonymous cuber, sees a ghost solve replay on YouTube or social media.

**Opening Scene:** 15-second clip: two 3D cubes side by side. Left ("Your Solve") has orange/red moves. Right ("Optimal") is smooth green. The visual gap is immediately obvious. Caption: "See where you're losing time. BearCube."

**Rising Action:** They click through to the landing page. They see the ghost solve demo, the daily challenge ("Try today's scramble — no account needed"), and a clear value prop. They try the daily challenge — one solve, instant ranking, shareable. No sign-up required.

**Climax:** They create a free account via Google sign-in. If they have a smart cube, they connect it and get their first AI debrief within 60 seconds. If not, they start with the timer, daily challenge, and algorithm trainer.

**Resolution:** Within a week they've either connected a smart cube and started the trial (→ potential premium), or they're using free tools daily and building a streak (→ engaged free user → eventual smart cube buyer).

**Capabilities revealed:** Landing page / marketing funnel, no-auth daily challenge, Google/social auth, zero-friction onboarding, smart cube detection and connection prompt.

---

### Journey 6: Parent — Decision-Maker / Payer

**Who:** Parent of a younger cuber (ages 10-15). Doesn't cube themselves.

**Opening Scene:** Their child asks for a BearCube subscription. The parent looks at the app — clean, professional, no ads, no chat with strangers, no social features that worry them.

**Rising Action:** They see the child's progress: "Ao100 improved this week. Practiced 6 of 7 days. Learning new algorithms." The weekly progress email arrives in the parent's inbox without them needing to check the app. The 13+ age requirement is handled transparently. Privacy policy is clear.

**Climax:** $6.95/month — less than most extracurricular subscriptions. Measurable improvement in something their child is passionate about. Annual plan at $59.99 saves 28%.

**Resolution:** They subscribe. The weekly emails keep them informed. They mention it to another cubing parent at a WCA competition.

**Capabilities revealed:** Parent-facing progress dashboard, weekly progress email reports, transparent age handling (13+ gate), clear privacy practices, professional design (no ads/chat), accessible pricing.

---

### Journey 7: Admin/Ops — Sean (Solo Developer at Launch)

**Who:** Sean, developer and operator. Managing the system solo at launch scale.

**Opening Scene:** Launch day. Users signing up, connecting smart cubes. Needs to know: Is the AI pipeline healthy? Are solves being analyzed correctly? Are connections succeeding?

**Rising Action:** Admin dashboard shows: active users, solves analyzed today, AI pipeline latency (avg/p95), failed analyses, connection success rate, trial/premium counts, error logs. A user reports a connection failure — logs show a GAN firmware edge case.

**Climax:** Sign-up spike from a Reddit post. System handles the load. Sean monitors concurrent users, API response times, Kociemba queue depth. No degradation.

**Resolution:** Daily review: 23 new users, 187 solves analyzed, 0 incorrect solutions, 97% connection success, 2 trial-to-premium conversions. System is working.

**Capabilities revealed:** Admin dashboard, system health monitoring (AI pipeline, Bluetooth, API), error logging, user management, subscription tracking, performance monitoring.

---

### Journey Requirements Summary

| Journey | Key Capabilities Revealed |
|---------|--------------------------|
| **Ethan (Intermediate)** | Google/social auth, age gate, smart cube connection, zero-config onboarding, AI solve review (move-efficiency focus), XCross generation, progressive algorithm fingerprinting, "Learn Next" engine, algorithm trainer, PR celebration, shareable cards, parent email |
| **Maya (Plateau)** | AI coaching with efficient alternatives, ghost solve replay, pause/lookahead detection, rotation counting, recognition time per case, F2L insertion analysis, targeted drills, trial→premium |
| **Jordan (No Smart Cube)** | Daily challenge (manual/verified distinction), leaderboard filtering, free tier timer, streaks, algorithm trainer, cross+XCross scramble analysis, freemium upsell |
| **Kai (Elite)** | Auto-reconstruction, XCross/pseudo slotting/ZBLL detection, lookahead gap measurement, inspection efficiency, turning style, personalized alg recommendations, community intelligence |
| **First Visitor** | Landing page, no-auth daily challenge, Google/social auth, zero-friction onboarding |
| **Parent** | Progress dashboard, weekly email, age handling, privacy, professional design, pricing |
| **Admin/Ops** | Admin dashboard, system monitoring, error logs, user management, subscription tracking |

**Cross-cutting capabilities:** Authentication (Google/social + email), cloud storage, responsive web PWA, HTTPS, subscription/billing management, ToS-based 13+ age requirement.

## Domain-Specific Requirements

### Compliance & Regulatory

- **COPPA (Children Under 13):** #1 compliance risk. Strategy: ToS states 13+ age requirement; no age question asked at signup (no "actual knowledge" of age). No personal data intentionally collected from known minors. If under-13 status is disclosed, account is handled per COPPA requirements. Defer full COPPA compliance (verifiable parental consent) to post-launch if under-13 demand warrants it
- **GDPR (EU Users):** Privacy policy in plain language, data subject rights (access/erasure/portability), breach notification within 72 hours. Article 8: users under 16 in EU need parental consent. Data Protection Impact Assessment (DPIA) required for AI-powered profiling features
- **CCPA/CPRA 2026 (California):** AI features trigger Automated Decision-Making Technology (ADMT) requirements — pre-use notice, opt-out rights, transparency. Personal data of known under-16 users classified as "sensitive"

### Technical Constraints

- **Web Bluetooth:** Chrome/Edge only — no Safari, Firefox, or iOS browser support. User gesture required to initiate connection. HTTPS mandatory. Cannot auto-connect or background scan
- **GAN Cube Encryption:** AES encryption using MAC-address-derived keys. MAC address discovery varies by platform. Adds connection complexity vs other brands
- **Proprietary Protocols:** Each smart cube manufacturer (GAN, MoYu, QiYi, GoCube) uses a different proprietary BLE protocol. No industry standard exists. csTimer's bluetooth.js is the de facto protocol reference
- **Timestamp Drift:** GAN cube internal clocks are imprecise — requires linear regression correction (`cubeTimestampLinearFit()`) for accurate timing data
- **GPL License Boundary:** Kociemba solver (GPL) must run server-side only (SaaS loophole). csTimer code (GPL) must never be bundled client-side. cubing.js used under MPL-2.0 terms. Smart cube Bluetooth handlers must be written from scratch using csTimer as behavioral reference only — not copied

### Integration Requirements

- **Smart Cube Hardware:** GAN cubes at launch via gan-web-bluetooth (MIT). Architecture abstracted behind interface for future MoYu/QiYi/GoCube support
- **AI Solving Pipeline:** Server-side Kociemba for guaranteed-correct near-optimal solutions. AlphaCube (MIT) for neural network solutions. Solution-analyzer (MIT) for CFOP/Roux/ZZ phase detection
- **Authentication Providers:** Google OAuth + additional social providers. Email/password as fallback
- **Payment Processing:** Stripe or equivalent for subscription billing ($6.95/mo, $59.99/yr)

### Risk Mitigations

| Risk | Impact | Mitigation |
|------|--------|------------|
| COPPA violation | FTC enforcement, fines, reputational damage | ToS requires 13+; no age collected at signup; no personal data from known minors; handle disclosures per COPPA |
| GPL contamination | Must open-source entire client codebase | Strict library audit, GPL code server-side only, rewrite Bluetooth handlers from scratch |
| iOS smart cube gap | Excludes ~50% of mobile users from smart cube features | Accept at launch; non-smart-cube features work everywhere; native iOS app in future vision |
| AI compute costs at scale | Server costs grow with each analyzed solve | Gate AI behind premium tier; Kociemba is CPU-cheap; cache repeated scramble solutions |
| Smart cube protocol breaking changes | Firmware updates break connectivity | Abstract Bluetooth layer behind interface; monitor manufacturer firmware releases and csTimer updates |
| Community trust failure | Niche community — negative word spreads fast | 100% solution correctness; professional design; transparent privacy; responsive to community feedback |
| Single-browser dependency | Web Bluetooth limited to Chromium | Non-smart-cube features work on all browsers; monitor Safari/Firefox Bluetooth progress |

## Innovation & Novel Patterns

### Detected Innovation Areas

**1. AI Solve Review (Primary Innovation)**
Chess.com-style move-by-move analysis applied to speedcubing. Compare every smart cube solve against AI-generated optimal solutions, phase by phase, with color-coded efficiency grading. No cubing tool does this — the community has been requesting it with zero implementations. This is the core differentiator.

**2. Integrated AI Coaching Pipeline**
Combining three existing open-source technologies into a novel coaching system:
- Smart cube BLE data (move sequences with timestamps) via gan-web-bluetooth
- AI optimal solution generation via Kociemba/AlphaCube (server-side)
- Automatic CFOP phase detection via solution-analyzer

Each component exists independently. The innovation is assembling them into an end-to-end pipeline that takes raw solve data and produces actionable coaching — "here's where you diverged from optimal and here's a better approach."

**3. Algorithm Fingerprinting**
Pattern-matching user move sequences against a known algorithm database to automatically detect which OLL/PLL/ZBLL cases they know, which they use 2-look on, and which they fumble. No existing tool attempts this — all require manual algorithm set input or don't track it at all.

**4. Advanced Technique Detection**
Identifying XCross attempts (successful and failed), pseudo slotting sequences, and ZBLL 1-look last layer from raw move data. Bridges the gap between what advanced cubers practice and what tools can measure.

**5. Ghost Solve Replay**
Side-by-side 3D visualization — user's actual solve playing simultaneously against the AI optimal. Color-coded moves (green/yellow/orange/red) make divergence immediately visible. This is the "aha moment" that sells the product in a 15-second video and is impossible without the AI pipeline.

**6. Compounding Cuber Profile**
Unlike a timer (commodity, easily switched), BearCube builds a progressive profile that becomes more valuable over time — algorithm knowledge map, weakness patterns, improvement trajectory, turning style data. Creates switching cost through accumulated data value.

### Market Context & Competitive Landscape

- **csTimer** (90% market share): Cannot add AI features — client-side only, no server infrastructure, no accounts, no compute budget. Structurally unable to compete on this axis.
- **Cubeast**: Best smart cube analytics but shows data without interpretation. Could add AI but hasn't. Closest competitive threat.
- **acubemy**: Spaced repetition and weakness identification, but no AI solve comparison or personalized algorithm recommendations. Growing fast (EUR 4.99/mo).
- **CubeStation (GAN)**: CFOP auto-segmentation with basic optimization suggestions, but GAN-locked and plagued by bugs.
- **No tool anywhere** combines AI solving + smart cube data + coaching into a single pipeline.

The competitive window is open now — the building blocks (AlphaCube MIT, solution-analyzer MIT, gan-web-bluetooth MIT) all reached maturity simultaneously in 2024-2025. First-mover advantage is available but not permanent.

### Validation Approach

**Technical validation (Feasibility Gate — Stage 1):**
- Can Kociemba reliably generate correct optimal solutions for any scramble? (Expected: yes, guaranteed by algorithm)
- Can the pipeline run end-to-end: scramble → smart cube solve → phase detection → AI comparison → user feedback?
- Can this happen in sub-3 seconds?

**Product validation (Launch — Stages 3-5):**
- Do users who engage with AI coaching show measurable Ao100 improvement?
- Do 30%+ of smart cube solves get AI review (not just timing)?
- Do 10-15% of trial users convert to premium?
- Does the ghost solve replay generate organic sharing?

**Market validation (Post-Launch):**
- Can BearCube retain paid subscribers beyond month 1?
- Does the community talk about it positively on SpeedSolving/Reddit?
- Does algorithm fingerprinting work accurately across diverse solving styles?

### Risk Mitigation

| Innovation Risk | Fallback |
|----------------|----------|
| AI optimal solutions aren't "human-friendly" enough to compare meaningfully | Start with pure move-count efficiency comparison (simpler, still valuable). Layer in human-friendly interpretation over time |
| Algorithm fingerprinting accuracy is low | Fall back to manual algorithm set input + progressive confirmation ("Did you use Sune for that OLL?") |
| Ghost solve replay is technically complex to build | Start with static side-by-side comparison (replay without animation). Add synchronized 3D replay as enhancement |
| Users don't engage with AI analysis (just want a timer) | Free tier is a competitive timer with streaks and daily challenge — works standalone. AI features are the premium upsell, not the only value |
| Competitive window closes (Cubeast/acubemy add AI) | Speed of execution matters. First to market with quality AI analysis builds community data moat that late entrants can't replicate |

## Web App Specific Requirements

### Project-Type Overview

BearCube is a Single Page Application (SPA) with Progressive Web App (PWA) capabilities, built with Next.js. The app combines a real-time smart cube connection interface (Web Bluetooth), 3D visualization (Three.js), and AI-powered analysis into a responsive web experience. PWA-first strategy enables installable app-like experience on both desktop and mobile without the overhead of native development or Electron packaging.

### Browser Support Matrix

| Browser | Desktop | Mobile | Smart Cube (BLE) | Notes |
|---------|---------|--------|-------------------|-------|
| Chrome | Full support | Full support | Yes | Primary target browser |
| Edge | Full support | Full support | Yes | Chromium-based, same capabilities |
| Safari | Timer + free features | Timer + free features | No | No Web Bluetooth API |
| Firefox | Timer + free features | Timer + free features | No | No Web Bluetooth API |
| iOS Safari | Timer + free features | Timer + free features | No | No Web Bluetooth on any iOS browser |

**Strategy:** All non-smart-cube features (timer, daily challenge, algorithm trainer, streaks) work on every modern browser. Smart cube features gracefully degrade with clear messaging directing users to Chrome/Edge.

### Responsive Design

- **Mobile-first layout:** Timer view, solve list, and daily challenge optimized for phone screens (360px+)
- **Tablet:** Side-by-side views for AI analysis (solve + 3D visualization)
- **Desktop:** Full multi-panel layout for ghost solve replay, detailed analysis, algorithm trainer
- **Touch interactions:** Large tap targets for timer start/stop, swipe navigation between solve views
- **Orientation:** Portrait-primary for timer, landscape-supported for 3D replay

### Progressive Web App (PWA) Features

- **Installable:** Add-to-homescreen prompt on mobile and desktop — feels like a native app
- **Offline timer:** Basic timer and local solve history available without network (syncs when reconnected)
- **Service worker caching:** Static assets, algorithm database, and UI cached for instant load
- **Push notifications (future):** Daily challenge reminders, streak alerts, PR notifications
- **App manifest:** Custom icon, splash screen, standalone display mode, theme color

### Performance Targets

See NFR1-NFR8 in Non-Functional Requirements for authoritative performance targets (AI pipeline < 3s, Kociemba < 1s, smart cube latency < 50ms, 60fps 3D, FCP < 1.5s, LCP < 2.5s, TTI < 3.0s, CLS < 0.1, bundle < 200KB gzipped, Lighthouse 90+).

### SEO Strategy

- **Minimal SEO scope at launch:** SPA with authenticated content — most value is behind login
- **Public SEO pages:** Landing page, daily challenge leaderboard, feature pages, pricing — server-rendered via Next.js
- **Meta tags and Open Graph:** Shareable solve cards and ghost solve previews generate rich link previews on social media
- **Future:** Public cuber profiles, algorithm database pages as SEO content

### Accessibility

See NFR25-NFR29 in Non-Functional Requirements for authoritative accessibility targets (WCAG 2.1 AA, keyboard navigation, colorblind-safe indicators, 4.5:1 contrast, reduced motion option).

### Implementation Considerations

- **Framework:** Next.js with App Router — SSR for public pages, client-side SPA for authenticated app
- **State management:** Zustand for client state (timer, cube state, UI) — lightweight, no boilerplate
- **3D rendering:** Three.js with React Three Fiber for cube visualization and ghost solve replay
- **Database:** PostgreSQL with Prisma ORM — relational model for solve data, user profiles, algorithm mappings
- **AI service:** Python containerized service (Kociemba + AlphaCube + solution-analyzer) — separate from Next.js, communicates via internal API
- **Deployment:** Vercel for Next.js frontend + API routes; containerized Python AI service on Railway/Fly.io or similar
- **PWA-first strategy:** Start with PWA for installable mobile/desktop experience. Evaluate native development (React Native or iOS Swift) only if PWA limitations become a user retention issue. Electron is not recommended — it would add packaging complexity without meaningful benefits over PWA for this use case
- **Authentication:** NextAuth.js with Google, GitHub, and additional social providers + email/password fallback

## Project Scoping & Phased Development

### MVP Strategy & Philosophy

**MVP Approach:** First-Impression MVP — release only when the product delivers enough value that the speedcubing community's first experience is "this is worth paying for." In a niche where word-of-mouth on r/Cubers and SpeedSolving makes or breaks a product, a premature release is worse than a delayed one.

**Resource Model:** Solo developer with AI-assisted development. Sean handles architecture decisions and quality oversight; AI tooling accelerates implementation. This shifts the bottleneck from raw coding speed to decision quality and integration complexity.

**Build Order Priority:** Validate the riskiest technical assumptions first (AI pipeline, phase detection, smart cube connection), then layer features on a proven foundation.

### MVP Feature Set (Phase 1 — Launch)

**Core User Journeys Supported:**
- Ethan (Intermediate, smart cube) — AI solve review, algorithm fingerprinting, XCross
- Maya (Plateau, smart cube) — move-efficiency coaching, ghost solve replay, pause detection
- Jordan (No smart cube) — timer, daily challenge, algorithm trainer, scramble analysis
- First Visitor — landing page, no-auth daily challenge, frictionless onboarding
- Parent — progress visibility, clean design, accessible pricing
- Admin/Ops — system monitoring dashboard

**Must-Have Capabilities (Launch):**

| Capability | Rationale |
|-----------|-----------|
| Auth (Google/social + email, ToS 13+ requirement) | Required for accounts, COPPA compliance |
| Professional timer with inspection + random-state scrambles | Table stakes — must match csTimer quality |
| Smart cube connection (GAN at launch) | Core differentiator enabler |
| 3D cube visualization (real-time state) | Visual proof the connection works |
| Server-side Kociemba solver | Guaranteed-correct solutions — the foundation |
| AI solve review (phase-by-phase efficiency comparison) | Primary innovation — the "aha moment" |
| CFOP phase detection (solution-analyzer) | Required for AI solve review to work — early validation needed |
| Move-by-move color grading (green/yellow/orange/red) | Makes solve analysis instantly visual |
| Ghost solve replay (animated side-by-side 3D) | The marketing moment — 15-second shareable video |
| XCross solution generation (toggleable) | Differentiator for intermediate+ cubers |
| Algorithm fingerprinting (OLL 57 + PLL 21) | Progressive — builds over time, ZBLL deferred post-launch |
| Algorithm knowledge map | Visual output of fingerprinting ("You know 15/21 PLL") |
| Basic cuber profile (strengths/weaknesses) | Foundation for all coaching features |
| Post-solve summary card + instant 2-line debrief | Makes every solve feel analyzed |
| Basic statistics (Ao5/12/50/100) | Table stakes timer feature |
| Practice streaks (daily counter) | Retention mechanic |
| Daily challenge (one scramble/day, ranked, manual/verified distinction) | Engagement for all users, viral sharing |
| PR celebration engine | Emotional reward, shareability |
| Scramble analysis (cross + XCross solutions) | Free tier value, inspection training |
| Algorithm trainer with spaced repetition | Free tier value, learning tool |
| Freemium gating ($6.95/mo, $59.99/yr, 30-day trial) | Revenue model |
| Cloud sync (premium) | Premium value, data portability |
| Zero-config onboarding (method/level detection from early solves) | Frictionless first experience |

**Deferred from Launch MVP:**

| Capability | Phase | Rationale |
|-----------|-------|-----------|
| "What Should I Learn Next" recommendation engine | Phase 2 | Depends on proven AI solve review + enough user data. Simple frequency-ranked list could be a fast follow |
| ZBLL detection + fingerprinting (~493 cases) | Phase 2 | Elite niche; OLL/PLL coverage sufficient for launch |
| Turning style detection + per-move TPS analysis | Phase 2 | Stage 6 feature — nice-to-have for elite cubers |
| Personalized algorithm recommendations (by turning style) | Phase 2 | Depends on turning style detection |
| MoYu / QiYi / GoCube smart cube support | Phase 2 | Need physical hardware for testing; GAN-only at launch |
| Non-smart-cube manual solution entry with AI analysis | Phase 2 | Expands addressable market but not core differentiator |
| csTimer JSON import | Phase 2 | Reduces switching friction, not needed for new users |
| Weekly progress email (parent-facing) | Phase 2 | Nice-to-have; deferred to post-launch |
| Adaptive training curriculum ("Train Me" auto-pilot) | Phase 3 | Requires mature recommendation engine + user data |
| Peer benchmarking by skill level | Phase 3 | Needs critical mass of users |
| Community algorithm intelligence (network effect) | Phase 3 | Needs critical mass of solve data |
| Native iOS app | Phase 3 | Only if PWA limitations hurt retention |
| Social features, coaching platform, AR overlay | Vision | Long-term differentiators |

### Risk Mitigation Strategy

**Technical Risks:**

| Risk | Severity | Mitigation |
|------|----------|------------|
| Phase detection (solution-analyzer) doesn't work accurately | High — blocks AI solve review | Validate first. Test with known CFOP solves before building UI. Fallback: simpler phase boundary detection using move-count heuristics |
| Smart cube connection unreliable | High — blocks core experience | GAN cube tested on developer's own hardware. Abstract Bluetooth layer for future brands. Graceful reconnection handling |
| AI analysis too slow (> 3s) | Medium — degrades experience | Kociemba is fast (< 1s). Profile full pipeline early. Cache repeated scramble solutions. Loading animation acceptable |
| Algorithm fingerprinting inaccurate | Medium — coaching quality | Progressive confidence (more solves = more accuracy). Fallback: manual algorithm set input + confirmation prompts |

**Market Risks:**

| Risk | Severity | Mitigation |
|------|----------|------------|
| Cubeast or acubemy ships AI features first | High | Speed of execution. First-mover with quality builds community data moat |
| Niche market too small for revenue targets | Medium | Validate with 3-month targets (5-20 paid users). Low infrastructure cost means low break-even |
| Bad first impression kills word-of-mouth | High | Don't release until stages 5-6. First solve must show value no other tool provides |

**Resource Risks:**

| Risk | Severity | Mitigation |
|------|----------|------------|
| Solo dev bottleneck on complex integrations | Medium | AI-assisted development. Modular architecture — AI service independent of frontend |
| Scope creep delays launch | Medium | Clear phase boundaries. Phase 2 features are explicitly deferred, not forgotten |
| Burnout from building everything alone | Medium | Ship launch MVP, then iterate. Don't gold-plate Phase 1 |

## Functional Requirements

### User Identity & Access

- FR1: Users can create an account using Google, social providers, or email/password
- FR2: Users can sign in and maintain an authenticated session across devices
- FR3: The system requires users to agree to Terms of Service (which state 13+ age requirement) during account creation
- FR4: Users can link their WCA (World Cube Association) profile to their BearCube account
- FR5: Users can manage their profile (display name, avatar, preferences)
- FR6: Administrators can view and manage user accounts

### Timer & Solve Recording

- FR7: Users can start and stop a solve timer using keyboard (spacebar) or touch input
- FR8: The system generates random-state scrambles for each solve
- FR9: Users can use a WCA-standard inspection countdown before each solve
- FR10: Users can view their solve history with individual times
- FR11: Users can mark solves as DNF or apply +2 penalties
- FR12: Users can delete individual solves from their history
- FR13: The system calculates rolling averages (Ao5, Ao12, Ao50, Ao100) automatically
- FR14: Users can customize which statistics are displayed and configure custom session averages (e.g., Ao5, Ao25, or any AoX)

### Smart Cube Integration

- FR15: Users can connect a GAN smart cube via Web Bluetooth
- FR16: The system reads real-time move data from a connected smart cube with timestamp correction
- FR17: The system displays a 3D cube visualization reflecting the real-time state of the connected smart cube
- FR18: The system records complete move sequences with timing data for each smart cube solve
- FR19: The system handles Bluetooth disconnection gracefully with reconnection prompts

### AI Solve Analysis

- FR20: The system generates an optimal (near-optimal) solution for any scramble using a server-side solver
- FR21: The system detects CFOP phases (cross, F2L pairs, OLL, PLL) from a user's recorded move sequence (Roux method detection deferred to Phase 2)
- FR22: Users can view a phase-by-phase efficiency comparison of their solve against the AI optimal solution
- FR23: Users can view move-by-move color grading (green/yellow/orange/red) indicating efficiency relative to optimal
- FR24: Users can view a post-solve summary card with key insights after each smart cube solve
- FR25: Users can view an instant 2-line AI debrief in the timer view after each smart cube solve
- FR26: The system generates XCross, double XCross, and pseudo solutions for scrambles, each independently toggleable by user preference
- FR27: Users can view a ghost solve replay — animated side-by-side 3D visualization of their solve vs. optimal

### Cuber Profile & Algorithm Intelligence

- FR28: The system auto-detects the user's solving method (CFOP at launch) and approximate skill level from early solves
- FR29: The system progressively identifies which OLL algorithms (57 cases) the user knows from solve data
- FR30: The system progressively identifies which PLL algorithms (21 cases) the user knows from solve data
- FR31: Users can view their algorithm knowledge map showing known vs. unknown cases
- FR32: Users can view a cuber profile summarizing their strengths, weaknesses, and improvement trajectory
- FR33: The system detects pause/hesitation patterns indicating recognition delays on specific cases
- FR34: The system detects XCross attempts (successful and failed) from move data
- FR35: The system detects pseudo slotting sequences from move data
- FR36: The system measures lookahead gaps between F2L pairs
- FR37: The system counts whole-cube rotations per solve

### Training & Practice

- FR38: Users can drill specific algorithm cases using a spaced repetition trainer
- FR39: Users can view cross, XCross, double XCross, and pseudo solutions for any scramble (scramble analysis mode)
- FR40: The system provides targeted drill recommendations based on identified weaknesses

### Engagement & Gamification

- FR41: Users can maintain and view daily practice streaks
- FR42: Users can participate in a daily challenge (one scramble per day, ranked leaderboard)
- FR43: The daily challenge supports both smart cube (verified) and manual (honor-system) solves with filtering
- FR44: The system detects and celebrates personal records (PBs, micro-records like fastest cross this week)
- FR45: Users can share solve cards and progress summaries externally

### Subscription & Billing

- FR46: Users can use free tier features (timer, streaks, daily challenge, algorithm trainer) without payment
- FR47: Users can subscribe to premium ($6.95/mo or $59.99/yr) to unlock AI analysis and smart cube features
- FR48: Users can start a 30-day free trial of premium features
- FR49: The system gates premium-only features behind subscription status

### Data & Sync

- FR50: Premium users' solve data syncs to the cloud and is accessible across devices
- FR51: Free tier users' data is stored locally with option to sync upon upgrading
- FR52: The system caches static assets and the algorithm database for offline timer use (PWA)

### Administration & Monitoring

- FR53: Administrators can view a system health dashboard (active users, solves analyzed, AI pipeline latency, connection success rate)
- FR54: Administrators can view error logs and investigate user-reported issues
- FR55: Administrators can view subscription and revenue metrics

## Non-Functional Requirements

### Performance

- NFR1: AI solve analysis pipeline completes end-to-end in < 3 seconds (scramble to optimal solution to phase detection to comparison to user feedback)
- NFR2: Server-side Kociemba solver returns solutions in < 1 second per scramble
- NFR3: Smart cube move input renders in the 3D visualization with < 50ms perceived latency
- NFR4: 3D cube visualization and ghost solve replay maintain 60fps
- NFR5: Page load: First Contentful Paint < 1.5s, Largest Contentful Paint < 2.5s, Time to Interactive < 3.0s
- NFR6: Initial JavaScript bundle < 200KB gzipped
- NFR7: Cumulative Layout Shift < 0.1
- NFR8: Lighthouse Performance score 90+

### Security

- NFR9: All data transmitted over HTTPS (also required for Web Bluetooth)
- NFR10: User passwords hashed using industry-standard algorithms (bcrypt/argon2)
- NFR11: OAuth tokens and session credentials stored securely, never exposed to client-side JavaScript
- NFR12: Payment processing delegated to PCI-compliant third party (Stripe) — no card data stored on BearCube servers
- NFR13: GPL-licensed code (Kociemba, csTimer references) runs server-side only — never bundled in client-side assets
- NFR14: API endpoints authenticated and rate-limited to prevent abuse
- NFR15: Users can delete their account and all associated data on request

### Scalability

- NFR16: Architecture supports 100+ concurrent users at launch without degradation
- NFR17: AI service (Python container) is independently scalable from the web frontend
- NFR18: Database schema and queries designed to handle 1M+ stored solves without performance degradation
- NFR19: Repeated scramble solutions cached to reduce redundant AI compute

### Reliability

- NFR20: Target 99% uptime (allows ~7 hours/month for maintenance and deployments)
- NFR21: Smart cube Bluetooth disconnections do not lose in-progress solve data — solve is recoverable or gracefully discarded
- NFR22: If the AI service is temporarily unavailable, timer and solve recording continue to function — AI analysis queued for when service recovers
- NFR23: Daily database backups with tolerance for up to 24 hours of data loss at launch scale
- NFR24: Premium users who cancel subscription retain access to their historical solve data (read-only) with premium features locked

### Accessibility

- NFR25: WCAG 2.1 AA compliance for all user-facing interfaces
- NFR26: Full keyboard navigation — timer operable via spacebar, all UI navigable without mouse
- NFR27: Color-coded efficiency grading (green/yellow/orange/red) supplemented with shape/icon indicators for colorblind users
- NFR28: Text meets minimum 4.5:1 contrast ratio
- NFR29: Reduced motion option disables 3D animations and ghost solve replay

### Data Privacy

- NFR30: Privacy policy in plain language, accessible from all pages
- NFR31: GDPR compliance: users can access, export, and delete their personal data
- NFR32: CCPA/CPRA compliance: pre-use notice for AI-powered profiling features, opt-out rights
- NFR33: Solve data retained indefinitely for active accounts; deleted within 30 days of account deletion request
- NFR34: No personal data sold to third parties

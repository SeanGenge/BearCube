# UI Design Research: Dark-Mode Analytics & Dashboard Patterns for BearCube

**Date:** 2026-02-22
**Purpose:** Research modern dark-mode dashboard and analytics UI designs to inform BearCube's analysis views — solve times, phase breakdowns, efficiency scores, coaching insights, progress charts, and session analytics.

---

## Table of Contents

1. [Sports Analytics Dashboards](#1-sports-analytics-dashboards)
2. [Gaming & Esports Analytics](#2-gaming--esports-analytics)
3. [Modern Dark-Mode SaaS Dashboards](#3-modern-dark-mode-saas-dashboards)
4. [Data Visualization in Dark Mode](#4-data-visualization-in-dark-mode)
5. [Synthesis: Recommended Patterns for BearCube](#5-synthesis-recommended-patterns-for-bearcube)

---

## 1. Sports Analytics Dashboards

### 1.1 Strava — Post-Activity Detail View

**Layout Structure (Mobile):**
- Activity detail page scrolls vertically through distinct sections
- Top: Map/route display (visual anchor)
- Summary stats bar: Distance, time, elevation, pace — inline horizontal row
- Splits/Laps section: Bar graph chart showing pace per lap, with numerical breakdown below (distance, elapsed time, pace per lap)
- Workout Analysis: Interactive line graph that users can scroll/scrub through to highlight sections
- Segment Results: Listed below workout analysis with medal indicators (bronze/silver/gold for top-3 personal times)

**Key Pattern — Phase Breakdown:**
- Splits are automatically created every mile/kilometer
- Each split shows a mini bar in a bar chart plus numerical stats
- Users can tap to expand and analyze specific sections
- Heart rate, power, speed, or distance breakdowns depend on recorded data channels

**Key Pattern — Interactive Analysis:**
- Scroll through a graph and highlight a section to analyze that segment specifically
- Stat view and map visible simultaneously (no screen switching during review)
- Post-activity preview shows a condensed version; tap to expand to full Workout Analysis screen

**Relevance to BearCube:**
- The "splits as bar chart + numerical table" pattern maps directly to CFOP phase breakdown (Cross, F2L pairs 1-4, OLL, PLL)
- Interactive scrubbing through a solve timeline could let users tap on specific moves/phases
- The condensed preview expanding to full analysis mirrors the "2-line debrief in timer view" expanding to full AI review

**Sources:**
- [Strava Mobile Workout Analysis](https://support.strava.com/hc/en-us/articles/115001136770-Mobile-Workout-Analysis)
- [Strava Run Activity Pages](https://support.strava.com/hc/en-us/articles/216919567-Run-Activity-Pages)
- [Strava Launches Redesigned Record Experience](https://press.strava.com/articles/strava-launches-redesigned-record-experience)
- [Strava Activity Page Guide](https://stories.strava.com/articles/strava-guide-your-activity-page-101)

---

### 1.2 Garmin Connect — Performance Dashboard

**Layout Structure:**
- Widget-based customizable dashboard — users arrange cards/widgets on their home view
- Activity Dashboard on web uses modular "widget" blocks that show summaries
- Individual activity detail view has: sidebar summaries for heart rate, power, and speed/pace data channels
- Reports feature provides long-term trend analysis with customizable graphs and charts

**Key Pattern — Performance Dashboard (Connect+):**
- Comprehensive view of training data
- Compare fitness and health data in customizable graphs and charts
- Edit Activity metadata (name, type, event type) from dashboard
- Drill-down from dashboard widgets into full detail views

**Key Pattern — Data Density:**
- Garmin handles extreme data density by separating "overview widgets" from "detail views"
- Quick summary at glance level, full data exploration behind a tap/click
- Custom Home Dashboard lets users choose which widgets appear

**Relevance to BearCube:**
- The widget/card approach works for BearCube's session analytics: one card for Ao5/12/100 trends, one for phase breakdowns, one for efficiency score, one for coaching insights
- Customizable dashboard ordering maps to letting users prioritize what matters (some cubers care most about F2L efficiency, others about OLL recognition speed)

**Sources:**
- [Garmin Connect+ Performance Dashboard](https://www.garmin.com/en-US/blog/fitness/what-is-the-garmin-connect-performance-dashboard/)
- [Garmin Connect Activity Chart Details](https://support.garmin.com/en-US/?faq=V0T9hu0HIa8uj2gi0ea9aA)
- [Garmin Connect Custom Home Dashboard](https://support.garmin.com/en-US/?faq=XwPv4qgvAj4tlgpt0tSK18)

---

### 1.3 WHOOP — Strain/Recovery Scoring

**Layout Structure (Mobile, Dark Mode Default):**
- Three circular dials/gauges at top of Home screen: Sleep, Recovery, Strain
- Each dial is a primary metric with a dedicated deep-dive page behind it
- Navigation bar at bottom of screen
- Dashboard is fully customizable — users reorder and prioritize features

**Key Pattern — Color-Coded Scoring System:**

Recovery uses a three-tier color system:
| Color | Range | Meaning |
|-------|-------|---------|
| Green | 67-99% | Well recovered, primed to perform |
| Yellow | 34-66% | Maintaining, ready for moderate strain |
| Red | 1-33% | Rest needed |

Strain uses a four-tier system (0-21 scale):
| Level | Range | Meaning |
|-------|-------|---------|
| Light | 0-9 | Minimal stress, room for recovery |
| Moderate | 10-13 | Moderate stress, maintains fitness |
| High | 14-17 | Increased stress, builds fitness |
| All Out | 18-21 | Significant stress on the body |

**Key Pattern — Metric Hierarchy:**
- Three primary dials visible at all times (the "at a glance" layer)
- Tap any dial for a deep-dive detail page
- Weekly and Monthly Performance Assessments provide trend analysis
- Journal feature correlates behaviors with metric outcomes

**Relevance to BearCube:**
- The circular gauge / score display pattern maps perfectly to BearCube's efficiency score per solve
- WHOOP's green/yellow/red recovery color coding parallels BearCube's green/yellow/orange/red move efficiency grading
- The "three dials at top" pattern could become: Efficiency Score, Phase Balance, Session Trend — three key metrics always visible
- Deep-dive from score into detailed breakdown matches BearCube's 2-line debrief expanding to full AI review
- The customizable dashboard ordering is worth adopting — let cubers prioritize what they care about

**Sources:**
- [WHOOP Home Screen](https://www.whoop.com/us/en/thelocker/the-all-new-whoop-home-screen/)
- [WHOOP Strain and Recovery Details](https://support.whoop.com/s/article/Strain-and-Recovery-Details-Screens?language=en_US)
- [WHOOP Overview Screen](https://www.whoop.com/us/en/thelocker/your-key-whoop-metrics-all-in-one-place/)
- [WHOOP Strain Explained](https://www.whoop.com/us/en/thelocker/how-does-whoop-strain-work-101/)

---

### 1.4 TrainingPeaks — Workout Analysis

**Layout Structure:**
- Quick View on click: Summary metrics (duration, distance, TSS, IF) with sidebars for heart rate, power, speed/pace
- Expand to full Analyze view: Map + graph displaying all recorded device data
- Stacked Charts: Color-coded "stacked" visualizations for quick breakdown
- Overlay Charts: Compare any stats on the same chart axis

**Key Pattern — Two-Tier Analysis:**
1. **Quick View** (instant, on click): Summary metrics, zone reports, key numbers
2. **Full Analysis** (expand/drill-down): Interactive graphs, overlays, deep data

**Key Pattern — Stacked & Overlay Charts:**
- Stacked Charts provide color-coded breakdowns without sifting through raw data
- Overlay Charts let users layer different metrics (e.g., heart rate over power) on the same timeline
- Users choose which fields to stack vs. overlap

**Key Pattern — Zone Reports:**
- Time-in-zone breakdowns for heart rate, power, or pace
- Automatically generated based on recorded data channels
- Visual zone bands with time and percentage for each

**Relevance to BearCube:**
- The Quick View / Full Analysis two-tier approach is exactly what BearCube needs:
  - Quick View = 2-line debrief + post-solve summary card
  - Full Analysis = complete AI review with ghost solve replay
- Stacked charts map to phase breakdown: Cross time + F2L time + OLL time + PLL time = total solve, shown as color-coded segments
- Overlay concept: overlay user's solve TPS curve against optimal TPS curve on the same timeline
- Zone reports concept: "time in efficiency zones" — how many moves were green vs. yellow vs. orange vs. red

**Sources:**
- [TrainingPeaks How to Analyze](https://help.trainingpeaks.com/hc/en-us/articles/208916857-How-to-Analyze-a-file-in-TrainingPeaks)
- [TrainingPeaks Metrics Introduction](https://www.trainingpeaks.com/learn/articles/an-introduction-to-trainingpeaks-metrics/)
- [TrainingPeaks Performance Management Chart](https://www.trainingpeaks.com/learn/articles/what-is-the-performance-management-chart/)

---

## 2. Gaming & Esports Analytics

### 2.1 OP.GG — Post-Match Review

**Layout Structure (Dark Mode):**
- Player profile page: Summoner name, rank, win rate at top
- Match history: Vertically scrolling list of recent matches
- Each match card: Champion icon, KDA, items, game duration, win/loss indicator (color-coded blue/red)
- Expand any match for detailed statistics for every player
- One-line performance summary badge system per match

**Key Pattern — Match Card Design:**
- Each match is a compact horizontal card with:
  - Win/loss color indicator (left edge color bar — blue for win, red for loss)
  - Champion icon + items
  - KDA numbers (large, prominent)
  - Game duration and mode
  - Expandable to full scoreboard
- Cards are data-dense but scannable because of consistent visual hierarchy

**Key Pattern — Performance Badges:**
- After each match, players receive badges and one-line summaries
- Visual shorthand that communicates performance quality at a glance
- Advanced metrics (Damage Share, Gold Differential @15, Vision Score per Hour) available in expanded view

**Key Pattern — Dark Mode Implementation:**
- Dark theme with switchable light mode (moon/sun toggle in top-right)
- High-contrast text on dark background
- Color coding for win/loss, tier/rank, and performance quality
- Match cards use subtle background color variations to distinguish wins from losses

**Relevance to BearCube:**
- The match card pattern maps directly to a "solve card" in BearCube's solve history:
  - Left edge color bar indicating efficiency (green to red gradient instead of win/loss)
  - Solve time (large, prominent, like KDA)
  - Phase split summary (like items row)
  - Efficiency score badge
  - Expandable to full AI review
- One-line performance summary = BearCube's 2-line AI debrief
- Badge system for solves: "Clean Cross", "Efficient F2L", "Sub-X PB"

**Sources:**
- [OP.GG App Store](https://apps.apple.com/us/app/op-gg/id605722237)
- [OP.GG Dark Mode Toggle](https://help.op.gg/hc/en-us/articles/31090599354393-How-can-I-switch-to-dark-or-light-mode)

---

### 2.2 Tracker.gg / Valorant Tracker — Performance Scoring

**Layout Structure:**
- Profile overview: Rank, win rate, K/D, headshot %, and key stats in a grid of metric cards
- Match history: List of previous matches with at-a-glance performance data
- Match detail: Roster, advanced scoreboard, and timeline from each match
- Real-time overlay during gameplay with round-by-round analytics

**Key Pattern — Tracker Score (Composite Performance Rating):**
- Single number out of 1,000 points combining multiple weighted performance indicators
- Relative scoring against the total player population
- Multiple stats collapsed into one intuitive number
- Breakdown available showing which component stats contribute to the score

**Key Pattern — Round-by-Round Timeline:**
- Each round in a match can be reviewed individually
- Timeline view shows performance across the match duration
- Post-match breakdown combines aggregate stats with per-round detail

**Key Pattern — Metric Grid Layout:**
- Key stats displayed in a grid of cards on the profile page:
  - K/D ratio
  - Headshot %
  - Win rate
  - Rank progression
  - Agent performance
  - Map statistics
- Each card is a single metric with its value prominently displayed and a trend indicator

**Relevance to BearCube:**
- Tracker Score (1,000-point composite) is the direct inspiration for BearCube's efficiency score
  - BearCube could score solves out of 100 (or 1,000) based on weighted factors: move efficiency per phase, pause count, rotation count, recognition speed
  - Show the single score prominently, with expandable breakdown of contributing factors
- The metric grid layout works for BearCube's session summary:
  - Card 1: Session Ao5/12/100
  - Card 2: Average Efficiency Score
  - Card 3: Best Phase (e.g., "Cross: 94% efficient")
  - Card 4: Biggest Opportunity (e.g., "F2L Pair 3: 62% efficient")
- Round-by-round timeline maps to solve-by-solve session timeline

**Sources:**
- [Tracker Score Performance Rating](https://tracker.gg/articles/tracker-score-our-new-performance-rating)
- [Valorant Tracker](https://tracker.gg/valorant)
- [Valorant Tracker App](https://tracker.gg/valorant/app)

---

### 2.3 U.GG — Post-Game Analysis

**Key Pattern — Role-Ordered Display:**
- Players listed in role order (top, jungle, mid, ADC, support) — not random
- Structured ordering makes comparison intuitive

**Key Pattern — Advanced Post-Game Metrics:**
- Beyond basic stats: Damage Share, Gold Differential @15, Vision Score per Hour
- Identifies whether a loss was a laning issue vs. macro/teamfighting issue
- Quick performance summary immediately after match for fresh analysis

**Relevance to BearCube:**
- Phase-ordered display: Always show Cross -> F2L (pairs 1-4) -> OLL -> PLL in consistent order
- Beyond basic stats: Not just "F2L took 7.5s" but "F2L pair 2 was 6 moves, optimal was 3 — here's the efficient insertion"
- The "laning vs. macro" distinction maps to "recognition delay vs. move inefficiency" — helping users understand *what kind* of mistake, not just *that* there was one

**Sources:**
- [U.GG](https://u.gg/)
- [U.GG App](https://u.gg/app)

---

### 2.4 General Esports Analytics Patterns

**Key Takeaways:**
- Clean and clear data visualization so users don't feel overwhelmed
- Goal: Make performance data understandable by users at any knowledge level
- Real-time analytics enables quick in-session adjustments
- Popular visualization tools: D3.js, Recharts (React), VisActor
- Challenge: balancing data density with clarity — avoid cognitive overload

**Sources:**
- [Data Visualization in Esports](https://www.numberanalytics.com/blog/data-visualization-esports-game-analytics)
- [Esports Analytics Dashboard on Dribbble](https://dribbble.com/shots/20095191-Statistics-for-Esports-Analytics-Web-Dashboard)

---

## 3. Modern Dark-Mode SaaS Dashboards

### 3.1 Linear — The Gold Standard for SaaS Dark Mode

**Layout Structure:**
- Left sidebar: Navigation (collapsible, personalized)
- Main content: Tabbed views with filter headers
- Right panel: Meta properties / detail panel
- Display modes: List, Board, Timeline, Split, Fullscreen
- Headers store filters and display options

**Key Pattern — Visual Noise Reduction:**
- 2024 redesign specifically targeted reducing visual clutter
- Adjusted sidebar, tabs, headers, and panels to:
  - Reduce visual noise
  - Maintain visual alignment
  - Increase hierarchy and density of navigation elements
- Current view, available actions, and meta properties presented more clearly
- Minimal ornamentation — content speaks for itself

**Key Pattern — Structured Layouts:**
- Consistent layout skeleton across all views
- Headers for filters and display options
- Side panels for meta properties
- Multiple display types on the same data (list, board, timeline)
- Users choose their preferred view

**Key Pattern — Dark Mode Implementation:**
- Compatible with both light and dark modes
- Custom theme generator for personalization
- Appearance and contrast carefully tuned for both modes
- Subtle glassmorphism effects (transparency, blur) create depth without noise
- Feature flag rollout allowed testing dark mode adjustments

**Key Pattern — "Linear Design" Aesthetic (Industry Trend):**
- Clean, minimal, high-contrast
- Fewer colors, more subtle glassmorphism, sharper visuals
- Results in fewer bugs, increased performance, faster development
- Easy to implement with pure code (Tailwind CSS, CSS variables)
- Now evolving: "linear design but bolder and with more individuality" in 2025-2026

**Relevance to BearCube:**
- The sidebar + main content + detail panel layout works for:
  - Sidebar: Session list / Solve history
  - Main content: Current solve analysis or session overview
  - Detail panel: AI coaching insights, algorithm suggestions
- Multiple display modes: BearCube could offer "Summary" vs. "Detail" vs. "Timeline" views of the same session
- The noise reduction philosophy is critical — BearCube shows a LOT of data (moves, phases, scores, comparisons, charts); Linear's approach to visual hierarchy prevents overwhelming users
- Custom themes could let users personalize their BearCube experience

**Sources:**
- [How We Redesigned the Linear UI](https://linear.app/now/how-we-redesigned-the-linear-ui)
- [Linear Design SaaS Trend Analysis (LogRocket)](https://blog.logrocket.com/ux-design/linear-design/)
- [Rise of Linear Style Design](https://medium.com/design-bootcamp/the-rise-of-linear-style-design-origins-trends-and-techniques-4fd96aab7646)
- [Welcome to the New Linear UI](https://linear.app/changelog/2024-03-20-new-linear-ui)
- [Personalized Sidebar](https://linear.app/changelog/2024-12-18-personalized-sidebar)

---

### 3.2 Vercel — Developer-Centric Dashboard

**Key Pattern — Respects User Time:**
- UI gets out of the way — minimal chrome, maximum content
- No fancy animations unless they add clarity
- Clean, minimal, flexible approach
- Collapsible sidebars and variable content widths accommodate different data density needs

**Key Pattern — Analytics Views:**
- KPI cards with trend indicators (sparklines)
- Real-time metric updates
- Date pickers for time range selection
- Card shadows and rounded corners for visual separation
- Grid layouts that reflow responsively

**Key Pattern — Component Architecture:**
- Built on shadcn/ui + Tailwind CSS
- 53 pre-built chart components with automatic dark mode support via CSS variables
- Charts use Recharts under the hood
- Dark/light mode switching uses system preference with toggle override

**Relevance to BearCube:**
- Vercel's "no unnecessary animation" philosophy is important for a timer app — cubers want speed, not flashiness
- The KPI card + sparkline pattern is perfect for:
  - Ao5: 14.2s [sparkline showing trend over last 20 solves]
  - Ao100: 15.1s [sparkline showing trend over last week]
  - Efficiency: 78% [sparkline showing improvement trajectory]
- shadcn/ui + Recharts + Tailwind CSS is the recommended implementation stack (BearCube already uses Next.js)
- CSS variable-based theming means dark mode works automatically across all chart components

**Sources:**
- [Vercel Dashboard Features](https://vercel.com/docs/dashboard-features)
- [Vercel's Dashboard UX Analysis](https://medium.com/design-bootcamp/vercels-new-dashboard-ux-what-it-teaches-us-about-developer-centric-design-93117215fe31)
- [shadcn/ui Chart Components](https://ui.shadcn.com/docs/components/radix/chart)
- [shadcn/ui Dark Mode](https://ui.shadcn.com/docs/dark-mode)

---

### 3.3 Raycast — Command Palette & Component System

**Key Pattern — UI Component Types:**
- **List:** Multiple similar items (solve history, algorithm cases)
- **Grid:** Image-heavy items with more space (algorithm knowledge map, cube state previews)
- **Detail:** In-depth information (full solve analysis, AI coaching detail)
- **Form:** Input creation (manual solve entry, settings)

**Key Pattern — Action Panel:**
- Context-sensitive actions associated with keyboard shortcuts
- Mouse-free operation possible
- Actions appear relevant to the current context

**Key Pattern — Adaptive Theming:**
- Supports light/dark with system preference detection
- Colors automatically adapt to current theme
- Component colors accept functions called with mode ('light' or 'dark')

**Relevance to BearCube:**
- The List/Grid/Detail/Form component taxonomy is a useful mental model for BearCube's views:
  - **List:** Solve history, session list
  - **Grid:** Algorithm knowledge map (57 OLL + 21 PLL cases in a grid), daily challenge leaderboard
  - **Detail:** Full solve analysis, cuber profile
  - **Form:** Settings, manual solve entry
- Keyboard-first design matters for speedcubers who already use spacebar for timer — extend keyboard navigation to the entire app
- Action panels with keyboard shortcuts: press 'R' to replay, 'A' to see AI analysis, 'N' for next solve

**Sources:**
- [Raycast User Interface API](https://developers.raycast.com/api-reference/user-interface)
- [Raycast Settings](https://manual.raycast.com/preferences)
- [Raycast Colors API](https://developers.raycast.com/api-reference/user-interface/colors)

---

### 3.4 Arc Browser — Sidebar Navigation & Spaces

**Key Pattern — Sidebar as Primary Navigation:**
- Everything starts in the left-hand sidebar
- Vertical orientation (superior to horizontal tab bars for many items)
- Contains: active items, pinned items, folders, spaces
- Tab expiry: temporary items auto-archive, important items are pinned

**Key Pattern — Spaces for Context Switching:**
- Distinct workspaces that don't interfere with each other
- Deep focus possible within a space
- Rapid context switching between spaces
- Visual identity per space (gradient theming)

**Key Pattern — Visual Identity:**
- Clean design, soft gradients, purposeful typography
- Layout respects space — creates "mental calm"
- Reduces noise in an information-dense environment

**Relevance to BearCube:**
- The "Spaces" concept maps to BearCube's session management:
  - Each practice session is a "space" with its own context
  - Pin important sessions (competition prep, PB sessions)
  - Regular sessions auto-archive after review
- Sidebar navigation with pinned vs. regular items:
  - Pinned: Current session, algorithm trainer, daily challenge
  - Regular: Past sessions, profile, settings
- The "mental calm" design philosophy is essential — cubers deal with complex data but need to focus on one thing at a time

**Sources:**
- [Arc Browser Design Analysis](https://medium.com/design-bootcamp/arc-browser-rethinking-the-web-through-a-designers-lens-f3922ef2133e)
- [Arc Spaces Documentation](https://resources.arc.net/hc/en-us/articles/19228064149143-Spaces-Distinct-Browsing-Areas)

---

## 4. Data Visualization in Dark Mode

### 4.1 Background & Surface Colors

**Best Practice: Never Use Pure Black (#000000)**

Use dark grays that reduce contrast harshness while maintaining the dark aesthetic:

| Surface | Recommended Values | Purpose |
|---------|-------------------|---------|
| Base background | #121212, #0A0A0A | Primary app background |
| Elevated surface | #1E1E1E, #1C1C1C | Cards, panels, modals |
| Chart background | Slightly lighter than surface (#1E1E1E on #121212 base) | Subtle separation |
| Grid lines | #333333, #3E3E3E | Low-contrast, non-competing |
| Borders | #2A2A2A, #333333 | Subtle card/section separation |

**Avoid pure white text** — use softer whites like #F0F0F0 or #E0E0E0 for body text, reserving near-white (#FAFAFA) for primary numbers and headings.

**Sources:**
- [Dark Mode Charts Best Practices (CleanChart)](https://www.cleanchart.app/blog/dark-mode-charts)
- [Implementing Dark Mode for Data Visualizations](https://ananyadeka.medium.com/implementing-dark-mode-for-data-visualizations-design-considerations-66cd1ff2ab67)
- [Dark Mode Color Palette Guide (Zeplin)](https://blog.zeplin.io/dark-mode-color-palette/)

---

### 4.2 Color Palettes for Charts on Dark Backgrounds

**Key Principles:**
- Don't simply invert light mode colors — create a dedicated dark mode palette
- Colors often need **lower saturation** in dark mode (high saturation on dark backgrounds creates visual vibration)
- Limit to 4-5 contrasting colors for most chart contexts
- 8-12 distinct hues maximum; avoid the rainbow
- Use semi-transparent colors (80-90% opacity) for filled areas

**BearCube Efficiency Color Scale (adapted for dark mode):**

| Efficiency Level | Light Mode | Dark Mode (Lower Saturation) | Usage |
|-----------------|------------|------------------------------|-------|
| Optimal (green) | #22C55E | #34D399 (emerald-400) | Moves matching or near-optimal |
| Good (yellow) | #EAB308 | #FBBF24 (amber-400) | Slightly inefficient moves |
| Suboptimal (orange) | #F97316 | #FB923C (orange-400) | Noticeably inefficient moves |
| Poor (red) | #EF4444 | #F87171 (red-400) | Highly inefficient moves |

**Phase Color Coding (for stacked charts):**

| Phase | Suggested Color | Hex |
|-------|----------------|-----|
| Cross | Blue | #60A5FA (blue-400) |
| F2L | Teal/Cyan | #22D3EE (cyan-400) |
| OLL | Purple | #A78BFA (violet-400) |
| PLL | Pink/Magenta | #F472B6 (pink-400) |

**Accent Colors on Dark:**
- Choose one bright brand color as primary accent
- Limit accent to smaller components (buttons, active states, highlights)
- Most page area occupied by low-light neutral colors
- Neon-style accents (electric blue, lime green) work well on dark backgrounds for small highlights

**Sources:**
- [Dark Mode Charts Best Practices (CleanChart)](https://www.cleanchart.app/blog/dark-mode-charts)
- [Colors in Data Vis Style Guides (Datawrapper)](https://www.datawrapper.de/blog/colors-for-data-vis-style-guides)
- [Color Palettes and Accessibility for Data Viz (Carbon Design)](https://medium.com/carbondesign/color-palettes-and-accessibility-features-for-data-visualization-7869f4874fca)
- [Neon Colors on Dark Backgrounds (Vev)](https://www.vev.design/blog/dark-mode-website-color-palette/)

---

### 4.3 Accessibility Requirements

**Contrast Ratios (WCAG 2.1 AA):**
- Text: Minimum 4.5:1 contrast ratio against background
- Large text (18px+/bold 14px+): Minimum 3:1 contrast ratio
- Non-text UI components: Minimum 3:1 against adjacent colors
- Chart backgrounds: Restrict to brightest and darkest theme backgrounds for maximum contrast

**Colorblind Safety:**
- BearCube's green/yellow/orange/red scale must be supplemented with a second cue (icons, patterns, labels, or shape indicators) per NFR27
- Test palette with deuteranopia, protanopia, and tritanopia simulations
- Use value (lightness) differences, not just hue differences, to distinguish levels

**Implementation:**
- shadcn/ui CSS variables system handles light/dark mode automatically
- All 53 shadcn chart components adapt to dark mode via CSS variables
- Use `next-themes` with `ThemeProvider` for system preference + manual toggle

**Sources:**
- [Color Palettes and Accessibility (Carbon Design)](https://medium.com/carbondesign/color-palettes-and-accessibility-features-for-data-visualization-7869f4874fca)
- [Accessible Color Contrast in UX](https://developerux.com/2025/07/28/best-practices-for-accessible-color-contrast-in-ux/)
- [Dark Mode Dashboard Design Principles (QodeQuay)](https://www.qodequay.com/dark-mode-dashboards)

---

### 4.4 Sparklines & Inline Charts

**Definition:** Small, wordsize graphics embedded inline with text or in table cells. No axes, no labels — just the shape of the data trend.

**Use Cases for BearCube:**
- Next to Ao5/12/100 numbers: Sparkline showing recent trend direction
- In solve history list: Tiny line chart showing last 10 solve times per session
- Dashboard KPI cards: Sparkline below the main number showing trajectory
- In algorithm knowledge map: Mini bar showing recognition speed per case

**Implementation:**
- Chakra UI Sparkline component (inline `<span>` element)
- MUI X SparkLine component
- shadcn/ui + Recharts SparkLine
- Color adapts to dark/light mode via function callback

**Best Practices:**
- Keep sparklines simple — line or bar, rarely both
- Use color to indicate trend direction (green for improving, red for declining)
- No interactivity needed — these are glanceable indicators
- Ensure sufficient contrast on dark backgrounds (use lighter line colors)

**Sources:**
- [Chakra UI Sparkline](https://chakra-ui.com/docs/charts/sparkline)
- [MUI X SparkLine](https://mui.com/x/react-charts/sparkline/)
- [shadcn/ui Table with Sparklines](https://www.shadcn.io/blocks/tables-sparkline)

---

### 4.5 Circular Progress & Score Displays

**Patterns for Score/Rating Display:**

1. **Circular Progress Ring** (WHOOP-style)
   - Ring fills proportionally to score
   - Number displayed in center
   - Color changes based on score tier
   - Compact — works in small spaces
   - Effective for determinate progress (known max value)

2. **Radial Gauge** (dashboard instrument style)
   - Semicircular or full-circle gauge
   - Needle or filled arc indicates value
   - Zone coloring on the gauge track (green/yellow/red zones)
   - Good for showing where a value falls in a range

3. **Linear Progress Bar with Segments**
   - Horizontal bar divided into colored segments
   - Shows score position relative to tiers
   - Can double as a phase breakdown (each segment = one phase's contribution)

**BearCube Application:**
- **Efficiency Score per Solve:** Circular progress ring (0-100%)
  - Center: Score number (large, bold)
  - Ring color: Green (80-100%), Yellow (60-79%), Orange (40-59%), Red (0-39%)
  - Ring animation on solve completion
- **Phase Balance:** Segmented horizontal bar
  - Each segment colored by phase (Cross/F2L/OLL/PLL)
  - Width proportional to time spent in each phase
  - Compared against "ideal" distribution line
- **Session Progress:** Linear progress with milestone markers
  - Shows solves completed in session
  - PB markers on the timeline

**Sources:**
- [Material Design Progress Indicators](https://m3.material.io/components/progress-indicators/overview)
- [Ant Design Progress](https://ant.design/components/progress/)
- [Progress Indicator UI Best Practices](https://mobbin.com/glossary/progress-indicator)
- [Animated Circular Progress (MagicUI)](https://magicui.design/docs/components/animated-circular-progress-bar)

---

### 4.6 Stacked/Segmented Bar Charts for Phase Breakdowns

**Pattern:** Horizontal stacked bar chart where each segment represents a solve phase.

**For BearCube Phase Breakdown:**
```
Solve Time: 14.2s
|████ Cross (1.2s) |██████████ F2L (7.8s)  |███ OLL (2.8s)|██ PLL (2.4s)|
```

**Best Practices:**
- Use highly contrasting colors between segments
- Avoid similar colors for adjacent segments
- Show numerical values within or above each segment
- Consistent segment ordering across all views (Cross -> F2L -> OLL -> PLL)
- Color intensity can encode efficiency (darker = more efficient within the phase color)

**Comparison Mode:**
```
Your Solve:  |████ 1.2s |██████████ 7.8s   |███ 2.8s |██ 2.4s | = 14.2s
Optimal:     |██ 0.8s   |█████ 4.2s        |██ 1.8s  |█ 1.5s  | = 8.3s
```

Shows both absolute time and proportional phase allocation at a glance.

**Sources:**
- [Stacked Bar Charts Guide (Atlassian)](https://www.atlassian.com/data/charts/stacked-bar-chart-complete-guide)
- [Segmented Bar Graph (ChartExpo)](https://chartexpo.com/blog/segmented-bar-graph)

---

## 5. Synthesis: Recommended Patterns for BearCube

### 5.1 Overall Design Philosophy

Based on this research, BearCube should adopt:

1. **"Linear Design" Aesthetic:** Clean, minimal, dark-first, high-contrast. Subtle glassmorphism for depth. No unnecessary ornamentation. Content-forward.
2. **Two-Tier Information Architecture:** Every data point has a "glance" version and a "deep dive" version. Never force users through detail to get to summary.
3. **Progressive Disclosure:** Show the most important insight first (2-line debrief), then let users drill into phase breakdowns, then individual moves.
4. **WHOOP-Style Scoring:** Single composite score (efficiency) prominently displayed with color coding, expandable to component breakdown.
5. **Strava-Style Phase Segmentation:** Phase breakdown as stacked bar + numerical table, with interactive drill-down per phase.

---

### 5.2 Recommended Screen Layouts

#### A. Timer View (Post-Solve State) — Mobile

```
┌─────────────────────────────┐
│  14.23s          Ao5: 14.8  │  ← Solve time (huge), current average (smaller)
│  ───────────────────────────│
│  ┌─────────────────────────┐│
│  │  Efficiency: 76%   ●●●○ ││  ← Circular score + dot rating (colorblind-safe)
│  │  "Cross efficient, F2L  ││  ← 2-line AI debrief
│  │   pair 3 cost 3 extra   ││
│  │   moves — tap to review"││
│  └─────────────────────────┘│
│  ┌─ Phase Breakdown ───────┐│
│  │ ████ ██████████ ███ ██  ││  ← Stacked bar (Cross/F2L/OLL/PLL)
│  │ 1.2  7.8       2.8 2.4  ││  ← Times below
│  └─────────────────────────┘│
│                              │
│  [Full Review]  [Replay]     │  ← Action buttons
│  ───────────────────────────│
│  Next Scramble: R U R' F... │  ← Ready for next solve
└─────────────────────────────┘
```

**Inspiration:** WHOOP (score dial) + Strava (splits bar chart) + OP.GG (compact match card with expandable detail)

#### B. Full Solve Review — Desktop

```
┌──────────────┬──────────────────────────────────────────┬──────────────┐
│  Solve List   │  Solve #47 — 14.23s (76% efficient)      │  AI Coaching  │
│  ─────────── │  ────────────────────────────────────────  │  ──────────  │
│  #50  13.8s  │  ┌─ Phase Breakdown ───────────────────┐  │  ┌─────────┐│
│  #49  14.5s  │  │ Cross  │  F2L   │ OLL  │  PLL       │  │  │ Insight ││
│  ▶#47  14.2s │  │ 1.2s   │  7.8s  │ 2.8s │  2.4s      │  │  │ F2L #3  ││
│  #46  15.1s  │  │ 92%    │  68%   │ 85%  │  91%       │  │  │ used 6  ││
│  #45  13.9s  │  └────────────────────────────────────┘  │  │ moves,  ││
│  ─────────── │                                           │  │ optimal ││
│  Ao5:  14.8  │  ┌─ Move Timeline ─────────────────────┐  │  │ is 3.   ││
│  Ao12: 14.5  │  │ ●●●●●○○●●●●●●○●●●○○●●●●●●●●●●●●●● │  │  │         ││
│  Ao100:15.1  │  │ ▲Cross ▲F2L-1 ▲F2L-2 ▲F2L-3 ...    │  │  │ [Drill] ││
│              │  └────────────────────────────────────┘  │  └─────────┘│
│  ┌─────────┐ │                                           │  ┌─────────┐│
│  │ Session  │ │  ┌─ Ghost Replay ─────────────────────┐  │  │ Similar ││
│  │ Sparkline│ │  │  [Your Solve]    [AI Optimal]       │  │  │ Pattern ││
│  │ ~~~~~~~~ │ │  │  ┌──────────┐   ┌──────────┐       │  │  │ in 5    ││
│  └─────────┘ │  │  │  3D Cube  │   │  3D Cube  │       │  │  │ recent  ││
│              │  │  │           │   │           │       │  │  │ solves  ││
│              │  │  └──────────┘   └──────────┘       │  │  └─────────┘│
│              │  │  [Play] [Pause] [Step] ■■■■■○○○○○  │  │              │
│              │  └────────────────────────────────────┘  │              │
└──────────────┴──────────────────────────────────────────┴──────────────┘
```

**Inspiration:** Linear (sidebar + main + detail panel) + TrainingPeaks (stacked chart + overlay analysis) + Tracker.gg (composite score breakdown)

#### C. Session Analytics Dashboard — Mobile

```
┌─────────────────────────────┐
│  Session: Practice 2/22     │
│  42 solves · 28 min         │
│  ───────────────────────────│
│  ┌─ Key Metrics ───────────┐│
│  │ Ao5     │ Ao12    │ Best ││  ← Metric cards in row
│  │ 14.2s   │ 14.8s   │ 12.9 ││
│  │ ↓0.3s   │ ↓0.1s   │ PB!  ││  ← Trend arrows + badges
│  │ ~~~~~~~~│ ~~~~~~~~│      ││  ← Sparklines under each
│  └─────────────────────────┘│
│  ┌─ Efficiency Trend ──────┐│
│  │  ╭──╮    ╭──╮           ││  ← Line chart of efficiency
│  │ ─╯  ╰──╮╯  ╰╮  ╭──     ││    scores across session
│  │         ╰    ╰──╯       ││
│  │  Avg: 74% ↑3% from last ││
│  └─────────────────────────┘│
│  ┌─ Phase Averages ────────┐│
│  │ Cross: 1.1s avg (91%)   ││  ← Per-phase averages
│  │ ████████████████████████ ││    with efficiency %
│  │ F2L:   7.2s avg (65%)   ││
│  │ █████████████████        ││
│  │ OLL:   2.6s avg (82%)   ││
│  │ ████████████████████     ││
│  │ PLL:   2.3s avg (88%)   ││
│  │ ██████████████████████   ││
│  └─────────────────────────┘│
│  ┌─ Coaching Summary ──────┐│
│  │ 🎯 Focus Area: F2L      ││
│  │ "Your F2L averaged 5.1  ││
│  │  moves/pair. Optimal is ││
│  │  3.5. 3 drills targeted ││
│  │  at your weakest pairs."││
│  │ [Start F2L Drills →]    ││
│  └─────────────────────────┘│
│  ┌─ Solve Timeline ────────┐│
│  │ ● ● ● ● ○ ○ ● ● ● ● ● ││  ← Dot plot, color = efficiency
│  │ Tap any solve to review  ││
│  └─────────────────────────┘│
└─────────────────────────────┘
```

**Inspiration:** WHOOP (scrollable card sections) + Garmin (widget-based customizable dashboard) + Vercel (KPI cards with sparklines)

---

### 5.3 Visual Hierarchy Rules for BearCube

**Level 1 — Hero Numbers (always visible):**
- Solve time (largest text on screen, 32-48px)
- Efficiency score (circular gauge or large number)
- Current averages (Ao5/Ao12)

**Level 2 — Summary Cards (visible on scroll):**
- Phase breakdown (stacked bar)
- 2-line AI debrief text
- Trend indicators (sparklines, arrows)

**Level 3 — Detail Views (on tap/click):**
- Full AI review with move-by-move color grading
- Ghost solve replay
- Coaching recommendations with drill links

**Level 4 — Deep Analytics (dedicated page):**
- Algorithm knowledge map grid
- Long-term progress charts
- Session comparison
- Cuber profile strengths/weaknesses

---

### 5.4 Component Inventory for BearCube Analysis Views

Based on patterns observed across all researched platforms:

| Component | Inspired By | BearCube Usage |
|-----------|-------------|----------------|
| **Circular Score Gauge** | WHOOP dials | Efficiency score per solve |
| **Stacked Phase Bar** | Strava splits + TrainingPeaks | Cross/F2L/OLL/PLL time breakdown |
| **Move Timeline** | OP.GG match timeline, Strava workout analysis | Color-coded move sequence (green/yellow/orange/red) |
| **KPI Card + Sparkline** | Vercel dashboard, Garmin widgets | Ao5, Ao12, Ao100 with trend line |
| **Expandable Solve Card** | OP.GG match card | Solve in history list, edge-color-coded by efficiency |
| **Composite Score Breakdown** | Tracker.gg Tracker Score | How efficiency score breaks down by phase/factor |
| **Coaching Insight Card** | WHOOP recovery recommendations | AI coaching text with action button (drill link) |
| **Algorithm Knowledge Grid** | Raycast Grid view | 57 OLL + 21 PLL cases, color-coded by mastery |
| **Session Dot Plot** | Fitness app workout views | Colored dots per solve in session timeline |
| **Comparison Overlay** | TrainingPeaks overlay charts | User solve vs. optimal on same timeline |
| **Side-by-Side 3D Replay** | (BearCube original — ghost solve) | Two 3D cubes playing synchronized |
| **Progress Line Chart** | Strava/Garmin long-term trends | Ao100 over weeks/months |
| **Badge/Medal System** | Strava segment medals, OP.GG badges | "Clean Cross", "Sub-X PB", "Efficient F2L" |

---

### 5.5 Dark Mode Implementation Recommendations

**Technology Stack:**
- `next-themes` for theme management (system preference + manual toggle)
- Tailwind CSS with `dark:` variant for component styling
- shadcn/ui components (built-in dark mode via CSS variables)
- Recharts for all charts (adapts to shadcn theme automatically)
- CSS variables for color tokens (instant theme switching, no reload)

**Color Token System:**

```css
:root {
  /* Surfaces */
  --background: 0 0% 100%;        /* #FFFFFF */
  --surface: 0 0% 96%;            /* #F5F5F5 */
  --surface-elevated: 0 0% 100%;  /* #FFFFFF */

  /* Text */
  --foreground: 0 0% 9%;          /* #171717 */
  --muted-foreground: 0 0% 45%;   /* #737373 */
}

.dark {
  /* Surfaces */
  --background: 0 0% 5%;          /* #0D0D0D */
  --surface: 0 0% 9%;             /* #171717 */
  --surface-elevated: 0 0% 12%;   /* #1E1E1E */

  /* Text */
  --foreground: 0 0% 95%;         /* #F2F2F2 */
  --muted-foreground: 0 0% 60%;   /* #999999 */

  /* Chart-specific */
  --chart-grid: 0 0% 20%;         /* #333333 */
  --chart-text: 0 0% 70%;         /* #B3B3B3 */
}
```

**Chart Color Tokens (Dark Mode Optimized):**

```css
.dark {
  /* Efficiency grading */
  --efficiency-optimal: 160 84% 39%;   /* Emerald-ish green */
  --efficiency-good: 45 93% 47%;       /* Amber-ish yellow */
  --efficiency-suboptimal: 27 96% 61%; /* Orange */
  --efficiency-poor: 0 91% 71%;        /* Soft red */

  /* Phase colors */
  --phase-cross: 217 91% 60%;    /* Blue */
  --phase-f2l: 188 94% 43%;      /* Cyan/Teal */
  --phase-oll: 258 90% 66%;      /* Purple */
  --phase-pll: 330 81% 60%;      /* Pink */

  /* Accent */
  --accent: 217 91% 60%;         /* Blue accent */
}
```

---

### 5.6 Mobile vs. Desktop Layout Strategy

**Mobile (360px - 768px):**
- Single column, vertically scrolling card sections
- Hero number (solve time) always visible at top
- Phase breakdown as compact horizontal stacked bar
- Coaching insight as a collapsible card
- Ghost replay: full-width, single cube at a time with tab to switch
- Solve history: compact list with edge color coding
- Bottom navigation bar (WHOOP pattern): Timer | History | Profile | Settings

**Tablet (768px - 1024px):**
- Two-column layout where possible
- Solve time + phase breakdown side by side
- Ghost replay: two cubes side by side (landscape)
- Session analytics: 2-column card grid

**Desktop (1024px+):**
- Three-panel layout (Linear pattern): Solve List | Main Analysis | AI Coaching
- Ghost replay: full side-by-side with generous spacing
- Session analytics: Multi-column dashboard grid
- Keyboard navigation for power users (spacebar timer, arrow keys through solves)

---

### 5.7 Key Tension: Data Density vs. Clarity

The central design challenge for BearCube is the same challenge faced by every platform researched: **showing lots of data without overwhelming users.**

**Solutions observed across platforms:**

1. **Progressive Disclosure** (Linear, Strava, TrainingPeaks)
   - Start with summary, reveal detail on demand
   - BearCube: 2-line debrief -> summary card -> full review -> move-by-move

2. **Customizable Dashboard** (Garmin, WHOOP)
   - Let users prioritize what matters to them
   - BearCube: Reorderable analytics cards, hideable sections

3. **Consistent Visual Hierarchy** (Vercel, Linear)
   - Same patterns repeated across views (numbers big, labels small, muted secondary text)
   - BearCube: Solve time always big, averages always medium, metadata always small

4. **Whitespace and Card Separation** (WHOOP, Vercel)
   - Space between cards prevents cognitive overload
   - BearCube: Generous spacing between phase breakdown, coaching, and statistics sections

5. **Tooltips and Hover States** (TrainingPeaks, OP.GG)
   - Hide dense labels, show on interaction
   - BearCube: Move timeline shows detail on hover/tap, not by default

6. **Concatenation** (Fitness dashboards)
   - Merge related data into single dense points
   - BearCube: "F2L: 7.8s / 68% / 5.1 moves avg" as one line instead of three separate displays

---

## Appendix: Sources Index

### Sports Analytics
- [Strava Mobile Workout Analysis](https://support.strava.com/hc/en-us/articles/115001136770-Mobile-Workout-Analysis)
- [Strava Run Activity Pages](https://support.strava.com/hc/en-us/articles/216919567-Run-Activity-Pages)
- [Strava Redesigned Record Experience](https://press.strava.com/articles/strava-launches-redesigned-record-experience)
- [Garmin Connect+ Performance Dashboard](https://www.garmin.com/en-US/blog/fitness/what-is-the-garmin-connect-performance-dashboard/)
- [Garmin Connect Custom Home Dashboard](https://support.garmin.com/en-US/?faq=XwPv4qgvAj4tlgpt0tSK18)
- [WHOOP Home Screen](https://www.whoop.com/us/en/thelocker/the-all-new-whoop-home-screen/)
- [WHOOP Strain and Recovery Details](https://support.whoop.com/s/article/Strain-and-Recovery-Details-Screens?language=en_US)
- [WHOOP Overview Screen](https://www.whoop.com/us/en/thelocker/your-key-whoop-metrics-all-in-one-place/)
- [TrainingPeaks How to Analyze](https://help.trainingpeaks.com/hc/en-us/articles/208916857-How-to-Analyze-a-file-in-TrainingPeaks)
- [TrainingPeaks Metrics](https://www.trainingpeaks.com/learn/articles/an-introduction-to-trainingpeaks-metrics/)
- [TrainingPeaks Performance Management Chart](https://www.trainingpeaks.com/learn/articles/what-is-the-performance-management-chart/)
- [Fitness App Dashboard Design Patterns](https://www.sportfitnessapps.com/blog/best-practices-for-athlete-performance-dashboards)

### Gaming & Esports
- [OP.GG](https://apps.apple.com/us/app/op-gg/id605722237)
- [Tracker Score Performance Rating](https://tracker.gg/articles/tracker-score-our-new-performance-rating)
- [Valorant Tracker](https://tracker.gg/valorant)
- [U.GG](https://u.gg/)
- [Data Visualization in Esports](https://www.numberanalytics.com/blog/data-visualization-esports-game-analytics)

### SaaS Dashboards
- [Linear UI Redesign](https://linear.app/now/how-we-redesigned-the-linear-ui)
- [Linear Design Trend (LogRocket)](https://blog.logrocket.com/ux-design/linear-design/)
- [Rise of Linear Style Design](https://medium.com/design-bootcamp/the-rise-of-linear-style-design-origins-trends-and-techniques-4fd96aab7646)
- [New Linear UI Changelog](https://linear.app/changelog/2024-03-20-new-linear-ui)
- [Vercel Dashboard Features](https://vercel.com/docs/dashboard-features)
- [Vercel Dashboard UX Analysis](https://medium.com/design-bootcamp/vercels-new-dashboard-ux-what-it-teaches-us-about-developer-centric-design-93117215fe31)
- [shadcn/ui Charts](https://ui.shadcn.com/docs/components/radix/chart)
- [shadcn/ui Dark Mode](https://ui.shadcn.com/docs/dark-mode)
- [Raycast UI API](https://developers.raycast.com/api-reference/user-interface)
- [Arc Browser Design Analysis](https://medium.com/design-bootcamp/arc-browser-rethinking-the-web-through-a-designers-lens-f3922ef2133e)

### Data Visualization
- [Dark Mode Charts Best Practices (CleanChart)](https://www.cleanchart.app/blog/dark-mode-charts)
- [Implementing Dark Mode for Data Viz](https://ananyadeka.medium.com/implementing-dark-mode-for-data-visualizations-design-considerations-66cd1ff2ab67)
- [Colors in Data Vis Style Guides (Datawrapper)](https://www.datawrapper.de/blog/colors-for-data-vis-style-guides)
- [Color Palettes and Accessibility (Carbon Design)](https://medium.com/carbondesign/color-palettes-and-accessibility-features-for-data-visualization-7869f4874fca)
- [Dark Mode Color Palette (Zeplin)](https://blog.zeplin.io/dark-mode-color-palette/)
- [Stacked Bar Charts (Atlassian)](https://www.atlassian.com/data/charts/stacked-bar-chart-complete-guide)
- [Dashboard Design Patterns](https://dashboarddesignpatterns.github.io/)
- [Dashboard UX Patterns (Pencil & Paper)](https://www.pencilandpaper.io/articles/ux-pattern-analysis-data-dashboards)
- [Dark Mode UI Best Practices 2025 (Graphic Eagle)](https://www.graphiceagle.com/dark-mode-ui/)
- [Modern Dashboard Design Principles 2025](https://medium.com/@allclonescript/20-best-dashboard-ui-ux-design-principles-you-need-in-2025-30b661f2f795)

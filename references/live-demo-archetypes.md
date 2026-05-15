# Live Demo Archetypes

A "**fake live demo**" slide is a single-slide animation that visually walks the judge through how the user's product works — using fake-but-accurate data and choreographed motion. It's the alternative to embedding a recorded video, useful when:

- The product isn't built yet (or backend is flaky and could crash on stage)
- The recorded video is the backup, and the animation is the primary proof
- The user wants something more "designed" than a screen recording
- Slide judging is async — judges watch in browser, not on a stage

This doc covers the **six animation archetypes** Claude can build, the **three questions** to ask the user per archetype to fill it with their content, and the **building-block recipes** for the "custom" escape hatch.

For the *recorded-video* path, see `video-integration.md`. The two modes are usually **mutually exclusive on the same slide** — a hackathon slide is either an embedded video or a fake animation, not both. (Rare exception: animation as fallback behind a "show animation instead" toggle on the same slide; see "Both modes on one slide" at the bottom.)

---

## How this fits the workflow

The Phase 1 questionnaire includes **Q6**: *"Live demo plan? (a) embed your recorded video, (b) Claude builds a fake-data animation now, (c) both — animation as backup, (d) skip."*

If the user picks **(a)** or **(d)**, Claude does not touch this doc — Phase 3 just inserts a video-placeholder slide (or no demo slide at all).

If the user picks **(b)** or **(c)**, Phase 3 adds a step:

```
Phase 3 step 5b — Fake Live Demo Slide construction
  ↓
  i.   Recommend 2–3 archetypes from the 6 below, with one-line "why for your product"
  ↓
  ii.  User picks one archetype (or asks for a different one)
  ↓
  iii. Claude asks the 3 elicitation questions for that archetype
  ↓
  iv.  Claude auto-drafts the slide using the chosen style preset's CSS variables
  ↓
  v.   Slide is added to the deck at the natural "How it works / Demo" position
```

After Phase 3, Phase 5 iteration treats the live-demo slide like any other slide — see "Iterating on a fake demo slide" at the bottom of this doc.

---

## The 6 Archetypes

### 1. Split Narrative

**Layout**: Fixed two-column. Left = chat / terminal pane. Right = visualization that morphs in sync with the chat.

**Motion language**:
- Left pane streams **typewriter user input** → **typing dots** → **agent message** → **tool call log** lines, in sequence
- Right pane runs **node opacity/transform animations** keyed to the chat steps (`step 0 → 1 → 2 → ...`)
- A small **status bar** at the bottom of the right pane cycles tool / sponsor states (`idle → working → done`)
- A **final reveal card** with a checklist + "see next" CTA appears at the end

**When to recommend**: any product where the user-facing interaction is *"user says something → system does something visible"*. Specifically: AI agents, copilots, assistants, voice apps, refactor tools, auto-generators, handoff/orchestration layers, anything conversational.

**Why this is the strongest default**: it shows both *what the user did* and *what the system did*, simultaneously. It's the archetype that wins demos because the judge never has to pick which pane to look at — the synchronized motion does that work.

**3 elicitation questions**:
1. **Protagonist input**: "What's the one sentence the user says/types to kick this off?" (e.g., *"hand off the front-end to Sarah"*, *"summarize this PDF in three bullets"*)
2. **Visible system steps (3–5)**: "What does your product visibly do in response, in 3–5 steps? Use ~5-word names — these become the chat-side narration." (e.g., *scan repo*, *ask user*, *preview plan*, *apply patches*)
3. **Final punchline**: "When it's done, what one number/sentence should the judge remember?" (e.g., *0 secrets leaked · workspace ready*, *answer in 1.2s*)

---

### 2. Pipeline Walk

**Layout**: Horizontal track. 3–6 named **stage cards** in a row. A single **packet dot** travels left → right, crossing each stage. Each stage **highlights as the packet enters** and dims after it leaves.

**Motion language**:
- `@keyframes packetWalk` moves the packet across the row (100% loop)
- `@keyframes stageActive` cycles each stage's glow (timed via negative animation-delay so they fire in sequence)
- Bottom row carries a **tiny label per stage** showing what the data looks like at that point (e.g., `raw → tokens → vec → top-k → response`)
- Final stage's glow stays on; a small **"output card" pops out** below the last stage with the result

**When to recommend**: any product whose value is "**X transformed into Y through N steps**". Specifically: ETL pipelines, RAG systems, AI workflows, video processing, order/payment processing, multi-step agents, any "stages" architecture.

**3 elicitation questions**:
1. **Stage names**: "What are the 3–6 stages of your pipeline, in order? Short names work best (1–2 words each)." (e.g., *ingest, parse, embed, rank, serve*)
2. **What flows through them**: "What's the 'thing' that travels through the pipeline, and how does it look at each stage? Tiny labels — `raw → tokens → vec → top-k → response`."
3. **Output card content**: "When the packet exits the last stage, what shows up? A number? A short sentence? A small generated artifact?" (e.g., *p95 latency: 180ms*, *answer card with 3 citations*)

---

### 3. Before / After Morph

**Layout**: Fixed two-column. Left = "before" state (messy, red/amber, has problems). Right = "after" state (clean, green, has fixed things). **Items physically slide from left to right**, transforming as they move.

**Motion language**:
- Left items have `@keyframes morphSlide` that translates them rightward + scales/fades during the move
- Right column items appear via `@keyframes cleanGlow` (delayed ~50% into the cycle), fading in as left items reach them
- A small **✓ badge** blooms in the bottom-right of the "after" panel after everything has migrated
- Loop has a 1-second pause at the end before resetting, so the "after" state lingers

**When to recommend**: products whose pitch is fundamentally a *transformation*: **refactor**, **cleanup**, **migration**, **redaction / sanitization**, **optimization**, **before-AI vs. after-AI**, **legacy → modern**. If the user describes their product as "we make X better" or "we replace bad-X with good-X", this is the archetype.

**3 elicitation questions**:
1. **Three messy items (left)**: "What 3 specific things does your product clean up / fix / replace? Short, concrete strings — looks better than abstract labels." (e.g., *api_key=sk_…*, *db.pwd="123"*, *aws.key=…*)
2. **Three clean counterparts (right)**: "What does each one look like after your product processes it? Same 3 strings, but in their fixed form." (e.g., *env.API_KEY*, *env.DB_PWD*, *env.AWS*)
3. **Final state badge**: "What's the one-line success message for the right panel? Usually a checkmark + a short verb phrase." (e.g., *✓ 0 secrets in source*, *✓ migration complete*)

---

### 4. Dashboard Fill-In

**Layout**: Fixed grid (typically 2×2 or 3×2) of **dashboard tiles**. Each tile starts empty/skeletal, then "**fills in**" with content during the animation: a counter ticks up, bars rise from baseline, a sparkline draws itself, a status pill flips from gray to green.

**Motion language**:
- `@keyframes counterTick` cycles a tile's number through 4–5 values to fake the rollup (use CSS `content` with `steps()` timing for crisp ticking)
- `@keyframes barRise` grows bar heights from a baseline value with bottom-anchored `transform-origin`
- `@keyframes sparkPath` animates `stroke-dashoffset` on an SVG path so it draws itself left-to-right
- Tiles can be staggered with `animation-delay` so the dashboard "**fills row by row**" instead of all at once
- After ~3 seconds the dashboard is "fully populated"; hold for 1 second then loop

**When to recommend**: products that are themselves dashboards / monitoring / analytics, **OR** products whose value-prop is *"now you can see X you couldn't see before"*. Specifically: observability, AI-insights tools, BI products, financial dashboards, status pages.

**3 elicitation questions**:
1. **Tile types and counts**: "What 3–5 'metric tiles' represent the heart of your product? Each tile is one of: counter, bar chart, sparkline, status pill. (e.g., *active users · 147* counter, *latency p95* sparkline, *error rate* status pill)"
2. **Realistic numbers / labels**: "What numbers and units feel real for your product? Avoid round suspicious numbers — `147 users` reads truer than `1000 users`."
3. **Punchline tile**: "Of all the tiles, which one is the *hero* — the one a judge should see ticking up and think 'wow'? We'll give that one extra glow + a slightly slower roll-up so it lands."

---

### 5. Network Graph Grow

**Layout**: A central node sits in the middle. Lines radiate out to a layer of 3–6 child nodes. Lines from those children radiate out to grandchild nodes. The **whole graph grows outward in three timed waves**.

**Motion language**:
- Layer 1 (center): scale-up `@keyframes nodePop` 0–25% of cycle
- Layer 2 (children): scale-up + line-grow 25–45% of cycle
- Layer 3 (grandchildren): scale-up + line-grow 45–60% of cycle
- Lines use `stroke-dasharray` + `stroke-dashoffset` animation to "draw" themselves outward
- Holds the full graph for the last 40% of the cycle so the judge can read it

**When to recommend**: products whose value-prop involves a **network, hierarchy, or branching structure**: knowledge graphs, social networks, infection / virality models, multi-agent systems, dependency trees, mind maps, org charts, citation networks. Also good for "**X spreads to Y to Z**" narratives.

**3 elicitation questions**:
1. **Center node label**: "What sits at the center of your graph? Usually one short label — a user, a query, a seed, a root." (e.g., *user query*, *founding agent*, *patient zero*)
2. **Layer 2 categories (3–5)**: "What kinds of things branch out from the center? Short labels for each branch." (e.g., for a knowledge graph: *Topics*, *People*, *Papers*, *Concepts*; for an agent network: *researcher*, *writer*, *critic*)
3. **Grandchild examples**: "Give one tiny example label per layer-2 branch — these become the leaf nodes. (e.g., under *Papers*: 'Attention Is All You Need'; under *People*: 'Vaswani'.)"

---

### 6. Map Heatbloom

**Layout**: A stylized map (continents / city outlines, intentionally abstract). 3–6 **city heat-points** appear in sequence, each one **blooming** (radial gradient + central dot + city label) before settling into a held state.

**Motion language**:
- Each heat-point uses `@keyframes bloom` (scale 0 → 1.2 → 1.0, opacity 0 → 0.8 → 0.9)
- Stagger them with `animation-delay` so cities light up one after another
- Optional: faint dashed lines connecting cities, animated with `stroke-dashoffset` to suggest flow / coverage
- Hold final state showing all cities lit for the last 30% of the cycle

**When to recommend**: products with a **geographic / logistics / supply-chain** dimension, OR products whose narrative includes "**global reach**" or "**city-by-city rollout**". Also good for delivery, ride-sharing, location intelligence, real-estate, travel.

**3 elicitation questions**:
1. **Cities (3–6)**: "Which 3–6 cities anchor your product story? Real cities work better than fictional ones — judges have spatial intuitions about real places."
2. **Per-city label / metric**: "For each city, what's the one tiny label that should appear next to it when it lights up? (e.g., *SF · 1.2k users*, *NYC · launching Q2*, *Tokyo · partner: SoftBank*)"
3. **Sequence meaning**: "What does the order of bloom mean — chronological rollout? rank by users? Important — it shapes how the bloom timing reads."

---

## Style preset coupling

Every fake demo slide must visually match the deck's chosen style preset. The archetype is **structural**; the styling is **inherited from the preset**.

When generating the slide HTML:

1. **Reuse the deck's `:root` CSS variables** — the live-demo slide must consume the same `--font-display`, `--font-body`, `--font-mono` (if defined), and core color variables as the rest of the deck. Never re-declare them inside the demo slide.

2. **Per-archetype palette inheritance**:

| Preset | Split Narrative | Pipeline Walk | Before/After | Dashboard Fill | Network Graph | Map Heatbloom |
|---|---|---|---|---|---|---|
| **Warm Editorial** | terminal pane → ivory background, dark warm-text; agent badge → terracotta | track → cream rule line, packet → terracotta, stage cards → bone with dotted ochre border | left → faded terracotta items, right → muted sage | tiles → ivory cards w/ honey accents, sparkline → rust | nodes → terracotta + sage layers, lines → thin ochre | map → off-white, blooms → terracotta + ochre, dotted-line lines |
| **Cyber Terminal** | terminal pane → near-black, mono everywhere, dashed neon; agent badge → primary neon | track → grid bg, packet → neon dot w/ glow, stages → dark cards w/ neon border | left → red neon items, right → green neon items | tiles → black w/ neon counters, sparkline → neon glow path | nodes → neon dots, lines → dashed flowing neon | map → near-black w/ faint grid, blooms → primary neon + secondary neon |
| **Citrus Punch** | left pane → off-white, bold sans; agent badge → primary citrus color | track → punchy primary line, packet → contrast color, stages → pill-shaped chips | left → bold red chips, right → bold green chips with thick borders | tiles → high-contrast cards, big bold numbers in primary citrus | nodes → bold colored chips, lines → thick solid lines | map → soft-white, blooms → punchy primary + secondary |
| **Electric Dusk** | terminal pane → deep navy, refined text; subtle gradient mesh; agent badge → primary elegant accent | track → fine-line track, packet → soft-glow accent, stages → fine-bordered cards on gradient bg | left → muted dim items, right → ice-blue/violet items, soft-glow ✓ | tiles → fine-border dark cards, soft gradient mesh on sparkline tile | nodes → soft-glow accent, lines → fine semi-transparent | map → navy w/ gradient mesh, blooms → elegant accent + secondary |
| **Pastel Chapters** | full split-panel — left pastel A is the chat pane, right pastel B is the visualization; muted accent badge | track horizontally laid across the duotone, packet → muted accent, stages → floating white cards w/ soft shadow | uses the duotone naturally — left panel is "before" pastel, right panel is "after" pastel | tiles → floating white cards on pastel A, accents from candy-pill palette | nodes → candy pills, lines → soft pastel-tone | full duotone bg, blooms → muted accent + 2 candy-pill colors |

3. **Typography**:
   - Headers / labels in the demo → `var(--font-display)` (matches the deck)
   - Streaming chat / terminal text → `var(--font-mono)` if the preset defines it (Cyber Terminal); otherwise `var(--font-body)`
   - Numbers in dashboard tiles → display font, large weight, with the preset's standard hero-number treatment

4. **Density**:
   - Cyber Terminal / Electric Dusk → can use higher density (faint grid bg, more tool-log lines, more status pills)
   - Warm Editorial / Pastel Chapters → fewer chrome elements, more whitespace, simpler chat-side log
   - Citrus Punch → bold and bright but not crowded

---

## Animation building blocks (the "custom" recipe book)

If the user rejects all 6 archetypes ("none of these fit my product"), Claude can compose a custom demo from the building blocks below. Each is a small, self-contained CSS/JS pattern that any archetype already uses internally — exposing them lets Claude recombine.

| Block | What it does | Where it's used |
|---|---|---|
| **Typewriter input** | Animates a string of text into an input field with a blinking cursor | Split Narrative (chat) |
| **Streaming agent reply** | Three-dot typing indicator → message bubble fades in line by line | Split Narrative |
| **Tool log line** | Tiny mono line with an icon that fades in below the chat ("`tool · indexed 85 files`") | Split Narrative |
| **Step state machine** | Numbered step counter (`step 0 → N`) that drives all other animations via JS `setTimeout` chains | Split Narrative, Pipeline Walk |
| **Node spawn** | Element scales `0.6 → 1.0` and fades `0 → 1` with a soft glow box-shadow | Network Graph, Split Narrative ("contractor agent" appearing) |
| **Node split** | One element shrinks + fades while two new elements grow into its old position, offset left/right | Split Narrative ("monorepo splits to fe/be") |
| **SVG flowing line** | `stroke-dasharray` + animated `stroke-dashoffset` to suggest data flow along a connection | Split Narrative, Network Graph |
| **Packet walk** | A small dot translates along a horizontal track via `@keyframes` keyed by `left:` percentages | Pipeline Walk |
| **Stage highlight cycle** | Multiple elements share an `@keyframes` but use staggered negative delays so they peak in sequence | Pipeline Walk |
| **Side-to-side morph** | Element translates X axis + scales/fades during the move; appears to "land" in a new column | Before/After |
| **Counter ticker** | CSS `content` cycled through values via `@keyframes` + `steps()` timing — looks crisp like an odometer | Dashboard Fill |
| **Bar grow** | `height: 4px → final%` with bottom-anchored `transform-origin` and ease-out curve | Dashboard Fill |
| **Sparkline draw** | SVG path with `stroke-dasharray` set to total path length, `stroke-dashoffset` animated to 0 | Dashboard Fill |
| **Status pill cycle** | Tiny pill that rotates through 3 states with color + label changes (`idle → working → done`) | All archetypes (footer status bar) |
| **Reveal badge** | Card scales `0.9 → 1.0` + fades in with a glow, holding center-stage; usually contains a checklist | All archetypes (final state) |
| **Heatbloom dot** | Radial-gradient circle scales out + fades to a held state; pairs with a small text label | Map Heatbloom |
| **Dashed line route** | `stroke-dasharray "4 3"` with infinite `stroke-dashoffset` animation — looks like flowing pipe | Split Narrative, Network Graph |

A custom demo is typically **3–5 building blocks composed**. Example: an AI chatbot product might use *typewriter input + streaming agent reply + counter ticker + reveal badge* — that's not exactly Split Narrative (no right-pane visualization) but it's clearly Split Narrative-shaped. Don't be precious about archetype boundaries; the building blocks are the real unit of composition.

---

## Auto-draft → refine flow

After the user picks an archetype and answers the 3 elicitation questions, Claude auto-drafts the slide directly. **Do not show the user a "draft preview" before inserting** — that's a wasted round-trip. Instead:

1. **Generate** the live-demo slide HTML inline in the deck, slotted at the natural "How it works / Demo" position (typically slide 5 or 6 of 12)
2. **Open the deck in the browser** and tell the user: "Live demo slide is in. Open the deck and watch slide N — let me know if the stages, labels, or punchline need adjustment."
3. **Iterate inline** in Phase 5 — the user might say "stage 3 should be 'embed' not 'vectorize'" or "make the final number bigger". Apply edits directly to the slide HTML.

The whole flow from "user picks archetype" to "demo plays in browser" should be **one Claude turn**. Don't bounce back and forth confirming details that the 3 elicitation questions already covered.

---

## Iterating on a fake demo slide (Phase 5 patterns)

| User says | What to change |
|---|---|
| "The animation goes too fast / too slow" | Adjust the master `@keyframes` `animation-duration` (default ~4s for a thumbnail-style slide; ~15–30s for the deck slide). Slow side: bump to 6–8s. Fast side: drop to 3s. |
| "It only plays once — can it loop?" | Add `animation-iteration-count: infinite` to the master keyframes. Most archetype templates already loop. |
| "Stage X label is wrong / I want a different number" | Direct text edit; no animation change needed. |
| "I want it to start when the slide is visible, not on load" | Wrap the animation triggers in a `slide-active` CSS class or a small `IntersectionObserver` snippet. |
| "Add a sponsor logo somewhere" | Add a small `<img>` to the bottom status bar, sized ~20px tall, opacity 0.7. Don't disrupt the main animation. |
| "Make it pause when I hover" | Add `:hover { animation-play-state: paused; }` to the master keyframes elements. |
| "Can the user click 'replay'?" | Add a small replay button that re-applies the animation classes via JS (already in the Split Narrative template). |

---

## Both modes on one slide (rare)

If the user picked option (c) in Phase 1 ("animation as backup behind a 'show animation' toggle on the same slide"), generate the slide with:

- Default visible: the `<video>` placeholder (or actual video if user has it)
- A small mono-styled toggle in the top-right: `[ animation ↺ ]`
- Clicking the toggle hides the video and reveals the inline animated demo

This is a hedge for live demos where the recorded video might fail to load (corrupt asset, network issue on stage, autoplay blocked). It costs ~30% extra HTML but removes the catastrophe scenario.

Don't volunteer this option in Phase 1 — let the user ask for it explicitly. It's overkill for most decks.

---

## Anti-patterns

- **Don't generate a fake demo slide if the user picked option (a)** in Phase 1. They have a video; respect it.
- **Don't use generic animation easings** (`linear`, `ease`). Use `cubic-bezier(.2,.8,.2,1)` or `ease-out` for "things landing"; `linear` is acceptable only for infinite loops where motion shouldn't accent.
- **Don't dump all 6 archetypes on the user**. Recommend 2–3 with one-line "why for your product"; let them pick.
- **Don't forget to inherit the deck's CSS variables**. Re-declaring fonts/colors inside the demo slide is the #1 way to make the slide visually clash with the rest of the deck.
- **Don't make the animation longer than 30 seconds**. Judges are scrolling; if the animation takes too long to land its punchline, they've already moved on. 15–25 seconds + reveal badge is the sweet spot.
- **Don't forget the final reveal**. Every archetype needs a clear "this is the moment that matters" beat at the end — a glow card, a checklist, a number. Without it, the loop just plays forever and the judge never knows what to take away.
- **Don't make the demo interactive in a way that requires clicking**. The slide should be passive viewing — animations auto-play and loop. Optional `replay` / `pause-on-hover` are fine; mandatory clicks are not.

---

## Quick decision tree (for Claude when recommending archetypes)

```
Is the product a conversational agent / copilot / assistant?
  → Recommend Split Narrative + (Pipeline Walk OR Before/After, depending on what it does)

Is the product a multi-stage data transformer (RAG, ETL, pipeline)?
  → Recommend Pipeline Walk + Dashboard Fill (if there are metrics to show)

Is the product about cleanup / refactor / migration / sanitization?
  → Recommend Before/After Morph + (Split Narrative if there's a chat interface)

Is the product analytics / monitoring / insights?
  → Recommend Dashboard Fill + (Pipeline Walk if there's a clear input pipeline)

Is the product a network / graph / multi-agent / social product?
  → Recommend Network Graph Grow + (Split Narrative if there's a user-facing chat)

Does the product have a strong geographic / logistics dimension?
  → Recommend Map Heatbloom + Dashboard Fill (for the metrics)

None of the above feel right?
  → Ask: "What's the one moment in your product where someone says 'oh, that's cool'?"
    Then map that moment to the closest building blocks and offer a custom composition.
```

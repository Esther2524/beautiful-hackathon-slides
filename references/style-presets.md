# 5 Style Presets (Aesthetic Archetypes)

These are **aesthetic directions**, not fixed color schemes. Each direction has:
- A characteristic typography pairing
- A tone/mood
- Guidance for picking colors (but **not hardcoded hex values**)

When generating previews, adapt each preset's color palette to:
1. The user's hackathon theme or existing brand, OR
2. A beautiful, theme-agnostic palette that fits the aesthetic

Do NOT default to the same exact colors every time. Be creative within the archetype.

---

## Preset 1: Warm Editorial

**Aesthetic direction**: Light, serif-driven, magazine-like, refined. Conveys thoughtfulness and craft. Feels like *The New Yorker* redesigned as a product deck.

**Typography** (the signature is the characterful serif — must keep a real serif, not sans):

```css
@import url('https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,300;0,9..144,400;0,9..144,600;0,9..144,800;1,9..144,300;1,9..144,400&family=Outfit:wght@300;400;500;600;700&display=swap');

:root {
  --font-display: 'Fraunces', Georgia, serif;
  --font-body: 'Outfit', system-ui, sans-serif;
}
```

Fraunces has distinctive optical sizing and italic variants — essential for this preset.

**Color guidance**:
- Base: warm off-white (cream, ivory, bone, beige)
- Primary accent: one warm pigment that fits the theme (honey, terracotta, ochre, rust, olive, sage, muted coral)
- Secondary accents: 1-2 muted complementary colors for section labels or callouts
- Dark text: almost black, warm-toned (never pure #000)

**When to choose it**:
- Products with emotional / human-centered themes (wellness, communication, education, creativity)
- Teams that want to feel "considered" rather than "move fast and break things"
- Non-technical audiences or mixed audiences

**What makes it distinctive**: Italic display serif for key words. Generous whitespace. Thin colored lines instead of heavy boxes. Section labels in small caps with letter-spacing.

**Avoid**: Bright saturated colors, neon effects, pure white backgrounds, Inter-as-display-font.

---

## Preset 2: Cyber Terminal

**Aesthetic direction**: Dark, mono-driven, hacker-aesthetic, unapologetically technical. Feels like a well-designed developer tool or CLI dashboard. Not edgy-for-its-own-sake — purposeful darkness with precision typography.

**Typography** (the signature is **Syne's distinctive geometric shapes** + **mono accents** everywhere — data, quotes, callouts):

```css
@import url('https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;500;700&family=DM+Sans:wght@300;400;500;700&display=swap');

:root {
  --font-display: 'Syne', system-ui, sans-serif;
  --font-body: 'DM Sans', system-ui, sans-serif;
  --font-mono: 'JetBrains Mono', 'Courier New', monospace;
}
```

Syne is chunky and architectural — nothing like other sans-serifs in this skill. JetBrains Mono is iconic for terminal aesthetics.

**Color guidance**:
- Base: near-black, slightly warm or cool (off-black with a 2-5% color shift, not pure #000)
- Primary accent: one saturated neon that fits the theme (electric blue, amber, lime, magenta, cyan)
- Secondary: subtle grid lines, muted grays for secondary text
- Text: warm off-white, never pure white

**When to choose it**:
- DevTools, infrastructure, AI/ML products, security, fintech
- Technical-heavy audiences
- Products that want to feel "hardcore" without being corporate

**What makes it distinctive**: Faint grid backgrounds. Terminal-style `>` prompts for key quotes. Monospace used for data/values. Subtle glow effects on accent elements. Sharp rectangular shapes over soft rounded ones.

**Avoid**: Pastel colors, ornate serifs, purple-on-black clichés, Matrix-style green text.

---

## Preset 3: Citrus Punch

**Aesthetic direction**: Light, bold-sans-driven, punchy, energetic. Feels like a confident startup that's excited about what it's building. Bright without being childish.

**Typography** (the signature is **Bricolage Grotesque's expressive variable widths** — its optical-size axis makes big headlines feel dynamic):

```css
@import url('https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@12..96,400;12..96,500;12..96,600;12..96,700;12..96,800&family=Plus+Jakarta+Sans:wght@300;400;500;600;700&display=swap');

:root {
  --font-display: 'Bricolage Grotesque', system-ui, sans-serif;
  --font-body: 'Plus Jakarta Sans', system-ui, sans-serif;
}
```

Bricolage has characterful wide headlines that feel energetic. Plus Jakarta Sans pairs cleanly without competing.

**Color guidance**:
- Base: soft off-white or subtle warm tint (not pure white)
- Primary accent: one energetic color that fits the theme (citrus orange, bright yellow, hot pink, electric teal, vibrant green)
- Secondary: 2-3 supporting colors for categorization (used sparingly for chips/tags)
- Dark text: strong contrast, near-black

**When to choose it**:
- B2C products, social products, creative tools, media, gaming
- Younger audiences or mainstream appeal
- Products with a "fun but professional" personality

**What makes it distinctive**: Large bold headlines. Color-coded category chips (pill-shaped). Colored underline/highlight effects behind key words. Strong geometric shapes. High information density in cards.

**Avoid**: Gradient overload, emojis everywhere, cartoon-y illustrations, overly saturated backgrounds.

---

## Preset 4: Electric Dusk

**Aesthetic direction**: Dark, clean-sans-driven, sleek, professional. Feels premium and considered — like an enterprise SaaS that hired a designer who actually knew what they were doing.

**Typography** (the signature is **Manrope's refined neutrality with a hint of warmth** — single family, weight variation for hierarchy):

```css
@import url('https://fonts.googleapis.com/css2?family=Manrope:wght@300;400;500;600;700;800&display=swap');

:root {
  --font-display: 'Manrope', system-ui, sans-serif;
  --font-body: 'Manrope', system-ui, sans-serif;
}
```

Manrope is tighter and more refined than the other sans choices — feels premium without being cold. Display uses weight 700-800, body uses 400.

**Color guidance**:
- Base: deep navy, charcoal, or rich dark tone (not black — slight color temperature)
- Primary accent: one elegant bright color (electric violet, ice blue, warm amber, emerald)
- Secondary: soft muted tones for supporting elements, gradients for atmosphere
- Text: soft warm white with hierarchy tiers (100%, 70%, 50% opacity)

**When to choose it**:
- B2B enterprise tools, fintech, data platforms, infrastructure
- Judges who are executives or senior engineers
- Products that need to project "seriousness" but with design quality

**What makes it distinctive**: Subtle gradient meshes in backgrounds. Fine-line borders instead of heavy boxes. Thoughtful hierarchy with opacity. Mathematical / architectural compositions. Never feels "plain dark" — always atmospheric.

**Avoid**: Neon glow effects, mono fonts (too techy), bright saturated accents, sci-fi aesthetics.

---

## Preset 5: Pastel Chapters

**Aesthetic direction**: Light, soft-duotone, split-panel, storytelling-focused. Every slide feels like a two-page spread in a design magazine or illustrated book — one pastel color on the left, a different pastel on the right, with each slide reading as its own "chapter."

**Typography** (the signature is **Nunito's rounded, friendly character** — single family, weight variation, storybook-like warmth):

```css
@import url('https://fonts.googleapis.com/css2?family=Nunito:wght@400;500;600;700;800;900&display=swap');

:root {
  --font-display: 'Nunito', system-ui, sans-serif;
  --font-body: 'Nunito', system-ui, sans-serif;
}
```

Nunito's rounded terminals make it feel human and approachable — visibly different from every other preset's fonts. Display uses weight 800-900, body uses weight 400.

**Color guidance**:
- Pick **two complementary pastel background colors** that work together (e.g., peach + lavender, mint + blush, butter + sky, sage + salmon, lilac + cream)
- These two backgrounds **alternate per slide**, OR split on each slide (left half one color, right half the other)
- One **muted accent color** serves as the "brand" tone — used for key words in headings, section labels, and primary highlights. Pick something grounded: muted purple, terracotta, deep teal, warm coral, olive, dusty rose
- A **palette of 4-6 candy-colored "pill" tags** for categorization (mint, yellow, pink, blue, orange, lilac) — used to label sections, timelines, or categories. They're playful but controlled
- Text: warm dark, never pure black

**When to choose it**:
- Education, wellness, creativity tools, consumer products
- Projects with strong character/mascot narratives or day-in-the-life stories
- Pitches that emphasize empathy, storytelling, or emotional resonance
- Teams that want to feel "designed" and "considered" without being too corporate

**What makes it distinctive**:
- **Split-panel layout** on most slides — the two pastel backgrounds divide each slide into left and right "pages"
- Optional subtle grid overlay on one of the panels for depth (e.g., 40px × 40px lines at very low opacity)
- **Floating white cards** with soft shadows sit on the pastel panels — containing content like quotes, metrics, or callouts
- **Slide numbers** displayed in the corner (e.g., `01`, `02`) in the accent color — reinforces the "chapter" feel
- **Bold headings where one word uses the accent color** (e.g., "Product**Name**" or "The **Solution**")
- **Color-coded pill badges** for inline categorization — a signature element

**Avoid**:
- Saccharine color combinations (baby pink + baby blue feels juvenile)
- Mixing serif + sans + mono (this style commits to one sans family)
- Comic sans or overly rounded display fonts
- Too-high saturation pastels (the colors should feel muted/dusty, not neon)
- Hand-drawn illustrations (clean vector or emoji characters fit better)

**Flexibility note**: The signature is the *split-panel + duotone + single-sans* combination. The specific colors, accent hue, and font choice should adapt to the user's project theme. Don't default to peach+lavender+purple every time — that's just one example. A wellness app might use mint+cream+sage. A food startup might use butter+blush+terracotta.

---

## Preset 6: Crafted Tactile

**Aesthetic direction**: Warm, paper-textured, handmade. Looks like notes pinned to a corkboard — scotch tape, post-its at slight angles, soft drop shadows. Feels considered without feeling precious.

**Typography** (the signature is **handwritten Caveat overlaid on geometric Space Grotesk** — paper note + machine type):

```css
@import url('https://fonts.googleapis.com/css2?family=Caveat:wght@500;600;700&family=Space+Grotesk:wght@400;500;600;700&family=DM+Mono:wght@400;500&display=swap');

:root {
  --font-display: 'Space Grotesk', system-ui, sans-serif;
  --font-body: 'Space Grotesk', system-ui, sans-serif;
  --font-hand: 'Caveat', cursive;
  --font-mono: 'DM Mono', ui-monospace, monospace;
}
```

Caveat handles the "scribble" / margin-note moments. DM Mono labels stamps and tape annotations.

**Color guidance**:
- Base: warm paper (cream, ecru, manila — not pure white)
- Primary accent: a single grounded craft color (sage green, terracotta, deep ochre, navy, oxblood)
- Secondary: pin red, post-it yellow, or scotch-tape amber as decorative touches (used sparingly)
- Text: warm dark, never pure black

**When to choose it**:
- Hardware products, physical-product startups, handcraft / artisan tools
- Productivity tools that emphasize "human" over "automated"
- Indie products that want to feel warm and made-by-people

**What makes it distinctive**: Post-it notes at 3-5° rotation. Scotch-tape overlays on photos. Handwritten Caveat overlaid on geometric type. Pin / push-pin decorative elements in corners. Soft layered drop shadows on every element. Background grain or paper texture.

**Avoid**: Pure white backgrounds (kills the paper feel), neon colors, more than 8° rotation (looks chaotic), Comic Sans (use Caveat), too many post-its (more than 2 looks cluttered).

**Sample reference**: `assets/preset-samples/crafted-tactile.html`

---

## Preset 7: Studio Electric

**Aesthetic direction**: Dark, design-led, electric. Modular sharp blocks of saturated color (electric magenta, cobalt, lime) on near-black, with massive Barlow display words. Looks like a contemporary design studio's portfolio — bold without being chaotic, technical without being hacker-y.

**Typography** (the signature is **Barlow Black at extreme weight 900** + IBM Plex Mono micro-labels — gallery-poster + design-system documentation):

```css
@import url('https://fonts.googleapis.com/css2?family=Barlow:wght@400;500;700;800;900&family=IBM+Plex+Mono:wght@300;400;500&display=swap');

:root {
  --font-display: 'Barlow', system-ui, sans-serif;
  --font-body: 'Barlow', system-ui, sans-serif;
  --font-mono: 'IBM Plex Mono', ui-monospace, monospace;
}
```

Display uses weight 900 (Barlow Black) for hero text. Body uses 400-500. Mono for labels, dates, and metadata only.

**Color guidance**:
- Base: deep ink near-black (slight color temperature shift, never pure #000)
- Primary accent: ONE saturated electric color (magenta, cobalt blue, lime, hot orange)
- Secondary: a contrasting electric used sparingly for callouts (e.g., magenta primary + cobalt secondary)
- Paper-tone text: warm off-white for body, never pure white

**When to choose it**:
- Design tools, creative AI products, media platforms, generative-art tools
- Products that want to project "we have taste" without being precious
- Hackathon decks for design-heavy projects

**What makes it distinctive**: Modular color blocks (one large saturated panel + one off-axis circle behind text). Barlow at extreme weight forms the hero composition. Sharp 0-radius geometry everywhere. IBM Plex Mono for tiny labels. Page-corner indicators with single-pixel dots.

**Avoid**: Curved / organic shapes (kills the studio feel), pastel colors (too soft), more than 2 saturated electric colors (gets noisy), thin display weights (Barlow needs 800+ to land).

**Sample reference**: `assets/preset-samples/studio-electric.html`

---

## Preset 8: Moody Nocturnal

**Aesthetic direction**: Black-background, hot-pink italic display, intimate and sultry. Late-night work, after-dark feel. The opposite of corporate dark mode — this is "expensive bar at 2am", not "Slack dark theme".

**Typography** (the signature is **DM Serif Display italic in hot pink** + Inter body in soft cream + JetBrains Mono small caps for labels):

```css
@import url('https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=Inter:wght@300;400;500;600&family=JetBrains+Mono:wght@400;500&display=swap');

:root {
  --font-display: 'DM Serif Display', Georgia, serif;
  --font-body: 'Inter', system-ui, sans-serif;
  --font-mono: 'JetBrains Mono', ui-monospace, monospace;
}
```

DM Serif Display italicizes for the key-word emphasis (the "feature" of the typography). Inter weight 300 for body to feel airy.

**Color guidance**:
- Base: pure black or near-black (`#060507` to `#0F0D11`)
- Primary accent: ONE hot saturated pink (or substitute: hot magenta, electric coral, neon orange) — used heavily on key words, hairlines, and labels
- Secondary: soft cream (`#F5EDF1` range) for body text
- Subtle pink hatching / diagonal-line texture in background for atmosphere (not noise)

**When to choose it**:
- Creative tools (music, writing, late-night productivity)
- Products that have an emotional / intimate / personal angle
- "Bar at 2am" energy products — dating, journaling, after-dark companions

**What makes it distinctive**: Vignette gradient at slide edges. Pink hairline `border` lines instead of solid borders. Italic display words glow softly with `text-shadow`. JetBrains Mono labels in pink, in extreme letter-spacing (.28em+), small. Hatching/scanline pattern in background for atmosphere.

**Avoid**: Bright pure white text (use soft cream), corporate dark (this isn't enterprise dark mode), more than one accent color (the single pink is the feature), neon glow on everything (only on the italic display words).

**Sample reference**: `assets/preset-samples/moody-nocturnal.html`

---

## Preset 9: Kawaii Retro

**Aesthetic direction**: Pastel pink + cyan + butter-yellow color blocks, win95 window chrome, pixel fonts, optional Japanese kana flourish. 90s-internet meets kawaii consumer product. Joyful, toy-like, but not childish — "small thing built with care".

**Typography** (the signature is **Big Shoulders Display chunky** + **Press Start 2P pixel font** for stickers/labels):

```css
@import url('https://fonts.googleapis.com/css2?family=Big+Shoulders+Display:wght@500;700;800;900&family=Albert+Sans:wght@400;500;600;700&family=Press+Start+2P&family=Noto+Sans+JP:wght@500;700&display=swap');

:root {
  --font-display: 'Big Shoulders Display', system-ui, sans-serif;
  --font-body: 'Albert Sans', system-ui, sans-serif;
  --font-pixel: 'Press Start 2P', cursive;
  --font-jp: 'Noto Sans JP', sans-serif;
}
```

Big Shoulders Display weight 900 for hero text (with a 4px 0px cyan drop shadow for the retro pop). Press Start 2P only for tiny labels / window chrome / stickers (it's hard to read at large sizes). Noto Sans JP optional for kana decoration.

**Color guidance**:
- Base: pastel pink + cyan + butter-yellow as **diagonal color blocks** (`linear-gradient(135deg, ...)`)
- Primary accent: hot pink (`--pink-deep`) for stickers and main action
- Window chrome: classic win95 grey + navy title bar (intentional retro)
- All hard borders are 2-3px solid black with offset drop shadows

**When to choose it**:
- Gaming products, AI companions, consumer playful tools
- Products with a strong "small and joyful" personality
- Products targeting Gen Z / consumer / fan communities
- Anything where the user's reaction should be "this is adorable"

**What makes it distinctive**: Old-school window chrome with `_ □ ×` controls. Hot-pink stickers at -6° rotation with offset shadows. Diagonal pastel color blocks (3-color gradient). 2-3px solid black borders everywhere. Optional kana subtitle (`トキメキ // tokimeki`) above the headline. Subtle scanline overlay for retro CRT feel.

**Avoid**: Pure white / pure black (use pastel paper bg), more than 4 colors, cute-overload (no kawaii face emojis everywhere — keep it controlled), modern UI components (defeats the retro feel).

**Sample reference**: `assets/preset-samples/kawaii-retro.html`

---

## Preset 10: Friendly Casual

**Aesthetic direction**: Warm cream paper, indie-not-corporate, conversational tone. Fraunces italic display paired with Bricolage Grotesque body, soft hand-drawn squiggle accents, small character avatars. Feels like a small studio's product launch — warm, considered, not trying too hard.

**Typography** (the signature is **Fraunces italic display + Bricolage Grotesque body** — magazine-elegant pairs with energetic sans):

```css
@import url('https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@12..96,400;12..96,500;12..96,600;12..96,700;12..96,800&family=Fraunces:ital,opsz,wght@0,9..144,400;0,9..144,600;0,9..144,700;1,9..144,400;1,9..144,500;1,9..144,600&display=swap');

:root {
  --font-display: 'Fraunces', Georgia, serif;
  --font-body: 'Bricolage Grotesque', system-ui, sans-serif;
}
```

Display uses Fraunces with italic for warmth. Body uses Bricolage for energy without sterility.

**Color guidance**:
- Base: warm butter / cream
- Primary accent: terracotta, mustard, sage, or rose — pick one warm pigment grounded in the project
- Secondary: 2-3 supporting warm tones used sparingly for chips/avatars
- Text: warm dark, never pure black

**When to choose it**:
- Community tools, hospitality, restaurants, food
- Indie / small-team products that emphasize "small and intentional"
- Wellness, social tools, anything with a "human + warm" angle

**What makes it distinctive**: Hand-drawn SVG squiggle under the headline (drawn left-to-right). Small character avatars in colored circles (emoji or face icons). Greeting word ("hey there", "welcome") in italic Fraunces above the headline. Soft pill chips with dashed/solid borders. Conversational copy throughout.

**Avoid**: Pure white background (too sterile — use warm cream), formal capitalization, more than one greeting per slide, photos of people (use emoji avatars instead — keeps it feeling indie not corporate).

**Sample reference**: `assets/preset-samples/friendly-casual.html`

---

## Preset 11: Lo-Fi Underground

**Aesthetic direction**: Photocopy off-white paper with grain/noise overlay, Bebas Neue oversized condensed display, handwritten Caveat margin scribbles with crossed-out text, single acid color (acid yellow / red) as highlight, cut-and-paste tilted blocks. Underground zine / DIY culture / scrappy-by-design.

**Typography** (the signature is **Bebas Neue oversized condensed** + **Caveat handwritten scribbles** + Space Grotesk body):

```css
@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Caveat:wght@400;600;700&family=Space+Grotesk:wght@300;400;500;600;700&display=swap');

:root {
  --font-display: 'Bebas Neue', sans-serif;
  --font-body: 'Space Grotesk', system-ui, sans-serif;
  --font-hand: 'Caveat', cursive;
}
```

Bebas Neue for the giant headlines (it's condensed, so even at 200px it fits 3 lines). Caveat for margin annotations and scribbled corrections.

**Color guidance**:
- Base: photocopy off-white (warm cream with subtle noise / grain overlay via SVG turbulence filter)
- Primary accent: ONE acid color (acid yellow `#F0FF00`, acid red, or neon green) — used for highlight blocks and crossed-out strikethroughs
- Text: warm near-black
- All decoration in black ink + acid color, NO grayscale

**When to choose it**:
- Indie / DIY products, music tools, art tools
- Anything with "scrappy / underground / community" vibe
- Hackathon projects that want to feel "made in 36 hours and proud of it"

**What makes it distinctive**: Bebas Neue display at clamp(120px, 15vw, 220px). Words highlighted with acid-yellow background block + offset black box-shadow. Strikethrough lines hand-drawn at -1° angle. Caveat scribbles in margins (rotated -8° to +8°). Pasted-block content area (rotated +3°) with offset acid-color shadow. SVG noise/grain texture overlay on the whole page.

**Avoid**: Clean / centered layouts (this is intentionally messy), corporate copy, more than one acid color, photos (use sparingly + with a halftone filter if at all).

**Sample reference**: `assets/preset-samples/lo-fi-underground.html`

---

## Preset 12: Bold Poster

**Aesthetic direction**: Cream paper, Shrikhand or Barlow Black mega-headline in oxblood/cobalt, Libre Baskerville italic for pull quotes, manifesto-poster energy. Looks like an editorial cover — single dramatic gesture per slide.

**Typography** (the signature is **Shrikhand display at extreme size** + **Libre Baskerville italic** body for literary contrast):

```css
@import url('https://fonts.googleapis.com/css2?family=Shrikhand&family=Libre+Baskerville:ital,wght@0,400;0,700;1,400&family=Space+Grotesk:wght@400;500;600;700&display=swap');

:root {
  --font-display: 'Shrikhand', serif;
  --font-body: 'Libre Baskerville', Georgia, serif;
  --font-mono: 'Space Grotesk', system-ui, sans-serif;
}
```

Shrikhand is a chubby slab — only one weight available, used at clamp(80px, 11.4vw, 168px) for the hero. Libre Baskerville italic for any pull-quotes or reflective copy.

**Color guidance**:
- Base: warm cream
- Primary accent: deep editorial color (oxblood, cobalt, forest, deep gold) — used for the hero word
- Secondary: a contrasting deep color for the second hero line ("Stop hedging." in oxblood / "Make the loud bet." in cobalt)
- Tertiary: gold or terracotta for tiny labels

**When to choose it**:
- Manifesto-style pitches (when there's ONE big idea to ship)
- Editorial / publication products
- Hackathon decks where the team has a strong, single-axis thesis

**What makes it distinctive**: Hero takes 60% of the slide. Pull-quote sidebar with 4px ink border-left. 3px solid ink rules at top and bottom of slide. Stamp-style bordered labels. Vol. number / publication name in narrow caps. Mono small-caps metadata.

**Avoid**: More than 2 sentences in the hero, multiple visual emphases competing (this preset is about ONE big move per slide), pastel colors, modern sans-serif for the hero (Shrikhand is the feature).

**Sample reference**: `assets/preset-samples/bold-poster.html`

---

## Preset 13: Architectural Grid

**Aesthetic direction**: Warm off-white paper with explicit visible 8-column modular grid, Newsreader serif italic for display words, deep cobalt blue accent, DM Mono for index labels and page numbers. Pentagram-design-studio energy: refined + structured + visually dense without being cluttered.

**Typography** (the signature is **Newsreader italic display** + **Hanken Grotesk body** + **DM Mono index labels** — three-font system organized like a field guide):

```css
@import url('https://fonts.googleapis.com/css2?family=Newsreader:ital,wght@0,400;0,500;1,300;1,400;1,500&family=Hanken+Grotesk:wght@400;500;600;700&family=DM+Mono:wght@400;500&display=swap');

:root {
  --font-display: 'Newsreader', Georgia, serif;
  --font-body: 'Hanken Grotesk', system-ui, sans-serif;
  --font-mono: 'DM Mono', ui-monospace, monospace;
}
```

Newsreader italics for the display "feature" words. Hanken Grotesk for body and side columns. DM Mono ONLY for index labels, section markers, page numbers.

**Color guidance**:
- Base: warm off-white (slightly warmer than pure cream)
- Primary accent: deep cobalt blue used only on chapter marks, italic display words, and index numbers
- Secondary: warm dark text body
- Faint vertical grid lines (rgba(20,20,14,.15)) showing the 8-column structure

**When to choose it**:
- Research tools, knowledge management, design-doc / spec tools
- AI for research or science
- Products with a "considered methodology" angle
- Hackathon decks that want to feel like a published field guide

**What makes it distinctive**: Visible 8-column grid (faint vertical lines). 3-column composition (index column on left, body in middle, metadata on right). Section markers in cobalt italic ("§ i. cover"). Roman numeral index. Top + bottom horizontal rules ink-thick. Page number "p. 01 / 12" in mono. Right-side metadata column with `<strong>` topic / value pairs.

**Avoid**: Center-aligned layouts (this is grid-aligned), more than one accent color, sans-serif display (Newsreader italic is the feature), single-column compositions (the multi-column grid IS the design).

**Sample reference**: `assets/preset-samples/architectural-grid.html`

---

## Critical: Font Weight Matters

**A common failure mode**: the deck looks thin, weak, and generic because imported font weights are too light, or because the `@import` URL doesn't match the `font-family` names used in CSS, causing silent fallback to system fonts.

**Rules to prevent this**:

1. **Always import multiple weights**. A display font needs **400 (body), 500, 600, 700, and 800** to render hierarchy correctly. For `h1`/`h2`, default to **weight 800** — thinner display text looks weak on slides.

2. **Import italic variants** if the preset uses italic for emphasis (e.g., Warm Editorial italicizes key words in headings).

3. **The font name in `font-family` MUST match the font in the `@import` URL.** Writing `font-family: 'Bricolage Grotesque'` when only `Fraunces` was imported causes silent fallback to system fonts → thin, ugly result.

4. **Use CSS variables `--font-display` and `--font-body`** (from the template) — never hardcode `font-family: 'Outfit'` in component CSS, or the fonts won't swap when the preset changes.

---

## Font Distinctiveness Summary

All 13 presets use **completely different primary display fonts**, so every preview Phase 2 generates should look visibly distinct:

| Preset | Primary Font | Signature Visual Feel |
|--------|--------------|-----------------------|
| Warm Editorial | **Fraunces** (serif) | Classic magazine elegance |
| Cyber Terminal | **Syne** + **JetBrains Mono** | Chunky geometric + terminal code |
| Citrus Punch | **Bricolage Grotesque** | Expressive optical-size bold |
| Electric Dusk | **Manrope** | Refined premium neutrality |
| Pastel Chapters | **Nunito** | Rounded friendly warmth |
| Crafted Tactile | **Caveat** + **Space Grotesk** | Handwritten paper + geometric machine type |
| Studio Electric | **Barlow Black** + **IBM Plex Mono** | Chunky display + design-system labels |
| Moody Nocturnal | **DM Serif Display** italic | Sultry serif with hot-pink accent |
| Kawaii Retro | **Big Shoulders Display** + **Press Start 2P** | Chunky modern + 8-bit pixel |
| Friendly Casual | **Fraunces** italic + **Bricolage Grotesque** | Warm serif + energetic sans pair |
| Lo-Fi Underground | **Bebas Neue** + **Caveat** | Condensed scream + handwritten margin |
| Bold Poster | **Shrikhand** | Chubby slab manifesto |
| Architectural Grid | **Newsreader** italic | Refined serif on visible grid |

If two preview files use the same primary display font, one of them is wrong. The 5 curated previews Phase 2 generates must use 5 visibly different display fonts — that's what makes "Show Don't Tell" actually work.

**Note on Friendly Casual + Warm Editorial**: Both reference Fraunces. They are NOT interchangeable — Warm Editorial pairs Fraunces with Outfit (clean and editorial), Friendly Casual pairs Fraunces *italic* with Bricolage Grotesque (warm and indie). If both are in the same Phase 2 preview set, swap one out — they'll look too close.

---

## Non-English / Multi-Language Slides

If the deck is in a language other than English (Chinese, Japanese, Korean, Arabic, Cyrillic, Hindi, etc.), most of the fonts suggested in Ready-to-paste Font Blocks **will NOT render the characters correctly** — they'll fall back to system fonts, breaking the visual consistency.

### What to use instead

For **Chinese (Simplified / Traditional)**:
- Display + body: `Noto Sans SC` or `Noto Serif SC` (or TC for Traditional) — import from Google Fonts
- Pair with a Latin font for any English text mixed in (e.g., `Noto Sans SC + Outfit`)

For **Japanese**: `Noto Sans JP` / `Noto Serif JP`

For **Korean**: `Noto Sans KR` / `Noto Serif KR`

For **Arabic**: `Noto Sans Arabic` / `Noto Kufi Arabic`

For **Cyrillic / Hindi / Thai / Hebrew**: corresponding `Noto Sans ...` family

### How to adapt presets

The aesthetic direction still applies — only the specific font changes:

- **Warm Editorial in Chinese**: `Noto Serif SC` (for display) + `Noto Sans SC` (for body)
- **Cyber Terminal in Japanese**: `Noto Sans JP` + mono (`M PLUS 1 Code` has a CJK-aware mono feel)
- **Citrus Punch in Korean**: `Noto Sans KR` with heavy weights (700/800)
- **Electric Dusk in Chinese**: `Noto Sans SC` — single family with weight variation
- **Pastel Chapters in Japanese**: `Noto Sans JP` — single family with weight variation
- **Crafted Tactile in Chinese**: `Noto Sans SC` for body + `Ma Shan Zheng` for handwritten accents
- **Studio Electric in Japanese**: `Noto Sans JP` weight 900 + IBM Plex Mono fallback
- **Moody Nocturnal in Chinese**: `Noto Serif SC` italic substitute + `Noto Sans SC` body
- **Kawaii Retro in Japanese**: native — already imports `Noto Sans JP` for the kana flourish
- **Friendly Casual in Korean**: `Noto Sans KR` body + `Noto Serif KR` for italic-flavored display
- **Lo-Fi Underground in Chinese**: `Noto Sans SC` weight 900 (no Bebas equivalent — substitute condensed weights)
- **Bold Poster in Chinese**: `ZCOOL KuaiLe` (display) + `Noto Serif SC` (body italic substitute)
- **Architectural Grid in Chinese**: `Noto Serif SC` italic + `Noto Sans SC` body + `M PLUS 1 Code` mono

The color palettes, layout patterns, and sizing all stay the same. Only `@import` URL and `font-family` change.

---

## Font Sanity Check (run after generating)

After generating any preview or deck, verify:

- [ ] The `@import` URL loads successfully (open HTML in browser, check Network tab — no failed requests)
- [ ] Every font name in `font-family` declarations appears somewhere in the `@import` URL
- [ ] Display font weight 700 or 800 is imported (otherwise `h1`/`h2` will look thin)
- [ ] If using italics anywhere (Warm Editorial), italic variants are imported (`ital@1`)
- [ ] When viewed in browser, `h1`/`h2` look **bold and designed**, not thin/generic

### For Phase 2 specifically (5 previews)

Additional distinctiveness check:
- [ ] Open all 5 previews side-by-side
- [ ] **Each preview should use a visibly different primary display font** — Fraunces / Syne / Bricolage / Manrope / Nunito
- [ ] If two previews look like "the same font with different colors", one of them has the wrong font. Fix before showing the user.
- [ ] The **quickest way to check**: look at the big h1 on each title slide. They should look like 5 different typefaces, not 5 variants of one.

If any of these fail, the fonts won't render correctly and the output will look amateurish regardless of layout/color choices.

---

## Color Priority: User Preference vs. Context vs. Archetype

**A subtle but critical rule**: when the user states a color preference ("I like pink", "make it green"), do NOT apply it to all 5 previews. Users don't know what they want until they see it — this is the whole point of Phase 2 (Show Don't Tell).

### Priority order (high to low)

1. **Preset archetype** — The 5 presets are by definition 5 different aesthetic directions. Each has its own natural color vocabulary. Never violate this. Electric Dusk doesn't do neon pink; Cyber Terminal doesn't do pastel mint. Honor the archetype first.

2. **Negative preferences** ("I hate X") — Respect 100%. Users are usually well-tested on what they dislike. Zero previews should violate a negative preference.

3. **Theme context** (inherent to the product) — Sustainability products lean green. Medical/health leans blue or white. Food leans warm. This is objective information about the product, not the user's taste. Weight this moderately.

4. **Positive preferences** ("I like pink") — Weak signal. Respect it in **some but not all** previews. Typically 2-3 out of 5 should honor a stated positive preference; the remaining 2-3 should deliberately explore other directions.

5. **Variety and contrast** — The 5 previews together must cover genuinely different palettes. If all 5 look similar, you've failed Show Don't Tell, regardless of how well you honored preferences.

### Practical rule for 5 previews

Given a user who says "I like pink":

| Preview | Treatment | Why |
|---------|-----------|-----|
| 1 | Honors preference where preset supports it | Shows "you can have what you want" |
| 2 | Honors preference where preset supports it | Same — another expression of the preference |
| 3 | Theme-driven palette, ignores preference | Shows "the product theme suggests other colors" |
| 4 | Deliberate contrast — no pink at all | Shows "here's a direction you didn't ask for" |
| 5 | Design-intuition palette, beautiful but unrelated | Sometimes the best option comes from nowhere |

**Result**: 2 previews honor the preference, 3 deliberately explore alternatives. The user gets to compare their initial instinct against options they didn't request — and often discovers they prefer one of those.

### Why this matters

- Users often can't articulate design preferences accurately. "I like pink" might mean "I want something warm and soft" — which could be better served by cream+terracotta than by actual pink.
- The moment of design insight is *"oh, I didn't know I'd like this"*. That can't happen if all 5 options conform to stated preferences.
- Generating 5 variations of the stated preference is the same failure mode as generating generic AI slop — it privileges the user's first instinct over showing them the possibility space.

### What to avoid

- **Don't** generate 5 pink previews because the user said "pink".
- **Don't** ignore positive preferences entirely — that feels disrespectful.
- **Don't** force a color into a preset where it doesn't fit (pink in Electric Dusk looks tacky; preserve archetype integrity).
- **Don't** hedge with "slightly pink-tinged" variations across all 5 — commit fully to preference in some, fully contrast in others.

### Impression choice and preset fit

The user's "first impression" answer from Phase 1 is the **primary signal** for Phase 2's curation — it tells you which 5 of the 13 presets to surface as previews:

| Impression | Most natural presets | Why |
|------------|---------------------|-----|
| Technically impressive | Cyber Terminal, Electric Dusk, Studio Electric, Architectural Grid | Technical / design-system aesthetics signal depth |
| Beautifully designed | Warm Editorial, Pastel Chapters, Architectural Grid, Friendly Casual | Design-forward aesthetics signal craft |
| Solves a real problem | Warm Editorial, Pastel Chapters, Crafted Tactile, Friendly Casual | Warm, human-centered aesthetics signal empathy |
| Creative / Bold | Citrus Punch, Pastel Chapters, Bold Poster, Studio Electric, Lo-Fi Underground | Energetic/unconventional aesthetics signal creativity |
| Quirky / Joyful | Kawaii Retro, Friendly Casual, Lo-Fi Underground | Personality-led aesthetics signal a "small thing made with care" |
| Moody / Personal | Moody Nocturnal, Crafted Tactile | Intimate aesthetics signal "for one person, deeply" |
| Manifesto / Loud | Bold Poster, Studio Electric, Lo-Fi Underground | High-conviction aesthetics signal "we have a thesis" |

This mapping helps Phase 2 curate which 5 of the 13 presets to show as previews — based on the user's Q5 impression answer. See `workflow-phases.md` Phase 2 for the curation algorithm.

### When explaining to the user

After Phase 2 picks 5 from the 13-preset pool and generates previews, be transparent about the curation:
> "From 13 style options, I picked 5 that fit your project: 2 lean into your stated preference for [color/mood], 2 are theme-aligned alternatives, 1 is a wildcard (often the wildcard ends up resonating). Take a look at all 5 before deciding."

This sets the right expectation and invites the user to update their own preferences based on visual evidence.

---

## Preview Summary Table (for showing the user)

When Phase 2 presents the 5 curated previews, use a per-deck summary table built from the chosen 5. The full 13-preset pool to draw from:

| Preset               | Feel                                           | Best for                                 |
|---------------------|------------------------------------------------|------------------------------------------|
| Warm Editorial      | Light, serif, refined, magazine                | Human-centered, considered               |
| Cyber Terminal      | Dark, mono, hacker-precise                     | DevTools, infrastructure, AI/ML          |
| Citrus Punch        | Light, bold sans, energetic                    | B2C, social, creative tools              |
| Electric Dusk       | Dark navy, clean sans, premium B2B             | Enterprise, fintech, data platforms      |
| Pastel Chapters     | Light, split-duotone, storytelling             | Education, wellness, character-driven    |
| Crafted Tactile     | Warm paper, post-it pinned, handmade           | Hardware, indie, "human" products        |
| Studio Electric     | Dark + electric magenta, design-led            | Design tools, generative AI, media       |
| Moody Nocturnal     | Black + hot pink, intimate / sultry            | Late-night tools, journaling, music      |
| Kawaii Retro        | Pastel + win95 + pixel, joyful retro           | Gaming, AI companions, consumer playful  |
| Friendly Casual     | Warm cream, indie, conversational              | Community, hospitality, food, wellness   |
| Lo-Fi Underground   | Photocopy zine + acid yellow, scrappy DIY      | Indie, art, music, "made in 36 hours"    |
| Bold Poster         | Cream + Shrikhand mega, manifesto editorial    | Single-axis pitches, publications        |
| Architectural Grid  | Cream + cobalt, visible 8-col grid             | Research, knowledge, design-doc tools    |

*(Step-by-step preview generation + curation algorithm live in `workflow-phases.md` Phase 2. This file is the source of truth for WHAT each preset is; the workflow file is the source of truth for HOW to pick + generate previews.)*

---

## Rule: No Style Should Feel "Safe"

If all 5 previews feel like variations on the same idea, you've failed the Show-Don't-Tell principle. Each preset should make the user think "oh wow, that's a different vibe." Bold commitment to each direction beats hedging.

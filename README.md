# Beautiful Hackathon Slides

A Claude Code skill for creating **distinctive, production-grade hackathon demo decks** — not the typical black-console-screenshot technical demo, but startup-pitch-style presentations that actually look designed.

A collection of workflow, patterns, and principles for building bold pitch decks with AI assistance — captured here so anyone can reuse them.

## What This Does

- **Walks you through a proven 9-phase workflow** — from clarifying questions to final demo video integration
- **Shows, doesn't tell** — curates 5 of 13 style presets based on your project + audience, then generates visually distinct previews instead of asking "what font do you want?"
- **Delivers single-file HTML decks** — zero dependencies, opens in any browser, responsive
- **Reserves explicit slots for live demo recordings** — hackathon decks always need them
- **Or builds an *animated demo slide* for you** — when the product isn't built yet (or as polish over a screen recording). 6 archetypes to pick from — Split Narrative, Pipeline Walk, Before/After Morph, Dashboard Fill-In, Network Graph, Map Heatbloom. See ["What's new"](#whats-new--animated-demo-slide) below.
- **Generates AI narration scripts** — matched to your video's time limit
- **Stores context in markdown files** — so long iteration sessions don't lose alignment

## Philosophy

This skill is built around three principles of AI collaboration:

1. **Ask clarifying questions before building** — never jump to implementation with thin context
2. **Store context outside the conversation** — markdown files outlast conversation windows
3. **Show, don't tell** — visual options beat verbal design descriptions

See [`references/ai-collaboration-principles.md`](references/ai-collaboration-principles.md) for the full rationale.

## Installation

Clone the skill into your Claude Code skills directory:

```bash
git clone https://github.com/Esther2524/beautiful-hackathon-slides.git ~/.claude/skills/beautiful-hackathon-slides
```

Plugin Marketplace publishing is coming soon. For now, use the git clone method above.

## Usage

Once installed, there are two ways to invoke the skill:

**Option 1: Just describe what you need (recommended)**

Claude will automatically detect that this skill applies based on your request:

```
"help me make a hackathon pitch deck"
"I need slides for my hackathon demo video"
"create a presentation for our hackathon submission"
```

**Option 2: Invoke directly with slash command**

If Claude doesn't automatically pick up the skill, you can invoke it explicitly:

```
/beautiful-hackathon-slides
```

Either way, the skill will walk you through the full workflow:

1. Ask a few targeted questions about your project
2. Generate 5 visually distinct style previews for you to choose from
3. Build a complete HTML deck in your chosen style
4. Write a `PLAN.md` to preserve context
5. Help you iterate specific slides
6. Generate an AI narration script
7. Guide you through inserting recorded demo videos
8. Package deliverables for submission

## Repository Structure

```
beautiful-hackathon-slides/
├── SKILL.md                              ← entry point, loaded by Claude Code
├── README.md                             ← this file
├── LICENSE                               ← MIT
├── references/
│   ├── ai-collaboration-principles.md    ← the three principles
│   ├── workflow-phases.md                ← detailed 9-phase workflow
│   ├── style-presets.md                  ← 5 aesthetic archetypes
│   ├── slide-patterns.md                 ← reusable slide pattern library
│   ├── iteration-patterns.md             ← common adjustments lookup
│   ├── video-integration.md              ← recording + inserting demos
│   └── live-demo-archetypes.md           ← 6 animated-demo archetypes + elicitation Qs
└── assets/
    ├── plan-template.md                  ← PLAN.md template
    ├── narration-script-template.md      ← narration script template
    ├── style-preview-template.html       ← HTML scaffolding
    ├── live-demo-template.html           ← 6-archetype scaffolds for animated demos
    └── preset-samples/                   ← 8 visual references for the added presets
        ├── _gallery.html                 ← side-by-side iframe gallery (open this first)
        ├── crafted-tactile.html
        ├── studio-electric.html
        ├── moody-nocturnal.html
        ├── kawaii-retro.html
        ├── friendly-casual.html
        ├── lo-fi-underground.html
        ├── bold-poster.html
        └── architectural-grid.html
```

## What's New · Animated Demo Slide

Most hackathon decks lean on a recorded screen video for the "demo" slide. That's fine — but two situations break it:

- **Your product isn't built yet** (or backend's flaky and could crash on stage)
- **A screen recording feels too "raw"** for the otherwise-designed deck

Now Phase 1 asks **Q6**: *"Live demo plan? (a) embed your video, (b) Claude builds an animated demo, (c) skip."* If you pick (b), Phase 3 runs a short follow-up:

1. Claude recommends 2–3 of the 6 archetypes for your specific product (with a one-line "why this one")
2. You pick one
3. Claude asks 3 elicitation questions (e.g., for *Pipeline Walk*: "what are your 3–6 stage names? what flows through them? what shows up at the end?")
4. Claude generates the slide inline — same fonts/colors as the rest of your deck — with a 15–25 second loop and a final reveal beat

The 6 archetypes:

| Archetype | Best for |
|---|---|
| **Split Narrative** | conversational / agentic products (chat on left, visual on right, synced) |
| **Pipeline Walk** | multi-stage data transformers (RAG, ETL, AI workflows) |
| **Before / After Morph** | cleanup / refactor / migration products |
| **Dashboard Fill-In** | analytics / monitoring / insights tools |
| **Network Graph Grow** | knowledge graphs / multi-agent / social |
| **Map Heatbloom** | logistics / geographic / global rollout |

Full archetype docs and the 3-questions-each elicitation patterns: [`references/live-demo-archetypes.md`](references/live-demo-archetypes.md).
Starter HTML scaffolds for all 6: [`assets/live-demo-template.html`](assets/live-demo-template.html) (open in browser to preview).

---

## The 13 Style Presets

Each is an *aesthetic direction*, not a fixed color palette. The skill picks colors to fit your specific project. Phase 2 picks 5 of these 13 based on your hackathon answers (the 5-2-2-1 curation: 2 match your stated impression, 2 fit your project theme, 1 is a wildcard).

The original 5 (curated and refined for hackathon use):

| Preset | Feel | Best For |
|--------|------|----------|
| **Warm Editorial** | Light, serif, magazine-like | Human-centered products, emotional themes |
| **Cyber Terminal** | Dark, mono, hacker-precise | DevTools, infrastructure, AI platforms |
| **Citrus Punch** | Light, bold sans, energetic | B2C products, creative tools, gaming |
| **Electric Dusk** | Dark navy, clean sans, sleek | Enterprise, fintech, data platforms |
| **Pastel Chapters** | Light split-duotone, storytelling | Education, wellness, character narratives |

8 added (with sample HTML references in [`assets/preset-samples/`](assets/preset-samples/)):

| Preset | Feel | Best For |
|--------|------|----------|
| **Crafted Tactile** | Warm paper, post-its, handmade | Hardware, indie, "human" products |
| **Studio Electric** | Dark + electric magenta, design-led | Design tools, generative AI, media |
| **Moody Nocturnal** | Black + hot pink, intimate / sultry | Late-night tools, journaling, music |
| **Kawaii Retro** | Pastel + win95 + pixel, joyful retro | Gaming, AI companions, consumer playful |
| **Friendly Casual** | Warm cream, indie, conversational | Community, hospitality, food, wellness |
| **Lo-Fi Underground** | Photocopy zine + acid yellow, scrappy | Indie, art, music, "made in 36 hours" |
| **Bold Poster** | Cream + Shrikhand mega, manifesto | Single-axis pitches, publications |
| **Architectural Grid** | Cream + cobalt, visible 8-col grid | Research, knowledge, design-doc tools |

Each of the 8 added presets has a sample HTML in `assets/preset-samples/` that Claude reads as a visual reference before generating the corresponding Phase 2 preview — text descriptions alone aren't enough for the more decorative ones (post-its, sticker badges, scanlines, 8-col grids).

## License

MIT — use freely for personal or commercial projects. See [LICENSE](LICENSE).

## Author

Created by [Esther Wang](https://github.com/Esther2524). The workflow, patterns, and principles captured here emerged from personal experiments in collaborating with AI tools on design and storytelling projects.

## Contributing

Improvements welcome. If you use this skill and find an iteration pattern, slide pattern, or style preset missing, open a PR with:
- The new addition
- A one-line description of when to use it
- A note on why the existing patterns weren't sufficient

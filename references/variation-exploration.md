# Variation exploration reference

Supporting material for the Phase 3 Variation Exploration path in `SKILL.md`. Covers lever vocabulary by logo type, card structure, an example variation paragraph, the HTML gallery scaffold, and naming conventions.

---

## Section 1: Lever vocabulary by logo type

These are the dimensions that can move while the Core DNA holds. Choose levers relevant to the open questions the user has, not the full list.

**Geometric mark**
- Node count (how many points, spokes, or intersections the form contains)
- Node density (how tightly nodes are packed; sparse vs. lattice-dense)
- Spoke treatment (solid, tapered, dotted, absent)
- Ring count (concentric layers, or none)
- Perimeter behaviour (closed, open, framed, bleeding to edge)
- Symmetry axis (radial, bilateral, asymmetric)
- Centre weight (heavy focal point vs. empty centre vs. counterform-led centre)
- Layered structure (flat vs. overlapping planes with transparency)
- Line weight (hairline, medium, bold; uniform vs. variable)
- Stroke type (continuous vs. dotted vs. dashed)
- Framing shape (hexagonal, circular, square, none)

**Wordmark / logotype**
- Typeface family (serif, sans-serif, slab, display, mono)
- Weight (light, regular, medium, bold, ultra)
- Letter-spacing (tight, default, open, very open)
- Case (all-caps, title, all-lowercase)
- Ligature treatment (standard, custom, suppressed)
- Custom letterform site (which specific character carries the distinctive edit)
- Counter shape (the enclosed or semi-enclosed space within letters -- modified to be rounder, sharper, wider)
- Descender or ascender variation (extended, cropped, looped, straightened)

**Lettermark / monogram**
- Stroke contrast (monolinear vs. high contrast)
- Overlap vs. separation (letters interlocking, touching, or clearly separated)
- Baseline alignment (co-aligned, staggered, one letter raised or lowered)
- Custom joinery (how two letters meet -- shared stroke, merged counter, bridged gap)

**Combination mark** (wordmark plus symbol)
Any of the above levers for either the wordmark or the symbol component, PLUS:
- Relationship orientation (horizontal lock-up, stacked, symbol floating free)
- Breathing space (tight coupling vs. deliberate gap)
- Scale ratio (symbol dominant, wordmark dominant, balanced)

When the exploration covers a combination mark, define whether you are varying the symbol, the wordmark, or the relationship. Mixing lever types within a single set without labelling them creates confusion; document which component each lever applies to.

---

## Section 2: Card structure in detail

Each variation card contains, in this order:

1. **Header line**: `VARIATION 01 · STRONG CANDIDATE` (or WORTH TESTING, or DOCUMENTED FOR THE FILE)
2. **Title**: Two to three words, evocative of the geometry or treatment, not the mood. See Section 5 on naming.
3. **Lever label**: `LEVER · [Name of lever]` -- stated explicitly so the user can cross-reference the set.
4. **The mark**: Rendered at consistent canvas dimensions across every card in the set. Visual weight must be comparable; do not allow one card's mark to be twice the size of another's.
5. **Brand lockup**: The mark in a representative small-scale lockup, same position on every card (e.g., always bottom-left, always the same proportional size). This lets the user evaluate how the variation sits in context, not just in isolation.
6. **Description**: Two to three sentences covering (a) what the lever produces in this variation, (b) what trade-off it introduces, and (c) what brand quality from the Phase 1 strategy it tests.
7. **Footer tags**: The qualities under active evaluation for this variation. Examples: `clarity · scalability · warmth · distinctiveness · restraint`. Tags help the user remember what they were testing when they return to the set the next day.

For SVG-based explorations, all cards should use the same `viewBox` dimensions. For image-gen explorations, all outputs should be requested at the same aspect ratio and resolution before placement in cards.

---

## Section 3: Example variation paragraph

The following example uses a hypothetical geometric mark for a company called Meridian. It is a tone reference only; do not import any of the visual specifics into a live project.

> **12-Node Lattice / LEVER: Node count**
> Extending the inner ring from eight to twelve nodes increases the visual density of the form and shifts it from a sparse, airy emblem toward something closer to a technical diagram. The trade-off is legibility at small scale: at 32x32 the lattice reads as texture rather than structure, which works against Meridian's requirement for a legible favicon. Worth testing at medium scale (app header, above-the-fold), where the density reads as precision rather than noise.

Note the structure: lever effect named directly, trade-off named, brand requirement tested. No superlatives, no marketing register. The description should read like a note from one designer to another reviewing the same brief.

---

## Section 4: HTML gallery scaffold

This is a minimal scaffold for the exploration document. It is a starting point for handoff to the frontend-design skill for production refinement, not a finished template. Brand colours and typography are declared as CSS custom properties so the document inherits the project's brand rather than the skill's defaults.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>[Brand name] — Variation Exploration</title>
  <style>
    /* ── Brand tokens: replace these with values from the Phase 2 brief ── */
    :root {
      --color-bg:         #f8f7f4;
      --color-surface:    #ffffff;
      --color-primary:    #1a1a1a;
      --color-accent:     #2d5be3;
      --color-muted:      #6b6b6b;
      --color-border:     #e2e0db;
      --font-display:     'Georgia', serif;     /* replace with brief typeface */
      --font-body:        'Inter', sans-serif;  /* replace with brief typeface */
      --font-mono:        'JetBrains Mono', monospace;
    }

    /* ── Reset ── */
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      background: var(--color-bg);
      color: var(--color-primary);
      font-family: var(--font-body);
      font-size: 14px;
      line-height: 1.6;
    }

    /* ── Cover spread ── */
    .cover {
      min-height: 60vh;
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      padding: 4rem;
      border-bottom: 1px solid var(--color-border);
    }

    .cover__label {
      font-family: var(--font-mono);
      font-size: 11px;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--color-muted);
      margin-bottom: 1rem;
    }

    .cover__title {
      font-family: var(--font-display);
      font-size: clamp(2rem, 5vw, 4rem);
      font-weight: 400;
      line-height: 1.1;
      margin-bottom: 0.5rem;
    }

    .cover__subtitle {
      font-family: var(--font-mono);
      font-size: 12px;
      color: var(--color-muted);
      margin-bottom: 2rem;
    }

    .cover__dna {
      max-width: 52ch;
      font-size: 15px;
      color: var(--color-muted);
      border-left: 2px solid var(--color-accent);
      padding-left: 1.25rem;
    }

    /* ── Card column ── */
    .cards {
      display: flex;
      flex-direction: column;
      gap: 0;
    }

    .card {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 0;
      border-bottom: 1px solid var(--color-border);
      background: var(--color-surface);
    }

    .card:nth-child(even) {
      background: var(--color-bg);
    }

    .card__mark {
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 3rem;
      border-right: 1px solid var(--color-border);
      min-height: 280px;
    }

    .card__mark svg {
      max-width: 180px;
      max-height: 180px;
      width: 100%;
      height: auto;
    }

    .card__meta {
      padding: 2.5rem 3rem;
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }

    .card__header {
      display: flex;
      align-items: center;
      gap: 1rem;
    }

    .card__number {
      font-family: var(--font-mono);
      font-size: 11px;
      letter-spacing: 0.1em;
      color: var(--color-muted);
    }

    .badge {
      font-family: var(--font-mono);
      font-size: 10px;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      padding: 0.2em 0.6em;
      border-radius: 2px;
    }

    .badge--strong   { background: #d4edda; color: #1a5c2a; }
    .badge--testing  { background: #fff3cd; color: #6b4c00; }
    .badge--file     { background: #f0f0f0; color: #555;    }

    .card__title {
      font-family: var(--font-display);
      font-size: 1.35rem;
      font-weight: 400;
    }

    .card__lever {
      font-family: var(--font-mono);
      font-size: 11px;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      color: var(--color-accent);
    }

    .card__description {
      font-size: 13.5px;
      line-height: 1.65;
      color: var(--color-primary);
      max-width: 48ch;
    }

    .card__lockup {
      margin-top: auto;
      padding-top: 1rem;
      border-top: 1px solid var(--color-border);
    }

    .card__lockup img,
    .card__lockup svg {
      max-height: 36px;
      opacity: 0.75;
    }

    .card__tags {
      display: flex;
      flex-wrap: wrap;
      gap: 0.4rem;
      margin-top: 0.75rem;
    }

    .tag {
      font-family: var(--font-mono);
      font-size: 10px;
      letter-spacing: 0.06em;
      color: var(--color-muted);
      border: 1px solid var(--color-border);
      padding: 0.15em 0.5em;
      border-radius: 2px;
    }

    /* ── Responsive: stack on narrow viewports ── */
    @media (max-width: 640px) {
      .cover { padding: 2rem; }
      .card  { grid-template-columns: 1fr; }
      .card__mark { border-right: none; border-bottom: 1px solid var(--color-border); }
      .card__meta { padding: 1.5rem 2rem; }
    }
  </style>
</head>
<body>

  <!-- Cover spread -->
  <section class="cover">
    <p class="cover__label">Variation exploration</p>
    <h1 class="cover__title">[Brand name]</h1>
    <p class="cover__subtitle">[N] variations — [Family name, e.g., Geometric mark]</p>
    <p class="cover__dna">Core DNA: [One sentence stating what stays constant across all variations.]</p>
  </section>

  <!-- Variation cards -->
  <div class="cards">

    <!-- Repeat this block for each variation -->
    <article class="card">
      <div class="card__mark">
        <!-- SVG or <img> goes here at consistent dimensions -->
        <svg viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
          <!-- mark -->
        </svg>
      </div>
      <div class="card__meta">
        <div class="card__header">
          <span class="card__number">VARIATION 01</span>
          <span class="badge badge--strong">Strong candidate</span>
          <!-- or: badge--testing / badge--file -->
        </div>
        <h2 class="card__title">[Two or three word name]</h2>
        <p class="card__lever">LEVER · [Lever name]</p>
        <p class="card__description">
          [Two to three sentences: what the lever produces, what trade-off it introduces,
          what brand quality it tests.]
        </p>
        <div class="card__lockup">
          <!-- Small-scale brand lockup, same position on every card -->
        </div>
        <div class="card__tags">
          <span class="tag">clarity</span>
          <span class="tag">scalability</span>
          <span class="tag">distinctiveness</span>
        </div>
      </div>
    </article>
    <!-- end card -->

  </div>

</body>
</html>
```

Hand this scaffold off to the frontend-design skill for production refinement. The scaffold intentionally defers all brand-specific values to CSS custom properties; replace the placeholder values at the top of the `:root` block with values from the Phase 2 brief before handing off.

---

## Section 5: Naming convention

**Pattern**: two to three words, descriptive of geometry or treatment, not mood.

**Strong names**: 12-Node Lattice, Concentric Tiered, Hexagonal Frame, Dotted Spokes, Sovereignty Crown, Split Crossbar, Open Counter, Tapered Spoke, Interlocked Ring, Hairline Radial.

**Weak names**: Calm, Bold, Ethereal, Energetic, Premium, Minimal. These describe feel rather than the lever, and they create ambiguity when the user wants to reference a specific candidate a week later.

The test for a name: can a person who was not in the room identify which variation it refers to from the name alone? If not, the name is too mood-driven. Revise toward the geometry or the treatment that distinguishes this variation from its neighbors in the set.

Names matter more than they look. Once a user builds a vocabulary around the set -- "I want to pursue Concentric Tiered but with a lighter line weight" -- the conversation becomes precise. Without names, feedback is positional and decays fast: "the third one" stops meaning anything once the set is reordered.

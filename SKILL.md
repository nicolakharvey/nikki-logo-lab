---
name: logo-development
description: 'Develop, refine, and critique brand logos through a strategy-first workflow: extract positioning, audience, and voice; produce a design brief; execute via SVG code, structured image-gen prompts (Midjourney, Leonardo, Flux), or variation exploration (single-lever direction-finding when the visual direction is still open); then critique against brand fidelity, design fundamentals, versatility, and distinctiveness. Use for any logo, wordmark, lettermark, monogram, symbol mark, combination mark, or visual identity work. Also use when they share an existing logo for feedback, describe a startup needing identity work, say "show me options", or say "I need a logo for X". Trigger in preference to generic image-generation help whenever the output is a logo rather than a one-off illustration.'
---

# Logo Development

This skill develops brand logos through four sequential phases: **strategy extraction**, **design brief**, **execution** (SVG generation, image-gen prompts, or variation exploration), and **critique**. Skipping the strategy phase is the most common failure mode in non-designer logo work; it produces marks that look fine in isolation but fail to embody the brand they represent.

Logo design is a craft with a real aesthetic ceiling. Be honest with the user about what an LLM can and cannot deliver here. Claude is strong at the strategic work, the brief, the critique, and at simple SVG marks (wordmarks, monograms, basic geometric symbols). Claude is weak at custom letterforms, refined optical balance in pictorial marks, and the kind of distinctive illustrative work that benefits from human or image-gen iteration. The skill leans into the former and routes the latter to image-gen tools rather than producing low-quality SVG.

## Why strategy comes first

A logo is a compression of a brand into a mark. Without knowing what the brand actually is — who it serves, what it stands for, what tone it strikes — visual choices are arbitrary and tend to default to whatever conventions are popular this year (currently: thin geometric sans-serif wordmarks, gradient orbs, generic abstraction). The strategy phase exists to give every subsequent visual decision a reason.

If the user resists strategy ("I just want a logo"), do a compressed version inline rather than skipping it. Ask three questions: who is this for, what does it stand for that competitors do not, and what tone should it strike. Move on once those have rough answers.

## Phase 1: Strategy extraction

Work through these in order. If the user has brand documentation already, read it and confirm what has been inferred before proceeding.

### Compressed strategy (when the user resists)

Some users will push back on Phase 1 ("I just need a logo, skip the strategy stuff"). Do a compressed version inline rather than skipping it entirely. The minimum viable strategy is three answers:

1. Who is this brand for? (Audience, one sentence.)
2. What does it stand for that the closest 2-3 competitors do not? (Positioning, one sentence.)
3. What three-word voice should it strike, each paired with an antonym? (Voice, e.g., "considered not precious, confident not assertive, warm not folksy".)

Synthesize these into a one-sentence positioning sentence and proceed. Tell the user explicitly that the compressed path produces less differentiated output than the full process, and offer to return to deeper strategy work if the first round disappoints. Do not skip this minimum: without at least three voice antonyms, Phase 4 critique has nothing to measure against and the whole loop loses its discipline.

### Full strategy (default)

**Positioning**
1. What does the brand do, in one sentence (functional)?
2. What does it stand for, in one sentence (emotional or ideological)?
3. Who are the most relevant 2-3 competitors, and how is this brand different?

**Audience**
1. Primary audience: demographic and psychographic.
2. What is the audience moving toward (aspiration) and away from (resistance)?
3. Where will they encounter the logo? App icon, website header, merch, packaging, social avatar, signage, video, dark mode, etc.

**Voice and personality**
1. Three to five adjectives that describe the brand's personality.
2. For each adjective, an antonym it explicitly is NOT. For example: "warm, not folksy"; "bold, not aggressive"; "premium, not exclusive". The antonyms matter more than the adjectives, because adjectives alone are too easily satisfied by generic choices.

**Constraints**
1. Industry conventions to embrace or break.
2. Existing visual assets that must be respected (parent brand, founder's other work, sub-brand relationships).
3. Practical: must work as a 32x32 favicon, must work in single color, must work alongside specific other marks, etc.

Synthesize this into a short positioning paragraph and confirm with the user before moving to Phase 2. This synthesis is the source of truth for every visual choice that follows. Without it, Phase 4 critique has nothing to measure against.

## Phase 2: Design brief

Produce a written brief covering each of the following.

### Logo type recommendation

Recommend one primary logo type with explicit reasoning grounded in the strategy. The main types and when each fits:

- **Wordmark / logotype** (e.g., Google, FedEx, Coca-Cola): Use when the name is short, distinctive, and pronounceable. Rewards typographic distinction. Sensible default for most brands with sub-10-character names.
- **Lettermark / monogram** (e.g., HBO, IBM, NASA): Use when the full name is long or descriptive and an acronym is already in active use. Risk: low distinctiveness, since most short letter combinations are visually crowded.
- **Pictorial / iconic** (e.g., Apple, Twitter, Target): Use when there is a concrete object that captures the brand. High memorability ceiling but high failure rate without skilled execution.
- **Abstract mark** (e.g., Nike swoosh, Pepsi, Chase): Use when no concrete object fits but a non-typographic mark is desired. Requires significant brand investment to load meaning into an arbitrary shape, which most early-stage brands lack the budget for.
- **Combination mark** (e.g., Adidas, Burger King, Lacoste): Wordmark plus symbol. Most flexible, also most generic if not handled well. Reasonable default when in doubt and the brand has any complexity.
- **Emblem** (e.g., Starbucks, Harley-Davidson, NFL teams): Wordmark contained within a shape. Heritage, traditional, formal feel. Generally weak for digital-native brands due to small-scale legibility loss.

### Visual direction

- Three to five descriptive adjectives the visual should embody, drawn from Phase 1 voice (not invented fresh).
- Two or three reference logos with explicit rationale: what is relevant about each, and what NOT to copy from each.
- Conceptual hooks the symbol or wordmark could evoke without being literal.

### Color direction

- One to three candidate palettes, each with reasoning grounded in positioning, category dynamics, and competitor differentiation.
- Specify roles: primary, secondary, accent, neutrals.

Be cautious about color psychology claims. Cross-cultural universal color meanings are weakly supported in the empirical literature (see Elliot & Maier's 2014 review in *Annual Review of Psychology*). Context-specific effects exist, but appeals to "blue means trust" or "red means energy" do not survive scrutiny. Justify color choices by category dynamics, brand differentiation, and consistency with voice rather than by claimed universal meanings.

### Typography direction

- Type category (serif, sans-serif, slab, display, mono, custom) with reasoning.
- Character (geometric, humanist, grotesque, transitional, neo-grotesque) where relevant.
- Two or three specific typeface candidates if going off-the-shelf, including weights.

### Anti-direction

What this logo should NOT look like. This section is often more useful than the positive direction because it constrains the search space. Examples: "no gradient orbs", "no thin generic geometric sans serif (Avenir, Montserrat, Poppins)", "not another rocket ship for a tech brand", "no overused wellness palette of sage green and dusty pink".

### Application tests

The contexts the final mark will be evaluated against. Pulled from Phase 1 audience touchpoints. Common ones: 32x32 favicon, social avatar at 80x80, single-color print, white-on-dark, dark-on-light, animated state, embroidery (loses fine detail), etched (no fills, only outlines).

**Required lockup forms:** Identify which lockups Phase 3 must produce, derived from the touchpoints. Default expectation for any complete identity is three lockups: a primary (usually horizontal), a stacked alternative for square spaces, and a symbol-only or favicon-derivative for small-scale. If the brand has chosen a wordmark-only system intentionally and no symbol is wanted, say so explicitly and document why. A wordmark with no small-scale derivative is an incomplete identity.

Confirm the brief with the user before executing. Briefs are cheap to revise; SVG and image-gen iterations are not.

## Phase 3: Execution

Choose the execution path based on the recommended logo type:

- **SVG generation path**: wordmarks, lettermarks, simple geometric or abstract marks, combination marks with a simple geometric symbol.
- **Image-gen prompt path**: pictorial marks, illustrative marks, complex symbols, mascots, marks requiring rich texture or stylization.
- **Hybrid**: SVG for the wordmark, image-gen prompts for the symbol, then composite. This is often the right answer for combination marks where the symbol is non-trivial.

### SVG generation

Use SVG when the mark is composable from typography and geometric primitives (rectangles, circles, polygons, simple paths). Honor these constraints:

- Use a viewBox like `0 0 100 100` for symbols or `0 0 200 60` for horizontal wordmarks so the mark scales cleanly.
- Build the mark with `<g>` groups so wordmark, symbol, and clear-space elements can be toggled independently.
- For typography, embed font choices via `<text font-family="...">` or convert to paths if the user wants self-contained SVG. Note this trade-off explicitly: text-based SVG depends on the font being available; path-based SVG is portable but loses editability. Make a clear recommendation rather than leaving the choice open.
- For symbols, prefer simple shapes built from explicit `<path>` coordinates, `<circle>`, `<rect>`, `<polygon>`. Avoid complex bezier curves; Claude is unreliable at producing aesthetically refined bezier work and the result often reads as "AI-generated" rather than designed.

#### Distinctive detail requirement

Generic logos result from accumulating safe defaults. The wordmark in a default font, in a safe color, with conventional spacing, is the path of least resistance and the path that fails the distinctiveness test in Phase 4. Avoid this by committing to at least one non-default choice per mark. This is the moment of authorship that distinguishes the logo from category conventions. Examples:

- A custom letterform: a modified "T" with extended crossbar reading as a lintel; an "O" with flat sides; a "g" with a distinctive descender; a ligature where letters meet.
- A non-standard proportion: notably tight or wide tracking; an unusually high crossbar; a wider-than-default counter.
- A characterful weight or contrast choice: a light weight where everyone uses regular; a stencil cut where everyone uses solid.
- An asymmetric element where symmetry is the default expectation.
- A subtle structural detail tied to the brand concept (not arbitrary; defensible against the Phase 1 strategy paragraph).

The detail should be defensible against the strategy. If you cannot articulate why the detail is there in terms of the strategy paragraph, replace it with a different one rather than removing it. An undifferentiated logo costs the brand more in the long run than a detail that's slightly too loud, because undifferentiation compounds silently while overdesign gets corrected at the next round.

Note: this requirement is for the SVG path. Image-gen marks have distinctiveness baked in by their nature (curated from many candidates with strategic intent), so the requirement is implicit there.

#### Required deliverables in the first pass

Produce a complete first-pass deliverable, which means BOTH color states AND lockup forms. Three of each, nine pieces minimum, though the same SVG often serves multiple cells.

**Color states (always produce all three):**
1. Full color (using the primary palette from Phase 2).
2. Single-color positive (typically black or the primary ink on transparent).
3. Reversed (off-white on the primary dark, not pure white on pure black, which often reads colder than intended).

**Lockup forms (produce all three by default):**
1. Primary lockup (usually horizontal): the main expression, what most uses default to.
2. Stacked lockup: a compact alternative for square spaces (social avatars, app icons, packaging panels).
3. Symbol-only or favicon-derivative: a derived monogram, extracted glyph, or simplified mark that works at 32x32. If the identity is wordmark-only and no symbol is wanted, say so explicitly and justify why no small-scale form is needed.

Be honest with the user about the aesthetic ceiling. Claude can produce competent wordmarks with thoughtful kerning suggestions, simple monograms, and basic geometric symbols. Claude cannot produce the kind of optically-balanced, custom-lettered, distinctively-crafted marks a skilled type or logo designer produces. If the brief calls for that level, say so and recommend either handing off the SVG output as a starting point to a designer, or shifting to the image-gen path and curating from many candidates.

#### HTML specimen sheet

After generating the SVGs, always produce a self-contained HTML specimen sheet. This is the primary review surface — do not ask the user to evaluate SVGs from code blocks. The specimen sheet must:

- Be a single self-contained HTML file with all SVGs inline (no external dependencies except Google Fonts via `<link>` if the mark uses a web font)
- Show all nine deliverables in a structured grid: three lockup forms (horizontal, stacked, symbol-only) as columns; three color state sections (full color on white, single color on white, reversed on the primary dark) as rows
- Include a scale row at the bottom showing the primary lockup at 240px wide, 80px wide, 40px wide, and 16px wide (favicon simulation)
- Include the brand name and positioning sentence at the top as context
- Use a clean neutral layout (white body, dark section for reversed variants, generous padding, clear section labels in a small neutral sans)

Instruct the user to open it in a browser. In Claude.ai the HTML will render inline in the conversation — point this out and tell them to use the expand button if it appears small.

### Variation exploration

Trigger this path when direction is still open after Phase 2: the brief is locked but the user has not committed to a visual direction. Common signals include "show me options", "I'm not sure which way to go yet", or any moment where the strategy is settled but the visual feel is genuinely uncertain. This is direction-finding work, not delivery work. It precedes first-pass execution on the selected direction; it does not replace it.

**Core DNA plus Lever framework**

Before generating any variations, state two things explicitly:

- **Core DNA** -- a single sentence naming what stays constant across every variation. The DNA is what makes 10 variations feel like a family rather than 10 unrelated sketches. For a wordmark this might be the typeface category and weight range; for a geometric mark it might be the primary form and radial structure. If you cannot write the DNA sentence, the brief is not finished: return to Phase 2.
- **Levers** -- the dimensions that can move while the DNA holds. Each logo type has its own lever set; see `references/variation-exploration.md` for vocabulary by type. Choose the levers most relevant to the open questions the user has.

**The one-lever rule**

Each variation pulls exactly one lever. Two levers moving simultaneously and the diagnostic value collapses: the user cannot tell which change is responsible for the result. This is not a stylistic preference; it is the minimum condition for the exploration to be legible.

**Exploration size**

Default to 8 to 12 variations. Three is too few to see patterns; twenty is overwhelming. Within that range, group related levers together so the set has an internal logic the user can read at a glance.

**Variation card structure**

Each variation is presented as a card. The card structure (detailed in `references/variation-exploration.md`) covers: a variation number with status badge, a two-to-three word evocative name, the lever stated explicitly, the mark rendered at consistent dimensions across every card, a brand lockup at small scale, a two-to-three sentence description naming what the lever produces, what trade-off it introduces, and what brand quality it tests, and a footer listing the qualities under evaluation (clarity, distinctiveness, scalability, warmth, etc.).

Names matter more than they look. They give the user a vocabulary to reference specific candidates in later conversation. Without names, the gallery collapses into "the third one" within a day.

**Three-state status rubric**

Apply the rubric during generation, not after the set is complete:

- **Strong candidate** -- passes strategy fidelity, has the required distinctive detail, performs in the critical applications identified in Phase 2.
- **Worth testing** -- has a quality that may be valuable but introduces an unresolved question. Name the question.
- **Documented for the file, not progressing** -- pulls the lever cleanly but the result fails the brand.

Honest exploration includes failed variations. A curated set that only shows winners loses the diagnostic value of seeing why some directions do not work. Label failed variations as such and keep them in the set.

**Sequencing**

Run exploration mode when direction is open. Once the user selects a direction, return to the standard SVG or image-gen first-pass path to build out the full deliverable on the selected variation. Exploration is direction-finding; first-pass is delivery. The two modes are sequential, not interchangeable.

**Brand inheritance**

The exploration document inherits the brand it is exploring -- its palette, typography, and voice -- not the skill's defaults. Lean on the Phase 2 brief for every visual decision in the cards.

For lever vocabulary by logo type, card structure detail, example variation paragraph, and the HTML gallery scaffold, see `references/variation-exploration.md`. Gallery production is handed off to the frontend-design skill rather than duplicated here.

### Image-gen prompts

For pictorial, illustrative, or visually rich marks, generate structured prompts for the user to run in their image-gen tool of choice. See `references/image-gen-prompts.md` for tool-specific patterns covering Midjourney, Leonardo, Flux, Imagen, and DALL-E.

Always produce:
- The core prompt.
- Three to five variations that each vary one dimension at a time (style, composition, mood, palette, era), not multiple dimensions at once. Varying one at a time makes it possible to identify what is and is not working in the outputs.
- Suggested negative prompts (things to exclude).
- Recommended parameters for the chosen tool (aspect ratio, stylization level, model version).
- A short note on how to evaluate the outputs against the brief, including which Phase 1 voice antonyms to actively check for.

## Phase 4: Critique and refinement

When Phase 3 ran in Variation Exploration mode, Phase 4 critique applies to the selected variation taken forward, not the full exploration set. The set has already been graded inline using the three-state rubric during generation. Phase 4 then deepens the critique on the chosen direction: applying the full strategy fidelity, design fundamentals, versatility, and distinctiveness dimensions to the one candidate the user has committed to pursuing.

Critique either the SVG/prompt outputs from Phase 3 or an existing logo the user has shared. Work through these dimensions in order; if a logo fails an earlier dimension it is rarely worth evaluating later ones.

**Strategy fidelity**
- Does the mark embody the positioning paragraph from Phase 1?
- Does it embody the voice adjectives, and crucially, does it avoid the antonyms? Walk through each adjective and its antonym; the mark should pull toward one and away from the other for each pair.
- Name 2-3 specific comparable brands (drawn from Phase 1's competitor set, plus the broader category if relevant). For each named brand, ask: could this logo plausibly belong to them? If yes for any of them, the mark is not distinctive enough. Specific named comparison is more rigorous than a vague "is it different from competitors" check, because it forces a side-by-side mental rendering.

**Design fundamentals**
- Legibility at 32x32 (favicon and avatar context). Render or describe what disappears.
- Performance in single color.
- Performance reversed (light on dark).
- Optical balance: does any element look heavier, lighter, or off-center than it should? Note that mathematical centering is rarely optical centering.
- Negative space: incidental or intentional?
- Complexity: van Grinsven & Das (2016) found that complex logos can build familiarity over time but harm initial recognition; simple logos are more immediately legible but build less distinctive memory. Match the complexity to the brand's lifecycle stage.

**Versatility**
- Are horizontal, stacked, and symbol-only lockups already provided or trivially derivable?
- Does it work across the application contexts identified in Phase 2?
- Are clear-space rules defined?

**Distinctiveness**
- Memorable after one look. Standard test: ask the user to describe it from memory five minutes later.
- Not interchangeable with category conventions.

For each issue, propose a specific refinement, not just a critique. "The wordmark feels generic" is unactionable. "The wordmark is set in a default geometric sans similar to Montserrat. Try a humanist sans (Inter, Söhne) or a more characterful grotesque (GT America, Untitled Sans) to add warmth without losing modernity. If the budget allows, custom-letter the first character to anchor distinctiveness" is actionable.

### Prioritizing the critique

A critique that lists every issue with equal weight is hard for the user to act on. After identifying issues across the four dimensions above, structure the recommendations by leverage:

- **What's working:** Name what should be preserved. Critique without acknowledgment of strengths can lead to wholesale redesign of marks that have a defensible foundation. This isn't softening the blow; it's identifying the parts that don't need to change.
- **If you can change one thing:** The single highest-leverage change. This is usually the change that addresses strategy fidelity most directly, because strategy issues compound silently over time while small craft issues can often be fixed at delivery.
- **If you can change three things:** The top three in priority order, with reasoning for why each ranks where it does.

This structure forces the critic to identify what matters most rather than dumping every observation equally, and it gives the user a budget-conscious decision path.

## Iteration

Logo development is iterative. After Phase 4, return to Phase 3 with the critique notes, regenerate, and re-critique. Two to three rounds is normal. If the user is happy after one round, push back gently: ask which specific weaknesses they considered, and whether they tested the logo at small sizes and in single color. First-round happiness usually means the critique was not rigorous.

## Honest limits

Some things the user may want that this skill cannot deliver well. Name them when they come up rather than producing low-quality output.

- **Custom letterform design**: True bespoke type requires a type designer or extensive iteration in Glyphs/FontForge. Recommend handoff or a humanist off-the-shelf alternative.
- **Hand-drawn or illustrative aesthetic**: Use the image-gen path and curate, rather than attempting in SVG.
- **Animated logo systems**: Claude can describe motion direction (entrance, idle states, transitions, easing) but cannot produce After Effects, Lottie, or Rive files.
- **Cultural or regional appropriateness in unfamiliar markets**: Recommend a local cultural review before finalizing for any unfamiliar market. Visual conventions, semiotic associations, and even simple legibility (e.g., bidirectional scripts, vertical scripts) vary in ways Claude will miss.
- **Trademark clearance**: Recommend a search via USPTO, WIPO Madrid, or the relevant national registry before committing.

When these limits apply, name them, suggest the bridge (designer handoff, image-gen tool, cultural review, IP search), and continue with what the skill can deliver well.

## Output structure

When delivering the full workflow, organize the response as four clearly-labeled sections matching the phases. When the user comes in mid-workflow (e.g., "critique this logo"), skip directly to the relevant phase but back-fill the strategy assumptions you are using to critique against, so the user can correct them if wrong.

## References

- `references/image-gen-prompts.md`: Tool-specific prompt patterns for Midjourney, Leonardo, Flux, Imagen, DALL-E. Read when entering Phase 3 image-gen path.
- `references/variation-exploration.md`: Lever vocabulary by logo type, card structure, example variation paragraph, HTML gallery scaffold, naming conventions. Read when entering Phase 3 variation exploration path.

# Image-generation prompt patterns for logos

This reference covers prompt patterns for the major image-generation tools as of early 2026. These tools update frequently; if the user mentions a model version not covered here, ask them about its prompt conventions or look up current docs rather than guessing.

The general principle across all tools: be specific about the type of mark, anchor the style explicitly, vary one dimension at a time across iterations, and generate many candidates. Expect to produce 8 to 20 outputs per direction to find one that meets the brief.

## Midjourney (v6, v7)

Midjourney handles natural language well in v6 and later; the comma-separated keyword soup style from v4 is less effective now. For logos, anchor the style at the start of the prompt and put modifiers after.

**Prompt structure that works:**

```
[logo type], [subject/concept], [style descriptors], [mood], [color direction], --ar 1:1 --s [stylization]
```

**Useful parameters:**

- `--ar 1:1` for symbol-only marks; `--ar 3:1` or `--ar 16:9` for wordmarks and horizontal lockups.
- `--s 50` to `--s 250` for more controlled, less hallucinatory results (default 100). Lower stylization is usually better for logos because it stays closer to the prompt.
- `--no` for negative prompts. For logos, common excludes: `--no text, lettering, photorealistic, 3D rendering, gradient, drop shadow, watermark, signature` unless any of those are wanted.
- `--sref [URL or random seed]` to lock in a style reference across iterations.
- `--v 7` to specify version if defaults have shifted.

**Anchoring style for logos:**

Useful style anchors at the start of the prompt: "minimalist vector logo", "flat 2D logo", "geometric brand mark", "modernist logo design", "Swiss design poster", "Bauhaus geometric mark", "vintage badge logo", "monoline icon".

Avoid generic anchors like "modern logo" or "professional logo"; they produce generic output.

**Example for a fictional sustainable apparel brand:**

```
minimalist vector logo for sustainable apparel brand, single leaf forming the letter Y, 
clean geometric construction, single color forest green on white, Swiss design influence, 
no shadows or gradients --ar 1:1 --s 100 --no text, photorealistic, 3D, gradient
```

**Iteration pattern:**

Generate 4 candidates from the core prompt, then vary one dimension at a time:
- Style swap: replace "Swiss design" with "Bauhaus" or "monoline"
- Concept swap: replace "leaf forming letter Y" with "stitching forming letter Y"
- Palette swap: replace color direction
- Construction swap: replace "geometric" with "organic"

Do not vary three things at once and try to reason about which one mattered.

## Leonardo.ai

Leonardo offers more direct control than Midjourney with explicit model selection, elements, and image-to-image refinement. Logos benefit from these specific choices.

**Recommended models for logos:**

- Leonardo Phoenix: best general-purpose model for logos as of early 2026, strong text rendering.
- Leonardo Vision XL: better for photorealistic or texture-heavy concepts.
- Leonardo Diffusion XL: solid all-rounder, faster than Phoenix.

**Prompt structure:**

Leonardo uses simpler prompts than Midjourney. Lead with the logo type and concept, follow with style and color.

```
Vector logo of [concept], [style], [color], minimalist, clean, no background
```

**Useful features:**

- "Elements" allow style blending; choose a Logo or Vector Art element at low to moderate strength (0.2 to 0.5).
- "Image to Image" for refining a generated logo or starting from a sketch.
- "Negative prompt" field: include `text, photorealistic, 3D, shadow, gradient, complex, busy, watermark` for clean vector-style results.
- "PhotoReal" mode: turn OFF for logos.

**Example:**

```
Prompt: Vector logo of a single leaf forming the letter Y, minimalist Swiss design, 
forest green, flat illustration, clean geometric, white background

Negative: text, lettering, photorealistic, 3D, shadow, gradient, complex, busy, 
watermark, signature, multiple colors

Model: Leonardo Phoenix
Element: Logo (strength 0.3)
Guidance scale: 7
```

## Flux (1.1 Pro, Dev, Schnell)

Flux is the strongest of these tools for text rendering, which matters for wordmarks and combination marks where the type needs to read cleanly. Flux uses natural language prompts and is less reliant on prompt engineering than Midjourney.

**Variant choice:**

- Flux 1.1 Pro: highest quality, slower, paid via fal.ai, Replicate, or BFL API.
- Flux Dev: open weights, runs locally if the user has a strong GPU.
- Flux Schnell: fastest, lower quality, useful for rapid iteration.

**Prompt structure:**

Write naturally as if describing the finished logo to a designer. Flux follows literal instructions better than stylistic suggestions.

```
A minimalist vector logo featuring a single stylized leaf shaped like the letter Y, 
on a white background. Single forest green color. Flat geometric design with clean 
lines, no gradients, no shadows. Centered composition.
```

**For wordmarks specifically:**

Flux is unusually good at rendering specified text. Spell the brand name in quotes and specify the typographic character.

```
Wordmark logo for the brand "Sapling". Custom geometric sans-serif lettering with 
slight humanist warmth. Single dark forest green color on white. Letter spacing 
slightly wide. Flat clean design.
```

Verify spelling in the output; even Flux occasionally gets letters wrong.

## Imagen (3, 4)

Imagen, accessible via Vertex AI or the Gemini app, is direct and natural-language native. Strong text rendering, less stylistic range than Midjourney.

**Prompt structure:**

```
A clean vector logo. [Description of mark]. [Style]. [Color]. [Background].
```

**Example:**

```
A clean vector logo. A stylized leaf shape forming the letter Y, drawn with a 
single continuous line. Minimalist Swiss design influence. Forest green on a 
white background. No text, no shadows, no gradients.
```

Imagen does not support negative prompts in the same way as Midjourney or Leonardo. Build avoidance into the positive prompt: "no text", "no shadows", "single color only".

## DALL-E 3 (via ChatGPT or API)

DALL-E 3 embellishes prompts unless told not to. For logos, this is usually counterproductive because embellishment adds detail that hurts simplicity.

**Suppress embellishment:**

When using via ChatGPT, prepend: "Use this exact prompt without modification or embellishment:" then provide the prompt.

**Prompt structure:**

```
Minimalist vector logo. [Subject]. [Style]. [Color]. White background. 
Flat design, no gradients, no shadows, no 3D, no text.
```

DALL-E 3 has no negative prompt field; bake exclusions into the prompt.

## Cross-tool principles

**Aspect ratio:**
- 1:1 for symbol marks and app icons.
- 3:1 to 4:1 for horizontal wordmarks.
- 1:2 to 1:3 for stacked combination marks (use sparingly; harder to generate well).

**Color specification:**

Specify color by name AND hex if possible: "forest green (#1F4D2C)". Most tools handle named colors better than hex alone, but hex helps when the brand has a precise palette.

**Style reference images:**

If the brief includes reference logos, upload them as style references where the tool supports it (Midjourney `--sref`, Leonardo Image Prompt, Flux via image-to-image, ChatGPT image attachment for DALL-E 3 inspiration). This is more powerful than describing the style in words.

**Curation:**

Generation is cheap; curation is the work. Generate 8 to 20 candidates per direction, narrow to 3 to 5 finalists against the brief, then refine. The Phase 4 critique applies to image-gen output the same way it applies to SVG output: hold every candidate against strategy fidelity, design fundamentals, versatility, and distinctiveness.

**Vector conversion:**

Image-gen tools produce raster output (PNG, JPG, WebP). To use the result as a logo, the user will need to vectorize. Recommended path:
1. Generate at the highest resolution the tool offers.
2. Vectorize via Adobe Illustrator's Image Trace, Inkscape's trace bitmap, or vectorizer.ai.
3. Clean up nodes manually; auto-trace produces overcomplicated paths.
4. Recreate in vector software if the trace is poor (often the case for refined logos).

This step is where the gap between "looks good as image-gen output" and "works as a usable logo" becomes obvious. Flag this to the user upfront if they expect a finished SVG from the image-gen path.

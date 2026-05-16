# Nikki Logo Lab

A Claude Code skill by Nicola Harvey for developing brand marks through a strategy-first workflow. Four sequential phases: strategy extraction, design brief, execution (SVG code, image-gen prompts, or variation exploration), and critique.

The strategy phase is not optional. A mark without a strategy brief defaults to whatever visual conventions are popular this year. Nikki Logo Lab is built to prevent that.

## What it does

**Phase 1: Strategy extraction**
Pulls out positioning, audience, voice, and competitive context before any visual work begins. If you push back on this phase, Nikki Logo Lab runs a compressed three-question version rather than skipping it entirely.

**Phase 2: Design brief**
Produces a written brief covering mark type recommendation, visual direction (with voice-to-visual translation), color direction, typography direction, logo misuse specification, and the application contexts it needs to survive (favicon, single-color, reversed, dark mode, etc.).

**Phase 3: Execution**
Three paths depending on the brief and how open the visual direction is:
- SVG generation for wordmarks, lettermarks, monograms, and simple geometric or abstract marks. Includes a minimum size and clear space specification, file format export guidance, and an HTML specimen sheet.
- Structured image-gen prompts (Midjourney, Leonardo, Flux, Imagen, DALL-E) for pictorial marks, illustrative marks, mascots, and anything requiring texture or stylization.
- Variation exploration when the brief is locked but the visual direction is still open. Holds a Core DNA constant, defines explicit design levers, and generates 8 to 12 variations each pulling a single lever. Each variation gets a status badge (Strong candidate / Worth testing / Documented for the file) applied during generation. Exploration precedes first-pass delivery; it does not replace it.

A hybrid of SVG and image-gen is common for combination marks.

**Phase 4: Critique**
Works through strategy fidelity, design fundamentals (legibility, single-color, reversed, optical balance, color-blindness simulation), versatility (lockup forms, application contexts), and distinctiveness. Each issue gets a specific refinement recommendation, not just a problem description. When Phase 3 ran in variation exploration mode, Phase 4 critiques the selected variation forward — the exploration set was already graded inline.

## Honest limits

Some things Nikki Logo Lab cannot deliver well. It will name these when they come up rather than producing low-quality output.

- **Custom letterform design.** True bespoke type requires a type designer. The skill will recommend handoff or a humanist off-the-shelf alternative.
- **Optical balance in complex pictorial marks.** Claude cannot produce the refined, hand-crafted balance a skilled logo designer achieves. The image-gen path is the bridge for pictorial work.
- **Animated logo systems.** The skill can describe motion direction and easing intent, but cannot produce After Effects, Lottie, or Rive files.
- **Cultural or regional appropriateness.** Visual conventions and semiotic associations vary in ways Claude will miss. Recommend a local cultural review before finalizing for any unfamiliar market.
- **Trademark clearance.** The skill does not search registries. Run a search via your relevant national registry (IP Australia, USPTO, WIPO Madrid) before committing to a mark.

## Installing for Claude Code

Clone the repo directly into your skills directory:

```bash
git clone https://github.com/nicolakharvey/nikki-logo-lab.git ~/.claude/skills/nikki-logo-lab
```

Claude Code picks up skills from `~/.claude/skills/` automatically. No restart needed.

## Installing for Claude desktop

1. Download or clone this repo.
2. Zip the `nikki-logo-lab` folder.
3. In Claude desktop, go to Settings > Capabilities > Skills.
4. Upload the zip file.

## Best experience: use the Cowork tab in Claude desktop

Nikki Logo Lab works significantly better in the **Cowork tab in Claude desktop** than in Claude Code. The reason is simple: Claude desktop renders SVG inline in the conversation, so you see the actual mark as you iterate. Claude Code outputs SVG as a code block — you have to copy it into a browser to see it.

Install via the Claude desktop method above, then open a new conversation in the Cowork tab and start from there.

## Viewing your options — the specimen sheet

After Phase 3 generates your SVG marks, ask Claude to produce an HTML specimen sheet:

> "Generate an HTML specimen sheet for all the mark variants."

The specimen sheet is a self-contained HTML file that renders all nine deliverables in one view:

- Three lockup forms (horizontal, stacked, symbol-only) across the top
- Three color state sections: full color on white, single color on white, reversed on dark
- A scale row showing the primary lockup at large, medium, small, and favicon (16px) sizes
- A size and clear space specification block at the bottom

Open it in any browser. This is the best way to evaluate the full system before moving to critique — you can see at a glance which variants hold up and which need work.

## Using Nikki Logo Lab

Once installed, mention logos or brand identity work and Claude will use Nikki Logo Lab automatically. You can also invoke it directly:

> "Use Nikki Logo Lab to help me develop a brand mark for [brand name]."

You can enter at any phase. If you bring an existing mark and want a critique, Nikki Logo Lab will back-fill the strategy assumptions it is critiquing against so you can correct them if they are wrong.

If you are not sure which visual direction to take after the brief, say so. The skill will run variation exploration rather than committing to a first pass prematurely.

After Phase 3 SVG output, always ask for the specimen sheet before moving to critique.

---

Part of the **Nikki** suite of AI tools by [Nicola Harvey](https://linkedin.com/in/nicolakharvey).

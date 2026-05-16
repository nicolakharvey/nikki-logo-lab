# logo-development

A Claude Code skill for developing brand logos through a strategy-first workflow. It covers four sequential phases: strategy extraction, design brief, execution (SVG code, image-gen prompts, or variation exploration), and critique.

The strategy phase is not optional. A logo without a strategy brief defaults to whatever visual conventions are popular this year. This skill is built to prevent that.

## What it does

**Phase 1: Strategy extraction**
Pulls out positioning, audience, voice, and competitive context before any visual work begins. If you push back on this phase, the skill runs a compressed three-question version rather than skipping it entirely.

**Phase 2: Design brief**
Produces a written brief covering logo type recommendation, visual direction, color direction, typography direction, what the logo should NOT look like, and the application contexts it needs to survive (favicon, single-color, reversed, etc.).

**Phase 3: Execution**
Three paths depending on the brief and how open the visual direction is:
- SVG generation for wordmarks, lettermarks, monograms, and simple geometric or abstract marks.
- Structured image-gen prompts (Midjourney, Leonardo, Flux, Imagen, DALL-E) for pictorial marks, illustrative marks, mascots, and anything requiring texture or stylization.
- Variation exploration when the brief is locked but the visual direction is still open. Holds a Core DNA constant, defines explicit design levers, and generates 8 to 12 variations each pulling a single lever. Each variation gets a status badge (Strong candidate / Worth testing / Documented for the file) applied during generation. Exploration precedes first-pass delivery; it does not replace it.

A hybrid of SVG and image-gen is common for combination marks.

**Phase 4: Critique**
Works through strategy fidelity, design fundamentals (legibility, single-color, reversed, optical balance), versatility (lockup forms, application contexts), and distinctiveness. Each issue gets a specific refinement recommendation, not just a problem description. When Phase 3 ran in variation exploration mode, Phase 4 critiques the selected variation forward — the exploration set was already graded inline.

## Honest limits

Some things this skill cannot deliver well. It will name these when they come up rather than producing low-quality output.

- **Custom letterform design.** True bespoke type requires a type designer. The skill will recommend handoff or a humanist off-the-shelf alternative.
- **Optical balance in complex pictorial marks.** Claude cannot produce the refined, hand-crafted balance a skilled logo designer achieves. The image-gen path is the bridge for pictorial work.
- **Animated logo systems.** The skill can describe motion direction and easing intent, but cannot produce After Effects, Lottie, or Rive files.
- **Cultural or regional appropriateness.** Visual conventions and semiotic associations vary in ways Claude will miss. Recommend a local cultural review before finalizing for any unfamiliar market.
- **Trademark clearance.** The skill does not search registries. Run a search via your relevant national registry (IP Australia, USPTO, WIPO Madrid) before committing to a mark.

## Installing for Claude Code

Clone the repo directly into your skills directory:

```bash
git clone https://github.com/nicolakharvey/logo-development.git ~/.claude/skills/logo-development
```

Claude Code picks up skills from `~/.claude/skills/` automatically. No restart needed.

## Installing for Claude desktop

1. Download or clone this repo.
2. Zip the `logo-development` folder.
3. In Claude desktop, go to Settings > Capabilities > Skills.
4. Upload the zip file.

## Best experience: use the Cowork tab in Claude desktop

This skill works significantly better in the **Cowork tab in Claude desktop** than in Claude Code. The reason is simple: Claude desktop renders SVG inline in the conversation, so you see the actual mark as you iterate. Claude Code outputs SVG as a code block — you have to copy it into a browser to see it.

Install via the Claude desktop method above, then open a new conversation in the Cowork tab and start from there.

## Viewing your options — the specimen sheet

After Phase 3 generates your SVG marks, ask Claude to produce an HTML specimen sheet:

> "Generate an HTML specimen sheet for all the logo variants."

The specimen sheet is a self-contained HTML file that renders all nine deliverables in one view:

- Three lockup forms (horizontal, stacked, symbol-only) across the top
- Three color state sections: full color on white, single color on white, reversed on dark
- A scale row showing the primary lockup at large, medium, small, and favicon (16px) sizes

Open it in any browser. This is the best way to evaluate the full system before moving to critique — you can see at a glance which variants hold up and which need work.

## Using the skill

Once installed, mention logos or brand identity work and Claude will use this skill automatically. You can also invoke it directly:

> "Use the logo-development skill to help me design a logo for [brand name]."

You can enter at any phase. If you bring an existing logo and want a critique, Claude will back-fill the strategy assumptions it is critiquing against so you can correct them if they are wrong.

If you are not sure which visual direction to take after the brief, say so. The skill will run variation exploration rather than committing to a first pass prematurely.

After Phase 3 SVG output, always ask for the specimen sheet before moving to critique.

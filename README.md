# Visual Story Kit

A reusable design and prompt system for creating consistent character-based visual stories with AI.

Visual Story Kit is a reusable guide system for creating consistent character-based visual stories with ChatGPT and image generation tools.

## What This Is

Visual Story Kit is a Korean-friendly production kit for AI-assisted visual stories: Instagram carousel comics, instatoon, card-based explainers, essay comics, brand stories, and short-form storyboards.

It is designed for creators who want to keep characters, style, story structure, and prompts consistent across multiple cards or episodes.

## Core Idea

```text
Plan first, render later.
```

Do not generate images first. Start with the brief, story plan, card structure, character lock, and review checkpoints. Then generate images card by card.

## What We Borrow From Good Pipelines

This repository intentionally takes the useful parts from auto-instatoon-style tools and instatoon production pipelines:

- Brief-to-carousel planning
- Card-by-card fields: headline, scene, narration, dialogue, caption, visual prompt
- Review-first workflow before rendering images
- Reference-based character consistency
- Interactive checkpoints between stages
- Single-card regeneration instead of full episode restart
- Optional carousel-to-Reels adaptation
- Local/private workflow awareness for drafts and references

## Production Workflow

```text
1. Brief
   Define audience, goal, topic, format, tone, and constraints.

2. Story Plan
   Convert the brief into a clear beginning, middle, and ending.

3. Card Planning
   Write each card with headline, scene, narration, dialogue, caption, and visual prompt.

4. Character Lock
   Fix character identity, references, expressions, poses, outfit, props, and must-avoid rules.

5. Prompt Generation
   Create image prompts from approved cards and fixed character settings.

6. Image Review
   Check character consistency, text readability, layout safety, and story flow.

7. Regeneration
   Rewrite only the failed card prompt and regenerate that card.

8. Export
   Prepare final carousel images and optional Reels adaptation.
```

## Core Features

- Korean guide documents for AI visual story production
- Character pack system: profile, hex palette, and reference images as one unit
- 4-view (turnaround), expression sheet, and pose sheet generation guides
- Scene and prop profiles for background and asset consistency
- 4-card, 6-card, and 8-card storyboard structures
- Pacing guide for card-to-card rhythm and composition contrast
- Prompt templates for planning (JSON card plans), image generation, and regeneration
- Review checklists with stage-by-stage approval gates
- Canvas rules for Instagram feed production

## Repository Structure

```text
docs/
  workflow-ko.md                      # 8-step production workflow (Korean)
character-system/
  character-profile-template.md       # quick-start character profile
  character-pack-template.md          # full pack: profile + palette + references
  four-view-reference-guide.md        # turnaround, expression, pose sheet prompts
asset-system/
  scene-profile-template.md           # recurring location consistency
  prop-profile-template.md            # prop and costume continuity
story-system/
  four-card-storyboard.md
  six-card-storyboard.md
  eight-card-storyboard.md
  pacing-guide.md                     # card-to-card rhythm rules
prompt-system/
  planning-prompt.md                  # brief -> story plan -> JSON card plan
  image-prompt.md                     # per-card image generation
  regeneration-prompt.md              # single-card regeneration
checklists/
  review-checklist.md                 # approval gates and publish checklist
```

## Canvas Rules

- Feed canvas: 1080 x 1350 px
- Safe drawing area: 1080 x 1080 px inside the canvas
- Use a separate guide layer for the safe area
- Keep key characters, text, and story beats inside the safe area
- Use the lower extra space only when it supports the feed layout

## Start Here

1. Read `docs/workflow-ko.md`.
2. Build a character pack with `character-system/character-pack-template.md`.
3. Create reference sheets with `character-system/four-view-reference-guide.md`.
4. Plan an episode with `prompt-system/planning-prompt.md` and a storyboard
   from `story-system/` (4, 6, or 8 cards).
5. Check rhythm with `story-system/pacing-guide.md`.
6. Generate prompts with `prompt-system/image-prompt.md`.
7. Review with `checklists/review-checklist.md`.
8. Regenerate weak cards with `prompt-system/regeneration-prompt.md`.

Approval gates: story plan -> card plan -> references -> card images.
Do not generate card images before the character references are approved.

## License

MIT

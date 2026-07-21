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
- Character profile templates for stable visual identity
- Reference image, expression sheet, and pose sheet guidance
- 4-card, 6-card, and 8-card storyboard structures
- Prompt templates for planning, image generation, and regeneration
- Checklists for character consistency and publishing readiness
- Canvas rules for Instagram feed production

## Canvas Rules

- Feed canvas: 1080 x 1350 px
- Safe drawing area: 1080 x 1080 px inside the canvas
- Use a separate guide layer for the safe area
- Keep key characters, text, and story beats inside the safe area
- Use the lower extra space only when it supports the feed layout

## Start Here

1. Read `docs/workflow-ko.md`.
2. Fill out `character-system/character-profile-template.md`.
3. Plan an episode with `story-system/six-card-storyboard.md`.
4. Generate prompts with `prompt-system/image-prompt.md`.
5. Regenerate weak cards with `prompt-system/regeneration-prompt.md`.

## License

MIT

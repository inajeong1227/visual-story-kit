# ToonPrint AI

A reusable design and prompt system for creating consistent Instagram comics with AI.

## Purpose

ToonPrint AI is a reusable guide system for people who want to create Instagram-style comics with ChatGPT and image generation tools while keeping characters, layouts, and visual style consistent.

It is designed as a shared production framework, not a topic-specific comic template.

## Core Features

- Character setting templates for stable visual identity
- Storyboard structure for short Instagram carousel comics
- Prompt rules for consistent AI-assisted drawing
- Style guidelines for line, color, lettering, and composition
- Review checklist for character and layout consistency

## Canvas Rules

- Feed canvas: 1080 x 1350 px
- Safe drawing area: 1080 x 1080 px inside the canvas
- Use a separate guide layer for the safe area
- Keep key characters, text, and story beats inside the safe area
- Use the lower extra space only when it supports the feed layout

## Planned Directory Structure

```text
character-system/
  character-template.md
  visual-identity.md
  expression-library.md
  pose-library.md

style-system/
  line-style.md
  color-system.md
  typography.md
  composition.md

templates/
  character-profile.yaml
  episode-brief.md
  six-panel-storyboard.md
  image-prompt-template.md

examples/
  sample-character/
  sample-episode/
```

## License

MIT

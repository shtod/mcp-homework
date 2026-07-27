---
name: intro-ppt-generator
description: Generate a beautiful self-introduction HTML PPT from a markdown profile. Use this skill when the user wants to create a presentation based on a personal profile (自我介绍), produce an HTML slideshow from markdown content, or publish such a PPT to GitHub. Also use when asked to "generate an HTML PPT", "make a slideshow from my intro", or "create a presentation from 自我介绍".
---

# Self-Introduction PPT Generator

Generate a polished, multi-page HTML PPT from a personal introduction markdown file. Supports keyboard navigation, clickable dots, and responsive design.

## When to Use

- User provides a markdown profile (e.g., `自我介绍.md`) and asks for an HTML PPT
- User wants to create a slideshow-style self-introduction
- User asks to expand a PPT with hometown info, skills, or creative content
- User wants the PPT published to a GitHub repository

## Workflow

### Step 1: Read the Source Content

Locate and read the source markdown file from:
- A GitHub repo (use the GitHub MCP tool)
- A local file on disk
- Content provided directly by the user

Extract key sections: name, personality traits, daily habits, hobbies, training attitude, and closing remarks.

### Step 2: Infer Additional Content

Based on clues in the source text, proactively suggest or add slides for:

- **Hometown** — If the user mentions or confirms their hometown, add a slide featuring local specialties, cultural highlights, and historical facts. Research famous local products and landmarks.
- **Coding Journey** — Craft a "My Story with Programming" slide: how they started, their learning style, why they chose this path. Use reasonable creative inference.
- **Skills Toolbox** — If they mention any tech stack (Java, Docker, Git, etc.), create a visual skills inventory slide with icon-style tags.

### Step 3: Generate the HTML PPT

Use the design system from `assets/template.html` as reference. Key structure:

| Slide | Tag | Content Pattern |
|-------|-----|-----------------|
| 1 | Cover | Greeting + Name, purple gradient |
| 2 | ABOUT ME | 3 personality cards in `.card-row` |
| 3 | DAILY LIFE | 4 items in `.habit-list` |
| 4 | HOMETOWN | Intro + 2×2 grid of `.hometown-item` |
| 5 | HOBBIES | 2×2 grid of `.hobby-item` |
| 6 | MY STORY | 3 `.story-block` narratives |
| 7 | SKILLS | 6 `.skill-tag` + extra note |
| 8 | ATTITUDE | 3 `.mindset-block` items |
| 9 | Closing | Green gradient, thanks |

### Step 4: Save and Publish

1. Save to Desktop as `自我介绍.html`
2. Upload/update to the GitHub repo via MCP tool

## Customization Guidelines

### Adding Slides
1. Add CSS in the `<style>` block before the closing `</style>`
2. Insert slide HTML between existing slides
3. Update all `data-index` attributes sequentially
4. Update all `slide-number` texts (e.g., `3 / 7` → `3 / 9`)
5. Add responsive rules for new grid classes

### Color Palette
- Purple: `#667eea` → `#764ba2` (cover, section tags)
- Warm earth: `#fdf6f0`, `#e8a850`, `#6b3a2a` (hometown)
- Blue: `#f0f4ff`, `#4a6cf7`, `#2d3b6b` (coding story)
- Green: `#11998e` → `#38ef7d` (closing)
- Base: `#f8f9fc`, `#1a1a2e` (backgrounds)

# GitHub Profile Redesign

**Date:** 2026-04-24  
**Status:** Approved

---

## Overview

Rebuild the GitHub profile README from scratch. Remove visual clutter, delete the 3D contribution workflow, and establish a clean dark-mode aesthetic with green accents.

---

## Aesthetic

- **Background:** GitHub dark (`#0d1117`)
- **Primary text:** `#e6edf3`
- **Secondary / muted text:** `#7d8590`
- **Accent (green):** `#3fb950` — used only on the `# joel` header
- **Feel:** Minimal, terminal-adjacent, no badge walls, no widget stacks

---

## Sections (in order)

### 1. Header / Intro

Two-column layout using an HTML table (GitHub markdown compatible):

- **Left:** Small circular profile photo (`src/me.jpeg`, ~80px, `border-radius: 50%`)
- **Right:**
  - `# joel` in green (`#3fb950`) — implemented as an inline SVG image (GitHub strips CSS/style tags but renders `<img>` pointing to an SVG data URI or a raw SVG file in the repo). A `profile-header.svg` file in `src/` will render the green name text.
  - Tagline: `Data scientist. Builder. Interested in agentic architecture, automation, and personalization.`
  - Three social links (icon badges, no label text): LinkedIn · Twitter · Instagram

### 2. What I Build

Plain list, no badges, each project name is a link:

| Project | Description |
|---|---|
| [Joel's Mindscape](https://joeloffbeat.github.io) | 2D isometric web experience built with Three.js and Vite |
| [Holocorn](https://github.com/joeloffbeat/holocorn) | Tool for managing public relations |
| Genesis | Agent world sandbox |

### 3. Currently

> Building data pipelines, curating a personal design system, and pushing the edges of agentic architecture.

### 4. GitHub Activity

Single centered widget — activity graph only:

```
https://github-readme-activity-graph.vercel.app/graph
  ?username=joeloffbeat
  &hide_border=true
  &bg_color=0d1117
  &color=7d8590
  &line=3fb950
  &point=3fb950
  &area=true
  &area_color=3fb950
  &title_color=3fb950
```

---

## Removed

- 3D contribution graph (`.github/workflows/profile-3d.yml` deleted, SVG reference removed)
- GitHub stats card
- Top languages card
- Streak stats
- Trophy widget
- Visitor badge
- Tech stack badge wall
- Social links: YouTube, Twitch, Patreon

---

## Files to Change

| File | Action |
|---|---|
| `README.md` | Full rewrite |
| `.github/workflows/profile-3d.yml` | Delete |
| `profile-3d-contrib/` | Delete directory if it exists |

---

## Color Reference

| Token | Hex | Used for |
|---|---|---|
| bg | `#0d1117` | Widget backgrounds |
| text | `#e6edf3` | Primary text |
| muted | `#7d8590` | Secondary text, graph color |
| green | `#3fb950` | Name header accent, graph line/point |

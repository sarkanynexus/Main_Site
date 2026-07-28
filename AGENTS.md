# Sarkany Nexus — Agent Guide

Personal static site (Jekyll + Decap CMS + Netlify). Vibe-code freely, but **safety first** and **public presentation second**.

## Priorities (in order)

1. **Safety** — never break deploys, never leak secrets, never delete content casually, never rewrite the stack without an explicit ask.
2. **Presentation** — the public site must look intentional and professional (book / author / brand quality, not a template).
3. **Consistency** — follow existing folders, CMS fields, layouts, and CSS variables.

## Stack (do not casually change)

Jekyll 4 · Markdown collections · Liquid layouts · plain CSS · Decap CMS · Netlify Identity/Git Gateway · GitHub → Netlify.

## Critical controls

| Control | Where | Meaning |
|---------|--------|---------|
| `coming_soon` | `_config.yml` | `true` = public coming-soon page; hide content nav |
| `published` | front matter / CMS | `false` = keep in repo, hide from site (prefer this over deleting) |

## Where things live

- Pages: `index.md`, `about/`, `contact/`, `stories/`, `boardgame/`, `projects/`
- Content: `_stories/`, `_updates/`, `_projects/`
- Layouts: `_layouts/`
- Styles: `assets/style.css`
- CMS: `admin/config.yml`
- Uploads: `assets/uploads/`

## Rules & skills

- Rules: `.cursor/rules/` (always-on safety + scoped design/content)
- Skills: `.cursor/skills/` — use **safe-change**, **visual-polish**, **publish-content** when relevant

## Before shipping visual or homepage work

Read and follow `.cursor/skills/visual-polish/SKILL.md`.

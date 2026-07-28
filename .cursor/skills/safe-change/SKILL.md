---
name: safe-change
description: Safety checklist before editing or shipping changes to Sarkany Nexus. Use when vibe-coding, making structural changes, editing config/CMS/layouts, preparing a deploy, or when the user asks to change something that could affect the live site.
---

# Safe change workflow

Use this before non-trivial edits on this repo.

## 1. Classify the change

| Risk | Examples | Action |
|------|----------|--------|
| Low | Copy tweak, CSS color, fix typo | Edit directly |
| Medium | Layout/Liquid, new page, CMS field add | Edit + verify listings/`published` behavior |
| High | `coming_soon`, mass publish, delete content, stack/hosting | **Confirm with user** first |

## 2. Pre-flight

- [ ] No secrets will be committed
- [ ] Prefer `published: false` over deleting content
- [ ] CMS field names stay compatible with existing front matter
- [ ] Unpublished filter still used in any new listing loops
- [ ] `/admin` Identity + Decap scripts left intact unless asked

## 3. Prefer reversible patterns

- Feature flags: `coming_soon` in `_config.yml`
- Visibility: `published` on collection docs
- Keep old CSS variables; add new ones rather than silently renaming used tokens

## 4. Before saying "done"

- Summarize what became public vs still hidden
- Call out anything that needs a Netlify redeploy or CMS re-login
- Do not push or commit unless the user asked

## 5. Rollback mental model

| Mistake | Fix |
|---------|-----|
| Published too early | Set `published: false`, push |
| Site too empty/public | Toggle `coming_soon` |
| Bad CMS field rename | Restore `admin/config.yml` + front matter |

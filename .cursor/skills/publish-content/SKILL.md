---
name: publish-content
description: Publishes, unpublishes, or prepares Sarkany Nexus content using published flags and coming_soon mode. Use when taking posts offline without deleting, going live, launching a book page, toggling drafts, or managing Decap CMS visibility.
---

# Publish / unpublish content

## Take offline (keep in project)

In the Markdown front matter or Decap **Published** toggle:

```yaml
published: false
```

Effects:

- Hidden from home/listing Liquid loops (`where_exp` on `published`)
- Jekyll does not write a public page for that document

Do **not** delete the file or its images unless the user explicitly wants permanent removal.

## Put online

```yaml
published: true
```

Ensure `coming_soon: false` in `_config.yml` if the full site should be visible (nav + listings). Otherwise content can be published but the public homepage may still be coming-soon.

## Site-wide coming soon

```yaml
# _config.yml
coming_soon: true   # minimal public face
coming_soon: false  # full site nav + homepage sections
```

## Book / launch promo (when asked)

1. Confirm whether coming-soon should end.
2. Add or enable the project/story with strong cover + excerpt.
3. Run **visual-polish** on the landing surface before calling it done.
4. Prefer a dedicated project entry or homepage feature section over cluttering every page.

## CMS note

`admin/config.yml` exposes `published` as a boolean on stories, updates, and projects. Keep that field; listings depend on it.

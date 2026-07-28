# Sarkany Nexus

Personal site for stories, boardgame design updates, and portfolio work.

**Stack:** Jekyll (static site) · Markdown content · Decap CMS · Netlify (build + host + Identity) · domain via GoDaddy

---

## How it works

1. You write or edit content in **Decap CMS** (`/admin`) or as Markdown files in the repo.
2. Changes are committed to **GitHub** (`main`).
3. **Netlify** builds the site with Jekyll and serves it over HTTPS.
4. Your **GoDaddy** domain points at Netlify via DNS.

---

## Local development

Requirements: Ruby 3+ and Bundler.

```bash
bundle install
bundle exec jekyll serve
```

Open [http://127.0.0.1:4000](http://127.0.0.1:4000).

---

## Content

| Folder | Collection | Purpose |
|--------|------------|---------|
| `_stories/` | stories | Fiction / prose |
| `_updates/` | updates | Boardgame design notes |
| `_projects/` | projects | Portfolio items |

Listing pages: `/stories/`, `/boardgame/`, `/projects/`.

### Publish on/off switch

Each story, update, and project has a **Published** field (boolean).

- **On** (`published: true`) — visible on the live site (and its page is built).
- **Off** (`published: false`) — stays in the repo / CMS, but is hidden from listings and has no public page.

Toggle it in Decap CMS, or set `published: false` in the file’s front matter.

### Coming soon mode

In `_config.yml`:

```yaml
coming_soon: true
```

When `true`, the homepage is a simple coming-soon page and content nav links are hidden. Set to `false` when you are ready to show the full site.

---

## CMS (Decap + Netlify)

1. Site is connected to Netlify with **Identity** and **Git Gateway** enabled.
2. Invite yourself (or users) under Netlify → Identity.
3. Open `https://YOUR-DOMAIN/admin/` and log in.
4. Edit Stories, Boardgame Updates, or Portfolio. Uploads go to `assets/uploads/`.

Editorial workflow is enabled: drafts can go through Netlify’s CMS review flow before landing on `main`.

---

## Deploy

Netlify builds from the GitHub repo on every push to `main`. Typical build settings:

- **Build command:** `jekyll build`
- **Publish directory:** `_site`

(Or use Netlify’s Jekyll preset if offered.)

---

## Go live checklist

1. Set `coming_soon: false` in `_config.yml`.
2. Turn **Published** on for the pieces you want public.
3. Push to `main` and confirm the Netlify deploy.

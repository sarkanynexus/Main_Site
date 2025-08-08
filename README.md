# Jekyll + Decap CMS Starter (GitHub Pages)

## 1) Use this repo
- Upload this folder to a new GitHub repository.
- In `admin/config.yml`, set `repo: YOUR_GITHUB_USERNAME/YOUR_REPO_NAME`.
- Commit & push.

## 2) Enable GitHub Pages
- Settings → Pages → Build from branch → `main` → `/ (root)`.

## 3) GitHub OAuth App (for Decap CMS login)
- Settings → Developer settings → OAuth Apps → New OAuth App.
- Homepage URL: `https://YOUR_GITHUB_USERNAME.github.io/YOUR_REPO_NAME/`
- Authorization callback URL: `https://YOUR_GITHUB_USERNAME.github.io/YOUR_REPO_NAME/admin/callback/`
- Copy the Client ID (Client Secret not needed for implicit flow).

## 4) Log in to the CMS
- Visit `https://YOUR_GITHUB_USERNAME.github.io/YOUR_REPO_NAME/admin/` and authorize with GitHub.
- The CMS will commit Markdown files into `_stories/` on your repo.

## 5) Add content
- Create stories in `/admin` or add Markdown files directly under `_stories/` with front matter.

## 6) Custom domain (GoDaddy)
- In GitHub Pages → Custom domain → add your domain.
- Follow GitHub’s DNS instructions (CNAME for `www`, and appropriate records for apex).

Happy writing!

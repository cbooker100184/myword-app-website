# My Word public website (GitHub Pages)

Static site for **https://myword-app.com/**.

| Path | File |
| --- | --- |
| `/` | `index.html` |
| `/privacy` | `privacy/index.html` |
| `/delete-account` | `delete-account/index.html` |

This folder is separate from the Expo app build. It does not contain API keys or `.env` values.

**Status:** Files are ready locally. Nothing has been published and DNS has not been changed.

## Preview locally

From this directory:

```bash
cd website
python3 -m http.server 5500
```

Open:

- http://127.0.0.1:5500/
- http://127.0.0.1:5500/privacy/
- http://127.0.0.1:5500/delete-account/

These pages are plain HTML. No sign-in is required.

## GitHub Pages setup (do this when you approve publish)

1. Create a GitHub repository for this site (recommended: a dedicated repo such as `myword-app-website`, or publish only the `website/` folder from a `gh-pages` branch / Actions workflow). Do **not** upload `.env` or app secrets.
2. Put the contents of this `website/` folder at the root of the publishing branch (so `CNAME`, `index.html`, `privacy/`, `delete-account/`, `styles.css`, and `assets/` are at the site root).
3. In the repo: **Settings → Pages**.
4. Set the source to the branch that contains these files (usually `main` or `gh-pages`, `/ (root)`).
5. Under **Custom domain**, enter `myword-app.com` and save. GitHub should keep or recreate the `CNAME` file (already included here with `myword-app.com`).
6. After DNS works, tick **Enforce HTTPS**. It can take up to 24 hours for the certificate option to appear.

Recommended custom domain in GitHub Pages settings: `myword-app.com` (apex). With the DNS below, `www.myword-app.com` will redirect to the apex (or the reverse, depending which you set as the primary custom domain).

## DNS at 123-reg (do not apply until you approve)

Values below match [GitHub’s current Pages custom domain docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site) (A / AAAA for apex; CNAME for `www`).

Replace `YOUR-GITHUB-USERNAME` with the GitHub user or organisation that owns the Pages site (for a user site that is often `YOUR-GITHUB-USERNAME.github.io`; for an org site, `YOUR-ORG.github.io`). Point the `www` CNAME at that host **without** a repository name suffix.

### Apex `myword-app.com`

| Type | Host / name | Value |
| --- | --- | --- |
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |
| AAAA | `@` | `2606:50c0:8000::153` |
| AAAA | `@` | `2606:50c0:8001::153` |
| AAAA | `@` | `2606:50c0:8002::153` |
| AAAA | `@` | `2606:50c0:8003::153` |

### `www.myword-app.com`

| Type | Host / name | Value |
| --- | --- | --- |
| CNAME | `www` | `YOUR-GITHUB-USERNAME.github.io` |

Remove conflicting default A/CNAME records 123-reg may have created for `@` or `www`. Do not use a wildcard `*.myword-app.com` record.

DNS can take up to 24 hours. Then enable **Enforce HTTPS** in GitHub Pages settings.

## Confirm before public launch

- Registered office address (and UK registration part if required on the site)
- Privacy Policy effective / adoption date
- ICO data protection fee / registration status
- Lawful bases and retention periods (including anonymised financial archive)
- Legal review of Privacy Policy wording
- How 18+ will be enforced at sign-up
- Exact GitHub username/org for the `www` CNAME target

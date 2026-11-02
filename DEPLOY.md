# Public site

These are the public pages referenced by the app registration on TikTok's
developer platform — the Terms of Service, the Privacy Policy, and a small
landing page.

They are plain static HTML with no build step and no dependencies.

## Where they live

The source of truth is this folder. The published copy is in a **separate
public repository**, because the pipeline repository is private and GitHub
Pages will not publish from a private repository on a free org plan.

| | |
|---|---|
| Public repo | `Kwentong-Barbero/legal` |
| `main` branch | the source files, for editing and history |
| `gh-pages` branch | what Pages actually serves |
| Live at | `https://kwentong-barbero.github.io/legal/` |

## Pushing a change

The `gh-pages` branch has to be refreshed after every edit, or Pages keeps
serving the old copy. From the public repo:

```bash
git clone git@github.com:Kwentong-Barbero/legal.git
cd legal

# copy the edited files across
cp /path/to/short-video-pipeline/site/*.html .

# refresh gh-pages from the new main
git checkout main && git pull
git checkout -B gh-pages
git rm -rq --cached . && rm -rf .github DEPLOY.md
git add -A && git commit -m "Update site"
git push origin gh-pages
```

## The URLs in the TikTok portal

These are the values to paste into the app configuration:

| Field | URL |
|---|---|
| Terms of Service URL | `https://kwentong-barbero.github.io/legal/terms.html` |
| Privacy Policy URL | `https://kwentong-barbero.github.io/legal/privacy.html` |
| Web/Desktop URL | `https://kwentong-barbero.github.io/legal/` |

Keep them consistent with whatever the site is actually served from.

## Note on the contact address

Both pages list `barberoscutmedia@gmail.com` as the contact address — that is
the address registered as the org owner on the TikTok developer platform. If
it should be a different one, change it in `terms.html` and `privacy.html`.

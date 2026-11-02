# Public site

These are the public pages referenced by the app registration on TikTok's
developer platform — the Terms of Service, the Privacy Policy, and a small
landing page.

They are plain static HTML with no build step and no dependencies.

## Publishing them

The pages have to be reachable over `https://` from the public internet for
TikTok's reviewers to open them. The repository they currently live in is
private, so they have to be served from somewhere public. Options:

**GitHub Pages (recommended).** Put these files in a public repository and
turn on Pages for it:

```bash
# in a public repo, e.g. Kwentong-Barbero/kwentong-barbero-site
cp site/*.html .
# then: Settings -> Pages -> Source: Deploy from a branch -> main / (root)
```

The result is served from `https://<org>.github.io/<repo>/`.

**Any static host.** The three HTML files are self-contained, so they also
work on Netlify, Cloudflare Pages, Vercel, or a plain web server. Point the
root at `index.html` and keep `terms.html` and `privacy.html` beside it.

## Updating the URLs in the TikTok portal

Once the site is live, the three URLs in the TikTok app configuration are:

| Field | URL |
|---|---|
| Terms of Service URL | `https://<host>/terms.html` |
| Privacy Policy URL | `https://<host>/privacy.html` |
| Web/Desktop URL | `https://<host>/` |

Keep them consistent with what the site is actually served from.

## Note on the contact address

Both pages list `barberoscutmedia@gmail.com` as the contact address — that is
the address registered as the org owner on the TikTok developer platform. If
it should be a different one, change it in `terms.html` and `privacy.html`.

# Exora Magazine website

Static site for Exora Magazine, an independent magazine for people who choose to live
together: coliving, cohousing, eco-villages, shared homes and communities.

- `index.html`: landing page
- `about.html`: the story behind Exora Magazine
- `policies.html`: privacy, pre-orders and refunds
- `gift/`: one page per downloadable gift card, so downloads show up in analytics
- `social/`: Instagram tiles (Drive is the current source for social)
- `favicon.svg`: browser tab icon

No build step: the repository root is the site.

Hosted on Cloudflare Workers. Workers Builds runs `npx wrangler deploy` on every push to
`main`, so a push is a live deploy — there is no staging. `.assetsignore` keeps the
repository's own files off the site. Config is in `wrangler.jsonc`.

Run it locally with any static server, for example:

    python3 -m http.server 8787

# BerlinDistance

Find where two people can both live based on public-transport commute time to
each of their jobs. Drag each marker to a job, set a max commute time per
person, and the **green overlap** is the area reachable from both.

It's a single static page ([index.html](index.html)) — no backend. Transit
reachability comes from the [Geoapify Isoline API](https://www.geoapify.com/isoline-api/)
(free tier), called directly from the browser; the overlap is computed
client-side with [Turf.js](https://turfjs.org/).

## Test locally

```sh
open index.html
```

Paste a free Geoapify key (from [myprojects.geoapify.com](https://myprojects.geoapify.com/),
no card needed) into the key field — it's saved in your browser only — then drag
a marker.

## Publish to GitHub Pages with the key prefilled

The key is **never committed**. It's stored as a repository secret and injected
into the page only at deploy time by [.github/workflows/deploy.yml](.github/workflows/deploy.yml).

One-time setup:

1. **Add the secret:** repo **Settings → Secrets and variables → Actions →
   New repository secret**. Name it `GEOAPIFY_KEY`, value = your key.
2. **Set the Pages source to Actions:** repo **Settings → Pages → Build and
   deployment → Source = "GitHub Actions"** (not "Deploy from a branch").
3. Push to `main`. The workflow builds and publishes; the live page works with
   no manual key entry.

## ⚠️ About the key

Keeping the key out of the repo does **not** keep it off the live site — any
client-side app sends the key in its network requests, so it's visible in the
browser. The real protection is to **restrict the key to your domain** in the
Geoapify dashboard:

- Allowed origins / HTTP referrers → add your Pages domain, e.g.
  `https://<owner>.github.io/*` (and `http://localhost/*` if you test locally).

Then even though the key is visible, it only works from your site and no one
can drain your daily quota.

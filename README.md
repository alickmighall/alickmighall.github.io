# miggle.one

Personal brand site for Alick Mighall — fractional AI &amp; data advisor for sports clubs, federations and platforms. Deployed via GitHub Pages at [miggle.one](https://miggle.one).

## Preview locally

No build step required. Open `index.html` directly in a browser, or serve from the repo root:

```
npx serve .
# or
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Analytics

A placeholder comment in `<head>` of `index.html` marks where to add analytics. To add Google Analytics 4 or a privacy-respecting alternative (e.g. Fathom, Plausible), insert the tracking snippet there.

## Contact form

The form on the homepage submits via `fetch()` POST to a Google Apps Script endpoint that writes to a Google Sheet. The endpoint URL is in the inline `<script>` at the bottom of `index.html`. Do not change the endpoint without updating the Google Apps Script deployment.

On success, the visitor is redirected to `formthanks.html`.

## Preserved files

The following are preserved from the previous site and should not be deleted without care:

| File / directory | Purpose |
|---|---|
| `CNAME` | GitHub Pages custom domain (`miggle.one`) |
| `manifest.json`, `browserconfig.xml` | PWA / Windows tile config |
| `/icons/` | Full favicon suite |
| `/fonts/` | Self-hosted Comfortaa and OpenSans |
| `images/logo.png`, `images/mobile-logo.png` | Brand logo (desktop and mobile) |
| `images/migglelogo.png` | OG / social-share image |
| `contact.html` | Legacy standalone contact page (may have inbound links) |
| `jquery/jquery.min.js` | Not used by new pages; retained to avoid 404s if linked |

## Deployment

Push the `rebuild` branch and open a pull request into `master`. GitHub Pages will update `miggle.one` automatically once `master` is updated. The site is live; do not force-push to `master`.

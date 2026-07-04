# Scripora — Landing Page

Public marketing/SEO landing page for Scripora. This is a **separate project**
from the main application repo (`scripora_vercel`) — it does not touch or
depend on the app's code, and deploying it will not affect the running app.

## Before deploying

Search every file for `REPLACE_WITH_LANDING_DOMAIN` and replace it with the
real domain this project ends up on (a new Vercel-assigned `*.vercel.app`
subdomain, or the `scripora.app` custom domain if you attach it here).
It appears in:

- `index.html` (canonical, Open Graph, Twitter tags)
- `privacy.html`, `terms.html` (canonical tags)
- `robots.txt` (sitemap reference)
- `sitemap.xml` (all `<loc>` entries)

Nothing else needs to change — the app's own domain (`scripora.vercel.app`)
is intentionally still referenced anywhere the page links out to the app
itself (the "Open Scripora" / "Start Writing" buttons, and the JSON-LD
`SoftwareApplication.url` field, which correctly points at the real app).

## Structure

```
index.html       — the landing page
privacy.html      — static Privacy Policy (same text as the in-app version)
terms.html        — static Terms of Use (same text as the in-app version)
styles.css        — all styling, tokens ported from the app's real palette
script.js         — nav toggle + FAQ accordion, vanilla JS
robots.txt
sitemap.xml
vercel.json
Icon/             — copied from the app's own icon set (not re-generated)
```

## Design source of truth

Colors, fonts, and the five script-stage colors (Hook/Context/Main
Body/CTA/Outro) are copied directly from the app's `styles.css` (Midnight
theme). The hero and "How It Works" mockups are coded recreations of the
real editor UI (verified against the app's actual screenshots), not
screenshots or generic illustrations, and use invented example script
content rather than real user data.

## Content accuracy notes

- Only features that exist in RC1 are described. AI, script scoring,
  collaboration, Google Drive integration, PDF export, and payments are
  intentionally absent from every section except "Coming Next."
- "Reorder Sections" is used instead of "Drag & Reorder" — the app moves
  paragraphs via up/down buttons, not a drag gesture.
- The "Coming Next" roadmap reflects `PROJECT_BIBLE_v2.md`'s Version 2
  Backlog, not any other draft roadmap.

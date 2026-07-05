# Scripora — Landing Page

Public marketing/SEO landing page for Scripora. This is a **separate project**
from the main application repo (`scripora_vercel`) — it does not touch or
depend on the app's code, and deploying it will not affect the running app.

## Deployment

Live at `https://scripora-site.vercel.app/`. This URL is set in the
canonical tags, Open Graph/Twitter tags, `robots.txt`, and `sitemap.xml`.

The app's own domain (`scripora.vercel.app`) is intentionally still
referenced anywhere the page links out to the app itself (the "Open
Scripora" / "Start Writing" buttons, and the JSON-LD
`SoftwareApplication.url` field, which correctly points at the real app) —
this is a separate project and does not touch or depend on the app's code.

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
favicon.ico       — root fallback, generated from Icon/icon-512.png
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

## v1.1 changes (product representation refinement)

- Added a **Script Library** section — the app's Draft/In Progress/Ready/
  Filmed workspace was previously not represented at all. Status pill
  colors are copied exactly from the app's real `.sbadge` CSS classes.
- Gave **Notes Drawer** and **Portfolio Export** their own showcase section
  with coded mockups, instead of a single icon card each. Example content
  (script titles, note text, author name) is entirely invented — no real
  screenshots or user data used, per instruction.
- Rebalanced the **Features** grid to the remaining secondary features
  (Paste & Detect, Reorder Sections, Cloud Sync, Offline Writing) now that
  Notes Drawer and Portfolio Export have their own showcase.
- Added a **mid-page CTA** after Features, since that's the point where a
  visitor has seen the full feature set and confidence is highest.
- Added a short "why" line to each card in **Who It's For**, replacing
  bare word chips.
- **Moved "Coming Next"** to appear before "Who It's For" instead of
  immediately before FAQ/Final CTA, so the roadmap doesn't introduce doubt
  right at the conversion moment.
- **Reduced "AI" repetition** in `<title>`, meta description, Open Graph,
  Twitter tags, and the JSON-LD description — the honest "no AI" statement
  now lives once in the Why Scripora section and once in the FAQ, rather
  than being repeated across every metadata field.
- Small **Hero** refinement only: named the audience ("YouTube creators")
  in the subhead and added a "Free to start. No signup required to begin
  writing." line under the CTAs. The headline itself was left unchanged.
- Google Analytics, Google Tag (gtag.js), Search Console verification,
  the favicon fix, `robots.txt`, `sitemap.xml`, JSON-LD, Open Graph,
  Twitter metadata, and both legal pages were preserved exactly as they
  were in the source ZIP.

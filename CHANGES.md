# Changes

Unlike a typical sports tech consultancy site, miggle.one presents a builder who has already done the work — specific tools that exist, engagement shapes that are defined, and a clear statement that he sits on the buyer's side of the table, not the supplier's.

## Editorial choices

- **Single-page architecture.** The PDF is a single cohesive document; the content reads as one narrative. Multi-page would add navigation friction with no benefit for a 30-second check-in visit.
- **Engagement shapes as a definition list, not cards.** `<dl>` is semantically correct for a set of labelled descriptions and avoids the three-card grid pattern that signals marketing-page thinking. The left-border accent provides visual weight without decorative icons.
- **Section headings as small-caps labels.** Restrained uppercase Comfortaa at 12px reads as editorial structure rather than marketing hierarchy. Body copy carries the weight; headings just orient the reader.
- **185% figure kept in context.** The brief explicitly asked for this: the PMY revenue figure sits inside the background paragraph, not isolated as a stat block.
- **Phone number updated to PDF canonical value.** The existing site showed 01273 358448; the PDF shows +44 (0) 7748 188012. Used the PDF number. Confirm this is correct before pushing.

## Preserved from previous site

- Contact form backend: Google Sheets endpoint unchanged.
- Fonts: Comfortaa-Regular, Comfortaa-Bold, OpenSans-Light from `/fonts/` — paths and family names preserved.
- Logo files: `images/logo.png` (desktop) and `images/mobile-logo.png` (mobile) — paths unchanged.
- Favicon suite: all files in `/icons/` untouched.
- `CNAME`, `manifest.json`, `browserconfig.xml` — untouched.
- Legacy HTML files (`contact.html`, `whatido.html`, etc.) — left in place.

## Replaced

- `index.html`: completely rewritten. Old content was a placeholder pointing to a Notion research hub.
- `css/screen.css`: completely rewritten. Old file was minified and used a dark navy background with light text; new file is white-background, custom-properties-based, and structured for editorial reading.
- `formthanks.html`: restyled to match new design. Success message and behaviour unchanged.

## Added

- `robots.txt`
- `sitemap.xml`

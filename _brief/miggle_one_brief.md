# Brief: rebuild miggle.one

You are rebuilding miggle.one from scratch. This is a personal brand site for
a senior sports tech consultant offering fractional AI/data advisory work.
The job is to produce a deployable static site that reflects the positioning
in the attached PDF (`alick_mighall_fractional_advisor.pdf`), nothing more
and nothing less.

**Work on a non-main branch only.** Before touching any files, confirm you
are not on `main` / `master` and that the user has created a working branch
(e.g. `rebuild`). If you are on `main`, stop and ask the user to switch
branches before proceeding. The site is live; pushing to `main` replaces
the live site instantly.

## Context

Alick Mighall is a sports tech consultant. CV includes Yahoo Europe, Tempus
Ex Machina (NFL Football Operations), and PMY Group (Premier League clubs,
LIV Golf, EuroLeague Basketball, ECB). He has spent the last nine months
building a working AI/data platform stack under the Miggle brand — TrackIt
event timestamping, sponsor analysis, multi-language commentary, automated
highlights, AI event detection, PPV/VOD.

He is now positioning miggle.one as the home for **fractional AI & data
advisory work for sports clubs, federations and platforms**, with the
platform stack as available infrastructure that comes with him.

The audience for the site is sports club CEOs, federation development
managers, and platform/broadcaster founders deciding whether to take a
30-minute call with him. Most arrivals will be from a LinkedIn message, an
email signature, or a referral. They're not browsing — they're checking him
out before replying.

## Source of truth

The attached PDF (`alick_mighall_fractional_advisor.pdf`) is the canonical
copy. Use its tone, structure, and language. Do not invent new copy or new
positioning. If the site needs more text than the PDF provides, expand
modestly within the same voice — short sentences, no jargon, no marketing
puff. When in doubt, lift directly from the PDF.

## Goals (in priority order)

1. A visitor lands, reads for 30 seconds, and understands: who he is, what
   he does, who he does it for, and how to start a conversation.
2. The site reads as the work of a senior operator — quietly confident,
   honest, specific. Not a startup landing page.
3. Mobile-first. A meaningful proportion of visitors will arrive via
   LinkedIn on mobile.
4. Fast: under 100KB initial payload excluding the logo. No build step
   required to deploy.
5. Accessible: semantic HTML, sufficient colour contrast, keyboard
   navigable, alt text on images.

## Non-goals

- No CMS, no admin panel, no auth.
- No analytics tooling beyond a placeholder comment showing where to add it.
- No newsletter signup. The contact mechanism is the existing contact form
  on the current miggle.one (it works and should be preserved — see "Contact
  form" below).
- No interactive widgets, sliders, or animations beyond the absolute minimum
  needed for polish (hover states, link transitions).

## Tech stack

The current miggle.one is already deployed via GitHub Pages. Use the
existing repo and its setup rather than starting fresh:

- Plain HTML, CSS, vanilla JS for the new site code. No frameworks, no
  build step, no Tailwind via CDN. Hand-written CSS using custom properties.
- The existing contact form's backend (whatever endpoint, third-party
  service, or hosting setup it currently uses) stays as-is. Only the
  front-end form markup is being rebuilt.
- Preserve any existing config files that GitHub Pages depends on
  (`.nojekyll`, `CNAME`, custom domain config, etc.). Do not delete
  or rename them without confirmation.
- One HTML file per route. If the site is single-page, one HTML file total.
- Inline critical CSS in `<head>`; defer or omit anything else.
- Include a basic `robots.txt` and a `sitemap.xml` if not already present.
- If the existing repo already has a favicon, preserve it. If not, derive
  one from the M1 logo.

Before deleting any existing file, check whether it's serving a purpose
(form backend, redirect rule, GitHub Pages config, legacy URL the user
might still link to). When in doubt, keep it and ask.

## Visual identity

- **Primary palette**: use the actual Miggle brand colours — these are the
  canonical values, supplied directly from the Miggle palette deck:

  - `#162F43` — deep navy (primary dark; use for body text and headings)
  - `#58BABB` — Miggle teal (primary brand accent; links, highlights, the
    teal in the M1 logo)
  - `#E92575` — Miggle pink (secondary brand accent; use sparingly, one or
    two places maximum, the pink in the M1 logo)
  - `#333333` — near-black (alternative body text where slightly softer
    contrast is needed)
  - `#7F8D98` — mid grey-blue (secondary text, captions, footer)
  - `#82A2AD` — steel blue (rules, hairlines, subtle dividers)
  - `#FFFFFF` or off-white — page background

  A pale tier exists for tinted backgrounds and callouts where appropriate
  (do not overuse): `#A3D9DA` light teal, `#D4EDED` pale teal, `#F387B3`
  light pink, `#F9C7DB` pale pink, `#AAC0C7` light steel.

  The pink should appear sparingly — it's an accent, not a structural
  colour. The teal is the workhorse brand colour for links and small
  accents. The deep navy carries the typographic weight.

  If the existing miggle.one CSS already uses these as named custom
  properties (e.g. `--miggle-teal`, `--miggle-pink`), preserve the variable
  names. If not, define them as CSS custom properties at `:root` with
  semantic names (`--ink`, `--accent`, `--accent-pink`, `--muted`) so they
  can be referenced cleanly throughout.
- **Typography**: keep the fonts already in use on the current miggle.one
  site. Read the existing CSS to identify which font families, weights,
  and any web-font loading mechanism (Google Fonts link, self-hosted woff2,
  @font-face declarations) are in use, and preserve them exactly. Do not
  swap to Inter, system fonts, or any other family even if you think it
  would render better. The fonts are part of the existing brand identity
  alongside the logo and palette. Sizes and hierarchy can be adjusted to
  hint at editorial layout (generous body text, restrained heading scale)
  rather than landing-page layout (huge hero font, tiny body), but the
  font families themselves stay.
- **Logo**: the existing repo has `icons/` and `images/` folders. Look at
  what's already in them — a Miggle logo file should be present (likely a
  PNG, SVG, or JPG named something like `miggle-logo`, `miggle.one`, `M1`,
  or similar). Use the existing file. Do not create a new folder, rename
  it, or move it. If you cannot find a logo in either folder, stop and ask
  the user where it is rather than inventing a path.
- **Layout**: single column, max content width around 680px for prose, up
  to 960px for hero/header sections. Generous vertical rhythm. Left-aligned
  text only — no centred body copy.
- **Imagery**: text-led, no new imagery. Do not introduce stock photos
  under any circumstances. If the existing `images/` or `icons/` folder
  contains assets beyond the logo (favicons, social-share images, OG
  images, photos), keep those that have a functional purpose (favicon,
  meta og:image) and ignore decorative ones unless they have a clear
  editorial reason to remain. The logo and a single OG/social-share image
  are the only visuals expected.

## Things to actively avoid

These are the failure modes that make AI-built sites look like AI-built
sites. Do not produce any of them:

- "Empower your team with AI" or any sentence containing "empower",
  "unleash", "leverage", "synergy", "transform", "revolutionise", or
  "next-generation".
- Hero gradients, gradient text, animated mesh backgrounds.
- Stock photos of diverse teams looking at laptops, athletes mid-stride,
  stadium aerials, or anything similar.
- Fake testimonials. Do not invent client quotes.
- Three-card "Our Services" grids with icons.
- Statistics presented as huge numbers ("185%+ revenue growth!") in a
  separate stat block. The 185% figure belongs in the background paragraph
  in context, not as a marketing trophy.
- "Get started" CTAs, especially repeated. The contact form is the
  conversion point, used once and not hammered.
- Sticky navigation bars, hamburger menus on desktop, scroll-triggered
  animations, parallax.
- Lorem ipsum, placeholder images, "Coming soon" sections.

## Site structure

You are free to choose between single-page and small multi-page. Pick
whichever better serves the positioning given the source copy. Justify the
choice in a comment in the HTML. The minimum content the site must contain
is everything that appears in the PDF: who he is, what he does, what comes
with him (the platform stack), where he focuses, his background, the three
engagement shapes, and links to his writing.

If multi-page, the routes should map cleanly to the PDF sections — do not
invent new ones.

The Medium publication is at `https://medium.com/miggle`. The flagship
article is at
`https://medium.com/miggle/timestamped-events-to-sponsor-roi-building-practical-ai-products-for-sport-a2a602b22f13`.
LinkedIn is at `https://www.linkedin.com/in/alickmighall/`.

## Contact form

The current miggle.one has a working contact form that should be preserved.
Before rebuilding, read the existing repo files to identify how the form
works (endpoint URL, expected field names, submission method, any honeypot
or spam protection, any client-side validation, any third-party service
config). Reproduce the same submission behaviour in the new site. Do not
change the backend; only the front-end markup and styling.

Form placement and tone:

- Place the form once, near the bottom of the page (or on a dedicated
  contact section if multi-page). Not in the hero.
- Three or four fields maximum: name, email, company/organisation
  (optional), message. If the existing form has more fields than this,
  match it exactly — do not strip fields without checking.
- The form heading should be a sentence, not a marketing call-to-action.
  Something like "Start a conversation" or "Get in touch" — restrained,
  matching the editorial tone of the rest of the page.
- No "We'll get back to you within 24 hours" promises. After submission,
  the success state should be a simple acknowledgement.
- Include the email address `alick@miggle.one` visibly nearby, so visitors
  who prefer email over forms have an obvious alternative.

If you cannot determine how the existing form works (e.g. the endpoint is
unclear or appears to use a third-party service whose configuration isn't
visible), stop and ask the user before proceeding. Do not invent an
endpoint or default to a generic Formspree/Netlify Forms setup without
confirmation.



1. Updated site source in the existing repo, replacing the current site,
   ready to commit and push. The existing GitHub Pages deployment will pick
   up the changes automatically.
2. An updated `README.md` covering: how to preview locally (one command),
   where to add analytics if wanted later, and a note on what was preserved
   from the previous site (contact form backend, GitHub Pages config, logo
   files, fonts, etc.).
3. A short `CHANGES.md` listing the editorial choices you made (e.g. "chose
   single-page because…", "placed engagement shapes after background
   because…") and what was preserved vs replaced from the previous site.
   Three or four bullet points each. This is for the user to sanity check
   your judgement, not a marketing document.
4. **Do not commit or push without confirmation.** Stage all changes and
   show the user a summary of what's changed before they push live. The
   site is already live; pushing replaces it instantly.

## Definition of done

- Site renders correctly in Chrome, Safari, Firefox, on desktop and mobile.
- Lighthouse score 95+ on all four metrics on a clean run.
- All copy is either lifted from or directly faithful to the PDF.
- No placeholder text, no broken links, no missing images. The logo
  reference must point to the actual existing file in `icons/` or
  `images/` — verify the path resolves before declaring done.
- The user could send the URL to a Premier League CEO and feel comfortable
  about it.

Begin by reading the PDF carefully. Do not start writing code until you can
state, in one sentence, what the site is communicating that's different
from a typical sports tech consultancy site. Put that sentence at the top
of `CHANGES.md`.

# Spotlight — Website (v12: proof, depth & polish pass)

Single-page site, no build step required (plain HTML/CSS/JS). Same playbill/box-office concept as v11 — this round adds the structural and trust elements that make a site feel professional rather than just pretty.

## Files you need — 11

1. `index.html` — the main site
2. `privacy.html`, `terms.html` — new, lightweight legal pages (templates — have a lawyer review before publishing; needed before Meta will fully approve Pixel-based conversion campaigns)
3. `favicon.png`, `hero-fixture.png`, `logo-full.png`, `logo-mark.png` — reuse your existing four images, flat at the repo root
4. `robots.txt`, `llms.txt` — unchanged from v11
5. `sitemap.xml` — updated with the new `#work`, `#notices`, `#team` sections and the two legal pages
6. `README.md` — this file (optional to upload)

## What's new in v12

**Social proof (the biggest gap in v11)**
- A **trust strip** under the hero listing the industry verticals Spotlight serves (honest placeholder — swap for real client logos the moment you have permission to display them)
- A new **"Selected Work" / Playbill Archive** section (`#work`) — three case-study-style cards (illustrative, clearly labeled as such) ready to swap for real, approved case studies
- A new **"Critics' Notices"** testimonials section (`#notices`) — three placeholder quotes in the theatre-review voice, styled with star ratings, ready for real client attributions
- A new **"Behind the Curtain"** team strip (`#team`) — four placeholder roles with initials-based avatars (no stock photos used), ready for real names/photos

**Sharper, more concrete copy**
- The Results section now uses actual numbers with an animated count-up on scroll (40%, 24h, 9x, 5d) instead of hedged phrasing like "meaningfully fewer" — each is marked illustrative with a footnote, since these should be swapped for your own verified figures once you have them. Don't publish these as hard claims without real data behind them.

**Conversion & ops polish**
- A **booking CTA** in the Contact section, with a commented, ready-to-activate Calendly/Cal.com embed block in `<head>` (same pattern as the Meta Pixel placeholder) — drop in your real booking link to turn it into a live inline scheduler instead of a mailto handoff
- A **footer newsletter signup** (validates client-side; wire the submit handler to your list provider or an n8n webhook to go live)
- **Privacy Policy and Terms of Service** pages, linked from the footer — templates only, needs legal review, but professional sites (and Meta Ads approval) expect these to exist

**Interaction/visual refinement**
- A page **load fade-in** instead of the page just appearing
- The service ticket "tear" now shows a genuine jagged zig-zag seam when opened, not just a plain height expand
- Stat numbers animate up into view rather than appearing static

Everything else carries over from v11 unchanged: the ticket-stub hero and service cards, backstage rigging automation diagram, call-sheet philosophy card, follow-spot cursor, Marquee blog/news/events board, scroll progress bar, active-nav highlighting, FAQ accordion, and the full JSON-LD stack (`ProfessionalService`, `WebSite`, `FAQPage`, `Blog`/`BlogPosting`, `Event`).

## Deploy on Vercel via GitHub

1. Upload `index.html`, `privacy.html`, `terms.html`, `sitemap.xml` to the repo root (replacing previous versions), plus `robots.txt`/`llms.txt` if not already present. Keep the four images where they already are.
2. Commit to `main` — Vercel auto-redeploys.
3. Once you have a real domain, replace every `https://www.spotlight.agency/` reference (in `index.html`'s `<head>`, `sitemap.xml`, and `llms.txt`) with your actual URL.

## Before you publish this for real

- Replace every illustrative stat, case study, and testimonial with verified content, or remove the sections until you have real material — placeholder "results" presented as fact is a credibility risk, not just a legal one.
- Get `privacy.html` and `terms.html` reviewed by a lawyer, especially if you're running Meta Ads or have EU/UK/California visitors.
- Fill in the `[DATE]` placeholders on both legal pages.
- Add your real Calendly/Cal.com link and Meta Pixel ID where flagged in `<head>`.

## Editing
- Copy and section content live directly in `index.html` — search for the section id (`#about`, `#services`, `#work`, `#systems`, `#how`, `#notices`, `#fitfor`, `#team`, `#dispatch`, `#results`, `#faq`, `#contact`).
- If you edit the FAQ text, update the matching `FAQPage` JSON-LD block in `<head>` too.
- Colors and fonts are CSS variables at the top of the `<style>` block (`:root`).

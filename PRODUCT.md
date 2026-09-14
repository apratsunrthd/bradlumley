# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

- **Search engines and AI answer engines** — crawl the page and its
  `schema.org` `Person` JSON-LD to answer "who is Brad Lumley" queries
  authoritatively, instead of guessing from scattered secondary sources.
- **Recruiters** — sourcing for data/analytics leadership roles; the
  `jobTitle` in structured data is deliberately phrased as a concrete,
  standard title ("VP, Data & Analytics") because research showed that
  outranks vaguer executive phrasing in recruiter search.
- **Professional contacts** — people who already know Brad and land here
  from a shared link, wanting a fast way to reach LinkedIn, RefHealth
  Consulting, or email.

Machine (search/AI) and human audiences are weighted equally — no design or
content decision should trade one off against the other.

## Product Purpose

A canonical, machine-readable personal identity page for Brad Lumley, and a
home base ("Lab") for side-project MVPs he ships with Claude Code. Success
looks like: search/AI systems surface accurate facts about Brad instead of
stale or third-party sources, human visitors reach the right link in one
click, and each shipped side project gets a permanent home
(`projectname.bradlumley.com`) instead of a one-off throwaway domain.

## Positioning

Not a second RefHealth Consulting site (`refhealth.consulting` already owns
"hire me for consulting") and not a blog or content site — no content
cadence is a deliberate choice, not a gap. What a neighboring page can't
copy: it's the one page Brad controls end-to-end as ground truth, with
structured data kept in sync with what's actually true, plus a permanent,
compounding home for every side project instead of scattered repos.

## Operating Context

- Static site, no CMS: content changes are direct edits to `index.html`
  pushed to `main`.
- Hosted on GitHub Pages; a GitHub Action regenerates `sitemap.xml` and
  injects the GA snippet on every push.
- New side projects get their own GitHub repo, their own GitHub Pages
  deploy, a subdomain CNAME at the registrar (currently a manual DNS step —
  see TODO.md), and a card added to the Lab section here.

## Capabilities and Constraints

- No build step, no framework, no dependencies — plain HTML/CSS/JS by
  design; this is a durable choice, not a temporary gap.
- The `schema.org` `Person` JSON-LD block is the authoritative source
  machines read — it must only ever state what's actually true, never
  aspirational copy.
- No blog, no content cadence — deliberately excluded from scope.
- DNS/subdomain provisioning for new Lab projects is a manual step (no
  registrar/DNS API access configured yet); domain is at Namecheap.

## Brand Commitments

- Name: Brad Lumley. Contact: bradmlumley@gmail.com.
- Real headshot required for the avatar, OG/share image, and favicons — no
  placeholder/initials avatar.
- Current visual identity (dark theme, card-link style, headshot-based
  avatar) is the incumbent implementation, not a locked brand commitment —
  a future redesign is free to replace it if there's a reason to.

## Evidence on Hand

- Real headshot and derived crops in `assets/` (avatar, OG image, favicons,
  apple-touch-icon), top-anchored crop as of PR #9.
- Live professional links: LinkedIn (`linkedin.com/in/bradlumley`),
  RefHealth Consulting (`refhealth.consulting`).
- No Lab projects have shipped yet — the Lab section is a placeholder
  ("Nothing shipped yet"). Do not fabricate project cards ahead of an
  actual ship.
- No testimonials, case studies, press, or pricing exist or should be
  implied anywhere on this page.

## Product Principles

1. Structured data is ground truth, not marketing — every claim in the
   `Person` JSON-LD must be verifiably true today.
2. Machine and human audiences get equal weight; never optimize one at the
   visible expense of the other.
3. This page stays a link/identity surface, not a content site — resist
   scope creep toward blogging or long-form writing.
4. Every shipped side project gets a permanent subdomain home here, not a
   disposable one-off domain.
5. Keep the zero-build, zero-dependency architecture — complexity here
   should earn its way in, not accumulate by default.

## Accessibility & Inclusion

WCAG AA is a required bar for this site (confirmed 2026-09-13), not just a
best-effort. Contrast, in particular, must meet AA minimums (4.5:1 body
text, 3:1 large text) — the current build has known AA-contrast failures
in the muted text color pending a fix.

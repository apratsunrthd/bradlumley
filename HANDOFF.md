# HANDOFF

Orientation for anyone (human or model) picking this repo up cold.

## Architecture

- Plain static HTML, one page: `index.html`. No build step, no dependencies,
  no framework. Edit the file directly.
- Hosted on **GitHub Pages** from this repo. `CNAME` file pins the custom
  domain (`bradlumley.com`); GitHub Pages serves whatever is on `main`.
- **GitHub Action** (`.github/workflows/sitemap.yml`), triggered on every push
  to `main`:
  1. Regenerates `sitemap.xml`.
  2. Runs `inject-ga.js`, which walks all `.html` files and inserts the GA
     `gtag.js` snippet into `<head>` if it isn't already present (it checks
     for the literal string `gtag(` or the GA script URL, so it's idempotent
     — safe to leave the snippet in `index.html` directly).
  3. Commits the results back to `main` with `[skip ci]` in the message (so it
     doesn't retrigger itself).
- No CMS, no server-side logic. Content changes = edit `index.html` and push.

## Where things live

- `index.html` — the entire site.
- `assets/` — images referenced by `index.html`:
  - `avatar.jpg` (480x480) — header avatar, square crop
  - `og-image.jpg` (1200x630) — Open Graph / Twitter Card share image
  - `favicon-32.png`, `favicon-16.png`, `apple-touch-icon.png` (180x180) —
    tight face crop, used for browser tab + iOS home screen icon
  - `headshot-source.jpg` — downsized (2000x3000) archival copy of the
    original headshot, kept so future crops don't need Brad to re-upload.
    Not referenced by the page itself.
  All generated from one source photo via `sips`/Pillow (`uv run --with
  pillow python3`) — see PR #8 for the crop-box math if new crops are needed.
- `CNAME` — custom domain for GitHub Pages.
- `sitemap.xml` — auto-generated, don't hand-edit (the Action overwrites it).
- `inject-ga.js` — GA injection script, run by the Action, not meant to be run
  standalone unless testing locally.
- `.github/workflows/sitemap.yml` — the Action described above.

## Gotchas

- Pushing to `main` triggers an automatic commit-back from
  `github-actions[bot]` shortly after (sitemap + GA check). Don't be surprised
  by an extra commit appearing after your push.
- The GA injector's idempotency check is a plain string match — if you ever
  reformat the `<head>` in a way that breaks the `gtag(` string, it'll
  double-inject the snippet on the next push.
- Standing repo policy (see the user's global CLAUDE.md) requires all material
  work to land via branch → commit → PR, never directly on `main`.
- `index.html` references images with root-relative paths (`/assets/...`),
  correct for the deployed site (GitHub Pages serves this repo at domain
  root). Previewing via `file://` locally breaks those paths (resolves
  against the filesystem root, not the repo root) — use a local HTTP server
  rooted at the repo (`python3 -m http.server`) instead when checking a
  change with `browse`/screenshots before pushing.

## Adding a new "Lab" project (side-project launchpad pattern)

When a Claude Code side-project MVP is ready to show:

1. **New GitHub repo** for the project (keep it separate from this repo —
   this repo stays the static identity page only).
2. **Enable GitHub Pages** on that repo, and add a `CNAME` file in it
   containing `projectname.bradlumley.com`.
3. **Add a DNS record** at the registrar for `bradlumley.com`: a `CNAME`
   record, host `projectname`, pointing to `apratsunrthd.github.io` (same
   pattern this repo uses for the apex domain — check this repo's own DNS
   config as the reference). This is currently a **manual step** — no
   registrar/DNS API access has been set up. If Brad wants this automated
   later (e.g. DNS lives on Cloudflare), that's a small follow-up.
4. **Add a card to the Lab section** in this repo's `index.html`, replacing
   or appending to the placeholder card:

   ```html
   <li><a class="link-card" href="https://projectname.bradlumley.com" target="_blank" rel="noreferrer">
     <div class="link-icon" aria-hidden="true">🚀</div>
     <div class="link-text">
       <strong>Project Name</strong>
       <span>One-line description</span>
     </div>
   </a></li>
   ```

   Remove the "Nothing shipped yet" placeholder card once the first real
   project is added.

## Conventions

- Keep the existing dark-card visual style (`--bg`, `--card`, `.link-card`
  component) rather than introducing a new design system for small additions.
- Any structured-data change (the `schema.org` `Person` JSON-LD block in
  `<head>`) should stay in sync with what's actually true — it's meant to be
  the authoritative source AI/search systems read, not aspirational copy.

## Open threads

- No projects have shipped to the Lab section yet.
- DNS/subdomain provisioning is unautomated — revisit if the project cadence
  picks up enough to make the manual step annoying.

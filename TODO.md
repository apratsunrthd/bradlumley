# TODO

What's planned but not done yet. Update this as items complete or new ones
come up.

## For Claude / other models

- [ ] When a Claude Code side-project MVP is ready to ship, follow the
      "Adding a new Lab project" checklist in `HANDOFF.md` and add its card.
- [ ] If DNS moves to a provider with API access (e.g. Cloudflare) and Brad
      grants access, automate the subdomain-record step in that checklist.

## For Brad (human)

- [x] Pick the first side project to feature in the Lab section once one is
      ready to show publicly. Undertow (iPhone focus app, live on the App
      Store) added.
- [x] Review/merge PR #8 (headshot, favicon, OG tags, email contact card,
      jobTitle → "VP, Data & Analytics"). Merged.
- [x] Review/merge PR #9 (fix top-of-head crop on `og-image.jpg`,
      `avatar.jpg`, `apple-touch-icon.png`, and both favicons). Merged.
- [ ] Confirm in a real share (Slack/iMessage/LinkedIn) that the OG
      image/link preview renders correctly with full headroom, and that the
      favicon shows in the browser tab.
- [ ] Submit the site to Google Search Console and Bing Webmaster Tools.
      `robots.txt`/`sitemap.xml`/JSON-LD only help once a search engine
      actually knows to look — this requires logging into each console and
      can't be done by Claude. See the "Search engine submission" checklist
      in `HANDOFF.md`.
- [ ] DNS automation prep (domain is at Namecheap) — decide which path, then
      gather the matching info before asking Claude to automate the
      subdomain-record step:
      - **Cloudflare (recommended)** — free account, add `bradlumley.com` as a
        site, switch nameservers at Namecheap to the two Cloudflare gives you,
        then generate an API token scoped to `Zone.DNS: Edit` for that zone.
        Provide: the token + the Zone ID.
      - **Namecheap native API** — check Profile → Tools → API Access first;
        it only unlocks once the account meets Namecheap's spend/domain-count
        eligibility bar. If eligible, provide: Namecheap username + API key.
        Whitelisting your current public IP is required per API call and
        needs redoing if your IP changes — the recurring cost of this path.

# TODO

What's planned but not done yet. Update this as items complete or new ones
come up.

## For Claude / other models

- [ ] When a Claude Code side-project MVP is ready to ship, follow the
      "Adding a new Lab project" checklist in `HANDOFF.md` and add its card.
- [ ] If DNS moves to a provider with API access (e.g. Cloudflare) and Brad
      grants access, automate the subdomain-record step in that checklist.

## For Brad (human)

- [ ] **Authority plan, Phase 3 (the main lever; no proof assets exist yet).**
      AI/search engines rank "best healthcare data leader" from third-party
      sources, not this site. Start with the cheapest, highest-signal items:
      1. ~~Align LinkedIn headline/About with this site~~ Done 2026-10-14
         (LinkedIn rewritten; site updated to match). Remaining: pin Skills
         (Healthcare Analytics, Data Strategy, AI Transformation) and add
         bradlumley.com to LinkedIn Featured.
      2. Pitch 2-3 healthcare/data podcasts as a guest.
      3. Submit a conference talk (HLTH, HIMSS, AHIP, Data Council).
      4. Pitch one guest byline (Healthcare IT News, Health Data Management).
      5. As each lands, tell Claude to add it to JSON-LD (`sameAs`, `award`,
         etc.) and `llms.txt`.
      Avoid pay-to-play "Top 100" lists and SEO agencies.
- [ ] Monthly (15 min): run "VP data analytics healthcare" and "healthcare
      data leaders" in Google, ChatGPT, Perplexity, Gemini, Claude; check GSC
      impressions for "Brad Lumley". Note results in `BRIEF.md`.
- [ ] Verify the Pager Health URL in JSON-LD (`https://www.pagerhealth.com`) is correct.

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
- [x] Submit the site to Google Search Console and Bing Webmaster Tools.
      Done 2026-09-14 via gstack `/browse` (Google account sign-in and the
      Namecheap DNS TXT record still needed Brad in the loop). Domain
      property verified, sitemap submitted on both. See "Search engine
      submission" in `HANDOFF.md` for status and next steps.
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

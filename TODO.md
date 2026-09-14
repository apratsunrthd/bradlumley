# TODO

What's planned but not done yet. Update this as items complete or new ones
come up.

## For Claude / other models

- [ ] When a Claude Code side-project MVP is ready to ship, follow the
      "Adding a new Lab project" checklist in `HANDOFF.md` and add its card.
- [ ] If DNS moves to a provider with API access (e.g. Cloudflare) and Brad
      grants access, automate the subdomain-record step in that checklist.

## For Brad (human)

- [ ] Pick the first side project to feature in the Lab section once one is
      ready to show publicly.
- [ ] Decide whether the `jobTitle` in the `Person` JSON-LD ("Data & Analytics
      Executive") is the phrasing you want public, or adjust it.
- [ ] Merge PR #4 (cycling removal) and this identity/launchpad PR, in either
      order — they're stacked, so land #4 first if possible to keep history
      clean.
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

# FullBars (fullbars.shmor.ai)

A Shmor marketplace (shared rules in `../../CLAUDE.md`): its own brand, design and SEO. Broadband, mobile, SIM-only, home phone and TV providers compared side by side. UK-first, with USA and Europe hubs. Name = "full signal bars"; tagline "Every connection, compared at full strength." Replaced the planned "Shmor Connect" card on shmor.ai (2026-10-14). Repo: `Shmorai/shmor-fullbars` (private until launch). Status: **building**.

## Where things are
| What | Where |
|---|---|
| Card on shmor.ai, search keywords, **referral links**, offers, SEO defaults | `shmor-site.json` |
| Pages (1 JSON file = 1 Google landing page) | `content/` (`home.json` = homepage) |
| Design: header, logo, footer | `templates/layout.html` |
| Design: styles | `assets/site.css` (kit defaults, then the FullBars theme block at the bottom) |
| Generated output (don't edit by hand) | `index.html`, `*/index.html`, `sitemap.xml`, `robots.txt`, `404.html`, `search/` |

## Pages (22)
Home · broadband · full-fibre-broadband · broadband-speed · mobile · sim-only-deals · networks (which network each MVNO uses, UK/US/EU) · home-phone (digital switchover) · tv-and-broadband · providers (directory) · switching · usa · europe · roaming · cheap-broadband (social tariffs) · rural-broadband (4G/5G home, satellite, USO) · blog + 5 posts (digital landline switchover, mid-contract price rises, One Touch Switch, FCC broadband labels, eSIM explained).
Top menu (`navOrder`): Broadband, Mobile, SIM only, Home phone, Providers, USA, Europe, Guides.

## Signature card styles (unique to this site)
- **SIM cards** = the kit's `specs` block: gold SIM-chip monogram (cyan chip for US, lilac for EU), clipped top-right corner, badge tab on the top edge, dotted-leader spec sheet, official-site link. `tabs` filter by region (UK/USA/Europe on home; by country on Europe and Providers). Provider facts only: network, tech, owner, brands. **No prices, speeds-for-sale or ratings.** Ownership/network facts checked October 2026 (e.g. VodafoneThree merger 2025, MasOrange 2024, Odido rename 2023): recheck when editing.
- **Signal meters** = the kit's `meters` block: midnight section, five stepped bars filled with the cyan→violet→pink gradient. Used for connection technology ceilings (ADSL → full fibre).
- Service tiles = `deals` block with a signal-bars corner that lights up on hover.
- Blocks can take `"class": "alt"` for a white band.

## Design
Light page #F6F5FB, white surfaces, midnight #0D0B24 / #17143A (top line, hero, meters, CTA, footer), signal pink #FF3EA5 (buttons, marks; never small text on white), link pink #C2136E, cyan #19C3E6, gradient cyan → #8B5CF6 → pink. Fonts: Space Grotesk headings + Inter body. Logo = midnight rounded square with four rising signal bars (cyan→pink), wordmark "Full**Bars**" with gradient "Bars". Hero = midnight with a faint grid and glow; home hero has animated signal bars (off for reduced motion) and a service picker (`heroHtml`). Footer has a five-colour signal stripe.
**Photos:** free-licence Unsplash images, credited, all checked loading. Mobile checked at 375px (no horizontal scroll).
Content was generated from a script once; edit the JSON files in `content/` directly from now on.

## Commands (run here)
```bash
node tools/build.js           # rebuild after ANY change to content/, templates/ or shmor-site.json
node tools/serve.js <port>    # local preview (see the "fullbars" preview config)
```
After changing `shmor-site.json`, also run `node tools/sync-network.js` in `../../shmor-ai`.

## Referral links
None yet. Natural fits: Awin/CJ/Impact programmes from UK broadband and mobile providers (and US carriers / Starlink for the USA hub). Add to `shmor-site.json` → `"links"`; on any SIM card add `"link": "<slug>"` to show a pink "See X plans" button; or list slugs in a page's `"partners"` (headings already set on broadband and mobile). Rebuild, sync the master, commit both repos.

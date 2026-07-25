# Handoff — 2026-07-25

## What this repo is
`justinalydia` = the personal landing page at **justinalydia.com** (single `index.html`, elegant static site). This is the `main/` directory of the local `~/Documents/REPOS/justinalydia` workspace, which also holds sibling site folders (`ai`, `blindfolded`, `coach-justinalydia`, `cuddles-justinalydia`, `drone`, `relating-lab`) — each its own site. The outer folder is NOT a git repo; each site is.

## Deploy / ops
- **justinalydia.com**: GitHub Pages from `main` branch, repo `jjanczyszyn/justinalydia`, root `/`. Push to `main` → Pages rebuilds (~1 min). No CI. Verify: `gh api repos/jjanczyszyn/justinalydia/pages/builds/latest`.
- Convention: land every change via PR + `CHANGELOG.md` entry, squash-merge, never commit to `main` directly.
- Favicon gotcha (fixed): `index.html` used to have TWO `<link rel="icon">` tags; the last wins. Keep it to ONE, pointing at `favicon.svg`.
- Brand accent for this site is **terracotta `#c2543a`** (`--accent`), not pink.

## Current state (all done + live)
The "Worlds" list on justinalydia.com now groups **Entrepreneurship** into two sub-tabs:
- **Nicaragua** → https://popoyo.co
- **Brazil** → https://rosemary.vibesqueen.com/
Favicons refreshed this session:
- justinalydia.com → terracotta **lotus** (`favicon.svg`, single source of truth).
- **popoyo.co** (`jjanczyszyn/popoyo`, plain Pages) → teal **wave** favicon (site had none before).
- **rosemary** (`jjanczyszyn/rosemary`, Astro + Convex, deploys via GitHub Actions on push to `main`; serves **rosemary.queenvibes.com**) → green **plant/sprig** favicon in `public/favicon.svg`.

## Open threads / notes
- Domain note: rosemary repo's CNAME is `rosemary.queenvibes.com`, but the Brazil link (per user) is `rosemary.vibesqueen.com`. User confirmed vibesqueen is correct for the link — assume it's a live alias/redirect to the same site. Revisit if that link ever 404s.
- Global convention says website hosting = AWS (S3/CloudFront/Route53); these sites actually run on **GitHub Pages**. Not migrated — flag if a hosting standardization pass is wanted.

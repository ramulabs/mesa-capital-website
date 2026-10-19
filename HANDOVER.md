# Mesa Capital website — Handover

_Written 2026-10-18 for the move to a new Claude account. Only the Claude account is moving. Account-level items are in the separate `ACCOUNT-HANDOVER.md`, which is not committed._

## What it is

A single-page static landing site for Mesa Capital: `index.html` (a self-contained bundle exported from Claude Design, v1.1 "1e Refined" direction), `favicon.png` / `favicon.svg`, `logo-white.png`, and a `_headers` file (CSP etc.). There is no build step and no framework.

## Hosting

**Cloudflare Pages**, project `mesa-capital-companyprofile`. Confirmed by the "Cloudflare Pages" check on this repo's PRs: every push builds a preview, and `main` deploys to production. `_headers` is the Pages headers file. There is no Vercel project for this site. Confirm the custom domain in the Cloudflare dashboard (Pages → `mesa-capital-companyprofile` → Custom domains).

## State

All work happened on 2026-07-01: initial commit → v1.1 design → favicon / CSP / bundle-escaping fixes → mobile hero uses `100dvh`. No open PRs, no task tracking (no `.forge/`).

## Gotchas

- `index.html` is a bundled export. When re-exporting from Claude Design, keep inline-script escaping intact (commit `5493ecf`) and keep the favicon external (inlining it broke JSON unpacking, `e54f89f`).
- If the CSP in `_headers` changes, re-test the bundle. It was tightened in `7e44e17`.
- The **Claude Design source project lives in the old Claude account.** Export or share it before the old account goes away, or future design edits must start from this HTML.

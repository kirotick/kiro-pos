# kiro-pos

KIRO POS: the restaurant billing app (billing, orders, tables, kitchen screen, cashier, offline storage). Served at kiro-pos.netlify.app/app/.

Part of KIRO (Kitchen Intelligence & Restaurant Operations). Owner: @kirotick. Migrated with full history from `kirotick/KIRO_POS` (commit `252de09`), see kiro-documentation/governance/REPOSITORY_MIGRATION_PLAN.md.

## What this repository owns
- POS web app (`app/index.html`, offline service worker `app/sw.js`)
- Bill arithmetic on the device (GST split, round-off) until the app syncs with kiro-backend
- Future: printer, cash drawer and customer display integrations

Nothing here may be copied into another KIRO repository; other repositories use it by version or through its API.

## Depends on
- Released to the website by tagging (e.g. `v1.0.1`) and changing `pos-version.txt` in **kiro-web** in a reviewed pull request
- **kiro-qa-testing**: browser tests (billing workflows, double-click safety, offline reload, XSS)

## Build
No build step: `app/index.html` is the whole app. Release = create a tag, then bump `pos-version.txt` in kiro-web.

## Test
With kiro-web and kiro-qa-testing next to this folder: in kiro-qa-testing `npm ci && npm run qa:pos`.

## Branches, reviews and releases
`main` is production and protected: changes arrive only by pull request with passing checks (see CONTRIBUTING.md). Versions follow semantic versioning; every release is a git tag `vMAJOR.MINOR.PATCH` with notes in CHANGELOG.md, so each deployment maps to one exact commit. Rollback = redeploy the previous tag.

## Security
See SECURITY.md. Never commit secrets: `.env` files are ignored, and secret scanning with push protection plus gitleaks in CI block them.

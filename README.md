# Cloudflare Pages Basket

Single repo for temporary Cloudflare Pages/Workers. Each subdirectory is a separate page.

## Structure
```
/dashboard/     — Project dashboard
/quiz/          — Anthropic Academy quiz  
/c4-diagrams/    — C4 architecture diagrams
```

## Adding a new page
1. Create a subdirectory with `wrangler.toml` (unique Worker name) and `worker.js`
2. Push to main — GitHub Actions deploys automatically
3. Note the expected teardown date in the subdirectory's README

## Removing a page
1. Delete the subdirectory
2. Manually delete the Worker from Cloudflare dashboard
3. Code stays in git history for redeployment

## GitHub Secrets needed
- `CLOUDFLARE_API_TOKEN` — Cloudflare API token with Workers deploy permissions
- `CLOUDFLARE_ACCOUNT_ID` — Cloudflare account ID

## Cost discipline
Each Cloudflare Worker on the paid plan costs money. Only deploy what's needed. Tear down when done.

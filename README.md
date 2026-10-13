# SellerLedger (working name)

Prototype site for a standalone brand selling Amazon and ecommerce seller contact lists to B2B buyers (agencies, advertising and marketing services, IT services and seller software, logistics, product imaging, lenders).

## What is here

- `public/index.html`: single-file prototype. Live list builder (marketplace, category, revenue band, FBA/FBM, required fields) with record count and price estimate, market stats, marketplace coverage, buyer presets, data fields, pricing, compliance, FAQ and quote form.

## Hosting (Cloudflare Workers via Wrangler)

Assets-only Worker named `sellerledger`. There is no Worker script: Cloudflare serves everything in `public/` directly, as configured in `wrangler.jsonc`.

- `public/index.html`: the site
- `public/404.html`: served with a 404 status for unknown paths
- `public/_headers`: security headers on every response

Commands (Node 20+):

```
npm install
npm run dev       # local preview at http://localhost:8787
npm run check     # wrangler deploy --dry-run, validates config and assets
npm run deploy    # wrangler deploy, needs `npx wrangler login` or CLOUDFLARE_API_TOKEN + CLOUDFLARE_ACCOUNT_ID
```

For Workers Builds (deploy on every push to `main`), connect this repo in the Cloudflare dashboard and set the deploy command to `npx wrangler deploy`.

The page carries `noindex` until counts and prices are final. Remove that meta tag at launch.

## Status

- Sourced: the four market stats (Marketplace Pulse via Modern Retail, Apr 2026; Store Leads via StoreInspect, May 2026).
- Placeholders: brand name, record counts, fill rates, prices.
- Sample rows are fictional.
- Quote form is not wired to a backend.

## Next steps

1. Replace counts and fill rates with LakeB2B and SPAN figures.
2. Confirm pricing.
3. Wire the quote form to the CRM.
4. Legal review of the compliance section.

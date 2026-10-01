# SellerLedger (working name)

Prototype site for a standalone brand selling Amazon and ecommerce seller contact lists to B2B buyers (agencies, seller software, 3PLs, lenders, packaging and freight).

## What is here

- `public/index.html`: single-file prototype. Live list builder (marketplace, category, revenue band, FBA/FBM, required fields) with record count and price estimate, market stats, marketplace coverage, buyer presets, data fields, pricing, compliance, FAQ and quote form.

## Hosting

Cloudflare Worker `sellerledger` serving static assets from `public/` (see `wrangler.jsonc`). Workers Builds deploys every push to `main`. The page carries `noindex` until counts and prices are final; remove that meta tag at launch.

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

# QAS website content: rules for Claude

## What this is
Populate content for the NEW QAS website on Shopify: products, collections, About, FAQ, SEO titles and
descriptions. The current site (local `QAS website` code repo) is being replaced; treat it as legacy and as a
source of existing content to migrate, not something to keep developing.

## Process
1. Inventory: what the old site has (pages, products, copy, images, URLs) and what the new Shopify store needs
   (`docs/inventory.md`). Keep a list of old URLs for redirects so SEO isn't lost at switch-over.
2. Source material goes in `30 Resources/` and is never edited.
3. Drafts in `docs/drafts/`, in batches of ~10 for Dom to review.
4. Approved content goes in via Shopify admin or a product CSV import that Claude prepares.
   Theme text/templates via the `QAS website` repo if it is the Shopify theme.
5. Never publish to Shopify without Dom's go-ahead.

## Locations
| What | Where |
|---|---|
| Store | _Shopify URL TBD_ |
| Old site code (legacy, being replaced) | `C:\Users\User\QAS website` on the work laptop (own git identity) |
| New site | Shopify (admin + theme), URL TBD |

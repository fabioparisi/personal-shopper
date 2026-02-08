---
name: product-verifier
description: >
  Verifies product URLs, checks site trustworthiness, validates prices and stock
  availability. Activates when evaluating shopping links, checking if a site is
  legit, "è affidabile", "posso fidarmi", or validating product information.
user-invocable: false
---

# Product Verifier — Background Knowledge

## Link Verification Checklist
For every product URL:
1. WebFetch the URL — must return HTTP 200
2. Verify the page shows the ACTUAL product (not category, not search results, not homepage redirect)
3. Extract and confirm: product name matches, price is visible, stock status shown
4. If WebFetch fails → use MCP Chrome browser tools as fallback

## Site Trust Assessment
When evaluating an unknown site:
- Check Trustpilot/reviews: WebSearch "[site] trustpilot", "[site] reviews", "[site] scam"
- Verify HTTPS/SSL certificate
- Check domain age (new domains = higher risk)
- Look for: physical address, business registration, return policy, customer service contact
- For pharmacies: check for national pharmacy licensing (AIFA for Italy, equivalent for other EU)
- Flag: no HTTPS, no physical address, too-good-to-be-true prices, stock photos, poor grammar

## Counterfeit Detection
- Health products: verify official distributor/seller, check batch numbers if visible
- Electronics: verify authorized dealer, check serial number patterns
- Fashion/luxury: verify official stockist, check for authenticity guarantees
- Generic red flags: prices 50%+ below market average, stock photos only, vague product descriptions

## Verification Output Format
- ✅ Verified: link works, price confirmed, product matches, site trustworthy
- ⚠️ Partially verified: some data confirmed, some not
- ❌ Failed: link broken, price mismatch, site suspicious, product doesn't match

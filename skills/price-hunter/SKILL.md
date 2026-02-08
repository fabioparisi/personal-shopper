---
name: price-hunter
description: >
  Finds the lowest verified price for specific products in Italy/EU. Activates when
  asked about prices, deals, discounts, "dove comprare", "prezzo più basso",
  "in offerta", "Black Friday", or where to buy a specific product.
user-invocable: false
---

# Price Hunter — Background Knowledge

When finding prices for Fabio (Milan, Italy):

## Price Verification Rules
1. NEVER state a price without visiting the actual product page via WebFetch
2. NEVER present a comparator link (Idealo, TrovaPrezzi) as a purchase URL — follow through to the merchant
3. NEVER state "in stock" without seeing stock indicators on the page
4. Always calculate total cost: product price + shipping to Milan

## Price Discovery Strategy
- Search the ENTIRE web, not just major retailers
- Use Idealo.it, TrovaPrezzi.it as DISCOVERY tools to find small shops
- Small niche ecommerce often has the best prices
- For each product: find 3+ verified purchase options sorted by total cost

## Deal Authenticity
- Calculate real discount: (original - current) / original × 100
- Flag suspicious "original prices" inflated before sales
- Prefer stores with 30+ day return policy and free returns
- For unknown stores with suspiciously low prices: verify trustworthiness

## Geographic Priority
Italian sites > EU sites shipping to Italy > international with IT shipping

## Date Stamp
Always note: "Prezzi verificati il [date]"

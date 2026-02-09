# PersonalShopper Plugin for Claude Code

Elite personal shopping assistant that finds, compares, verifies, and recommends products across any category.

## What it does

- Searches globally, filters for EU/Italy availability, verifies every link and price on the actual page
- Multi-track parallel research: expert benchmark, innovation frontier, real-world sentiment, EU availability
- Tiered ranking: best overall, premium, best value, best for you
- XLSX reports for large result sets (10+ products)
- Browser automation fallback for JS-heavy e-commerce sites
- Zero hallucination: every price and link verified via WebFetch or Chrome MCP

## Installation

### From marketplace (recommended)
```bash
claude plugin marketplace add https://github.com/fabioparisi/personal-shopper
claude plugin install personal-shopper@fabio-tools
```

### Local development
```bash
claude --plugin-dir ~/personal-shopper
```

## Usage

```
/personal-shopper:shop trova custodia Nomad Leather Case brown iPhone 14 Pro Max sotto 40 euro
/personal-shopper:shop migliori dentifrici per gengive sensibili + impianti
/personal-shopper:shop confronta ISEO x1R Smart vs CISA DOMO Connexa
/personal-shopper:shop per mia madre, cerca TUTTI i prodotti con questi ceppi probiotici...
```

## Components

| Component | Type | Description |
|-----------|------|-------------|
| `/personal-shopper:shop` | Command | Main search command with full multi-track research protocol |
| `shopping-advisor` | Skill (auto) | Background shopping knowledge, auto-triggers on product discussions |
| `price-hunter` | Skill (auto) | Price verification knowledge, auto-triggers on price queries |
| `product-verifier` | Skill (auto) | Link/site verification knowledge, auto-triggers on trust checks |
| `deep-researcher` | Agent | Parallel subagent for deep research tracks (A/B/C/D) |
| `xlsx_report.py` | Script | Generates formatted XLSX reports with openpyxl |

## Query Types

1. **Exact product** — Find specific products by name/SKU/brand+model
2. **Health/medical** — Exhaustive formulation matching, strain-by-strain verification
3. **Benchmark funnel** — Global best > EU available > Best for you
4. **Deal hunting** — Discount verification with authenticity checks
5. **Comparison** — Side-by-side with weighted scoring
6. **Replacement/upgrade** — Find better alternatives
7. **Creative/advisory** — Expert domain advice + product search
8. **Quick lookup** — Fast verified answers
9. **Cross-matching** — Find accessories for existing product list
10. **Site trust** — Verify e-commerce site legitimacy

## Requirements

- Claude Code with WebSearch and WebFetch access
- Python 3 (for XLSX generation, auto-bootstraps openpyxl)
- Claude in Chrome extension (optional, for browser automation fallback)

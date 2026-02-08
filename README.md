# PersonalShopper Plugin

Elite personal shopping assistant for Claude Code / Claude Cowork.

## What it does

Finds, compares, verifies, and recommends products across any category. Searches globally, filters for EU/Italy availability, verifies every link and price on the actual page. Never hallucates.

## Installation

```bash
# Test locally
claude --plugin-dir ~/personal-shopper

# Or add to a marketplace
/plugin marketplace add ./personal-shopper
```

## Usage

```
/personal-shopper:shop trova custodia Nomad Leather Case brown iPhone 14 Pro Max sotto 40 euro
/personal-shopper:shop migliori dentifrici per gengive sensibili + impianti
/personal-shopper:shop confronta ISEO x1R Smart vs CISA DOMO Connexa
/personal-shopper:shop per mia madre, cerca TUTTI i prodotti con questi ceppi probiotici...
```

## Components

### Command
- `/personal-shopper:shop` — Main search command with full research protocol

### Skills (auto-triggered)
- `shopping-advisor` — Background shopping knowledge and user profile
- `price-hunter` — Price verification and deal authenticity
- `product-verifier` — Link verification and site trust assessment

### Agent
- `deep-researcher` — Forked subagent for parallel deep research on complex queries

### Scripts
- `xlsx_report.py` — Generates formatted XLSX reports (auto-installs openpyxl)

## Query Types Supported

1. **Exact product search** — Find specific products by name, SKU, brand+model
2. **Health/medical** — Exhaustive formulation matching, strain-by-strain verification
3. **Benchmark funnel** — Global best → EU available → Best for you
4. **Deal hunting** — Find discounts with authenticity verification
5. **Comparison** — Side-by-side with weighted scoring
6. **Replacement/upgrade** — Find better alternatives to a bad product
7. **Creative/advisory** — Expert domain advice + product research
8. **Quick lookup** — Fast factual answers
9. **Cross-matching** — Find accessories matching an existing product list
10. **Site trust** — Verify if an ecommerce site is legitimate

## Key Features

- **Zero hallucination**: Every price verified on actual page, every link visited
- **Multi-track research**: Global benchmark, innovation frontier, real-world sentiment, EU availability
- **Tier ranking**: Best overall, premium, best value, best for you
- **XLSX reports**: Auto-generated for 10+ results, opens automatically
- **Health override**: Extra thoroughness for medical/health products
- **Baby protocol**: Safety certification verification for baby products
- **Deal authenticity**: Flags fake discounts and suspicious pricing

## Requirements

- Claude Code with WebSearch and WebFetch access
- Python 3 (for XLSX generation)
- MCP Chrome tools (optional, for JS-heavy site fallback)

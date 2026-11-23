# AL-KARA Cosmetics & GCC Store MCP Server

[![Transport](https://img.shields.io/badge/MCP-Streamable%20HTTP-blue)](https://agent.alkaratr.com/mcp)
[![Auth](https://img.shields.io/badge/Authentication-None%20(Read--Only)-brightgreen)](https://alkaratr.com/.well-known/mcp/server-card.json)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)

Public, unauthenticated, read-only **Streamable HTTP Model Context Protocol (MCP)** server and AI discovery gateway for **[AL-KARA](https://alkaratr.com/)** (`BASMA GLOBAL LOJİSTİK LİMİTED ŞİRKETİ`), offering **64+ ÜTS barcode-verified** cosmetics & personal care products in **Turkish & Arabic**, live TRY pricing, and GCC air-cargo eligibility rules.

---

## Endpoints & Discovery Standards

| Resource | URL |
|---|---|
| **Remote MCP (Streamable HTTP)** | `https://agent.alkaratr.com/mcp` |
| **MCP Server Card** | `https://alkaratr.com/.well-known/mcp/server-card.json` |
| **OpenAPI 3.1 Spec** | `https://agent.alkaratr.com/openapi.json` |
| **A2A Agent Card (v1.0)** | `https://alkaratr.com/.well-known/agent-card.json` |
| **AI Resource Directory (ARD v1.0)** | `https://alkaratr.com/.well-known/ai-catalog.json` |
| **LLMs Index (`TR` / `AR` / Full)** | `https://alkaratr.com/llms.txt` · `https://alkaratr.com/ar/llms.txt` · `https://alkaratr.com/llms-full.txt` |
| **Zero-Egress Edge CDN Manifest** | `https://cdn.alkaratr.com/catalog/manifest.json` |
| **Service Health** | `https://agent.alkaratr.com/health` |

---

## MCP Capabilities

### Tools (`tools/list`)
1. **`search_products`** — Filter the bilingual Turkish & Arabic catalog by keyword, brand, stock availability, GCC air-cargo eligibility, and maximum TRY price.
2. **`get_product`** — Retrieve full details, ÜTS/GTIN barcode verification, FAQ, safety notes, and shipping/return policies by product ID, SKU, GTIN, slug, or title.
3. **`get_store_info`** — Retrieve canonical store metadata, legal registration details, Türkiye/GCC shipping policies, PayTR payment rules, and optional Markdown catalog index.
4. **`check_gulf_shipping`** — Verify air-cargo eligibility for **`SA`**, **`AE`**, **`QA`**, **`KW`**, **`BH`**, **`OM`** (BASMA Global + SMSA Express, 4–7 business days) and flag IATA-restricted items (colognes, perfumes, acetone, aerosols).

### Resources (`resources/list`)
- `alkara://llms.txt` — Canonical Turkish Markdown store index (`text/markdown`)
- `alkara://ar/llms.txt` — Canonical Arabic Markdown store index (`text/markdown`)

---

## Quick Connect Configuration

### Claude Desktop / Cursor / VS Code / Standard Streamable HTTP MCP Client

```json
{
  "mcpServers": {
    "alkara-store": {
      "type": "streamable-http",
      "url": "https://agent.alkaratr.com/mcp"
    }
  }
}
```

### Quick `curl` JSON-RPC 2.0 Test

```bash
curl -sS -X POST https://agent.alkaratr.com/mcp \
  -H "Content-Type: application/json" \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/call","params":{"name":"search_products","arguments":{"query":"Mor Şampuan","limit":3}}}'
```

---

## Official Storefront & Compliance

- **Storefront:** [https://alkaratr.com/](https://alkaratr.com/) (TR) · [https://alkaratr.com/ar/](https://alkaratr.com/ar/) (AR)
- **Operating Entity:** BASMA GLOBAL LOJİSTİK LİMİTED ŞİRKETİ (Istanbul, Türkiye)
- **Contact:** `info@alkaratr.com`

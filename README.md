# Dermalytics

<div align="center">

![Dermalytics Logo](https://www.dermalytics.dev/icon.svg)

**Structured cosmetic ingredient and product data for developers.**

[Website](https://www.dermalytics.dev/) -
[API Docs](https://api.dermalytics.dev/docs) -
[OpenAPI](https://api.dermalytics.dev/openapi.json) -
[Contact](mailto:contact@dermalytics.dev) -
[X](https://x.com/dermalytics)

[![Status](https://img.shields.io/badge/status-live-brightgreen)](https://www.dermalytics.dev/)
[![API](https://img.shields.io/badge/API-production-blue)](https://api.dermalytics.dev/docs)
[![npm](https://img.shields.io/npm/v/dermalytics?label=npm)](https://www.npmjs.com/package/dermalytics)
[![PyPI](https://img.shields.io/pypi/v/dermalytics?label=PyPI)](https://pypi.org/project/dermalytics/)

</div>

---

## What We Build

Dermalytics is a live skincare ingredient analysis API for apps, agents, and developer tools. It helps teams look up cosmetic ingredients, analyze full INCI lists, and build product experiences with structured safety and ingredient data.

The public API supports:

- Ingredient search by name, synonym or CAS/EC identifiers
- Product search by name or brand, with ingredient filters
- Product lookup with a stored ingredient list
- Single ingredient lookup by INCI-style name or synonym
- Batch product ingredient analysis
- Safety severity scoring
- Comedogenicity and irritancy ratings when available
- CAS, EC, Ph. Eur. and formula metadata
- Cosmetic function lists and ingredient trait flags
- Credit-aware REST responses
- MCP access for AI agents using the same API key

## Get Started

Try the hosted REST API without registration:

```bash
curl "https://api.dermalytics.dev/v1/ingredients/niacinamide"
```

You can make 5 requests per IP in a 24-hour window starting with the first request, shared across all REST data endpoints. Search returns up to 3 results without pagination; analysis accepts up to 5 ingredient names. Admitted empty or invalid requests count too. Shared networks share the allowance; IPv6 uses a /64 network.

The API sends remaining/reset headers and, from the second request, an `X-API-Key-URL` registration link. After the allowance, HTTP 429 includes the link and `Retry-After`. [Register for an API key](https://www.dermalytics.dev/dashboard) and 100 welcome credits, then send `Authorization: Bearer YOUR_API_KEY` for full access. Hosted MCP always requires a key.

Or install an SDK:

```bash
npm install dermalytics
```

```bash
pip install dermalytics
```

## Public Repositories

| Repository | Description |
| --- | --- |
| [dermalytics-js](https://github.com/dermalytics-dev/dermalytics-js) | JavaScript and TypeScript SDK for the Dermalytics API. |
| [dermalytics-python](https://github.com/dermalytics-dev/dermalytics-python) | Python SDK for ingredient and product search, lookup and analysis. |
| [dermalytics-dev](https://github.com/dermalytics-dev/dermalytics-dev) | GitHub organization profile. |

## API Surfaces

| Surface | URL |
| --- | --- |
| Website | <https://www.dermalytics.dev/> |
| Swagger UI | <https://api.dermalytics.dev/docs> |
| OpenAPI JSON | <https://api.dermalytics.dev/openapi.json> |
| MCP docs | <https://api.dermalytics.dev/v1/mcp/docs> |

Both SDK repositories are preparing version **1.0.0** with catalog methods, optional API keys and a runtime public-field allowlist. Registry publication is pending; the install commands above currently install the previously published releases. REST, MCP and the dashboard already support the catalog. Product responses omit slugs, source URLs, copied descriptions, images, barcodes and internal metadata. Stored ratings and tags are informational and may be incomplete.

## SDK Examples

TypeScript:

```ts
import { Dermalytics } from 'dermalytics';

const client = new Dermalytics({ apiKey: process.env.DERMALYTICS_API_KEY! });
const ingredient = await client.getIngredient('niacinamide');

console.log(ingredient.trait_flags);
```

Python:

```python
from dermalytics import Dermalytics

client = Dermalytics(api_key="YOUR_API_KEY")
ingredient = client.get_ingredient("niacinamide")

print(ingredient["trait_flags"])
```

## Connect

- Website: <https://www.dermalytics.dev/>
- X: <https://x.com/dermalytics>
- Email: <contact@dermalytics.dev>

---

<div align="center">

Built by the Dermalytics team.

</div>

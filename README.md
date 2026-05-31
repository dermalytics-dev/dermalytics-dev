# Dermalytics

<div align="center">

![Dermalytics Logo](https://www.dermalytics.dev/icon.svg)

**Research-backed skincare ingredient intelligence for developers.**

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

- Single ingredient lookup by INCI-style name or synonym
- Batch product ingredient analysis
- Safety severity scoring
- Comedogenicity and irritancy ratings when available
- CAS, EC, Ph. Eur. and formula metadata
- Cosmetic function lists and ingredient trait flags
- Credit-aware REST responses
- MCP access for AI agents using the same API key

## Get Started

Use the hosted API directly:

```bash
curl "https://api.dermalytics.dev/v1/ingredients/niacinamide" \
  -H "Authorization: Bearer $DERMALYTICS_API_KEY"
```

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
| [dermalytics-python](https://github.com/dermalytics-dev/dermalytics-python) | Python SDK for ingredient lookup and product analysis. |
| [dermalytics-dev](https://github.com/dermalytics-dev/dermalytics-dev) | GitHub organization profile. |

## API Surfaces

| Surface | URL |
| --- | --- |
| Website | <https://www.dermalytics.dev/> |
| Swagger UI | <https://api.dermalytics.dev/docs> |
| OpenAPI JSON | <https://api.dermalytics.dev/openapi.json> |
| MCP docs | <https://api.dermalytics.dev/v1/mcp/docs> |

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

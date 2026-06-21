# SF Compute (sfcompute)

SF Compute (San Francisco Compute Company) runs a spot-priced market for very large scale GPU clusters. The api.sfcompute.com REST API lets buyers and sellers place market orders for blocks of H100 GPU-hours, manage tradable cluster contracts, query live market prices, check balances, and provision managed Kubernetes clusters, nodes, and VMs - all driven by the `sf` CLI and language SDKs.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/sfcompute/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/sfcompute/refs/heads/main/apis.yml)

## Tags

- GPU
- Compute
- Marketplace
- H100
- Spot Pricing

## Timestamps

- **Created:** 2026-06-21
- **Modified:** 2026-06-21

## APIs

### SF Compute Orders / Market API

Place, list, fetch, and cancel buy/sell market orders for blocks of GPU compute. Buy orders specify instance type, quantity, price, duration, and start; sell orders list unused contract time back to the market. Orders fill against the orderbook and resolve into contracts.

- **Human URL:** [https://docs.sfcompute.com/docs/using-the-api](https://docs.sfcompute.com/docs/using-the-api)
- **Base URL:** `https://api.sfcompute.com/v0`

#### Tags

- Orders
- Market
- GPU

#### Properties

- [Documentation](https://docs.sfcompute.com/docs/orders)
- [API Reference](https://fogdocs.sfcompute.com/api-reference)
- [OpenAPI](openapi/sfcompute-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sfcompute.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sfcompute.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### SF Compute Contracts API

List and retrieve tradable cluster contracts - the multi-node H100 InfiniBand reservations produced when buy orders fill. Contracts carry an instance type, an interval/quantity shape, optional zone and cluster, and can be resold by placing sell orders.

- **Human URL:** [https://docs.sfcompute.com/docs/using-the-api](https://docs.sfcompute.com/docs/using-the-api)
- **Base URL:** `https://api.sfcompute.com/v0`

#### Tags

- Contracts
- Clusters
- Reselling

#### Properties

- [Documentation](https://docs.sfcompute.com/guide/reselling)
- [API Reference](https://fogdocs.sfcompute.com/api-reference)
- [OpenAPI](openapi/sfcompute-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sfcompute.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sfcompute.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### SF Compute Prices / Quote API

Request a live market quote for a desired instance type, quantity, duration, and start window. Returns an indicative per-GPU-hour and total price derived from current orderbook depth. There is no single fixed price per GPU-hour - each block is priced independently by the market.

- **Human URL:** [https://docs.sfcompute.com/docs/how-the-market-works](https://docs.sfcompute.com/docs/how-the-market-works)
- **Base URL:** `https://api.sfcompute.com/v0`

#### Tags

- Prices
- Quote
- Spot

#### Properties

- [Documentation](https://sfcompute.com/prices)
- [API Reference](https://fogdocs.sfcompute.com/api-reference)
- [OpenAPI](openapi/sfcompute-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sfcompute.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sfcompute.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### SF Compute Clusters / Nodes API

Manage managed-Kubernetes clusters, nodes, VM instances, procurements (auto-scaling fleets), and the kubeconfig credentials used to reach them. Covers listing instances and zones, fetching clusters tied to an order, and provisioning, redeploying, extending, and releasing nodes.

- **Human URL:** [https://docs.sfcompute.com/docs/nodes](https://docs.sfcompute.com/docs/nodes)
- **Base URL:** `https://api.sfcompute.com/v0`

#### Tags

- Clusters
- Nodes
- Kubernetes

#### Properties

- [Documentation](https://docs.sfcompute.com/docs/nodes)
- [API Reference](https://fogdocs.sfcompute.com/api-reference)
- [OpenAPI](openapi/sfcompute-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sfcompute.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sfcompute.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### SF Compute Balance API

Read account balance (available and current cents), credit balance, transactions, and account identity. Used to confirm spend headroom before placing market orders and to reconcile usage.

- **Human URL:** [https://docs.sfcompute.com/docs/using-the-api](https://docs.sfcompute.com/docs/using-the-api)
- **Base URL:** `https://api.sfcompute.com/v0`

#### Tags

- Balance
- Billing
- Account

#### Properties

- [Documentation](https://docs.sfcompute.com/docs/using-the-api)
- [API Reference](https://fogdocs.sfcompute.com/api-reference)
- [OpenAPI](openapi/sfcompute-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sfcompute.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sfcompute.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### SF Compute Inference API

OpenAI-compatible inference served on SF Compute capacity. Models are listed via the models endpoint and called through a standard chat completions interface, letting bought GPU capacity be exposed as an inference fleet.

- **Human URL:** [https://docs.sfcompute.com/guide/inference-fleet](https://docs.sfcompute.com/guide/inference-fleet)
- **Base URL:** `https://api.sfcompute.com/v0`

#### Tags

- Inference
- LLM
- OpenAI Compatible

#### Properties

- [Documentation](https://docs.sfcompute.com/guide/inference-fleet)
- [OpenAPI](openapi/sfcompute-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

## Common Properties

- [GitHub Organization](https://github.com/sfcompute)
- [LinkedIn](https://www.linkedin.com/company/sfcompute)
- [Website](https://sfcompute.com)
- [Documentation](https://docs.sfcompute.com)
- [Plans](plans/sfcompute-plans-pricing.yml)
- [Rate Limits](rate-limits/sfcompute-rate-limits.yml)
- [Fin Ops](finops/sfcompute-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com

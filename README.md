# SF Compute (sfcompute)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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

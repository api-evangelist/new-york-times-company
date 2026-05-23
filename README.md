# The New York Times Company

The New York Times Company (NYSE: NYT) is the publisher of The New York Times and operator of a portfolio of news, product-review, sports, cooking, and games products including The Athletic, Wirecutter, Wordle, NYT Cooking, and NYT Games. The company also runs a public developer program at [developer.nytimes.com](https://developer.nytimes.com/) that exposes a family of read-only REST APIs over its newsroom content.

This repository is an [APIs.json](https://apisjson.org/) profile of that public developer surface, with OpenAPI specs, JSON Schema, JSON Structure, JSON-LD context, Naftiko capabilities, Spectral rules, vocabulary, plans/pricing, rate-limit, and FinOps artifacts generated from it.

- **Developer portal:** https://developer.nytimes.com/
- **API catalog:** https://developer.nytimes.com/apis
- **Canonical OpenAPI specs:** https://github.com/nytimes/public_api_specs
- **GitHub org:** https://github.com/nytimes (104 public repos)
- **Engineering blog:** https://open.nytimes.com/
- **Contact:** code@nytimes.com

## APIs Documented

All NYT public APIs share `https://api.nytimes.com` as host and authenticate via an `api-key` query parameter.

| API | Base path | Notes |
|---|---|---|
| [Article Search](openapi/article-search-v2-openapi.yml) | `/svc/search/v2` | Lucene-style `fq=` filters, paginates up to 100 pages of 10. |
| [Top Stories](openapi/top-stories-v2-openapi.yml) | `/svc/topstories/v2` | 26 sections plus `home`. |
| [Most Popular](openapi/most-popular-api-v2-openapi.yml) | `/svc/mostpopular/v2` | Emailed / Shared / Viewed for 1, 7, 30 days. |
| [Times Newswire](openapi/timeswire-v3-openapi.yml) | `/svc/news/v3` | Near-real-time firehose of newly published articles. |
| [Archive](openapi/archive-api-openapi.yml) | `/svc/archive/v1` | Full month-by-month NYT metadata going back to 1851. |
| [Books](openapi/books-api-openapi.yml) | `/svc/books/v3` | Best-seller lists + book reviews (by author, ISBN, title). |
| [Movie Reviews](openapi/movie-reviews-v2-openapi.yml) | `/svc/movies/v2` | Reviews, Critics' Picks, and critic biographies. |
| [TimesTags](openapi/times-tags-v3-openapi.yml) | `/svc/suggest/v1` | Auto-suggest over ~27K controlled-vocabulary tags. |
| [Semantic](openapi/semantic-api-openapi.yml) | `/svc/semantic/v2/concept` | 100K+ Times Topics concepts (people, places, orgs, descriptors). |
| [Geographic](openapi/geo-api-v2-openapi.yml) | `/svc/semantic/v2/geocodes` | NYT places enriched with GeoNames data. |
| [Community](openapi/community-api-v3-openapi.yml) | `/svc/community/v3` | Article comments. **Deprecated by NYT.** |

## Repository Structure

```
new-york-times-company/
├── apis.yml                                    APIs.json profile
├── README.md                                   This file
├── openapi/                                    11 OpenAPI 2.0 (Swagger) specs
├── examples/                                   Representative response payloads
├── json-schema/                                JSON Schema for core entities
├── json-structure/                             JSON Structure variants
├── json-ld/                                    JSON-LD context (schema.org-aligned)
├── rules/                                      Spectral ruleset enforcing NYT conventions
├── capabilities/
│   ├── shared/                                 Per-API Naftiko capabilities
│   ├── newsroom-monitoring.yaml                Workflow: live monitoring
│   ├── archive-research.yaml                   Workflow: historical research
│   └── culture-discovery.yaml                  Workflow: books + film
├── vocabulary/                                 Vocabulary/taxonomy
├── plans/                                      API Commons Plans 0.1
├── rate-limits/                                API Commons Rate Limits 0.1
└── finops/                                     FOCUS-aligned FinOps
```

## Authentication, Plans, and Limits

- **Auth:** `?api-key=YOUR_KEY` on every request. Sign up at https://developer.nytimes.com/accounts/create.
- **Plans:** A single free Developer tier covers all 11 APIs. See [plans/new-york-times-company-plans-pricing.yml](plans/new-york-times-company-plans-pricing.yml).
- **Rate limits:** Per-minute and per-day caps, enforced via HTTP 429. NYT describes them as "subject to change"; the Community API historically documented 5,000 req/day. See [rate-limits/new-york-times-company-rate-limits.yml](rate-limits/new-york-times-company-rate-limits.yml).
- **Cost model:** Free. No billing surface, no FOCUS billing data. See [finops/new-york-times-company-finops.yml](finops/new-york-times-company-finops.yml).
- **Attribution:** Required. See [developer.nytimes.com/attribution](https://developer.nytimes.com/attribution).

## Notable Patterns

- **Swagger 2.0.** All canonical specs are still OpenAPI 2.0; modernizing to 3.x would unlock components, webhooks, and oneOf schemas.
- **Query-string API keys.** Convenient for browser testing but means keys appear in server logs and browser history.
- **JSON-only.** All operations produce `application/json`.
- **No webhooks, no async, no GraphQL.** Pure REST, pull-based.
- **No published per-API quotas.** Only the deprecated Community API ever published an integer (5,000/day).

## Notable Absences

- No public Athletic, Wirecutter, Cooking, Games, or Wordle APIs.
- No paid tier or upgrade path published.
- No SLA or status page documented for the developer APIs.
- No OAuth, no JWT, no scoped tokens.
- No OpenAPI 3.x.
- No first-party SDKs (the GitHub org publishes infra tooling and visualization libraries, not API client SDKs).

## Sources

- `developer.nytimes.com` API catalog and per-API docs
- `github.com/nytimes/public_api_specs` (canonical OpenAPI 2.0 files)
- `github.com/nytimes` org metadata (verified, 104 repos, 1007 followers)
- NYT corporate Wikipedia entry (revenue, subscribers, subsidiaries)

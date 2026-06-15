# The New York Times Company (new-york-times-company)

The New York Times Company (NYSE: NYT) is the publisher of The New York Times and operator of a portfolio of news,
product-review, sports, cooking, and games products including The Athletic, Wirecutter, Wordle, NYT Cooking,
and NYT Games. The company also runs a public developer program at developer.nytimes.com that exposes a family
of read-only REST APIs over its newsroom content: article search, top stories, most popular, archive going back
to 1851, best-seller and book-review lists, movie reviews, the Times Newswire firehose, the controlled
vocabulary that powers Times Topics (TimesTags), the Semantic API, and a Geographic API that pairs Times
geo-tagged content with the GeoNames database. All APIs share api.nytimes.com as the host, use a query-string
api-key for authentication, and respond as JSON.

**APIs.json:** [https://nytimes.com](https://nytimes.com)

## Tags

- News
- Media
- Publishing
- Newspapers
- Articles
- Books
- Movies
- Sports
- Games
- Cooking
- Reviews
- Search
- Semantic
- Tagging
- Controlled Vocabulary
- Geographic
- Archive

## Timestamps

- **Created:** Thu Mar 11 2010 19:00:00 GMT-0500 (Eastern Standard Time)
- **Modified:** Fri May 22 2026 20:00:00 GMT-0400 (Eastern Daylight Time)

## APIs

### Article Search API

Look up New York Times articles by keyword. Supports filtering with Lucene-style filter queries (fq=...)
against an Elasticsearch-backed index, facets, date range filters, and pagination up to 100 pages of
10 results each (1,000 results max). Coverage runs from 1851 to today.

- **Human URL:** [https://developer.nytimes.com/docs/articlesearch-product/1/overview](https://developer.nytimes.com/docs/articlesearch-product/1/overview)
- **Base URL:** `https://api.nytimes.com/svc/search/v2`

#### Tags

- Articles
- Search
- Elasticsearch
- News

#### Properties

- [Documentation](https://developer.nytimes.com/docs/articlesearch-product/1/overview)
- [OpenAPI](openapi/article-search-v2-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/article-search-v2.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/article-search-v2.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/article-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/article-search-example.json)
- [Sign Up](https://developer.nytimes.com/accounts/create)

### Top Stories API

Returns an array of articles currently on a specified NYTimes.com section (or the homepage). 26
sections are supported including arts, business, opinion, politics, science, sports, technology,
upshot, and world.

- **Human URL:** [https://developer.nytimes.com/docs/top-stories-product/1/overview](https://developer.nytimes.com/docs/top-stories-product/1/overview)
- **Base URL:** `https://api.nytimes.com/svc/topstories/v2`

#### Tags

- Articles
- Top Stories
- Sections
- News

#### Properties

- [Documentation](https://developer.nytimes.com/docs/top-stories-product/1/overview)
- [OpenAPI](openapi/top-stories-v2-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/top-stories-v2.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/top-stories-v2.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/article-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/top-stories-home-example.json)

### Most Popular API

Returns the most emailed, most shared (Facebook), and most viewed articles on NYTimes.com for the
last 1, 7, or 30 days.

- **Human URL:** [https://developer.nytimes.com/docs/most-popular-product/1/overview](https://developer.nytimes.com/docs/most-popular-product/1/overview)
- **Base URL:** `https://api.nytimes.com/svc/mostpopular/v2`

#### Tags

- Articles
- Most Popular
- Analytics
- Sharing

#### Properties

- [Documentation](https://developer.nytimes.com/docs/most-popular-product/1/overview)
- [OpenAPI](openapi/most-popular-api-v2-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/most-popular-api-v2.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/most-popular-api-v2.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/article-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/most-popular-emailed-example.json)

### Times Newswire API

An up-to-the-minute stream of metadata and links for articles as soon as they are published on
NYTimes.com. Can be filtered by source (all, nyt, iht) and one or more sections.

- **Human URL:** [https://developer.nytimes.com/docs/timeswire-product/1/overview](https://developer.nytimes.com/docs/timeswire-product/1/overview)
- **Base URL:** `https://api.nytimes.com/svc/news/v3`

#### Tags

- Articles
- Firehose
- Newswire
- Real Time

#### Properties

- [Documentation](https://developer.nytimes.com/docs/timeswire-product/1/overview)
- [OpenAPI](openapi/timeswire-v3-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/timeswire-v3.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/timeswire-v3.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/article-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/timeswire-content-example.json)

### Archive API

Returns an array of NYT articles for a given month, going back to 1851. Response fields mirror the
Article Search API. Useful for bulk-loading article metadata locally. Responses can be ~20MB and
contain thousands of articles per month.

- **Human URL:** [https://developer.nytimes.com/docs/archive-product/1/overview](https://developer.nytimes.com/docs/archive-product/1/overview)
- **Base URL:** `https://api.nytimes.com/svc/archive/v1`

#### Tags

- Articles
- Archive
- History
- Bulk Data

#### Properties

- [Documentation](https://developer.nytimes.com/docs/archive-product/1/overview)
- [OpenAPI](openapi/archive-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/archive-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/archive-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/article-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/archive-month-example.json)

### Books API

Provides information about NYT book reviews and The New York Times Best Sellers lists. Some lists
are weekly and some monthly. Supports current and historical date lookups, list metadata, and
review lookup by author, ISBN, or title.

- **Human URL:** [https://developer.nytimes.com/docs/books-product/1/overview](https://developer.nytimes.com/docs/books-product/1/overview)
- **Base URL:** `https://api.nytimes.com/svc/books/v3`

#### Tags

- Books
- Best Sellers
- Reviews
- Lists

#### Properties

- [Documentation](https://developer.nytimes.com/docs/books-product/1/overview)
- [OpenAPI](openapi/books-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/books-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/books-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/best-seller-book-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/books-best-sellers-list-example.json)

### Movie Reviews API

Search NYT movie reviews by keyword, filter by Critics' Picks, and retrieve metadata about Times
movie critics.

- **Human URL:** [https://developer.nytimes.com/docs/movie-reviews-api/1/overview](https://developer.nytimes.com/docs/movie-reviews-api/1/overview)
- **Base URL:** `https://api.nytimes.com/svc/movies/v2`

#### Tags

- Movies
- Reviews
- Critics
- Culture

#### Properties

- [Documentation](https://developer.nytimes.com/docs/movie-reviews-api/1/overview)
- [OpenAPI](openapi/movie-reviews-v2-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [JSON Schema](json-schema/movie-review-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/movie-reviews-search-example.json)

### TimesTags API

Auto-suggest service over the New York Times controlled vocabulary used to build Times Topics pages
(approximately 27,000 tags: 3,000 Descriptors, 1,500 Geographic, 7,500 Organizations, 15,000 People).
Useful for building tag pickers, normalizing entity names, or feeding the Article Search fq=
parameter.

- **Human URL:** [https://developer.nytimes.com/docs/timestags-product/1/overview](https://developer.nytimes.com/docs/timestags-product/1/overview)
- **Base URL:** `https://api.nytimes.com/svc/suggest/v1`

#### Tags

- Tags
- Controlled Vocabulary
- Semantic
- Auto Suggest

#### Properties

- [Documentation](https://developer.nytimes.com/docs/timestags-product/1/overview)
- [OpenAPI](openapi/times-tags-v3-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/times-tags-v3.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/times-tags-v3.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/tag-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/times-tags-example.json)

### Semantic API

Complements Article Search by exposing the full controlled vocabulary of over 100,000 people,
places, organizations, and descriptors used as metadata by The New York Times since 1981. Returns
the full Times Topics record for a concept, including ticker symbols, related URLs, taxonomic
relations, and combinations of search criteria.

- **Human URL:** [https://developer.nytimes.com/docs/semantic-api-product/1/overview](https://developer.nytimes.com/docs/semantic-api-product/1/overview)
- **Base URL:** `https://api.nytimes.com/svc/semantic/v2/concept`

#### Tags

- Semantic
- Concepts
- Linked Data
- Controlled Vocabulary
- Entities

#### Properties

- [Documentation](https://developer.nytimes.com/docs/semantic-api-product/1/overview)
- [OpenAPI](openapi/semantic-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/semantic-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/semantic-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/concept-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/semantic-concept-example.json)

### Geographic API

Linked-data extension of the Semantic API that pairs the location concepts in the Times controlled
vocabulary with the GeoNames database, returning a normalized record for places (events, venues,
film ratings, etc.) with lat/long, bounding-box, and date-range filtering.

- **Human URL:** [https://developer.nytimes.com/docs/geo-product/1/overview](https://developer.nytimes.com/docs/geo-product/1/overview)
- **Base URL:** `https://api.nytimes.com/svc/semantic/v2/geocodes`

#### Tags

- Geographic
- Places
- Linked Data
- GeoNames
- Events

#### Properties

- [Documentation](https://developer.nytimes.com/docs/geo-product/1/overview)
- [OpenAPI](openapi/geo-api-v2-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/geo-api-v2.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/geo-api-v2.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Example](examples/geo-query-example.json)

### Community API (Deprecated)

Get access to comments from registered users on New York Times articles. Marked deprecated by NYT;
a replacement was in progress at the time the spec was published. Documented here for completeness
and historical use only. Documented daily limit was 5,000 requests per day.

- **Human URL:** [https://developer.nytimes.com/docs/community-api-product/1/overview](https://developer.nytimes.com/docs/community-api-product/1/overview)
- **Base URL:** `http://api.nytimes.com/svc/community/v3`

#### Tags

- Community
- Comments
- User Generated Content
- Deprecated

#### Properties

- [Documentation](https://developer.nytimes.com/docs/community-api-product/1/overview)
- [OpenAPI](openapi/community-api-v3-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/community-api-v3.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/community-api-v3.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Example](examples/community-comments-example.json)
- [Status](https://developer.nytimes.com/docs/community-api-product/1/overview)

## Common Properties

- [About Company](https://www.nytco.com/)
- [Developer Portal](https://developer.nytimes.com/)
- [A P Is](https://developer.nytimes.com/apis)
- [Sign Up](https://developer.nytimes.com/accounts/create)
- [F A Q](https://developer.nytimes.com/faq)
- [Terms Of Use](https://developer.nytimes.com/terms)
- [Attribution Guidelines](https://developer.nytimes.com/attribution)
- [Blog](https://open.nytimes.com/)
- [Git Hub](https://github.com/nytimes)
- [Open A P I Specs Repo](https://github.com/nytimes/public_api_specs)
- [Contact Email](mailto:code@nytimes.com)
- [Wikipedia](https://en.wikipedia.org/wiki/The_New_York_Times_Company)
- [About The Athletic](https://www.nytco.com/products/the-athletic/)
- [About Wirecutter](https://www.nytco.com/products/wirecutter/)
- [About Cooking](https://www.nytco.com/products/cooking/)
- [About Games](https://www.nytco.com/products/games/)
- [Spectral Rules](rules/new-york-times-rules.yml)
- [Vocabulary](vocabulary/new-york-times-company-vocabulary.yml)
- [J S O N L D Context](json-ld/new-york-times-company-context.jsonld)
- [Plans Pricing](plans/new-york-times-company-plans-pricing.yml)
- [Rate Limits](rate-limits/new-york-times-company-rate-limits.yml)
- [Fin Ops](finops/new-york-times-company-finops.yml)
- [Capability Workflow](capabilities/newsroom-monitoring.yaml)
- [Capability Workflow](capabilities/archive-research.yaml)
- [Capability Workflow](capabilities/culture-discovery.yaml)
- [L L Ms Txt](https://developer.nytimes.com/llms.txt)

## Maintainers

**FN:** API Evangelist
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com

# Yodeck (yodeck-signage)

Yodeck is a cloud-based digital signage platform for managing screens and content at scale, typically on Raspberry Pi based Yodeck Players. Teams upload and organize media, build playlists and multi-zone layouts, schedule content, group content into shows, and monitor and control players remotely. Alongside the web app, Yodeck publishes a **REST API** that programmatically manages media, playlists, layouts, screens (monitors), schedules, shows, and workspaces using named, role-scoped API tokens.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/yodeck-signage/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/yodeck-signage/refs/heads/main/apis.yml)

## Access Model (Important)

- **The REST API is real and documented, but gated.** The interactive API reference lives at [https://app.yodeck.com/api-docs/](https://app.yodeck.com/api-docs/) and is **behind an account login**. The API feature is available on the **Premium and Enterprise plans** only.
- **Authentication** uses a **named, role-scoped API token** generated under *Account Settings > Advanced Settings > API Tokens*. The token acts as a user and inherits the permissions of the role assigned to it. The token is shown once at creation.
- **Endpoints in this repository are MODELED.** Because the live reference is login-gated, the OpenAPI spec and Postman/Open Collection here are modeled from Yodeck's published resource set and product/feature pages, **not** copied from an official machine-readable spec. The base path (`https://app.yodeck.com/api/v1`), exact field names, pagination, and the precise `Authorization` header value format should be confirmed against the live reference before use. See `review.yml` (`endpointsModeled: true`).
- **Player HTTP API is separate and local-only.** Each player exposes a Player HTTP API bound to `http://127.0.0.1:8080` for on-device apps (`/device`, `/request` proxy, `/storage`). It is not a public network API and not a WebSocket.
- **No public WebSocket API.** See `review.yml`.

## Tags

- Digital Signage
- Screen Management
- Content Management
- Media
- Playlists
- Scheduling
- Raspberry Pi

## Timestamps

- **Created:** 2026-07-05
- **Modified:** 2026-07-05

## APIs

### Yodeck Media API

Programmatically upload, list, update, and delete media assets - images, videos, documents, web pages, and app content - and sync media from external URLs into Yodeck.

- **Human URL:** [https://www.yodeck.com/features/yodeck-api/](https://www.yodeck.com/features/yodeck-api/)
- **Base URL:** `https://app.yodeck.com/api/v1` (modeled)

### Yodeck Playlists API

Create, list, get, update, and delete playlists - ordered sequences of media with per-item durations and transitions - and manage the media items within each playlist.

- **Human URL:** [https://www.yodeck.com/features/yodeck-api/](https://www.yodeck.com/features/yodeck-api/)
- **Base URL:** `https://app.yodeck.com/api/v1` (modeled)

### Yodeck Layouts API

Build and manage multi-zone screen layouts that split a display into regions, each region playing its own media, playlist, or widget.

- **Human URL:** [https://www.yodeck.com/features/yodeck-api/](https://www.yodeck.com/features/yodeck-api/)
- **Base URL:** `https://app.yodeck.com/api/v1` (modeled)

### Yodeck Screens API

Register and manage screens (monitors/players), assign default content, read player status and health, and trigger remote actions such as reboot or content refresh. In Yodeck a screen is often called a monitor.

- **Human URL:** [https://www.yodeck.com/features/yodeck-api/](https://www.yodeck.com/features/yodeck-api/)
- **Base URL:** `https://app.yodeck.com/api/v1` (modeled)

### Yodeck Schedules API

Define time-based schedules that control which content plays on which screens and when, including recurring dayparting rules and date ranges.

- **Human URL:** [https://www.yodeck.com/features/yodeck-api/](https://www.yodeck.com/features/yodeck-api/)
- **Base URL:** `https://app.yodeck.com/api/v1` (modeled)

### Yodeck Shows API

Manage shows - reusable groupings of media, playlists, and layouts that can be assigned to screens as a single content set.

- **Human URL:** [https://www.yodeck.com/features/yodeck-api/](https://www.yodeck.com/features/yodeck-api/)
- **Base URL:** `https://app.yodeck.com/api/v1` (modeled)

### Yodeck Workspaces API

Programmatically create, configure, and control workspaces - separate environments with their own users, permissions, and content - for agencies and multi-location deployments.

- **Human URL:** [https://www.yodeck.com/features/yodeck-api/](https://www.yodeck.com/features/yodeck-api/)
- **Base URL:** `https://app.yodeck.com/api/v1` (modeled)

## Artifacts

- [OpenAPI (modeled)](openapi/yodeck-signage-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection (modeled)](collections/yodeck-signage.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection (modeled)](collections/yodeck-signage.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Plans & Pricing](plans/yodeck-signage-plans-pricing.yml)
- [Rate Limits](rate-limits/yodeck-signage-rate-limits.yml)
- [FinOps](finops/yodeck-signage-finops.yml)

## Pricing (per screen, per month)

Per Yodeck's published pricing following the April 1, 2026 update:

- **Free:** $0 for exactly one registered screen with Basic features (free only while the account has one screen).
- **Basic:** $8 / screen / month.
- **Premium:** $12 / screen / month — includes REST API access.
- **Enterprise:** $16 / screen / month — includes REST API access and workspaces; deployments over 50 screens need a custom quote from Yodeck sales.

Annual billing does not discount the per-screen rate but bundles free Yodeck Player hardware per screen. Third-party aggregators list Premium/Enterprise at $11/$15; Yodeck's own documentation lists $12/$16, used here.

## Common Properties

- [Website](https://www.yodeck.com)
- [LinkedIn](https://www.linkedin.com/company/yodeck)
- [Documentation](https://www.yodeck.com/docs/)
- [API Reference (login-gated)](https://app.yodeck.com/api-docs/)
- [Sign Up](https://app.yodeck.com/signup/)
- [Plans](plans/yodeck-signage-plans-pricing.yml)
- [Rate Limits](rate-limits/yodeck-signage-rate-limits.yml)
- [FinOps](finops/yodeck-signage-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com

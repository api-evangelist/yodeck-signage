# Yodeck (yodeck-signage)

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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

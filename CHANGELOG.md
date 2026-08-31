# Changelog

## v2.0.6 - 2026-08-31

### Added
- Added admin batch regenerate for repository documents.
- Added cluster-wide configurable wiki generation concurrency with database slots and instance heartbeats (default concurrency is 1).
- Added homepage server-side rendering with a 10-second cache so the first paint no longer waits on a client repository-list request.
- Added broader default wiki languages (Traditional Chinese, Spanish, French, German, Portuguese, Polish, Russian, Arabic) and made `WIKI_LANGUAGES` take effect.
- Added OrcaRouter as a built-in AI provider preset.
- Added shareable recommendation time-window filters and trending scores.
- Added a default 1-hour sitemap cache that serves a stale map while refreshing in the background.

### Changed
- Allowed administrators to regenerate any repository, not only ones they own.
- Switched the repository explorer tree to popover navigation and optimized sitemap generation with concurrent default-tree fetches while excluding branch language variants.
- Updated project docs for the current .NET 10 / Microsoft.Agents.AI stack, ZIP and local-directory import, and background workers.
- Removed obsolete standalone database query tools.

### Fixed
- Replaced the chat MCP wrapper with a real MCP client so provider tools speak Streamable HTTP / JSON-RPC.
- Fixed distributed wiki generation lock assignment across multiple instances.
- Normalized LLM Mermaid before persistence and surfaced render errors before falling back to a code block.
- Stopped retrying failed mind-map records and recovered orphaned Processing jobs.
- Cleared nested DocCatalog parents before repository delete.
- Coerced null tool-call arguments to an empty JSON object.
- Bound the GitHub App installation department foreign key to the navigation property.
- Fixed the wiki language selector TypeScript types, Star History chart, and Aliyun ACR image pushes by disabling Buildx provenance and SBOM.

## v2.0.5 - 2026-08-12

### Added
- Added organization/folder filter search in the repository explorer sidebar.
- Added shared `WithAnnouncement` layout wrapper so the top announcement banner appears across main and repository pages.

### Changed
- Redesigned the repository explorer left panel with initials avatars, A–Z sticky grouping, teal selected-state accent, and denser Linear-style scanning.
- Localized explorer filter/empty-state copy across supported languages.

## v2.0.4 - 2026-08-12

### Added
- Added repository branch generation tasks, admin controls, and workspace isolation for multi-branch wiki builds.
- Added repository scan plan controls and startup schema updates.
- Added repository tree/explorer view for browsing public repositories.
- Added SITE_URL support for public site URL configuration and SEO/sitemap generation.
- Added Brazilian Portuguese (pt-BR) UI translations.
- Added global MCP provider endpoint.
- Added RoutinAI sponsorship top announcement banner with multi-language copy and dismiss state.
- Added shared admin UI building blocks (page header, data table, pagination, status badge, breadcrumbs).

### Changed
- Redesigned the main sidebar into Discover / Workspace / Tools groups with path-based active states.
- Reworked the homepage into a compact workspace layout with tighter search and actions.
- Refreshed admin dashboard and list pages for clearer hierarchy and denser operational layouts.
- Localized admin UI and added language toggle to the admin header.
- Improved sitemap generation with branch and language support.
- Updated wiki generation workflow, including segmented content generation and repository page layout polish.

### Fixed
- Fixed nested `.env` key loading and stale wiki model bindings for DeepSeek setups.
- Fixed Gemini `finish_reason` normalization for the OpenAI SDK path.
- Prevented incremental updates from wiping the wiki catalog; added regression coverage.
- Fixed ZIP upload multipart/form-data handling.
- Fixed source file links for non-GitHub hosts (e.g. Azure DevOps).
- Fixed chat stream keepalive and code-block rendering issues.
- Hardened branch generation locking/mutations and backfilled SQLite schema.
- Escaped sitemap XML URLs.
- Improved document generation error handling so partial failures do not always fail the whole repository job.
- Fixed local Git source branch handling.

## v2.0.3 - 2026-05-30

### Added
- Added AI billing and token usage accounting across chat, document tools, and admin statistics.
- Added AI provider preset loading and expanded admin controls for AI providers and model configs.

### Changed
- Reworked repository processing, incremental updates, wiki generation, and prompt cache handling.
- Updated admin pages, repository UI, SEO metadata, sitemap, and i18n content.

### Fixed
- Fixed Graphify build tooling support.
- Fixed several backend and frontend regressions surfaced by the new AI and admin flows.

### Added
- Added AI provider and model config management with built-in preset loading.
- Added repository skill export support and related data model and pipeline updates.

### Changed
- Reworked repository processing, chat, Graphify, statistics, and admin settings flows.
- Updated frontend admin screens, repository views, and i18n content.
- Upgraded several foundational dependencies to match the current platform stack.

### Fixed
- Fixed database initialization, API mapping, and frontend property passing issues.
- Expanded test coverage to reduce regression risk.

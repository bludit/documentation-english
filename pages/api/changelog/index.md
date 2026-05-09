# Changelog
<!-- position: 4 -->

This page tracks behaviour changes to the API plugin. Older changes that predate the introduction of this changelog are not listed.

<h2 id="unreleased">Unreleased</h2>

### Added

- **Real HTTP status codes.** Endpoints now return `200`, `201`, `400`, `401`, `404`, `500` based on the outcome instead of always `200`. The `status: "0"|"1"` body field is kept for back-compat. See [Error responses](../errors).
- **Full page object on create and edit.** `POST /api/pages` and `PUT /api/pages/{key}` now return the complete page object (title, content, uuid, etc.) under `data`, not just `{key}`. The `key` field is still present.
- **`meta` block on list responses.** `GET /api/pages` includes `meta.total`, `meta.pageNumber`, `meta.pageSize`, and `meta.hasMore` for pagination.
- **`scheduled` filter on `GET /api/pages`** to include scheduled pages in the listing.

### Changed

- `POST /api/pages` returns `201 Created` on success.
- `GET /api/pages/{key}`, `PUT /api/pages/{key}`, `DELETE /api/pages/{key}` return `404 Not Found` when the page does not exist.
- `GET /api/tags/{key}`, `GET /api/categories/{key}`, `GET /api/users/{username}` return `404` when not found.

### Fixed

- **Pagination crash past the end.** Requests with a `pageNumber` past the last page (or with a non-positive `pageNumber` / `numberOfItems`) used to crash the API. They now return `200` with an empty `data` array and `meta.hasMore: false`.
- **Double-encoding on form-encoded inputs.** Submitting `title=Cats & Dogs` via form-encoding used to store `Cats &amp;amp; Dogs` (double-encoded). Values are now sanitised once, by core.

### Security

- Generated API tokens are shorter (256 bits / 64 hex characters instead of 512 bits / 128 hex characters). Existing tokens continue to work; new installs get the shorter format.

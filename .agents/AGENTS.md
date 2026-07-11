# AGENTS.md

Static JSON API served via GitHub Pages (no build, tests, or lint toolchain). Data is the product; there is no application code.

## What this repo is

- `index.json` — root directory listing API endpoints; bump `lastUpdated` (ISO date) when endpoints change. Validated by `index.schema.json`.
- `communities/` — competitive programming clubs, keyed by country, then state. One `data.json` + one `schema.json`.
- `credentials/` — catalog of free certificates/programs/certifications/platforms. One `data.json`, one `schema.json`, plus `domains-categories.md` (human-readable enum reference) and a `index.html` test panel.
- Served at `https://cpc-gallos.github.io/api/...` once merged to `main` (GitHub Pages auto-deploys).

## Conventions to follow (from CONTRIBUTING.md — verify before editing)

- **JSON keys in English** (`name`, `description`, `provider`); **values in Spanish.**
- All JSON data files (`index.json`, `data.json`) must reference their schema at the root: `"$schema": "schema.json"` (or `index.schema.json`).
- All schemas must use draft `2020-12` and define an absolute `$id`. E.g.: `"$id": "https://cpc-gallos.github.io/api/credentials/schema.json"`, followed by `"$schema": "https://json-schema.org/draft/2020-12/schema"`.
- Schemas describe the *entire* file structure (e.g., `credentials/schema.json` defines the `credentials` array at its root).
- When adding a credential, every enum value must match `credentials/schema.json` exactly:
  - `providerGroup`: `Big Tech` | `Enterprise Tech` | `Government` | `University` | `Other`
  - `type`: `program` | `certificate` | `certification` | `platform`
  - `domain`: `Technology & Computer Science` | `Languages` | `Business & Professional Development`
  - `category`: see the full enum in `schema.json` (also listed in `credentials/domains-categories.md`). Mismatch breaks schema validation.
- `credentials/data.json` entries require: `id, name, provider, providerGroup, type, domain, category, url`. `id` is a kebab-case slug of the name. `image` is `""` when no logo. `tags` optional (values seen: `woman`, `mooc`, `superbadge`, `python`, etc.).
- In `communities/data.json`, every country is a top-level key, containing its states. States without clubs use `"clubs": null` (don't omit them). Per-club required: `name`, `status` (`activo` | `inactivo`).

## Verification (no toolchain — do it manually)

- `python -m json.tool < file.json` or `jq . file.json` to confirm valid JSON before committing.
- Validate against the schema with any JSON Schema 2020-12 validator (e.g. `ajv`) if available; otherwise cross-check enum values against `schema.json` by eye.
- **CI Validation:** A GitHub Action workflow runs on every PR and push to `main` to validate all JSON files against their schemas using `ajv-cli`. Ensure your JSON is valid before pushing.

## Workflow

- Default branch is `main`. Changes go via PR (see `CONTRIBUTING.md`); merging to `main` publishes to GitHub Pages automatically — treat `main` as production.

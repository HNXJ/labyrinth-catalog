# HNXJ Labyrinth Catalog

Canonical public registry for the HNXJ ecosystem gallery rendered at
[hnxj.github.io/labyrinth](https://hnxj.github.io/labyrinth/).

## Authority

- **registry.json** — mutable catalog entries (applications, surfaces, experiments)
- **registry.schema.json** — contract schema
- **validate-registry.mjs** — deployment gate
- **MANIFEST.json** — publication metadata and contract version

## Publication

On merge to `main`, CI validates `catalog/registry.json` and publishes to the
`catalog-latest` GitHub Release at:

`https://github.com/HNXJ/labyrinth/releases/download/catalog-latest/registry.json`

The Pages renderer consumes this endpoint and falls back to its sealed snapshot when the
remote registry is unavailable, malformed, schema-invalid, or uses an unsupported contract
version.

## Editing

```bash
node catalog/validate-registry.mjs
```

Routine catalog changes belong here — not in `HNXJ/hnxj.github.io`.

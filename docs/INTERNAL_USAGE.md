# Internal Usage

## `docs/internal-tooling-circular`

> ⚠️ **This preset is intended ONLY for the four core internal tooling repositories listed below.**

### Purpose

The four core internal tooling repositories form a circular tooling dependency graph:

- [juancarlosjr97/pre-commit-to-rule-them-all](https://github.com/juancarlosjr97/pre-commit-to-rule-them-all)
- [juancarlosjr97/github-actions-workflows-to-rule-them-all](https://github.com/juancarlosjr97/github-actions-workflows-to-rule-them-all)
- [juancarlosjr97/release-it-containerized](https://github.com/juancarlosjr97/release-it-containerized)
- [juancarlosjr97/renovate-configuration](https://github.com/juancarlosjr97/renovate-configuration)

Without this preset, Renovate continuously generates PRs updating cross-references among them, causing endless update churn. This preset disables Renovate updates for all four internal repos while preserving normal Renovate behaviour for every other dependency.

### Usage

Each of the four internal repositories must extend **both** the default configuration and this preset (both unpinned, tracking latest):

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": [
    "github>juancarlosjr97/renovate-configuration",
    "github>juancarlosjr97/renovate-configuration:docs/internal-tooling-circular"
  ]
}
```

> **Note:** Do not use this preset in non-core repositories. It is specifically designed to prevent circular update churn among the four internal tooling projects listed above.

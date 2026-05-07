# Renovate Configuration

Centralized configuration for Renovate.

## Usage

Please use the latest tag as a reference from the [latest release](https://github.com/juancarlosjr97/renovate-configuration/releases/latest).

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>juancarlosjr97/renovate-configuration#x.y.z"]
}
```

## Configuration

The Renovate configuration is available on the [default.json](./default.json).

## Presets

### `internalToolingCircular/main-pin`

A special preset intended **only** for the following core internal tooling repositories:

- [juancarlosjr97/pre-commit-to-rule-them-all](https://github.com/juancarlosjr97/pre-commit-to-rule-them-all)
- [juancarlosjr97/github-actions-workflows-to-rule-them-all](https://github.com/juancarlosjr97/github-actions-workflows-to-rule-them-all)
- [juancarlosjr97/release-it-containerized](https://github.com/juancarlosjr97/release-it-containerized)
- [juancarlosjr97/renovate-configuration](https://github.com/juancarlosjr97/renovate-configuration)

**Purpose:** These four repositories form a circular tooling dependency graph. Without this preset, Renovate would continuously generate PRs updating cross-references among them, causing endless update churn. This preset disables Renovate updates for all four internal repos while preserving normal Renovate behaviour for every other dependency.

**Usage** — find the latest release tag on the [releases page](https://github.com/juancarlosjr97/renovate-configuration/releases/latest) and replace `x.y.z`:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>juancarlosjr97/renovate-configuration:internalToolingCircular/main-pin#x.y.z"]
}
```

The preset already extends the default `github>juancarlosjr97/renovate-configuration` configuration (unpinned, so it tracks the latest release automatically), so you do not need to include the default preset separately.

> **Note:** Do not use this preset in non-core repositories. It is specifically designed to prevent circular update churn among the four internal tooling projects listed above.

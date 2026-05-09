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

### `docs/internal-tooling-circular/main-pin`

A special preset intended **only** for the four core internal tooling repositories to prevent circular dependency update churn. See [docs/INTERNAL_USAGE.md](./docs/INTERNAL_USAGE.md) for full details and usage instructions.

# Renovate Configuration

Centralized configuration for Renovate.

## Usage

For the internal shared-tooling ecosystem, pin this configuration to `main` intentionally:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>juancarlosjr97/renovate-configuration#main"]
}
```

This branch pinning is intentional to reduce circular Renovate update churn between:

- `juancarlosjr97/pre-commit-to-rule-them-all`
- `juancarlosjr97/github-actions-workflows-to-rule-them-all`
- `juancarlosjr97/release-it-containerized`
- `juancarlosjr97/renovate-configuration`

## Configuration

The Renovate configuration is available on the [default.json](./default.json).

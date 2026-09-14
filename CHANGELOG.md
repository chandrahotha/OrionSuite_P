# Changelog (product level)

This file tracks user-visible releases of the official distribution
`@orionscanner/cli`. It intentionally contains no implementation details.

## 0.9.1 (current, `latest`)

- Official public distribution via `@orionscanner/cli`.
- `orion --version`, `orion --help`, `orion .` entry points.
- SARIF / JSON / HTML report outputs.
- Incremental scanning, auto-fix, threat-modeling entry points.

Verify after install:

```bash
orion --version
orion --help
```

## Prior releases

- `0.9.0`, `0.8.0`, and earlier `0.5.x` lines were stepping stones to the
  current showcase/distribution split. The npm `latest` dist-tag is the
  source of truth - do not downgrade or reset versions based on this file.

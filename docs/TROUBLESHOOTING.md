# Troubleshooting

## `orion: command not found`

Reinstall globally and ensure npm globals are on PATH:

```bash
npm install -g @orionscanner/cli
orion --version
```

## `Orion executable not found`

Your install resolved the JS wrapper but no platform binary. Reinstall
from npm - do not attempt a source checkout (none is published).

## Version looks stale

```bash
npm view @orionscanner/cli dist-tags
npm install -g @orionscanner/cli@latest
orion --version
```

`latest` (currently 0.9.1) is authoritative.

## SARIF upload shows nothing

Confirm the SARIF file was written (`--output orion.sarif`), then check
the upload step's `sarif_file` path. Validate JSON shape against
`examples/sarif.example.json`.

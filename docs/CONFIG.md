# Configuration (safe example)

Public users configure scans via flags and an optional JSON config.
Never commit real credentials - the example below is redacted.

`examples/orion.config.example.json`:

```json
{
  "target": ".",
  "report": ["html", "json", "sarif"],
  "incremental": true,
  "failOn": "high"
}
```

Precedence: CLI flags override config-file values. `orion --help`
lists every supported flag for the installed version.

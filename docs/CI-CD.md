# CI/CD usage (via npm, no source)

Install the published package in your pipeline - never clone a source
repo for scanning.

## GitHub Actions (minimal)

```yaml
- uses: actions/setup-node@v4
  with:
    node-version: 20
- run: npm install -g @orionscanner/cli
- run: orion . --security
- uses: actions/upload-artifact@v4
  with:
    name: orion-reports
    path: ORION SCANNER REPORTS/
- uses: github/codeql-action/upload-sarif@v3
  with:
    sarif_file: ORION SCANNER REPORTS/
```

Full annotated example with incremental PR scans:
`examples/github-action-example.yml`.

## Gating

The scan exits non-zero when critical/high findings are present, so the
job fails on severe findings by default. Use the JSON report in
`ORION SCANNER REPORTS/` for custom thresholds.

## Other CI systems

1. Install Node 20+.
2. `npm install -g @orionscanner/cli` (or `npx @orionscanner/cli .`).
3. Run `orion . --security` (add `--incremental` for changed files only).
4. Archive `ORION SCANNER REPORTS/` as build artifacts.

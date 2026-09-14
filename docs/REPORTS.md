# Reports

Every scan writes its reports to the `ORION SCANNER REPORTS/` folder in
the working directory. Same scan, four views - no extra tooling required.

| Format | Use it for |
|--------|-----------|
| **HTML** | Dark theme human review: sidebar navigation, expandable findings, score and grade |
| **JSON** | Pipelines, dashboards, custom quality gates (shape: `examples/json-report.example.json`) |
| **SARIF** | GitHub code scanning via `github/codeql-action/upload-sarif` (shape: `examples/sarif.example.json`) |
| **TXT** | Plain human-readable summary |

```bash
# Open the latest HTML report (Windows)
start "ORION SCANNER REPORTS\*.html"

# Open the latest HTML report (Linux/macOS)
xdg-open "ORION SCANNER REPORTS"/*.html
```

Example console tail (illustrative, redacted):

```text
Total Findings: 16 (illustrative)
Reports written to ORION SCANNER REPORTS/
```

CI pattern (artifact archive plus code scanning upload):
`examples/github-action-example.yml`.

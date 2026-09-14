# Security & privacy

- **Zero-cloud by default.** Scans run on your workstation or CI runner.
  Source never leaves your infrastructure for analysis.
- **Zero third-party runtime dependencies** for the scanning core.
- **Optional live CVE enrichment** (OSV feed) is opt-in, cached, and
  fails open - offline scans are unaffected.
- **Optional AI verification** (`ai_verify`) is disabled by default and
  requires your own key plus explicit outbound-network consent. Without
  both, the scan stays fully offline.
- **No secrets in this repo.** Example configs and SARIF samples are
  redacted. Never paste real keys into issues or discussions.

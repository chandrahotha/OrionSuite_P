<div align="center">

<img src="assets/logo.png" alt="Orion Engine Suite logo" width="300" />

# ORION ENGINE SUITE

### SEE. ANALYZE. IMPROVE.

[![npm version](https://img.shields.io/npm/v/@orionscanner/cli?logo=npm&logoColor=white&color=cb3837)](https://www.npmjs.com/package/@orionscanner/cli)
[![license](https://img.shields.io/badge/license-Proprietary-red)](./LICENSE)
[![node](https://img.shields.io/badge/node-%3E%3D16-339933?logo=node.js&logoColor=white)](./docs/INSTALL.md)
[![platforms](https://img.shields.io/badge/platforms-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey)](./docs/PLATFORMS.md)
[![engines](https://img.shields.io/badge/engines-77-success)](./docs/ENGINE_CATALOG.md)
[![reports](https://img.shields.io/badge/reports-SARIF%20%7C%20JSON%20%7C%20HTML-blue)](./docs/REPORTS.md)

[Quick Start](#-quick-start) -
[CLI](#-cli-in-30-seconds) -
[Features](#-what-you-get) -
[Engines](#-engine-categories) -
[Reports](#-reports) -
[CI/CD](#-cicd) -
[Docs](#-documentation-map)

> Proprietary software. This repo contains no source code: it is the product
> showcase and docs. The real product ships as compiled standalone binaries
> through the official npm package below. There is nothing to build from source here.

</div>

---

## Table of contents

1. [Quick Start](#-quick-start)
2. [CLI in 30 seconds](#-cli-in-30-seconds)
3. [What you get](#-what-you-get)
4. [Engine categories](#-engine-categories)
5. [Reports](#-reports)
6. [Configuration](#-configuration)
7. [CI/CD](#-cicd)
8. [Report preview](#-report-preview)
9. [Troubleshooting](#-troubleshooting)
10. [Security and privacy](#-security-and-privacy)
11. [Repository model](#-repository-model)
12. [Documentation map](#-documentation-map)
13. [Release and license](#-release-and-license)

---

## Quick Start

### Option A: global install (recommended)

```bash
npm install -g @orionscanner/cli
orion --version
orion --help
orion .
```

### Option B: one shot, no global install

```bash
npx @orionscanner/cli .
```

### Verify it worked

| Step | Command | Expected |
|------|---------|----------|
| 1 | `orion --version` | Prints a version such as `0.9.1` |
| 2 | `orion --help` | Prints the full flag reference |
| 3 | `orion .` | Scans the current directory and writes reports |

Requirements: **Node.js 16+ only**. No Python, no pip, no git clone of any
source repo, no private access, no third party runtime dependencies for the
core scan. See [docs/INSTALL.md](./docs/INSTALL.md) and
[docs/PLATFORMS.md](./docs/PLATFORMS.md).

---

## CLI in 30 seconds

```bash
# scan the current directory
orion .

# scan one folder
orion ./src

# focused suites (same flags as orion --help)
orion . --security
orion . --incremental --security
```

<details>
<summary><b>What each entry point does (click to expand)</b></summary>

* `orion --version`: prints the shipped product version. Source of truth for
  what you installed.
* `orion --help`: prints every flag supported by that exact binary.
* `orion .`: runs the full 77 engine suite against the target path.
* Aliases `orion-engine` and `orion-cli` run the same binary.

Full page: [docs/CLI.md](./docs/CLI.md)

</details>

---

## What you get

| Pillar | What it means for you |
|--------|-----------------------|
| **SEE** | Inventory your attack surface: polyglot file scan, dependency inventory with SBOM output, architecture overview with trust boundaries |
| **ANALYZE** | 77 specialized engines across app security, supply chain, AI/LLM, containers and IaC, privacy and compliance, quality and robustness |
| **IMPROVE** | Act on results: SARIF plus JSON plus HTML from one scan, incremental rescans, auto fix entry points, threat model summary |

<details>
<summary><b>Capability checklist (click to expand)</b></summary>

* App security: SAST, taint analysis, secrets, SSRF, XXE, deserialization,
  open redirect, header injection, template injection, LDAP and XPath injection
* Session and API: JWT misuse, CSRF gaps, CORS misconfiguration, IDOR,
  GraphQL and WebSocket risk areas
* Supply chain: vulnerable deps with opt in CVE enrichment, SBOM, typosquat
  detection, install script review, manifest and lockfile drift, committed
  binaries, secrets in git history
* AI and LLM: prompt injection patterns, agent tool boundary review, RAG
  retrieval into prompt review
* Containers and IaC: Dockerfile, Compose, Kubernetes, Helm, Terraform, CI
  workflow hardening
* Privacy and compliance: PII shapes mapped to GDPR, PCI DSS, SOC 2, HIPAA
* Quality and robustness: complexity, duplication, error handling,
  performance anti patterns, C/C++ memory safety patterns

Details: [docs/FEATURES.md](./docs/FEATURES.md)

</details>

---

## Engine categories

> Product level labels only. This catalog describes WHAT Orion reports.
> Detection internals, rules, thresholds and heuristics are proprietary and
> are not documented here.

<details open>
<summary><b>Core security (8)</b></summary>

`sast` `taint` `reachability` `authorization` `sandbox_escape`
`secrets` `crypto_guard` `api_security`

Injection families, tainted input reaching dangerous sinks, missing
authorization on routes, sandbox escape patterns, hardcoded secrets, weak
cryptography, REST and API design risks, reachable path evidence.

</details>

<details>
<summary><b>Injection and exploit guards (11)</b></summary>

`ssrf_guard` `xxe_guard` `deserialization_guard` `open_redirect_guard`
`header_injection_guard` `ssti_guard` `log_injection_guard`
`ldap_xpath_injection` `mass_assignment_guard` `prototype_pollution`
`csrf_guard`

</details>

<details>
<summary><b>Session, API and protocol (6)</b></summary>

`jwt_guard` `session_cookie_flags` `cors_misconfig_guard` `idor_guard`
`graphql_guard` `websocket_guard`

</details>

<details>
<summary><b>Understanding, quality and robustness</b></summary>

* Understanding: `callgraph` `cfg` `symbol` `dataflow` `orphan`
  `dead_import` `wiring_trace` `state`
* Quality: `complexity` `duplication` `error_handling` `logging_c`
  `license` `lint` `test_coverage`
* Robustness: `redos_scanner` `toctou_guard` `zip_slip_guard`
  `perf_guard` `regression` `chaos` `chaos_config`

</details>

<details>
<summary><b>Config, infra, supply chain, privacy, AI (28+)</b></summary>

* Config and infra: `config_engine` `config_validation` `container`
  `iac_security` `k8s_rbac_analyzer` `contract_probe`
* Supply chain: `deps` `supply_chain_sbom` `provenance`
  `typosquat_guard` `manifest_script_audit` `lockfile_drift`
  `git_history_secrets` `binary_blob_detector` `entropy_secrets_v2`
  `api_contract_drift`
* Privacy: `pii_scan` `sensitive_data`
* Memory and leaks: `memory_safety_c` `hardcoded_infra_leak`
* Meta: `fp_suppression` `compliance` `architecture` `threat_model`
* AI and LLM: `prompt_security` `llm_security` `rag_security`, plus
  optional `ai_verify` (bring your own key, off by default, fully offline
  when not configured)

</details>

Full list: [docs/ENGINE_CATALOG.md](./docs/ENGINE_CATALOG.md)

---

## Reports

| Format | Use it for |
|--------|-----------|
| **SARIF** | GitHub code scanning and other SARIF viewers (`github/codeql-action/upload-sarif`) |
| **JSON** | Pipelines, dashboards, custom quality gates |
| **HTML** | Human readable single file review with `assets/logo_report.png` branding |
| **TXT** | Plain summary for quick reads and CI logs |

```text
ORION ENGINE SUITE: scan summary (illustrative, redacted)
Target: ./src
Engines: 77 active
Total Findings: 16 (illustrative)
Reports written to ORION SCANNER REPORTS/
```

Sample shape: [examples/sarif.example.json](./examples/sarif.example.json).
Guide: [docs/REPORTS.md](./docs/REPORTS.md).

---

## Configuration

Safe, redacted example (never commit real credentials):

```json
{
  "target": ".",
  "report": ["html", "json", "sarif"],
  "incremental": true,
  "failOn": "high"
}
```

Copy: [examples/orion.config.example.json](./examples/orion.config.example.json).
Guide: [docs/CONFIG.md](./docs/CONFIG.md). CLI flags override config values;
`orion --help` is authoritative for your installed version.

---

## CICD

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

Annotated copy: [examples/github-action-example.yml](./examples/github-action-example.yml).
Guides: [docs/CI-CD.md](./docs/CI-CD.md) and
[docs/GITHUB_ACTION.md](./docs/GITHUB_ACTION.md).

---

## Troubleshooting

| Symptom | Fix |
|---------|-----|
| `orion: command not found` | Reinstall globally, check npm globals on PATH |
| `Orion executable not found` | Reinstall from npm; never use a source checkout (none is published) |
| Stale version | `npm view @orionscanner/cli dist-tags`, then `npm install -g @orionscanner/cli@latest` |
| Empty SARIF upload | Confirm `--output` path, validate against the example JSON |

Full page: [docs/TROUBLESHOOTING.md](./docs/TROUBLESHOOTING.md)

---

## Security and privacy

* **Zero cloud by default.** Scans run on your machine or runner.
* **Zero third party runtime dependencies** for the scanning core.
* **Opt in CVE enrichment** is cached and fails open; offline scans unaffected.
* **Optional AI verification** is off by default and needs your own key plus
  explicit outbound consent. Without both, the scan stays fully offline.
* **No secrets in this repo.** Samples are redacted.

Full page: [docs/SECURITY-PRIVACY.md](./docs/SECURITY-PRIVACY.md)

---

## Repository model

```text
PRIVATE source (not here)
  -> build pipeline -> compiled standalone binaries
  -> npm @orionscanner/cli -> orion .

PUBLIC showcase (this repo)
  -> README, docs, examples, SARIF samples
```

* npm is the official executable distribution.
* GitHub is the official product showcase (this repo).
* Public architecture view: [docs/ARCHITECTURE.md](./docs/ARCHITECTURE.md)

---

## Documentation map

* Install and verify: [docs/INSTALL.md](./docs/INSTALL.md)
* CLI: [docs/CLI.md](./docs/CLI.md)
* Platforms: [docs/PLATFORMS.md](./docs/PLATFORMS.md)
* Features: [docs/FEATURES.md](./docs/FEATURES.md)
* Engine catalog: [docs/ENGINE_CATALOG.md](./docs/ENGINE_CATALOG.md)
* Reports: [docs/REPORTS.md](./docs/REPORTS.md)
* Config: [docs/CONFIG.md](./docs/CONFIG.md)
* CI/CD: [docs/CI-CD.md](./docs/CI-CD.md), [docs/GITHUB_ACTION.md](./docs/GITHUB_ACTION.md)
* Troubleshooting: [docs/TROUBLESHOOTING.md](./docs/TROUBLESHOOTING.md)
* Security: [docs/SECURITY-PRIVACY.md](./docs/SECURITY-PRIVACY.md)
* Architecture: [docs/ARCHITECTURE.md](./docs/ARCHITECTURE.md)
* Examples: [`examples/`](./examples) (suites, interactive map, SARIF and JSON shapes, CI workflow, [detection demos](./examples/detections/))
* Release notes: [CHANGELOG.md](./CHANGELOG.md)

---

## Release and license

Current release: **0.9.1** via `@orionscanner/cli` (`latest` dist tag).
The package name stays canonical; versions are never reset for this showcase.

**Proprietary.** See [LICENSE](./LICENSE). All rights reserved. No source
license is granted by this repository. The only licensed artifact users
receive is the compiled binary distributed through `@orionscanner/cli`.

# Scan suites (copy-paste commands)

Every command below comes straight from `orion --help`. Pick one suite
per run, or run a bare `orion <path>` for the full sweep.

```bash
# Full sweep: all engines against the current directory
orion .

# Security, SAST and vulnerability engines
orion . --security

# Infrastructure-as-Code and cloud engines
orion . --iac

# LLM and AI agent security engines
orion . --ai

# Cryptographic flaw and key auditor
orion . --crypto

# Code quality and standards engines
orion . --quality

# Architecture and dataflow engines
orion . --arch

# Threat modeling and privacy engines
orion . --threat

# SBOM, dependencies, provenance, typosquatting
orion . --supply-chain
```

## Fast local loops

```bash
# Changed files only (git diff since HEAD)
orion . --incremental --security

# --diff is an alias for --incremental
orion . --diff --baseline main
```

## Auto fix (CI mode)

```bash
# Preview first, then apply without prompts in CI
orion fix . --apply --yes
```

Reports from every run land in `ORION SCANNER REPORTS/` (HTML, JSON,
SARIF, TXT). The scan exits non-zero when critical/high findings are
present, so CI jobs fail on severe findings by default.

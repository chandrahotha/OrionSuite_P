# CLI reference (public surface)

All commands run against the compiled binary installed via npm.
Flag list below matches `orion --help` - that output is authoritative
for the installed version.

```bash
orion                 # Launch interactive terminal UI
orion <path>          # Scan a file or directory (orion . for here)
orion fix <path>      # Automatically fix security and quality flaws
orion --version       # Show version
orion --help          # Show help
```

## Scan suites (one flag per run, or no flag for everything)

```bash
orion . --security      # Security, SAST and vulnerability engines
orion . --iac           # Infrastructure-as-Code and cloud engines
orion . --ai            # LLM and AI agent security engines
orion . --crypto        # Cryptographic flaw and key auditor
orion . --quality       # Code quality and standard engines
orion . --arch          # Architecture and dataflow engines
orion . --threat        # Threat modeling and privacy engines
orion . --supply-chain  # SBOM, deps, provenance, typosquatting
```

## Incremental and baseline

```bash
orion . --incremental --security  # Changed files only (diff since HEAD)
orion . --diff --baseline main    # Diff scan against main branch
```

## Auto fix

```bash
orion fix . --apply --yes         # Apply fixes without prompts (CI mode)
```

## Advanced config

```bash
orion . --config-json '{"toggles":{"deps":{"osv_lookup":true}}}'
```

Copy-paste set: `examples/scan-suites.md`. Interactive UI map:
`examples/interactive-mode.md`.

Do not rely on any Python-module invocation (`python -m ...`,
`pip install -e .`): those are private development paths and do not
exist for npm users.

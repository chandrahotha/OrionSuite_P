# Engine catalog (product level - WHAT, not HOW)

Orion ships **77 specialized engines**. Names below are the public
capability labels. Detection methods, rules, thresholds, and internal
wiring are proprietary and intentionally omitted.

## Core security

`sast`, `taint`, `reachability`, `authorization`, `sandbox_escape`,
`secrets`, `crypto_guard`, `api_security`

Covers: injection families, tainted input reaching dangerous sinks,
missing authorization on routes, sandbox-escape patterns, hardcoded
secrets, weak cryptography, REST/API design risks, reachable-path
evidence for findings.

## Injection & exploit guards

`ssrf_guard`, `xxe_guard`, `deserialization_guard`,
`open_redirect_guard`, `header_injection_guard`, `ssti_guard`,
`log_injection_guard`, `ldap_xpath_injection`, `mass_assignment_guard`,
`prototype_pollution`, `csrf_guard`

## Session, API & protocol

`jwt_guard`, `session_cookie_flags`, `cors_misconfig_guard`,
`idor_guard`, `graphql_guard`, `websocket_guard`

## Disclosure & hygiene

`error_disclosure_guard`, `obfuscation_detector`

## Code understanding

`callgraph`, `cfg`, `symbol`, `dataflow`, `orphan`, `dead_import`,
`wiring_trace`, `state`

## Quality

`complexity`, `duplication`, `error_handling`, `logging_c`, `license`,
`lint`, `test_coverage`

## Robustness & performance

`redos_scanner`, `toctou_guard`, `zip_slip_guard`, `perf_guard`,
`regression`, `chaos`, `chaos_config`

## Config & infrastructure

`config_engine`, `config_validation`, `container`, `iac_security`,
`k8s_rbac_analyzer`, `contract_probe`

## Supply chain

`deps`, `supply_chain_sbom`, `provenance`, `typosquat_guard`,
`manifest_script_audit`, `lockfile_drift`, `git_history_secrets`,
`binary_blob_detector`, `entropy_secrets_v2`, `api_contract_drift`

## Data & privacy

`pii_scan`, `sensitive_data`

## Memory & infrastructure leaks

`memory_safety_c`, `hardcoded_infra_leak`

## Meta

`fp_suppression`, `compliance`, `architecture`, `threat_model`

## AI & LLM security

`prompt_security`, `llm_security`, `rag_security`, plus optional
`ai_verify` (bring-your-own-key, disabled by default, fully offline
when not configured).

Language coverage spans Python, JS/TS, Java, Go, Rust, PHP, Ruby,
C/C++, C#, HTML/CSS, config formats, and Dockerfiles - per-engine
applicability varies; the scanner routes files automatically.

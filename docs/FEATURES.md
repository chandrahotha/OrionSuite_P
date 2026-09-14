# Features (product level)

## SEE - inventory your attack surface

- Polyglot project scan: Python, JavaScript/TypeScript, Java, Go, Rust,
  PHP, Ruby, C/C++, C#, HTML/CSS, YAML/JSON/TOML, Dockerfiles.
- Dependency inventory with SBOM output (CycloneDX shape).
- Architecture overview: modules, call relationships, trust boundaries.

## ANALYZE - 77 specialized engines

- SAST: SQLi, XSS, command injection, SSRF, path traversal, XXE,
  deserialization, open redirect, header injection, template injection,
  LDAP/XPath injection.
- Taint analysis: user input to dangerous sinks, same-file and
  cross-file project scope.
- Secrets: API keys, tokens, passwords, private keys, entropy-assisted.
- Session/API: JWT misuse, CSRF gaps, CORS misconfiguration, IDOR,
  GraphQL and WebSocket risk areas.
- Supply chain: vulnerable deps (opt-in live CVE enrichment), typosquat
  detection, install-script review, manifest/lockfile drift, committed
  binaries, secrets in git history.
- AI/LLM: prompt-injection patterns, agent tool-boundary review, RAG
  retrieval-into-prompt review.
- Container/IaC: Dockerfile, Compose, Kubernetes, Helm, Terraform, CI
  workflow hardening.
- Privacy/compliance: PII shapes, GDPR / PCI-DSS / SOC 2 / HIPAA mapping.
- Quality & robustness: complexity, duplication, error handling,
  performance anti-patterns, memory-safety patterns in C/C++.

## IMPROVE - act on results

- SARIF, JSON, and HTML reports for humans and tooling.
- Incremental scanning for fast local loops.
- Auto-fix entry points for safe, reviewable changes.
- STRIDE-style threat-model summary.

All items above describe WHAT Orion reports. Detection internals,
heuristics, and rule implementations are proprietary and not documented
here.

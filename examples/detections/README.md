# Detection demos (illustrative)

Three textbook cases showing what an Orion finding looks like end to
end: vulnerable sample, redacted finding, fixed sample. Samples are
written fresh for this showcase in OWASP textbook style. They are not
taken from any test suite, and findings below are redacted
illustrations, not real scan dumps.

| Demo | Engines shown | File |
|------|---------------|------|
| Hardcoded secret | `secrets` | [01-hardcoded-secret.md](./01-hardcoded-secret.md) |
| SQL injection via tainted input | `taint`, `sast` | [02-tainted-sql.md](./02-tainted-sql.md) |
| JWT signature check disabled | `jwt_guard` | [03-jwt-unverified.md](./03-jwt-unverified.md) |

Rules of this gallery:

* RESULTS only. No rule logic, no thresholds, no detection internals.
* No bypass discussion. Nothing here describes what any engine misses.
* Fix samples show the safe pattern, not engine behavior.

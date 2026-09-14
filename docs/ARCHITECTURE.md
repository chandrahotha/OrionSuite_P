# Architecture (public view - no internals)

```text
                    ORION ENGINE SUITE
                  SEE. ANALYZE. IMPROVE.
                             |
   +---------------------------------------------------+
   | PRIVATE (not in this repo)                        |
   |   proprietary source --> build pipeline           |
   |     --> compiled standalone binaries              |
   +-------------------------+-------------------------+
                             |
   +---------------------------------------------------+
   | DISTRIBUTION (npm)                                |
   |   @orionscanner/cli                               |
   |   npm install -g @orionscanner/cli --> orion .    |
   +-------------------------+-------------------------+
                             |
   +---------------------------------------------------+
   | PUBLIC SHOWCASE (this repo)                       |
   |   README / docs / examples / SARIF samples        |
   |   CI pointers (consume npm binary, never source)  |
   +---------------------------------------------------+
```

Design notes (non-proprietary):

- One scan fans out to many specialized capability areas; a
  correlation step keeps the strongest finding per location and records
  corroboration.
- Reports (SARIF/JSON/HTML) are different views of one result set.
- Incremental mode reuses prior results for fast local loops.

Internal module boundaries, parsers, taint internals, rule logic, and
heuristics are proprietary and are not diagrammed here.

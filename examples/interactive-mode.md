# Interactive mode (terminal UI)

Run `orion` with no arguments to open the interactive terminal UI.
Map below matches `orion --help` on the installed version.

```text
[1]      Scan Wizard (guided: target, scan type, incremental mode)
[2-11]   One-keystroke scans (quick, full, plus specialized sweeps)
[R]      Report viewer (pick and open any generated report)
[F]      Finding Explorer (interactive browse and filter)
[S]      Engine Health Matrix (every engine, availability status)
[E]      Engine Catalog (browse engines with per-engine details)
[A]      AI Verification Setup (bring your own key, off by default)
[D]      Documentation Index (guides and references)
[X]      Auto-Fix Wizard (guided remediation with preview)
[0]      Exit
```

Wizard navigation, in every interactive flow:

```text
[B]      Back to the previous step
[C]      Cancel the current flow
```

Tip: start with `[1]` Scan Wizard. It asks for target, scan type, and
incremental mode, then runs the same engines as the CLI flags in
`scan-suites.md`. Nothing here needs Python or a source checkout: the UI
drives the installed compiled binary.

# Platforms

Orion ships as compiled standalone binaries via `@orionscanner/cli`.

- Windows: supported via the shipped executable.
- macOS / Linux: supported through the npm-published platform binaries;
  run `orion --version` after install to confirm the binary resolved on
  your machine.

The npm wrapper selects the correct binary automatically. If no binary
resolves, reinstall from npm - public users should never fall back to a
source tree (none is published).

CI runners: use Node 20+ with `npm install -g @orionscanner/cli`.
No Python toolchain is required for scanning.

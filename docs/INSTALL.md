# Install

Official distribution only. There is no source build for public users.

## Global install (recommended)

```bash
npm install -g @orionscanner/cli
```

Requires Node.js >= 16. No Python, no pip, no git clone.

## Verify

```bash
orion --version
orion --help
orion .
```

## One-shot without global install

```bash
npx @orionscanner/cli .
```

## Notes

- Package: `@orionscanner/cli`, `latest` = 0.9.1.
- Binaries provided: `orion`, `orion-engine`, `orion-cli` (all aliases).
- If `orion .` reports a missing executable, reinstall from npm - do not
  attempt a source checkout (no public source exists).

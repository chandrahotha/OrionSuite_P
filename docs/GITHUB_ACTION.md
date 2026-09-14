# GitHub Action usage

You have two supported patterns. Both consume the npm binary - neither
needs the engine source.

## Option A - npm step (recommended)

Use the workflow in `examples/github-action-example.yml`: setup Node,
`npm install -g @orionscanner/cli`, run `orion .`, upload SARIF.

## Option B - composite wrapper

If you publish a thin `orion-scan` composite action in this showcase
repo later, it must wrap the npm package (`npm i -g @orionscanner/cli`
then `orion`), never a source checkout or Python toolchain.

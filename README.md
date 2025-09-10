# setup-hctl

A GitHub action for installing the Humanitec hctl binary within a workflow.

## Usage

```
name: ci

on:
  push:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v5
      - uses: humanitec/setup-hctl@v1
        with:
          # Can have the format "1", "1.36", "1.36.7", or a semver range https://github.com/npm/node-semver#ranges
          # Check https://github.com/humanitec/hctl/releases for available versions
          version: "1"
          # The token is required if a range is specified
          token: ${{ secrets.GITHUB_TOKEN }}
      - run: hctl --version
```

* Checkout the [Documentation](https://developer.humanitec.com/platform-orchestrator/docs/integrations/cli/) for more installation and usage examples of the CLI.

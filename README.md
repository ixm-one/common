# Overview

This repository currently houses *both* commonly used github action workflows
usable via `workflow_call` and a common [Mend
Renovate](https://docs.renovatebot.com) configuration for use across all of the
IXM project's various repositories.

# Usage (Actions)

Per documentation found [here][1], calling workflows from elsewhere looks like
the following:

```yaml
jobs:
  actionlint:
    uses: ixm-one/common/.github/workflows/actions.lint.yml@main
  spellcheck:
    name: Lint Spelling
    uses: ixm-one/common/.github/workflows/spellcheck.yml@main
```

Several jobs for this repository use the same workflows in this repository for
some basic operations.

# Usage (Renovate)

Extending from any of the configurations placed within this repository is very
simple. To use all of them, simply add `"ixm-one/common"` to the `"extends"`
field in your renovate configuration file. Alternatively, if only specific
configurations are desired, users are free to explicitly list a specific
configuration by using `"ixm-one/common:<config>"`. For example, the following
are both valid ways to pull in the GitHub Actions related configuration
settings:

```json
{ "extends": ["ixm-one/common"] }
```

```json
{ "extends": ["ixm-one/common:actions"] }
```



[1]: https://docs.github.com/en/actions/using-workflows/reusing-workflows#calling-a-reusable-workflow

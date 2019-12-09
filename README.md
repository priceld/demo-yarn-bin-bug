# demo-yarn-bin-bug
A simple monorepo to demo a [bug](https://github.com/yarnpkg/yarn/issues/7748) with 'yarn bin'

> Note: This repo uses a yarn policy to ensure version `1.19.2` of yarn is used.

# Reproduce the bug

1. Run `yarn` to install
2. CD into the `packages/my-package` folder
3. Run `yarn bin semver`

Observe that the output is a path to the `semver` that is hoisted in the root of the repo, but it should be
the `semver` installed by `my-package`.

To see another aspect of this bug you can also run `yarn run semver -h` (again from the `packages/my-package`
folder) and observe that the wrong help is printed.

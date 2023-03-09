# cargo-release-action

Contains a set of actions and utilities based on the `cargo release` action from the example in their repository.

[https://github.com/crate-ci/cargo-release]

## Steps

- Create your GitHub Action, the `post-release.yaml` file in this repository can be used as a good basis for your own workflow. If using the example directly be sure to update the `bin_name` input if you are releasing a binary package or remove build section otherwise.
- Add `CHANGELOG.md` based on the following template, must always have an unreleased section and the comments below for it to be automatically updated.
- In `CHANGELOG.md` and `release.toml` update the GitHub URL to be the correct one for the repository, if releasing a binary package.

```md
# Changelog

<!-- next-header -->

## [Unreleased] - ReleaseDate

<!-- next-url -->

[unreleased]: https://github.com/org/repo/compare/v0.0.0...HEAD
```

## When releasing

- Run `cargo release --execute`
- Can do `cargo release --execute 1.0.0` or `cargo release major/minor/patch/release/rc/beta/alpha`
- The command will automatically push to remote then the action will run and create the actual action.

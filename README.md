# cargo-release-action

Contains the two files required for a `cargo release` action from the example in the repository with some small changes for my own needs.

[https://github.com/crate-ci/cargo-release]

## Steps

- Add `post-release.yaml` and `release-notes.py` to `.github/workflows` and `release.toml` to the root directory
- Run `git update-index --chmod=+x ./.github/workflows/release-notes.py` to give `release-notes.py` the required execute permissions
- Add `CHANGELOG.md` based on the following template, must always have an unreleased section and the comments below for it to be automatically updated
- In `CHANGELOG.md` and `release.toml` update the GitHub URL to be the correct one for the repository

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

# `cairo` Fork with CLI Package

This is a [`cairo`](https://github.com/starkware-libs/cairo) fork with the addition of a `cairo-cli` package for easier binary installation:

```console
$ cargo install --locked --path cli
```

Now you have all the following commands installed:

- `cairo-compile`
- `cairo-lsp`
- `cairo-run`
- `cairo-fmt`
- `sierra-compile`
- `starknet-compile`
- `starknet-sierra-compile`

This fork exists to demonstrate the refactoring suggested in [this issue](https://github.com/starkware-libs/cairo/issues/1083).

Powered by a [GitHub Actions workflow](https://github.com/xJonathanLEI/cairo/actions/workflows/sync.yml), this fork syncs the `main` branch with the upstream continuously:

- First, a commit is made on top of the upstream `main` branch to bring files from the [`home`](https://github.com/xJonathanLEI/cairo/tree/home) branch to `main`. This is necessary for making changes to CI workflows and the README file you're reading right now.

- Then, actual patch commits living on the fork `patch/cli` branch gets rebased. Before pushing, the branch is compiled to make sure it still builds.

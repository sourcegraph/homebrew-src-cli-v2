# Homebrew tap for the Sourcegraph CLI

This tap provides the `src-cli` formula, which installs `src`, the
[Sourcegraph CLI](https://github.com/sourcegraph/sourcegraph/tree/main/cmd/src),
on macOS and Linux (arm64 and x86_64).

## Install

```sh
brew install sourcegraph/src-cli-v2/src-cli
```

To upgrade:

```sh
brew upgrade src-cli
```

## Switching from the old tap

The old `sourcegraph/src-cli` tap installs a `src` binary too, so remove it
first:

```sh
brew uninstall sourcegraph/src-cli/src-cli
brew untap sourcegraph/src-cli
brew install sourcegraph/src-cli-v2/src-cli
```

See the [migration guide](https://sourcegraph.com/docs/cli/migration) for what
changed in the CLI itself.

## How this tap is updated

Do not edit `Formula/src-cli.rb` by hand. Every stable Sourcegraph release
(`vX.Y.Z`) publishes the CLI to
[sourcegraph/src-cli-v2](https://github.com/sourcegraph/src-cli-v2/releases),
and `cmd/src/dist/release.sh publish-homebrew` in the Sourcegraph monorepo then
writes the formula, with its version and checksums read from that release.
Prereleases are not published here.

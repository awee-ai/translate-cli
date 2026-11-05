# translate-cli

Releases of `translate`, the command line tool that syncs an iOS or Android repository's translation files with an Awee translations project. This repo holds the release binaries. The Homebrew cask lives in [toaweme/homebrew-tap](https://github.com/toaweme/homebrew-tap) and the Scoop manifest in [toaweme/scoop-bucket](https://github.com/toaweme/scoop-bucket).

## Install

macOS, with Homebrew.

```sh
brew install toaweme/tap/translate
```

Windows, with Scoop.

```sh
scoop bucket add toaweme https://github.com/toaweme/scoop-bucket
scoop install toaweme/translate
```

Linux, or any platform without a package manager, takes the archive for its OS and architecture from the [latest release](https://github.com/awee-ai/translate-cli/releases/latest).

```sh
VERSION=0.1.0
wget -qO- https://github.com/awee-ai/translate-cli/releases/download/v$VERSION/translate_${VERSION}_linux_x64.tar.gz | tar xz
sudo mv translate /usr/local/bin/
```

Every release carries `checksums.txt`, signed with cosign.

## Use

```sh
translate init                   # or: translate init --from crowdin.yml
export AWEE_TRANSLATE_TOKEN=...  # the app's API key
translate push sources
translate push translations
translate pull translations
```

Run `translate --help` for every command and flag.

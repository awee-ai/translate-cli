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
export AWEE_TRANSLATE_TOKEN=...  # your personal key, or an organization key
translate push sources
translate push translations
translate pull translations
```

The token is an API key from the app's API keys page. A personal key acts as you, so it reaches the projects you picked when you made it and does what your role on each of them allows. A read-only personal key pulls and never pushes. An organization key, made by an admin, holds a role of its own such as `publisher` and keeps working when people leave, which suits CI.

Run `translate --help` for every command and flag.

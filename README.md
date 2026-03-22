# homebrew-gsdw

Homebrew tap for [gsd-wired](https://github.com/The-Artificer-of-Ciphers-LLC/gsd-wired) — GSD workflow orchestration for Claude Code backed by a beads graph engine.

## Install

```sh
brew tap The-Artificer-of-Ciphers-LLC/gsdw
brew install gsdw-cc
```

## Verify Installation

```sh
gsdw version
gsdw doctor
```

## Supported Platforms

| Platform | Architecture | Status |
|----------|-------------|--------|
| macOS | arm64 (Apple Silicon) | ✅ Signed + Notarized |
| macOS | amd64 (Intel) | ✅ Signed + Notarized |

Linux users: install via `go install` or download binaries from [GitHub Releases](https://github.com/The-Artificer-of-Ciphers-LLC/gsd-wired/releases).

## Alternative Install Methods

### go install

```sh
go install github.com/The-Artificer-of-Ciphers-LLC/gsd-wired/cmd/gsdw@latest
```

### Container

```sh
docker pull ghcr.io/the-artificer-of-ciphers-llc/gsdw:latest
```

## Troubleshooting

### Gatekeeper: "unidentified developer"

The cask runs `xattr -dr com.apple.quarantine` automatically during installation. If you installed manually or the quarantine flag persists:

```sh
xattr -dr com.apple.quarantine $(which gsdw)
```

### Binary not found after install

Ensure `/opt/homebrew/bin` (Apple Silicon) or `/usr/local/bin` (Intel) is in your PATH:

```sh
echo $PATH | tr ":" "
" | grep -E "homebrew |local"
```

### Dependencies

gsd-wired requires `bd` (beads) and `dolt`. Run `gsdw check-deps` after installation to verify all dependencies are present.

## Links

- [gsd-wired](https://github.com/The-Artificer-of-Ciphers-LLC/gsd-wired) — Source code
- [Releases](https://github.com/The-Artificer-of-Ciphers-LLC/gsd-wired/releases) — Binary downloads
- [Beads](https://github.com/steveyegge/beads) — Graph persistence layer
- [Dolt](https://github.com/dolthub/dolt) — Git-for-data database

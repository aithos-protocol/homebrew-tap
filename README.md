# aithos Homebrew tap

```sh
brew tap aithos-protocol/tap
brew install aithos
```

`aithos` publishes and verifies signed A2A Agent Cards. Source, specification
and audit history: <https://github.com/aithos-protocol/registry>.

## Before you trust the binary

Homebrew is the convenient way in, not the checkable one. This tap points at
release tarballs and pins their checksums, which protects you from a tarball
being swapped after the fact — it does not tell you where the tarball came
from. That does:

```sh
gh release download --repo aithos-protocol/registry v0.1.0-alpha.1
gh attestation verify aithos-*.tar.gz --repo aithos-protocol/registry
```

It proves the artifact was built by that repository's release workflow, from a
named commit. For a tool that will hold your signing keys, it is worth the
extra thirty seconds.

## Formulae here are generated

`Formula/aithos.rb` is produced by `scripts/brew-formula.sh` in the main
repository, from a published release. A formula is four URLs and four checksums
that must move together on every tag, and editing that by hand is how a tap ends
up serving one architecture from the previous release. Do not edit it here.

# LevitateOS releases

Signed releases of LevitateOS and AcornOS.

- Each release is a GitHub release of this repository named `<os>-<serial>`
  (for example `levitateos-1`). It holds the install ISO, the archives an
  installed system updates from (`base.tar.zst`, `boot.tar.zst`,
  `recipes.tar.zst`), and the signed manifest `release.json` with
  `release.json.sig`.
- `channels/<os>/stable.json` and `stable.json.sig` are a copy of the newest
  release's manifest. An installed system reads only this file to learn
  whether a newer release exists.

The manifest is signed with Ed25519. An installed system accepts a release
only when one of the public keys in its `/usr/share/levitate/release-keys/`
verifies the signature. Everything else is checked against the SHA-256 values
inside the signed manifest.

Nothing is written here by hand. `cargo xtask release publish <distro>` in
[LevitateOS/LevitateOS](https://github.com/LevitateOS/LevitateOS) uploads a
release and moves the channel file last. The design is in that repository's
`docs/release-engineering.md`.

No release has been published yet.

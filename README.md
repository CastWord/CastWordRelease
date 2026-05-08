# CastWord — Releases

Distribution channel for CastWord macOS release binaries and the Sparkle auto-update appcast.

The download link at [castword.ai](https://castword.ai) points at `CastWord.dmg` on the latest GitHub release, so it stays static across versions.

## Latest

| Version | Download | SHA-256 | Size | macOS |
|---------|----------|---------|------|-------|
| **0.0.24** | [CastWord.dmg](https://github.com/CastWord/CastWordRelease/releases/latest/download/CastWord.dmg) | `ca0a3eff88dfae1e3d6a1ea28e560a8d261fa51afe363d45599596b6d858b56d` | 15.0 MB | 13.0+ (Apple Silicon) |

Older versions remain available on the [Releases page](https://github.com/CastWord/CastWordRelease/releases).

## Install

1. Download the `.dmg` from the table above.
2. Double-click the DMG to mount it.
3. **Drag `CastWord` into the `Applications` folder** shown in the installer window.
4. Eject the volume, then launch CastWord from `/Applications` (or Spotlight).

The app is signed with an Apple Developer ID and notarized by Apple — it opens cleanly on first launch with no Gatekeeper warning.

### Required permissions

Grant these in **System Settings → Privacy & Security**:

| Permission | What it's for | When |
|------------|---------------|------|
| **Input Monitoring** | Global hotkeys (dictation, action mode) | Required on first run |
| **Accessibility** | Pasting transcribed text, native UI automation | Required on first run |
| **Microphone** | All voice capture | macOS prompts automatically |
| **Screen & System Audio Recording** | Only the *"take a screenshot"* voice command | Optional — every other feature works without it |

## Verify

```bash
shasum -a 256 CastWord.dmg
```

Should match the SHA-256 in the table above.

You can also verify the notarization status directly:

```bash
spctl -a -vv -t open --context context:primary-signature CastWord.dmg
# expected: source=Notarized Developer ID
```

## Auto-update

CastWord checks for updates via [Sparkle](https://sparkle-project.org/) using [`appcast.xml`](./appcast.xml) in this repo. New versions are picked up automatically; you can also trigger a check from **Settings → Check for Updates…**.

## Releasing a new version

Releases are produced automatically by `release.sh` in the [main CastWord repo](https://github.com/CastWord/CastWord). The script bumps semver, signs + notarizes the app and DMG, uploads `CastWord-X.Y.Z.dmg` and a static `CastWord.dmg` to a new GitHub release here, and signs + publishes the matching `appcast.xml` entry in one shot.

## Issues

Report bugs at [castword.ai](https://castword.ai) or open an issue on this repo.

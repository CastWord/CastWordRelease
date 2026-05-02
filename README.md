# CastWord — Releases

Distribution channel for CastWord macOS release binaries.

## Latest

| Version | Download | SHA-256 | Size | macOS |
|---------|----------|---------|------|-------|
| **0.0.1** | [CastWord-0.0.1.dmg](./CastWord-0.0.1.dmg) | `cbaf9c7e4d0742a68adc5f5fbbab677d84c25a30fd6f1f1a74d2b8a45a25f57a` | 886 KB | 13.0+ (Apple Silicon) |

## Install

1. Download the `.dmg` from the table above.
2. Double-click the DMG to mount it.
3. **Drag `CastWord` into the `Applications` folder** shown in the installer window.
4. Eject the volume, then launch CastWord from `/Applications` (or Spotlight).

### First-launch dialogs

Because the build is ad-hoc signed (no Apple Developer ID), Gatekeeper will warn the first time:

- macOS shows *"CastWord can't be opened because it is from an unidentified developer."*
- Right-click `CastWord.app` in `/Applications` → **Open** → confirm.

After that it launches normally on every subsequent run.

### Required permissions

Grant these in **System Settings → Privacy & Security**:

| Permission | What it's for | When |
|------------|---------------|------|
| **Input Monitoring** | Global hotkeys (dictation, action mode) | Required on first run |
| **Accessibility** | Pasting transcribed text, native UI automation | Required on first run; resets after every rebuild |
| **Microphone** | All voice capture | macOS prompts automatically |
| **Screen & System Audio Recording** | Only the *"take a screenshot"* voice command | Optional — every other feature works without it |

## Verify

```bash
shasum -a 256 CastWord-0.0.1.dmg
```

Should match the SHA-256 in the table above.

## Older releases

None yet. Older versions will remain available as GitHub releases.

## Issues

Report bugs at [castword.ai](https://castword.ai) or open an issue on this repo.

# PRevue releases

Builds of the PRevue desktop app for macOS (Apple Silicon). This repository holds only the installer and the releases; the source lives elsewhere.

## Install

```bash
curl -fsSL https://raw.githubusercontent.com/hayksaryan/prevue-releases/main/install.sh | sh
```

The script downloads the latest release's DMG, copies `PRevue.app` into `/Applications` (or `~/Applications` if you can't write there) and opens it. Run the same command to update.

Options, as environment variables before `sh`:

- `PREVUE_VERSION=v0.1.0`: install that release instead of the latest.
- `PREVUE_INSTALL_DIR=~/Applications`: install somewhere else.
- `PREVUE_NO_OPEN=1`: don't open the app afterwards.

The app isn't signed with an Apple Developer ID yet. Installed this way it opens normally. If you download the DMG from the Releases page in a browser instead, run this once before opening it:

```bash
xattr -dr com.apple.quarantine /Applications/PRevue.app
```

## After installing

PRevue signs in with your GitHub CLI login: `brew install gh`, then `gh auth login` and `gh auth refresh -s notifications`. The guide that opens on first launch checks the rest.

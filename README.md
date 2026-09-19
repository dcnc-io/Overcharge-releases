# Overcharge AGENT · Windows beta

Download from [overcharge.io/download](https://overcharge.io/download/), or choose a version under [Releases](https://github.com/dcnc-io/Overcharge-releases/releases).

This repository contains release metadata, documentation and downloadable binaries. Product source repositories remain private.

## Current beta

**0.1.0-connector.9 · Windows x64 · Unsigned**

- Installer: installs for the current Windows user and creates a Start menu shortcut.
- Portable: runs without installation.
- The Agent handles local Dota preparation and GSI connection. Heroes, Builds and Matches open Overcharge.io in the default browser.
- Updates are manual through the download page.

**Execution testing is incomplete.** Windows App Control blocked the unsigned executable on our validation machine. Source tests, package construction and Authenticode/hash inspection passed; this build's Windows execution, install/upgrade/uninstall lifecycle and live-game reception are unverified. Do not disable your device's security protections. Unknown-publisher warnings and policy-based blocks may occur.

See [Windows guide](WINDOWS_GUIDE.md), [future signing procedure](SIGNING.md), the [release manifest](release.json), and each release's SHA256SUMS.

The public release tag identifies this metadata repository. `release.json.sourceCommit` identifies the private Agent source used for the binaries. The two repositories have distinct Git histories.

Independent companion. Not affiliated with Valve.

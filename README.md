# Overcharge AGENT · Windows beta

Download from [overcharge.io/download](https://overcharge.io/download/), or choose a version under [Releases](https://github.com/dcnc-io/Overcharge-releases/releases).

This repository contains release metadata, documentation and downloadable binaries. Product source repositories remain private.

## Current beta

**0.1.0-connector.13 · Windows x64 · Unsigned**

- Installer: installs for the current Windows user and creates a Start menu shortcut.
- Portable: runs without installation.
- Play hosts the local connection, waiting screen and draft overlay. Heroes, Builds, Matches, Meta and Pros open the live website inside a shared desktop header. A fresh match signal hides the tabs; Show tabs restores navigation.
- Occupied receiver ports recover automatically to a saved free local port. Use Install / repair connection afterward, and restart Dota yourself when convenient.
- Updates are manual through the download page.

**Execution testing is incomplete.** Windows receiver tests reproduced an unavailable port, recovered to a free loopback port, accepted authenticated synthetic data and reused the saved port after restart. Full installation/upgrade/uninstall and live-game reception remain unverified; release notes distinguish source and packaged runtime evidence. Do not disable your device's security protections. Unknown-publisher warnings and policy-based blocks may occur.

See [Windows guide](WINDOWS_GUIDE.md), [future signing procedure](SIGNING.md), the [release manifest](release.json), and each release's SHA256SUMS.

The public release tag identifies this metadata repository. `release.json.sourceCommit` identifies the private Agent source used for the binaries. The two repositories have distinct Git histories.

Independent companion. Not affiliated with Valve.

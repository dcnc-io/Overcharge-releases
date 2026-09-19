# Overcharge AGENT 0.1.0-connector.9 · Public beta

First public Windows x64 release with **installer and portable EXE**.

- Game preparation: process status, connection setup, explicit launch and separate game-update status.
- Heroes, Builds and Matches open the production website in the default browser.
- Version display and manual update link.
- Existing Overcharge icon, shared Io 0.4.1 and existing Ranked/GSI functionality retained.
- Per-user installer configured without elevation, with a Start menu shortcut and preservation of user data.

## Verification and limitations

Both files are **unsigned** (Authenticode `NotSigned`). SHA-256 and byte size are provided in `release.json` and `SHA256SUMS`.

Source checks: 95 JavaScript files; 230 product tests (229 passed, 1 existing skip), scene/tuning checks, and 15 release-tool tests passed.

**Actual execution is not verified for this release.** Windows App Control blocked the unsigned candidate on the validation PC. Installation, upgrades, uninstall behavior, packaged browser launch and live Dota reception remain unverified. Publishing with this explicit limitation was approved. No security protection was disabled.

SmartScreen or other endpoint policies may warn or prevent execution. Keep security protections enabled. This beta does not promise complete Ranked picks/bans or all ten players' lineups; missing inputs remain unknown. Local capture is optional and starts off. Do not publish private capture files or GSI credentials.

Download the setup EXE for normal installation, or portable EXE for installation-free use. Updates are manual via [the download page](https://overcharge.io/download/).

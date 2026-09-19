# Overcharge AGENT 0.1.0-connector.12 · Public beta

Windows x64 installer and portable EXE from the same immutable source. Includes the Figma overlay and integrated desktop follow-up; connector.10 remained a local candidate. Connector.11 was withdrawn to draft before website activation after an actual window-close test found a detached WebContents cleanup issue. Connector.12 fixes and verifies that exit path.

- One Astro-compatible header for native Play and sandboxed Heroes, Matches, Meta, Pros, Builds and library/settings web content.
- PLAY OVERCHARGED waiting screen: Io explicitly waits for a new match signal. Dota launch remains an explicit user action. Positive process detection opens the waiting view without relaunching the game.
- Fresh authenticated match phases transition into the native draft overlay and hide tabs. Show tabs / Esc restores navigation. Stale input stays labeled and does not invent a game exit.
- Manual draft planning, item paths, local team notes and source-linked historical purchase examples. Design examples are labeled; no claim of complete live Ranked draft coverage.
- One Io 0.4.1 renderer. Web content has no native preload or Node access. Offline and connection recovery remain available locally.
- Same app identity and user-data directory; per-user NSIS installer without elevation, Start menu shortcut, data-preserving removal configuration. Manual updates only.

## Verification and limitations

Both files are **unsigned**, Authenticode **NotSigned**. Byte sizes, SHA-256 and private source commit are recorded in release.json and SHA256SUMS. Public tag history is distinct from private source history.

Source: 111 JavaScript syntax checks; 245 product tests passed (1 existing skip); scene/tuning checks; 15 release tests passed. Web integration: 355 tests passed (1 existing skip), Astro check and full production build. Browser inspection covered pending, synthetic match focus, stale/exit, search/profile, embedded navigation and minimum window geometry.

Hidden Linux Electron source checks: overlay 8/8, integrated shell 11/11, deployed WebContentsView 13/13 (including denied-network recovery). Synthetic authenticated GSI, capture and lifecycle checks passed. **The strict full graphical smoke did not pass because this host blocklists WebGL2.** Functional fallback receipts do not certify GPU rendering in the Windows package.

**Windows execution testing remains incomplete.** App Control blocked an unsigned executable on the validation PC; publishing with this limitation was explicitly authorized. The final Windows EXEs have not completed installation/reinstallation/update/removal, visible runtime, real Dota or Bot Pick tests. Do not disable security protections. SmartScreen or other policies may warn or prevent execution.

Download the setup EXE for normal installation or the portable EXE for installation-free use. Updates are manual via [the download page](https://overcharge.io/download/). Existing connector.9 remains available under its original versioned release.

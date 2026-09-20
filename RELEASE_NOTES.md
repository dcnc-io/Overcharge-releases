# Overcharge AGENT 0.1.0-connector.13 · Receiver recovery beta

Fixes a reported Windows failure where the default GSI port 47831 returned EADDRINUSE and the app remained at Receiver error.

- On an occupied default/saved port, the authenticated receiver directly binds one OS-selected free loopback port and saves it for the next restart. No process is killed and no firewall or security setting is changed. Explicit environment port overrides remain explicit; unrelated errors do not trigger fallback.
- Connection settings shows the active port and recovery state. Choose Install / repair connection after a port change, then restart Dota yourself when convenient if it still targets the old endpoint.
- A running Dota process no longer hides receiver failure behind a generic waiting message. Desktop ready, receiver listening, config mismatch and game-data receipt remain distinct.
- Existing native Play, Figma overlay, shared web tabs, user records, Io 0.4.1 and manual update behavior are preserved.

## Verification

Source 95ff673ca918a4d9be8b0f6fd8e83e32db0f45a1; 114 JavaScript syntax checks, 250 tests passed / 1 existing skip, scene/tuning checks; release tooling 15/15. Five recovery regressions passed on native Windows and Linux. A separate native Windows source run reproduced actual 47831 failure, recovered to 58311, accepted authenticated synthetic HERO_SELECTION with HTTP 200, then restarted on 58311. This is not a live-game claim.

Hidden Linux Electron: overlay 8/8, shell 11/11 and all functional GSI/authentication checks passed with no application errors. Strict full graphical smoke still fails the host's WebGL2 blocklist. No graphics/security bypass was used.

The actual Windows portable launched in isolated hidden smoke mode using its packaged-default entry. All functional opening, IPC/isolation, authenticated GSI, synthetic draft/reset and layout checks passed; overlay 8/8 and shell 11/11 passed, with zero application errors. The strict graphical smoke did not pass because the renderer was in fallback. This does not certify visible GPU rendering or a real game.

## Installation and limits

Both Windows x64 EXEs are unsigned (NotSigned). Same current-user installer, app identity and user data; updates are manual. Full install/reinstall/update/removal, real Dota/Bot Pick and complete Ranked draft coverage remain unverified. Do not disable device security protections. Old versioned assets are retained; checksums and source mapping are in release.json and SHA256SUMS.

Normal Windows portable launch also recovered the unavailable default port and listened on its saved new endpoint. The existing app-owned Dota config was repaired and independently checked as ready, with a private local backup. Dota was not restarted or launched by this repair; live-game receipt is still unverified.

# Overcharge AGENT 0.1.0-connector.14 · Io and local hero repair beta

Fixes the held Io introduction, the old landing electrical rectangle in integrated Play, and missing display of a received local hero when no team draft slots are supplied.

- Desktop Io keeps progressive first rendering but allows a bounded 45-second cold shader startup. The former 8-second cutoff interrupted 14/16 ready programs on the tested Windows GPU. Io 0.4.1 and full authored rendering remain unchanged.
- Legacy landing surfaces and their anchors are disabled in integrated Play and native research. Hiding and restoring the window cannot bring them back.
- A received local hero appears as **You**, even when Dota supplies no team lineup. It is counted once and selected for same-hero item comparison. Unseen teammates, enemy picks and exact team slots are never fabricated.
- An authenticated heartbeat without hero or match fields is labeled connected without match data. It is not proof of draft recognition.
- The connector.13 receiver fix is retained: a busy default/saved port recovers once to an OS-selected loopback port and saves it. Repair the connection file after a port change; Dota restart remains user-controlled.

## Verification and limits

Private source: 45744400dea408222d647acfb4245a93ad02d606. Syntax114; source253 passed,1 existing skip; scene/tuning checks; release tooling15/15. An isolated Windows source probe passed real WebGL startup, completed intro, core-Tether movement, authenticated synthetic GSI, overlay8/8 and shell13/13 including Phantom Lancer display and retired landing surfaces. The final connector.14 portable also passed the complete Windows packaged smoke with zero errors: real WebGL2, completed intro, core-Tether rendering, overlay8/8 and shell13/13. This is synthetic input, not a live bot-game acceptance test.

Actual connector.13 accepted authenticated traffic from a user-started bot game, but live Phantom Lancer recognition failed in the old UI. A subsequent seven-packet private capture occurred after return to the main menu and had no hero/map fields; it cannot prove the bot game's payload or validate the correction. Synthetic14 tests do not certify real Bot Pick or complete Ranked pick/ban coverage.

Both Windows x64 executables are unsigned (NotSigned), with the same current-user installer identity and preserved data path. Full installation/update/removal and real-game correction verification remain incomplete unless explicitly recorded in the manifest. Do not disable security protections. Updates are manual. Prior versioned assets are retained; source mapping, sizes and SHA-256 are in release.json and SHA256SUMS. Private game captures are never published.

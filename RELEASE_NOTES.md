# Overcharge AGENT connector.15 — real artwork and stable overlay

Hero and item images now use the verified real asset catalog shared with the website, rather than crops of design illustrations. Unchanged image elements survive incoming GSI updates, and ally/opponent rows stay above the item route panel. Unknown roles no longer display inferred role icons.

The source Windows probe decoded all 536 unique catalog images. All 542 mapped hero/item entries matched the web catalog ID, key and SHA-256. Final executable validation is recorded in release.json.

Local Slardar and Zeus recognition was reported in actual user screenshots. Other-player pick recognition remains unresolved: the current capture has not yet been located, and old menu-only data cannot establish what the game supplies during selection. Synthetic observer/team fixtures are not proof of actual player-mode team coverage. No hidden picks are inferred. This release does not claim that missing ally picks are fixed.

Unsigned Windows x64 beta; manual updates; same app ID and data path. Full installer update/removal lifecycle remains unverified. Security settings, Steam launch options and the active game are unchanged.

Final unsigned portable passed hidden Windows WebGL2/GSI smoke with zero errors, overlay 8/8 and shell 16/16. An earlier unpacked run during compression failed two shell transition checks; retained in release.json as an unresolved test-timing limitation.

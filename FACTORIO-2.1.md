# Factorio 2.1 compatibility and verified tests

Current release: **1.0.2**. Engine/API target: **Factorio 2.1.23**. Updated 2026-10-23.

## API and compatibility changes

- Keep GUI sprite source rectangles at their real 30/32 pixel dimensions and apply GUI scaling through scale; default 1.5x no longer fails graphical loading.
- Declare Factorio 2.1 compatibility.
- Retain native Lua table functions with current FLib, strict quality sorting and local price iteration.
- Use an optional temporary bridge to import original mod-private financial and trader storage.
- Use current fluid storage reads and named-fluid extraction for tank trading.
- Use helpers file APIs in the debug logger.
- Account for independent/shared recipe probabilities and fractional output in prices.
- Remove obsolete prototype/style fields reported unused by Factorio 2.1.

The audit used the installed runtime/prototype schemas and reviewed removed members, read-only writes, changed signatures, defines and named table arguments. Indirect calls and optional branches require manual review; this is not a formal proof of every execution path.

## Mod-specific checks

Graphical multiplayer startup passed with the default 1.5x GUI scale in all three power profiles. The sprite source rectangles no longer exceed their images. The earlier actual automatic item/fluid/energy trading, saved-order, credit and clean-reload results remain documented below; that suite originally used 1.0.1.

- Constructed and updated the main and item-selection GUI windows.
- Exercised fluid evaluation/selling, clearing a residual different fluid, buying fluid, helpers debug-file output and expected probabilistic recipe output.
- Compared financial/order state before import, after import and after disabling the bridge: three forces, 95 traders and 52 complete orders retained their credit balances and orders exactly. Saved and reloaded without the bridge.

## Multiplayer feature verification (2026-10-23)

Passed two complete feature rounds with a real client connected, followed by a clean-release restart/rejoin. Each full round automatically sold 100 normal iron plates, 1,000 crude oil and 10 MJ, and bought 10 plates, 50 oil and 2 MJ. Assertions checked emptied/filled inventories and buffers, credit gains/debits, persistence and execution of all three saved buy orders again after the clean restart.

Traders were built through the connected player's normal engine build path. A private setup interface configured auto/period/orders, but trades ran on the production hourly tick path; it did not call the trading functions directly. The clean third round removed the setup interface and repeated sales plus saved-order purchases. No exhaustive price/tax/quality matrix or GUI-click automation was performed.

Two full feature rounds were separated by server save/restart/client rejoin. A third restart/rejoin used unchanged clean release ZIPs, verified saved trading/distribution/science state, and exercised native features again. No desync, checksum mismatch or nonrecoverable error was detected in the final three rounds. Tests used localhost and the installed base/Space Age/Matt's mod set; raw saves, player profiles, logs and private bridges remain unpublished. No production-code fix or release-archive replacement was required.

## Shared save and multiplayer checks

The final enabled mod set passed isolated map creation, copied-save migration, bridge-free save/reload and 3,000-tick behavior/simulation checks. Matching clean release archives also passed a real localhost host/client join, 30 seconds of simulation, server save/restart, client rejoin and another 30 seconds plus save, without a detected desync. The direct multiplayer feature assertions above are separate from this earlier shared smoke coverage.

## Scope and limits

The fluid/API fixtures and migration checks do not exhaustively validate every item/energy transaction, pricing configuration or optional mod integration. Optional integrations outside the installed base/Space Age/Matt's profile were not all independently exercised; WAN and long-duration stress were not tested. Historical performance or compatibility results elsewhere in the documentation retain their original engine/workload scope.

Targeted API/interaction fixtures used temporary private hooks where needed. Those hooks, raw saves, profiles, credentials and logs are excluded from public source and release ZIPs. The current release ZIP is identified by the digest on its GitHub release asset. Runtime code and private fixtures are kept separate.

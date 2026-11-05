# Factorio 2.1 notes

Version **1.0.4**, tested with **Factorio 2.1.24**.

## Changes

Merges original BlackMarket2 2.2.24 circuit, price/menu guard, blueprint and wallet fixes. Blueprints, planners and remotes cannot be traded, including when an older save contains a price for them. Blueprint orders use the engine's exact source-entity mapping. The unused flib dependency is removed.

The fork retains correct independent/shared probabilities, fractional recipe output, strict quality sorting and optional migration-bridge import.

## Verified

- Automatic item, fluid and electricity sales and purchases, including credit changes and saved orders.
- Upgrade from 1.0.3 preserved the tested balances, inventories and orders. Trading continued with clean 1.0.4 archives and a connected client, followed by save, server restart and rejoin without a detected desync.
- Expected-output calculations, missing/removed recipe guards and the missing-group buy menu.
- Stale saved prices cannot bypass tool exclusions for valuation, sales or purchases.
- Actual red and green circuit connections toggled automatic trading.
- Blueprint handler checks used engine-created stacks and source mappings, relative coordinates and a selected surface different from the player's surface. These used synthetic setup events; the player GUI and library-record path were not tested end to end.
- Prototype duplication clears inherited upgrade targets without changing the source prototype.
- Base-game loading without flib; headless consistency checks with the installed mod profile.

Focused internal checks used private hooks in separate mod copies. The upgrade's connected-client phase used clean release archives. Player saves, raw logs and test hooks are not distributed. Tests cover representative trades and the installed profile, rather than every recipe, quality or third-party integration.

## Earlier migration evidence

The original-mod migration bridge previously preserved credits, trader settings and orders on Factorio 2.1.23. The bridge import code is retained; this update tested the existing fork's 1.0.3-to-1.0.4 upgrade rather than repeating every original-mod migration path.

# Black Market 2: Updated

## Factorio 2.1 compatibility and validation

Multiplayer feature checks passed, including save/restart/rejoin and a final clean-release verification. The linked guide describes the exact actions, controls and limits.

Current release **1.0.2** targets Factorio **2.1.23**. See [API fixes, this mod's verified tests and coverage limits](FACTORIO-2.1.md).

Factorio 2.1 update of Black Market 2. Original author: djmango. Sell and buy items/fluids/energy on the universal black market using trading chests/tanks/accumulators, choosing the frequency of exchanges and related fees. You can now sell your overproduction and buy things that you don't want to craft by yourself. You can also use these trading units as a paying shipment system.

For an existing save, use the temporary BlackMarket2_2.2.20.zip migration bridge from this repository's GitHub release alongside this fork. It transfers credits, orders and trader state. Save under a new filename, then remove the bridge. Without the bridge, mod-private financial state cannot be recovered automatically.

Multiplayer feature checks: Graphical multiplayer startup passed with the default 1.5x GUI scale in all three power profiles. The sprite source rectangles no longer exceed their images. The earlier actual automatic item/fluid/energy trading, saved-order, credit and clean-reload results remain documented below; that suite originally used 1.0.1. See [methods and coverage limits](FACTORIO-2.1.md).

See [Factorio 2.1 changes and validation](FACTORIO-2.1.md) and [original credits and license](ATTRIBUTION.md).

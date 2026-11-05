# Black Market 2: Updated

Buy and sell items, fluids and electricity through trading chests, tanks and accumulators.

**Factorio 2.1 · Version 1.0.4**

## Fork changes

- Prices recipe outputs using their actual chances, ranges and fractional quantities.
- Corrects quality ordering used by market pricing and trading.
- Copies trader orders to the correct blueprint entities, including selections on another surface.
- Prevents blueprints, planners and remotes from becoming tradable through prices retained in an older save.
- Provides a temporary bridge to import the original mod's credits, orders and trader state.

The fork includes original BlackMarket2 2.2.24 fixes and retains its automatic orders, trading frequency and fees.

## Installation and migration

Requires Factorio 2.1.23+. For a normal installation, disable the original BlackMarket2 and enable this fork.

To transfer an original-mod save:

1. Replace the original BlackMarket2 ZIP with the [temporary migration bridge](https://github.com/FactorioMods/black-market-2-updated/releases/download/v1.0.4/BlackMarket2_2.2.20.zip), then enable the bridge and this fork together.
2. Load the old save and save under a new filename.
3. Remove the bridge and continue with the fork.

Never load with the bridge alone: it contains no trading entities. Without the bridge, existing traders can be adopted, but the original mod's private credits and orders are not imported. [Migration instructions](migration-bridge/README.md).

Original mod by [djmango](https://github.com/djmango/BlackMarket2), maintained by johnmart19 / FactorioMods under [GPLv3](ATTRIBUTION.md).

[Mod Portal](https://mods.factorio.com/mod/black-market-2-updated) · [Source](https://github.com/FactorioMods/black-market-2-updated) · [Downloads](https://github.com/FactorioMods/black-market-2-updated/releases) · [Changes and tests](FACTORIO-2.1.md)

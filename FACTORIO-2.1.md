# Factorio 2.1 notes

Tested with **Factorio 2.1.23**. Current fork version: **1.0.3**.

## Changes

- Updated fluid reads and named-fluid removal, product probabilities and quality handling.
- Fixed sprite scaling at the default 1.5× GUI size.
- Fixed in-game changelog parsing; original entries are preserved in docs/UPSTREAM-CHANGELOG.txt.

## Tests

- Automatic item, fluid and energy sales and purchases; credit changes and saved orders.
- Migration preserved credits, trader settings and orders.
- Connected-client trading passed again with 1.0.2 during the cleaner regression suite, followed by clean save/restart/rejoin.

Trading fixtures configured orders through private setup hooks in the first two rounds; the last round used clean archives. Not every price, quality or GUI interaction was exercised.

Tests used private copies of saves and local host/client sessions. Raw player data and test hooks are not shipped.

The 1.0.3 patch changes changelog text and version metadata only; the feature tests above apply to the unchanged gameplay code.

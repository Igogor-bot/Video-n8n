## Redmine task:
 https://tasks.dxloo.com/issues/30765

## Idea

Add a configurable filter that excludes vehicles by AMS sale status. This is an estimate combined into one task for two targets; at implementation, split into two separate tasks (one per widget). The filter must support these statuses: `CheckIn`, `ReRun`, `RollOver`, `InStock`, `IfSale`, `NoSale`, `NoShow`, `Departure`, `BlockSale`, `LotSale`, `IfDown`, `TurnDown`, `IfAccept`.

## To Do

1. Add a multi-select setting `Sale Status Filter` to the `Search Simple` widget (Settings). Selected statuses are **excluded** from the widget’s results and counters.
1. In `Widget Builder 2`, add a `Sale Status Filter` element under `Settings > Filtering` (project-level setting for the inventory page). Selected statuses are **excluded** from the inventory list/grid.
1. Apply default behavior consistent with similar settings: if a status is hidden, vehicles in that status must not appear in `Search Simple` counters and must not appear on the page with `Widget Builder 2` inventory widget setup.
1. If no statuses are selected, show all vehicles (no exclusions).
1. Ensure the exact status options available are: `CheckIn`, `ReRun`, `RollOver`, `InStock`, `IfSale`, `NoSale`, `NoShow`, `Departure`, `BlockSale`, `LotSale`, `IfDown`, `TurnDown`, `IfAccept`.

## Logic

1. Scope: MAP2 only; applies to `Search Simple` (its results + counters) and the `Widget Builder 2` inventory view (list/grid and derived totals).
1. Exclusion rule: Any vehicle whose sale status matches a selected/hidden status must be omitted from the rendered results and any visible counters/aggregations within the respective widget.
1. Empty selection means no filtering is applied. Partial selection excludes only the chosen statuses.
1. No changes to AMS status definitions; this feature only consumes the existing AMS sale status value to drive filtering.

**Mockups/Screenshots:**

Settings MAP
https://tasks.dxloo.com/attachments/download/128625/Screenshot_102.jpg

Sale Status filter MAP
https://tasks.dxloo.com/attachments/download/128626/Screenshot_103.jpg

Sale Status filter WB2
https://tasks.dxloo.com/attachments/download/128627/Screenshot_104.jpg
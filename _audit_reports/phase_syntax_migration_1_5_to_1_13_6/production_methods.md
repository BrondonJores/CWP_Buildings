# Production Methods Syntax Migration Audit (1.5 -> 1.13.6)

## 1. Removed Syntax
* UNVERIFIED – requires vanilla file comparison.

## 2. New Syntax
* UNVERIFIED – requires vanilla file comparison.

## 3. Modified Syntax
* **Building Ownership Changes (1.7+)**: Update 1.7 completely revised Building Ownership. Owners of a building no longer have to work in that building or live in the same state. Production methods that previously managed ownership directly via workforce requirements and local distributions may have been significantly restructured or offloaded to external mechanisms (like Financial Districts or Manor Houses).
* UNVERIFIED – requires vanilla file comparison for specific script structural changes regarding `workforce` or `ownership` blocks in PMs.

## 4. Compatibility Risks
* **Ownership Production Methods**: Any 1.5 PMs dealing directly with building ownership (e.g., granting dividends to local capitalists or aristocrats) will likely be broken, behave inconsistently, or cause silent failures/gameplay issues in 1.13.6 due to the separation of ownership from the local building operation.
* UNVERIFIED – requires vanilla file comparison.

## 5. Migration Recommendations
* Review all ownership-related Production Methods. Adapt them to the new 1.7+ global ownership framework, removing local capitalist/aristocrat allocations where they are now handled by external investment pool logic.
* UNVERIFIED – requires vanilla file comparison.

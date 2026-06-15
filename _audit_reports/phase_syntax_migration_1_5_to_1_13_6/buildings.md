# Buildings Syntax Migration Audit (1.5 -> 1.13.6)

## 1. Removed Syntax
* UNVERIFIED – requires vanilla file comparison.

## 2. New Syntax
* **Resource Potential Effects**: Introduced new effects in 1.13.x allowing dynamic resource potential changes via scripts.
  * `add_resource_potential = building_type`
  * `remove_resource_potential = building_type`
  * `change_resource_potential = building_type`
  *(These operate in the `state` or `state_region` scope.)*
* UNVERIFIED – requires vanilla file comparison for additional newly supported fields.

## 3. Modified Syntax
* **State Traits Workaround**: Prior to 1.13, modifying resource distributions often required overwriting entire state definitions. The addition of resource potential effects changes how resources (like oil or iron mines) should be injected dynamically.
* UNVERIFIED – requires vanilla file comparison.

## 4. Compatibility Risks
* **Static Resource Overrides**: Mods that heavily modify state resources via direct file overwriting may experience conflicts or break compatibility with other mods. It is highly recommended to migrate to the new `add_resource_potential` effects.
* UNVERIFIED – requires vanilla file comparison.

## 5. Migration Recommendations
* Replace explicit state definition overrides for new resources with the dynamic script effect `add_resource_potential`.
* UNVERIFIED – requires vanilla file comparison.

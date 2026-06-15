# Global Syntax Migration Report (1.5 -> 1.13.6)

## Overview
This audit provides a read-only compatibility review of scripting structures between Victoria 3 version 1.5 and 1.13.6. It is largely based on official patch notes, dev diaries, and modding documentation since actual vanilla files were not directly provided for deep comparison. Due to this constraint, many specific scripting keys remain marked as "UNVERIFIED".

## Key Findings & Priority Matrix for Migration

The following systems introduce breaking changes or significant structural paradigms between 1.5 and 1.13.6. They should be addressed in the following order of priority during the CWP compatibility review:

### Priority 1: Production Methods (Building Ownership Overhaul)
* **Reason**: Update 1.7 completely decoupled building ownership from local workforce. Capitalists and Aristocrats now often operate out of Manor Houses and Financial Districts globally rather than living in the state the building is in. Any 1.5-era Production Methods governing "Ownership" (e.g., allocating dividends to local pops) are functionally obsolete and risk severe economic collapse or silent failures if not adapted to the new system.
* **Action**: Audit all ownership-related PM groups.

### Priority 2: Buildings (Dynamic Resource Potentials)
* **Reason**: Update 1.13 introduced `add_resource_potential`, `remove_resource_potential`, and `change_resource_potential`. Modifying the map to add oil, iron, or custom resources no longer requires overwriting entire state definition files or using the `add_state_trait` workaround.
* **Action**: Update building and map setup scripts to utilize the dynamic resource potential effects instead of static overrides. This ensures cross-mod compatibility and prevents map-breaking overrides.

### Priority 3: Laws & Diplomatic Interactions
* **Reason**: Subsequent patches after 1.5 refined how laws are enacted via script, introducing `start_enactment` and specific `on_impose_law` hooks.
* **Action**: Review scripts that force law changes to ensure they use the correct new enactment actions, preserving the game's internal law enactment tracking and UI.

### Priority 4: Technologies
* **Reason**: While specific breaking changes to technology syntax weren't explicitly highlighted in high-level dev diaries compared to ownership and buildings, technologies that unlock obsolete modifiers or legacy PMs will naturally need to be refactored.
* **Action**: Audit technology modifier fields and unlock lists once PMs and Buildings are stable.

## Note on Unverified Content
Because this is a read-only task relying heavily on documentation without performing direct diffs on 1.5 and 1.13.6 vanilla source files, any specific keys, nesting changes, or obsolete triggers must undergo a direct file comparison pass. Areas marked "UNVERIFIED" represent domains where documentation is insufficient to provide exact syntax diffs without inspecting the raw game files.

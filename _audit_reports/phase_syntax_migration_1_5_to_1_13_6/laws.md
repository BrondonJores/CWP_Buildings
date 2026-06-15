# Laws Syntax Migration Audit (1.5 -> 1.13.6)

## 1. Removed Syntax
* UNVERIFIED – requires vanilla file comparison.

## 2. New Syntax
* UNVERIFIED – requires vanilla file comparison.

## 3. Modified Syntax
* UNVERIFIED – requires vanilla file comparison.

## 4. Compatibility Risks
* **Imposing Laws via Script**: Introduced `start_enactment` and `on_impose_law` in 1.5.8/1.6, changing how forced laws are scripted compared to early 1.5 versions. Modders must ensure they use these new effects instead of raw force-changes to ensure proper UI updates and subject interactions.
* UNVERIFIED – requires vanilla file comparison.

## 5. Migration Recommendations
* Ensure any script that forces a law on a country (e.g., overlord imposing on subject) utilizes the newer `start_enactment` and specific `on_impose_law` actions if applicable to avoid breaking UI or event flow.
* UNVERIFIED – requires vanilla file comparison.

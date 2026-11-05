# Drupal 7 checks

Use these in place of the Drupal 8+ checks when the project is Drupal 7.
Do not apply modern Drupal advice to a Drupal 7 codebase.

## Check

- `hook_menu()` access callbacks and access arguments
- `hook_permission()` and `user_access()` checks
- Entity access control
- `db_select()`, `db_query()` and placeholders
- Form API validation and submission handlers
- Form tokens and CSRF protection
- Output safety: `check_plain()`, `filter_xss()`, `check_markup()`, `t()`
  placeholders
- Render arrays and theme functions
- The Cache API and cache invalidation
- The Variable API
- `hook_schema()` and `hook_update_N()`
- PHP syntax and APIs supported by the project's PHP version
- Interactions with custom and contributed modules
- Compatibility with legacy dependencies

Distinguish genuine vulnerabilities from established Drupal 7 patterns.

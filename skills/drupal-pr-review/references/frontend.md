# JavaScript and front-end checks

Use these when the pull request changes JavaScript, libraries, Twig
templates or themes.

## Check

- JavaScript runtime errors
- Drupal behaviors and `Drupal.attachBehaviors()` integration
- `once()` usage, and the version of `core/once` the project has
- AJAX handling
- Duplicated event listeners
- DOM injection and XSS through `innerHTML` or unescaped strings
- Async race conditions
- Accessibility regressions
- Broken asset dependencies and incorrect `*.libraries.yml` declarations
- Unnecessary front-end processing

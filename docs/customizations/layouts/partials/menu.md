# `layouts/partials/menu.html` override

- **File:** [`layouts/partials/menu.html`](../../../../layouts/partials/menu.html)
- **Shadows upstream:** `themes/hugo-theme-relearn/layouts/partials/menu.html`
- **Risk on Relearn upgrade:** 🔴 HIGH

## What this override does

This project overrides Relearn's `menu.html` with two customizations:

1. **Home as the first main-menu item**
2. **H1 headings as a collapsible submenu for leaf pages**

This is the most internally coupled template override in the project and
should be reviewed carefully when upgrading Relearn.

## Customization 1 — Home as the first menu item

Relearn normally renders the Home link in a separate `#R-homelinks` region.

For I4C 2026, the landing-page button is disabled through:

```toml
disableLandingPageButton = true

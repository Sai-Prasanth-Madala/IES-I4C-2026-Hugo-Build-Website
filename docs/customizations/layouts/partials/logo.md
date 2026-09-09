# `layouts/partials/logo.html` override

- **File:** [`layouts/partials/logo.html`](../../../../layouts/partials/logo.html)
- **Shadows upstream:** `themes/hugo-theme-relearn/layouts/partials/logo.html`
- **Risk on Relearn upgrade:** 🟡 MEDIUM

## What this override does

This project overrides Relearn's default logo rendering with a simple,
controlled logo implementation.

The override:

- reads the logo path from `params.logo.src`
- falls back to `/images/logo.png` when no logo source is configured
- renders the logo as a standard `<img>`
- removes unwanted default image styling such as borders and white
  backgrounds
- constrains the logo size so it fits cleanly inside the sidebar
- provides an optional title below the logo

The sidebar title is controlled by `params.linkTitle`.

- A non-empty `params.linkTitle` displays that text below the logo.
- An empty or unset value can be used when only the logo should be displayed.

## Why it exists

The default Relearn logo rendering is designed around the theme's standard
logo handling and styling. For the I4C 2026 site, the project uses a PNG
conference logo and requires more predictable sizing and presentation.

The custom implementation gives the project direct control over:

- logo source
- image dimensions
- image styling
- alternative text
- optional sidebar title

This prevents the conference logo from appearing with unwanted borders,
backgrounds, or excessive dimensions.

## Current logo configuration

The logo is configured through the Hugo parameters:

```toml
[params]
  logo = { src = "/images/logo.png" }

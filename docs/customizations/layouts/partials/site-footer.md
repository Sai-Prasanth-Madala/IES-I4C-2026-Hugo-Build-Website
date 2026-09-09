# `layouts/partials/site-footer.html` (NEW partial)

- **File:** [`layouts/partials/site-footer.html`](../../../../layouts/partials/site-footer.html)
- **Shadows upstream:** None — this is a project-specific partial
- **Risk on Relearn upgrade:** 🟢 LOW

## What this partial does

This partial renders the **visible I4C 2026 site footer** at the bottom of
the main page content.

The footer is separate from Relearn's built-in sidebar footer and contains
the conference's site-wide footer information and branding.

The footer is rendered inside `#R-body` through the
[`baseof.html` override](../_default/baseof.md).

## Why it exists

The project needs a visible footer inside the main content area rather than
using Relearn's `custom-footer.html` slot.

The `custom-footer.html` partial is called at the end of the document and is
used by this project as an empty hook for trailing scripts.

Therefore, the project introduced `site-footer.html` and explicitly
includes it inside the main page layout.

This ensures that the footer appears below the page content instead of
behaving as a separate body-level layout element.

## What's custom vs upstream

This is an entirely project-specific partial. Relearn does not provide an
upstream `site-footer.html` equivalent used by this project.

The partial can be customized independently without modifying the Relearn
theme.

## Re-applying on a Relearn upgrade

There is normally nothing to re-apply because this is a project-owned
partial and does not shadow an upstream template.

However, verify the connection to `baseof.html` after a Relearn upgrade.

The following line must remain inside the appropriate `#R-body` content
area:

```go-template
{{- partial "site-footer.html" . }}

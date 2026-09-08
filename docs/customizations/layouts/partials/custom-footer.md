# `layouts/partials/custom-footer.html` override

- **File**: [`layouts/partials/custom-footer.html`](../../../../layouts/partials/custom-footer.html)
- **Shadows upstream**: `themes/hugo-theme-relearn/layouts/partials/custom-footer.html`
- **Risk on Relearn upgrade**: 🟢 LOW

## What this override does

This file is intentionally kept as an empty placeholder.

The visible I4C 2026 site footer is **not rendered here**. It is implemented
in [`site-footer.html`](site-footer.md) and injected into the page content
through the `baseof.html` override.

The current file contains only a Hugo documentation comment.

## Why it exists

Relearn 9.x calls `custom-footer.html` at the very end of `<body>`, outside
the main `#R-body` content area.

The partial is intended for content that belongs at the end of the document,
such as trailing `<script>` tags.

The visible site footer was previously placed here, following an older
Relearn 6.x pattern. In Relearn 9.x this caused the footer to behave as a
body-level flex item and become visually hidden/out of position.

The visible footer was therefore moved to:

```text
layouts/partials/site-footer.html

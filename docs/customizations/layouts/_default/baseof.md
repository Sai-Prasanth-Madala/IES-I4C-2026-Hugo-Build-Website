# `layouts/_default/baseof.html` override

- **File:** [`layouts/_default/baseof.html`](../../../../layouts/_default/baseof.html)
- **Shadows upstream:** `themes/hugo-theme-relearn/layouts/_default/baseof.html`
- **Risk on Relearn upgrade:** 🔴 HIGH

## What this override does

This is a full copy of Relearn's `baseof.html` with one project-specific
addition:

```go-template
{{- partial "site-footer.html" . }}

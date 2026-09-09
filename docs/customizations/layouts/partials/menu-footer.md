# `layouts/partials/menu-footer.html` override

- **File:** [`layouts/partials/menu-footer.html`](../../../../layouts/partials/menu-footer.html)
- **Shadows upstream:** `themes/hugo-theme-relearn/layouts/partials/menu-footer.html`
- **Risk on Relearn upgrade:** 🟢 LOW

## What this override does

Replaces Relearn's default sidebar footer text with two organization logos:

- IEEE Industrial Electronics Society (IEEE IES)
- IEEE

The logos are displayed vertically and centered at the bottom of the
sidebar.

## Why it exists

The default Relearn menu footer contains the theme's promotional text.
For the I4C 2026 website, this area is instead used for IEEE and IEEE IES
branding.

The `menu-footer.html` partial is the appropriate Relearn slot for content
that should appear at the bottom of the sidebar menu.

## What's custom vs upstream

The upstream partial provides Relearn's default footer/promotion content.

The I4C 2026 override replaces that content with:

```html
<div class="menu-footer-class">
    <a href="https://www.ieee-ies.org" target="_blank" rel="noopener">
        <img src="/images/ies.png" alt="IEEE Industrial Electronics Society">
    </a>

    <a href="https://www.ieee.org" target="_blank" rel="noopener">
        <img src="/images/ieee.png" alt="IEEE">
    </a>
</div>

# Content migrations

Documents the Markdown-level deviations from stock Relearn content
expectations — specifically, front-matter keys we had to rename when
upgrading from Relearn 6.4.1 to 9.0.3.

---

## Per-conference edits in home-page front matter

[`content/_index.en.md`](../../content/_index.en.md) carries two values
that identify the specific conference:

```toml
+++
archetype = "home"
title = "IEEE IES Industrial Innovation Conclave 2026"  # hero / browser-tab prefix
description = "IEEE IES Industrial Innovation Conclave 2026 — Advancing Electrification, Automation, AI, Renewable Energy & Smart Mobility."  # meta description, OG/Twitter card
+++
```

- **`title`** — goes into the browser tab (before the site-level title) and
  the home-page breadcrumb. Conclave-specific. For I4C 2026, use
  `"IEEE IES Industrial Innovation Conclave 2026"`.

- **`description`** — meta description + OpenGraph / Twitter card.
  Conclave-specific tagline. For I4C 2026, use
  `"IEEE IES Industrial Innovation Conclave 2026 — Advancing Electrification, Automation, AI, Renewable Energy & Smart Mobility."`

These are edited alongside the home page content anyway, so the user isn't
editing an "extra" file — they're writing `_index.en.md` to set up the home
hero.

See [`config.md`](config.md) for the other three per-conclave values that
live in `hugo.toml`.

---

## Relearn 7.0 rename: `menuTitle` → `linkTitle`

Relearn 7.0 renamed the front-matter key for "label to show in the sidebar"
from `menuTitle` to `linkTitle`. Our content files use the new form:

```toml
# correct — used by our content
linkTitle = "For Authors"

# deprecated — warning surfaced by Hugo since Relearn 7.0
menuTitle = "For Authors"
```

Files migrated during the 6.4.1 → 9.0.3 upgrade:

- [`content/about/_index.md`](../../content/about/_index.md)
- [`content/committee/_index.md`](../../content/committee/_index.md)
- [`content/for_attendees/_index.en.md`](../../content/for_attendees/_index.en.md)
- [`content/program/_index.en.md`](../../content/program/_index.en.md)
- [`content/sponsors/_index.md`](../../content/sponsors/_index.md)

New content should always use `linkTitle`.

---

## Relearn 6.0 change: home-page `description`

Relearn 6.0 moved the site description from `params.description` (site-level
config) to the home page's front matter. Our `content/_index.en.md` has the
`description` line accordingly; `params.toml` no longer sets it at site level.

If you see `UNSUPPORTED usage of 'params.description' config parameter found`
during a build, the fix is to ensure the value lives in
`content/_index.en.md` front matter (not in `params.toml`).

---

## Shortcodes used by content

Our content files call the following shortcodes. See
[`shortcodes.md`](shortcodes.md) for details on each.

- `{{< slideshow >}}` — home-page hero carousel + for-attendees venue shots
- `{{< card >}}` — titled information panels (home, committee, for-authors)
- `{{< imagesRow >}}` — committee / sessions photo rows
- `{{< imageWithOverlay >}}` — occasional hero-style single image
- `{{< pdf-embed >}}` — embedded PDFs (call-for-papers templates, programs)
- `{{< spacer >}}` — vertical spacing in content-heavy pages

Upstream Relearn's shortcodes (`{{% notice %}}`, `{{< tabs >}}`, etc.) are
also available and in use (e.g. `notice` in `content/news_and_updates/_index.md`).

---

## Re-applying on upgrade

Relearn sometimes renames front-matter keys. The build surfaces these as
`DEPRECATED`/`UNSUPPORTED` warnings. To migrate in bulk, a typical pattern:

```bash
# Example: if Relearn renamed linkTitle → navTitle in a future version
find content -name '*.md' -exec sed -i '' 's/^linkTitle /navTitle /' {} +
```

Verify by building and checking the warnings count drops to zero.

---

## Related

- [`config.md`](config.md) — the other 3 per-conclave values (baseURL, full title, short title)
- [`shortcodes.md`](shortcodes.md) — the shortcodes called from content
- [`layouts/partials/menu.md`](layouts/partials/menu.md) — how the sidebar reads `linkTitle`

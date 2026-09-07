# Custom shortcodes

- **Files**: [`layouts/shortcodes/*.html`](../../layouts/shortcodes/)
- **Purpose**: Custom reusable components developed for the I4C 2026 website
- **Shadows upstream**: These are site-level custom shortcodes maintained by
  the I4C 2026 website.
- **Risk on Relearn upgrade**: 🟢 LOW (self-contained Hugo templates)

Relearn 9.0.3 provides its own shortcodes such as `notice`, `tabs`, `expand`,
`button`, and others. The I4C 2026 website additionally provides twelve
custom shortcodes for conference-specific layouts, speakers, dates, news,
images, documents, and interactive content.

| Shortcode | File | Purpose |
|---|---|---|
| `card` | [`card.html`](../../layouts/shortcodes/card.html) | Displays a styled content card with a title and body |
| `cards` | [`cards.html`](../../layouts/shortcodes/cards.html) | Provides a container/layout for displaying multiple cards |
| `imageWithOverlay` | [`imageWithOverlay.html`](../../layouts/shortcodes/imageWithOverlay.html) | Displays an image with text overlaid on top |
| `imagesRow` | [`imagesRow.html`](../../layouts/shortcodes/imagesRow.html) | Displays a responsive row of images with captions and participant details |
| `keyDates` | [`keyDates.html`](../../layouts/shortcodes/keyDates.html) | Displays important conference dates and milestones |
| `newsItem` | [`newsItem.html`](../../layouts/shortcodes/newsItem.html) | Displays an individual conference news or announcement item |
| `pageHero` | [`pageHero.html`](../../layouts/shortcodes/pageHero.html) | Provides a reusable hero section for conference pages |
| `pdf-embed` | [`pdf-embed.html`](../../layouts/shortcodes/pdf-embed.html) | Embeds internal or external PDF documents |
| `popup` | [`popup.html`](../../layouts/shortcodes/popup.html) | Displays additional content in a popup/modal interface |
| `slideshow` | [`slideshow.html`](../../layouts/shortcodes/slideshow.html) | Displays an auto-advancing image slideshow with navigation |
| `spacer` | [`spacer.html`](../../layouts/shortcodes/spacer.html) | Adds configurable vertical spacing between sections |
| `speaker` | [`speaker.html`](../../layouts/shortcodes/speaker.html) | Displays speaker information in a consistent conference layout |

---

## `card`

The `card` shortcode displays a styled content card with a title and
Markdown body content.

### Example

```hugo
{{< card title="Topics of Interest" >}}
- AI & Industry 5.0
- Electrification & Intelligent Industrial Drives
- EVs & Smart Mobility
- Battery Technologies & Charging
{{< /card >}}

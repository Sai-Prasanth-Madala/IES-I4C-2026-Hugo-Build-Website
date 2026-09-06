{{/* 
  I4C 2026 — IEEE IES Industrial Innovation Conclave 2026

  Custom Relearn topbar override.

  Purpose:
  - Displays the IEEE Industrial Electronics Society (IES) logo
  - Displays the IEEE parent-organisation logo
  - Keeps the standard Relearn topbar buttons
  - Places the conference branding inside Relearn's existing
    topbar-area-end section

  Conference:
  IEEE IES Industrial Innovation Conclave 2026
  22–23 September 2026
  Engineering Staff College of India (ESCI)
  Gachibowli, Hyderabad, Telangana, India
*/}}

<div class="site-brand-logos">

  <!-- IEEE Industrial Electronics Society -->
  <a
    href="https://www.ieee-ies.org/"
    target="_blank"
    rel="noopener"
    aria-label="IEEE Industrial Electronics Society"
  >
    <img
      src="{{ "images/ies.png" | relURL }}"
      alt="IEEE Industrial Electronics Society"
    >
  </a>

  <!-- IEEE -->
  <a
    href="https://www.ieee.org/"
    target="_blank"
    rel="noopener"
    aria-label="IEEE"
  >
    <img
      src="{{ "images/ieee.png" | relURL }}"
      alt="IEEE"
    >
  </a>

</div>

<style>
  /*
    I4C 2026 — Topbar Conference Branding

    The logos are intentionally kept inside Relearn's
    existing topbar-area-end container so they participate
    correctly in the topbar flex layout.
  */

  #R-topbar .site-brand-logos {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    margin-right: 10px;
    flex-shrink: 0;
  }

  #R-topbar .site-brand-logos a {
    display: flex;
    align-items: center;
    justify-content: center;
    text-decoration: none;
    line-height: 0;
  }

  #R-topbar .site-brand-logos img {
    display: block;
    width: auto;
    height: 34px;
    max-width: 100px;
    object-fit: contain;
  }

  /*
    Keep the branding compact on smaller screens.
  */

  @media (max-width: 768px) {
    #R-topbar .site-brand-logos {
      gap: 6px;
      margin-right: 6px;
    }

    #R-topbar .site-brand-logos img {
      height: 28px;
      max-width: 82px;
    }
  }

  @media (max-width: 480px) {
    #R-topbar .site-brand-logos {
      gap: 4px;
      margin-right: 4px;
    }

    #R-topbar .site-brand-logos img {
      height: 24px;
      max-width: 68px;
    }
  }
</style>

{{/* 
  Relearn topbar buttons.

  Keep this list synchronized with:
  themes/hugo-theme-relearn/layouts/partials/topbar/area/end.html

  If the Relearn theme changes its button partials in a future
  upgrade, update this section accordingly.
*/}}

{{ partial "topbar/button/edit.html" . }}
{{ partial "topbar/button/source.html" . }}
{{ partial "topbar/button/markdown.html" . }}
{{ partial "topbar/button/print.html" . }}
{{ partial "topbar/button/prev.html" . }}
{{ partial "topbar/button/next.html" . }}
{{ partial "topbar/button/more.html" . }}

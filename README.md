# Fan Rescue — Brand Assets

Centralised hosting for logos, brand tokens, and company info.
All assets served from **`https://assets.fanrescue.co.uk`** via Cloudflare Pages.

---

## Live URLs

### Logos (SVG — preferred, infinitely scalable)

| Lockup | Gold on Navy | Transparent |
|---|---|---|
| **Stacked** (hero / business card / letterhead)     | `/logos/FR-Stacked-Gold-Navy.svg`      | `/logos/FR-Stacked-Transparent.svg`      |
| **Horizontal** (website header / email signature)   | `/logos/FR-Horizontal-Gold-Navy.svg`   | `/logos/FR-Horizontal-Transparent.svg`   |
| **Mark only** (social avatar / watermark)           | `/logos/FR-Mark-Gold-Navy.svg`         | `/logos/FR-Mark-Transparent.svg`         |
| **Wordmark only** (tight vertical space)            | `/logos/FR-Wordmark-Gold-Navy.svg`     | `/logos/FR-Wordmark-Transparent.svg`     |

### Logo PNG fallbacks

Where SVG isn't supported (most social networks, some legacy email clients), use the matching PNG. `@2x` files are retina/high-DPI.

```
/logos/FR-Stacked-Gold-Navy.png         (400px)
/logos/FR-Stacked-Gold-Navy@2x.png      (800px)
/logos/FR-Horizontal-Gold-Navy.png      (600px)
/logos/FR-Horizontal-Gold-Navy@2x.png   (1200px)
...etc for each lockup × variant
```

### Favicon set

| File | URL | Purpose |
|---|---|---|
| `favicon.svg`             | `/favicon/favicon.svg`             | Modern browsers — sharp at any size |
| `favicon.ico`             | `/favicon/favicon.ico`             | Legacy / IE / multi-resolution |
| `favicon-16.png`          | `/favicon/favicon-16.png`          | Browser tab |
| `favicon-32.png`          | `/favicon/favicon-32.png`          | Browser tab high-DPI |
| `favicon-48.png`          | `/favicon/favicon-48.png`          | Windows site tiles |
| `favicon-96.png`          | `/favicon/favicon-96.png`          | Browser tab @2x retina |
| `apple-touch-icon.png`    | `/favicon/apple-touch-icon.png`    | iOS home screen (rounded) |
| `android-chrome-192.png`  | `/favicon/android-chrome-192.png`  | Android home screen |
| `android-chrome-512.png`  | `/favicon/android-chrome-512.png`  | Android splash / PWA |

### Brand data

| File | URL | Purpose |
|---|---|---|
| `tokens.css`   | `/brand/tokens.css`   | CSS variables — `--fr-navy-deep`, `--fr-gold`, fonts |
| `company.json` | `/brand/company.json` | Machine-readable BESA no., address, bank, palette |

---

## Brand colours

| Name           | Hex       | Use                                    |
|----------------|-----------|----------------------------------------|
| Navy Deep      | `#0A1628` | Primary background, wordmark on light  |
| Navy Mid       | `#162844` | Monogram background, mid-tone surfaces |
| Navy Light     | `#1E3A5F` | Tertiary accent                        |
| Gold Primary   | `#C8973E` | Wordmark, monogram, accent on dark     |
| Gold Light     | `#D4A94E` | Hover states, active accents           |
| Gold Pale      | `#E8D5A3` | Tagline text, subtle highlights        |
| Warm White     | `#F5F2EC` | Light backgrounds, page canvas         |
| Slate          | `#3D4F5F` | Body copy                              |
| Warm Grey      | `#8A9BAB` | Captions, muted text                   |

## Typography

| Role     | Font          | Weight  | Use                              |
|----------|---------------|---------|----------------------------------|
| Display  | Archivo Black | 900     | Headings, wordmark, monogram     |
| Body     | Source Sans 3 | 400–700 | Body copy, tagline, UI           |

**Letter-spacing:** wordmark `0.12em` · monogram `0.02em` · tagline `0.25em`

Both fonts are free via Google Fonts and loaded automatically by `tokens.css`.

---

## Using these in proposals & websites

### In an HTML proposal — add to `<head>`

```html
<!-- Favicons -->
<link rel="icon" type="image/svg+xml" href="https://assets.fanrescue.co.uk/favicon/favicon.svg">
<link rel="icon" type="image/x-icon" href="https://assets.fanrescue.co.uk/favicon/favicon.ico">
<link rel="apple-touch-icon" href="https://assets.fanrescue.co.uk/favicon/apple-touch-icon.png">

<!-- Brand tokens (CSS variables + Google Fonts) -->
<link rel="stylesheet" href="https://assets.fanrescue.co.uk/brand/tokens.css">
```

### Then in your CSS, reference tokens

```css
.fr-hero {
  background: var(--fr-navy-deep);
  color: var(--fr-warm-white);
  font-family: var(--fr-font-body);
}
.fr-hero h1 {
  font-family: var(--fr-font-display);
  color: var(--fr-gold);
  letter-spacing: var(--fr-tracking-wordmark);
}
.fr-btn {
  background: var(--fr-gold);
  color: var(--fr-navy-deep);
}
.fr-btn:hover { background: var(--fr-gold-light); }
```

### Embedding the logo

```html
<!-- Dark hero — gold-on-navy SVG sits on its own navy background -->
<img src="https://assets.fanrescue.co.uk/logos/FR-Horizontal-Gold-Navy.svg"
     alt="Fan Rescue" height="48">

<!-- Light page section — transparent SVG, fonts will pick up the page colour... -->
<!-- (use the gold-navy variant on light backgrounds if you want the gold wordmark) -->
<img src="https://assets.fanrescue.co.uk/logos/FR-Horizontal-Gold-Navy.svg"
     alt="Fan Rescue" height="48">
```

> **Note on transparent SVGs:** the "Transparent" variants have no background and rely on CSS fills, so on a light page they'll appear in their fill colours (gold + pale gold). If you need the wordmark in *navy* on a light page, that's a separate variant we'd need to generate — at the moment the pack is set up for "gold on dark" branding.

---

## Choosing the right logo file

| Context                                  | File                                                            |
|------------------------------------------|-----------------------------------------------------------------|
| Website header (desktop)                 | `FR-Horizontal-Gold-Navy.svg`                                   |
| Website header (mobile / narrow)         | `FR-Mark-Gold-Navy.svg`                                         |
| Social media profile picture             | `FR-Mark-Gold-Navy.svg` (or `.png@2x` if SVG isn't accepted)    |
| Browser tab icon                         | `favicon.svg` (with `favicon.ico` fallback)                     |
| iOS home-screen icon                     | `apple-touch-icon.png`                                          |
| Android home-screen icon                 | `android-chrome-512.png`                                        |
| Business card / letterhead / invoice     | `FR-Stacked-Gold-Navy.svg`                                      |
| Dark hero section / slide deck cover     | `FR-Stacked-Gold-Navy.svg`                                      |
| Email signature banner                   | `FR-Horizontal-Gold-Navy.png@2x` (most email clients block SVG) |
| Tight vertical space, brand needed       | `FR-Wordmark-Gold-Navy.svg`                                     |

---

## Usage rules

1. **Use SVG where possible.** Infinitely scalable. PNGs only for platforms that won't accept SVG.
2. **Leave clear space.** Padding around the logo ≥ height of the "E" in ESTABLISHED.
3. **Don't recolour.** If full palette won't reproduce, fall back to flat navy or flat black — never a new colour.
4. **Don't stretch, skew, or rotate.** If a lockup doesn't fit, switch to a different lockup.
5. **Don't edit the tagline size independently.** The 35% ratio is intentional — keep scales locked.
6. **Minimum sizes:** Stacked 40 mm / 160 px wide · Horizontal 60 mm / 240 px · Mark 10 mm / 40 px.
7. **Don't place the logo on busy photography** without a solid Navy Deep pad behind it.

---

## Deployment

This repo is connected to **Cloudflare Pages**. Push to `main` → live within ~30 seconds. No build step.

### One-time setup

1. Create the GitHub repo: **`fanrescue-assets`** (public)
2. Push this folder's contents to `main`
3. Cloudflare → Pages → Create project → connect GitHub → select repo
4. Build settings: leave blank (no build command, output directory `/`)
5. Custom domain → add `assets.fanrescue.co.uk` (DNS auto-created if on Cloudflare)

### Caching

The `_headers` file sets long cache lifetimes on logos and favicons (1 day browser / 7 days CDN) and shorter ones on `tokens.css` and `company.json` (so updates propagate within an hour). CORS is permissive — `*.fanrescue.co.uk` subdomains can pull these freely.

---

## Adding new assets

1. Drop file into `logos/`, `favicon/`, or `brand/`
2. Use the naming convention: lowercase, hyphen-separated, descriptive
3. Add a row to the URL table above
4. Commit and push

---

## Versioning

The brand pack is at **v2.0.0** (full SVG pack with Archivo Black + Source Sans 3, palette updated from previous Bitter + Montserrat / `#192840` / `#C9A84C` system).

Templates that reference the old palette (`#192840`, Bitter, Montserrat) need updating in their own repos to consume the new tokens.

---

_Maintained by Ben — Fan Rescue Ltd._

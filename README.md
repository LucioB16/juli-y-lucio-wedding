# Altare - Wedding Invitation Template

English | [Espanol](./README.es.md)

Elegant, static wedding invitation template powered by Astro + Tailwind v4, with a visual config builder.

[![Use this template](https://img.shields.io/badge/Use_this_template-238636?style=for-the-badge&logo=github&logoColor=white)](https://github.com/LucioB16/Altare/generate)
[![Live demo](https://img.shields.io/badge/Live_demo-5A7156?style=for-the-badge)](https://luciob16.github.io/Altare/)
[![Config Builder](https://img.shields.io/badge/Config_Builder-3C5A7A?style=for-the-badge)](https://luciob16.github.io/Altare/config-builder/)

---

## Create Your Invitation in 4 Steps

### Step 1: Create your repository

Click **Use this template** and create your own GitHub repository.

Important: your final invitation URL is based on your GitHub user + repo name.
Example: `https://mariaj.github.io/my-wedding/`

### Step 2: Enable GitHub Pages

1. Open **Settings -> Pages** in your repository.
2. In **Source**, choose **GitHub Actions**.

### Step 3: Configure your invitation

Use the visual Config Builder:

[![Open Config Builder](https://img.shields.io/badge/Open_Config_Builder-5A7156?style=for-the-badge)](https://luciob16.github.io/Altare/config-builder/)

The builder guides you through couple data, visual theme, events, photos, gifts, dress code, RSVP, socials, playlist, useful info cards, and OG/share image.

### Step 4: Upload YAML and photos

Quick links (inside your repo):

- [Open `wedding.yml`](./src/data/wedding.yml)
- [Open hero folder (`public/media/hero/`)](./public/media/hero/)
- [Open story folder (`public/media/couple/`)](./public/media/couple/)
- [Open social image folder (`public/media/og/`)](./public/media/og/)

`wedding.yml`:

1. Open `wedding.yml`.
2. Click the pencil icon.
3. Replace content with your generated YAML.
4. Commit changes.

Photos:

- `public/media/hero/` -> upload selected hero photo.
- `public/media/couple/` -> upload story photos with the exact selected filenames.
- `public/media/og/` -> upload share image (recommended 1200x630).

Your site will be published at:
`https://YOUR_USER.github.io/YOUR_REPO/`

---

## Language and i18n

- The builder saves selected language as `site.language`.
- Supported locales are auto-discovered from `src/i18n/locales/*.json`.
- Default locale is `en`.
- Backward compatibility:
  - If `site.language` is missing, fallback is `locale.language`.
  - If both are missing/unknown, fallback is `en`.
- Generated user repos are monolingual by default.
- Demo repos can expose extra locale routes through `demo.locales`.

### Add a New Language (Quick)

1. Duplicate `src/i18n/locales/en.json` to `src/i18n/locales/<code>.json` (example: `fr.json`).
2. Translate keys and set `contentDefaults.locale.language` (example: `fr-FR`).
3. Run:

```bash
bun run sync:themes
bun run build
```

The builder locale selector and site locale resolution will pick the new locale automatically.

---

## Features

- Responsive layout for mobile, tablet, and desktop.
- Visual config builder (no coding needed).
- Modular sections with enable/disable toggles.
- Optional religious ceremony, civil ceremony, and celebration blocks.
- Story gallery (1-4 photos).
- Gifts section with optional bank data.
- Countdown, RSVP, socials, playlist, and useful info cards.
- Static deployment on GitHub Pages.

## Theming

- Shared token-based theme system for site and builder.
- Available themes:
  - `jardin-clasico` (default)
  - `marfil-editorial`
  - `botanica-nocturna`
  - `rosa-antiguo`
  - `galeria-moderna`
- `theme.id` is optional; fallback is `jardin-clasico`.
- Theme changes aesthetics only (colors, fonts, ornaments), without changing layout logic.

---

## Local Development

```bash
bun install
bun run dev
```

### Commands

| Command | Action |
| :-- | :-- |
| `bun install` | Install dependencies |
| `bun run sync:themes` | Sync themes, fonts, and locales to builder assets |
| `bun run dev` | Start Astro dev server |
| `bun run build` | Build production output to `dist/` |
| `bun run preview` | Preview production build locally |
| `bun astro ...` | Run Astro CLI commands |

### Project Structure

```text
src/
  components/
  data/
    wedding.yml
    weddingData.ts
  i18n/
    config.ts
    messages.ts
    site.ts
    locales/
  theme/
  layouts/
  pages/
  styles/
public/
  media/
    hero/
    couple/
    og/
  config-builder/
scripts/
  sync-themes.mjs
```

---

## Credits and License

Based on [SaidYes](https://github.com/roicort/saidyes) by [@roicort](https://github.com/roicort), under AGPL-3.0.

This fork keeps AGPL-3.0. See [LICENSE](./LICENSE).

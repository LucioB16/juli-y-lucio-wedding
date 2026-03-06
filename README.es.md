# Altare - Template de Invitacion de Boda

[English](./README.md) | Espanol

Invitacion digital de boda, elegante y 100% configurable, desplegable en minutos con GitHub Pages.

[![Usar este template](https://img.shields.io/badge/Usar_este_template-238636?style=for-the-badge&logo=github&logoColor=white)](https://github.com/LucioB16/Altare/generate)
[![Ver demo en vivo](https://img.shields.io/badge/Ver_demo_en_vivo-5A7156?style=for-the-badge)](https://luciob16.github.io/Altare/)
[![Abrir Config Builder](https://img.shields.io/badge/Abrir_Config_Builder-3C5A7A?style=for-the-badge)](https://luciob16.github.io/Altare/config-builder/)

---

## Crear tu invitacion en 4 pasos

### Paso 1: Crear tu repositorio

Hace click en **Use this template** y crea tu repo en GitHub.

Importante: la URL final depende de tu usuario + nombre del repo.
Ejemplo: `https://mariaj.github.io/mi-boda/`

### Paso 2: Activar GitHub Pages

1. Entra a **Settings -> Pages** en tu repo.
2. En **Source**, elige **GitHub Actions**.

### Paso 3: Configurar tu invitacion

Usa el Config Builder visual:

[![Abrir Config Builder](https://img.shields.io/badge/Abrir_Config_Builder-5A7156?style=for-the-badge)](https://luciob16.github.io/Altare/config-builder/)

El builder te guia paso a paso para configurar pareja, tema visual, eventos, fotos, regalos, dress code, RSVP, redes, playlist, cards utiles e imagen OG/compartir.

### Paso 4: Subir YAML y fotos

Accesos rapidos (desde tu repo):

- [Abrir `wedding.yml`](./src/data/wedding.yml)
- [Abrir carpeta portada (`public/media/hero/`)](./public/media/hero/)
- [Abrir carpeta historia (`public/media/couple/`)](./public/media/couple/)
- [Abrir carpeta imagen redes (`public/media/og/`)](./public/media/og/)

`wedding.yml`:

1. Abre `wedding.yml`.
2. Haz click en el lapiz.
3. Reemplaza el contenido con tu YAML generado.
4. Commit de cambios.

Fotos:

- `public/media/hero/` -> sube la foto de portada seleccionada.
- `public/media/couple/` -> sube fotos de historia con los mismos nombres seleccionados.
- `public/media/og/` -> sube imagen para compartir (recomendado 1200x630).

Tu sitio se publicara en:
`https://TU_USUARIO.github.io/TU_REPO/`

---

## Idiomas e i18n

- El builder guarda el idioma elegido en `site.language`.
- Los locales soportados se detectan automaticamente desde `src/i18n/locales/*.json`.
- El idioma por defecto es `en`.
- Compatibilidad hacia atras:
  - Si falta `site.language`, se usa `locale.language`.
  - Si faltan ambos o son invalidos, se usa `en`.
- Repos de usuarios generados desde este template: monolingue por defecto.
- Repos demo/template: pueden exponer rutas extra con `demo.locales`.

### Agregar un idioma nuevo (rapido)

1. Duplica `src/i18n/locales/en.json` como `src/i18n/locales/<codigo>.json` (ejemplo: `fr.json`).
2. Traduce las claves y define `contentDefaults.locale.language` (ejemplo: `fr-FR`).
3. Ejecuta:

```bash
bun run sync:themes
bun run build
```

El selector de idioma del builder y la resolucion del sitio tomaran ese locale automaticamente.

---

## Features

- Responsive para mobile, tablet y desktop.
- Builder visual para configurar sin codigo.
- Secciones modulares con toggles on/off.
- Ceremonia religiosa, civil y celebracion opcionales.
- Galeria de historia (1-4 fotos).
- Regalos con datos bancarios opcionales.
- Cuenta regresiva, RSVP, redes, playlist e info util.
- Deploy estatico en GitHub Pages.

## Novedades de theming

- Sistema de temas por tokens compartidos entre sitio y builder.
- Temas disponibles:
  - `jardin-clasico` (default)
  - `marfil-editorial`
  - `botanica-nocturna`
  - `rosa-antiguo`
  - `galeria-moderna`
- `theme.id` es opcional; fallback: `jardin-clasico`.
- El tema solo cambia estetica (colores, tipografias, ornamentos), no el layout.

---

## Desarrollo local

```bash
bun install
bun run dev
```

### Comandos

| Comando | Accion |
| :-- | :-- |
| `bun install` | Instala dependencias |
| `bun run sync:themes` | Sincroniza temas, fuentes y locales al builder |
| `bun run dev` | Levanta servidor de desarrollo Astro |
| `bun run build` | Genera build de produccion en `dist/` |
| `bun run preview` | Previsualiza build de produccion |
| `bun astro ...` | Ejecuta comandos del CLI de Astro |

### Estructura del proyecto

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

## Creditos y licencia

Basado en [SaidYes](https://github.com/roicort/saidyes) por [@roicort](https://github.com/roicort), bajo AGPL-3.0.

Este fork mantiene AGPL-3.0. Ver [LICENSE](./LICENSE).

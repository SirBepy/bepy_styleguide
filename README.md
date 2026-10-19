# sirbepy-styleguide

Joe's design system, hosted on CDN via GitHub Pages.

## What's here

- **Styleguide explorer** - `index.html` showcases all components, typography, colors, and utilities
- **16 themes** - each with a dark and a light variant, all using CSS custom properties
- **Settings widget** - floating gear button with theme switcher, background, and about panel
- **Compiled styleguide** - `styleguide.css` with reusable component classes

## CDN usage

Projects pull themes and widgets from this repo via jsDelivr:

```
https://cdn.jsdelivr.net/gh/sirbepy/sirbepy-styleguide@main/themes/theme-void.css
https://cdn.jsdelivr.net/gh/sirbepy/sirbepy-styleguide@main/widget/settings.js
https://cdn.jsdelivr.net/gh/sirbepy/sirbepy-styleguide@main/styleguide.css
```

## Themes

| Theme           | Description           |
| --------------- | --------------------- |
| **Void**        | Dark purple - default |
| **Glacier**     | Cool blue-grey        |
| **Cosmo**       | Vibrant and colorful  |
| **Nebula**      | Deep space tones      |
| **Forest**      | Deep green            |
| **Ember**       | Warm amber            |
| **Graphite**    | Neutral gray          |
| **Crimson**     | Deep red              |
| **Catppuccin**  | Mocha / Latte         |
| **Gruvbox**     | Retro warm            |
| **Nord**        | Arctic blue           |
| **Solarized**   | Classic low contrast  |
| **Tokyo Night** | Night / Day           |
| **Rose Pine**   | Main / Dawn           |
| **Dracula**     | Dracula / Alucard     |
| **One**         | One Dark / One Light  |

Each file declares `[data-theme="<id>"]` (dark) and `[data-theme="<id>"][data-mode="light"]` (light), plus `--color-domain-*` tokens for question-card chips. The settings widget's theme switcher still lists only the original four (`FALLBACK_THEMES` in `widget/settings.js`).

All themes define CSS custom properties (`--color-primary`, `--font-heading`, `--radius-card`, etc.) that the styleguide components consume.

## Repo structure

```
sirbepy-styleguide/
  index.html         - Styleguide explorer page
  styleguide.css     - Compiled component classes
  themes/            - Theme CSS files
  widget/            - Settings widget + animated background
  package.json       - Repo metadata
```

# Token Map — claude_usage / kit → styleguide

Canonical token vocabulary for the unified Tauri look is the styleguide's `--color-*`
set (defined per palette × mode in `themes/theme-{void,nebula,glacier,cosmo}.css`).
claude_usage and `sirbepy_tauri_kit` migrate onto these names; their old token names
are retired (temporary `var(--color-*)` aliases allowed only to stage the migration).

## claude_usage (`src/styles/themes.css`) → styleguide

| claude_usage   | styleguide          |
|----------------|---------------------|
| `--bg`         | `--color-background`|
| `--surface`    | `--color-surface`   |
| `--surface-alt`| `--color-surface-alt`|
| `--primary`    | `--color-primary`   |
| `--secondary`  | `--color-secondary` |
| `--text`       | `--color-text`      |
| `--text-dim`   | `--color-text-muted`|
| `--border`     | `--color-border`    |
| `--danger`     | `--color-danger`    |
| `--success`    | `--color-success`   |
| `--accent`     | `--color-accent`    |

## kit (`frontend/settings/styles/tokens.css`, `palettes/sirbepy-default.css`) → styleguide

| kit               | styleguide          |
|-------------------|---------------------|
| `--kit-bg`        | `--color-background`|
| `--kit-bg-alt`    | `--color-surface`   |
| `--kit-bg-hover`  | `--color-surface-alt`|
| `--kit-text`      | `--color-text`      |
| `--kit-text-dim`  | `--color-text-muted`|
| `--kit-accent`    | `--color-primary`   |
| `--kit-accent-hover` | `--color-secondary` |
| `--kit-border`    | `--color-border`    |
| `--kit-danger`    | `--color-danger`    |

`--kit-danger-bg` / `--kit-danger-border` (danger-zone tints) and the `--scrollbar-*`
tints are lightness-keyed, not palette-keyed; they stay as kit-local helpers (or move
to a shared light/dark layer), not 1:1 styleguide tokens.

## Token availability (verified 2026-05-31)

All `--color-*` targets above already exist in every `themes/theme-*.css` (dark + light):
`--color-primary`, `--color-primary-rgb`, `--color-secondary`, `--color-accent`,
`--color-background`, `--color-surface`, `--color-surface-alt`, `--color-text`,
`--color-text-muted`, `--color-border`, `--color-success`, `--color-danger`, `--color-info`,
plus `--font-*`, `--radius-card`, `--radius-badge`, `--shadow-card`.
`--color-danger` was added across all four palettes in `af10f88`.

## Palette values

claude_usage's palette colors are the reference. As of `af10f88` the styleguide's
Void/Nebula/Glacier/Cosmo values match claude_usage's `themes.css` (Void already matched;
Nebula/Glacier/Cosmo were reverted from the styleguide's earlier teal/blue/orange to
claude_usage's purple/sky/pink). The kit's `sirbepy-default.css` also already carried
these values. So claude_usage = kit = styleguide on palette values.

## Selector convention

Styleguide uses 2D selectors: `[data-theme="void"]` (dark) + `[data-theme="void"][data-mode="light"]`.
The kit historically used flat ids (`[data-theme="void"]` / `[data-theme="void-light"]`).
Phase 1 migrates the kit to the 2D convention so the vendored styleguide CSS matches
verbatim (see plan Task 1.4/1.5).

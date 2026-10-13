# hecate

hecate is a contract-first web API framework for Lua 5.5. Its identity reads like a figure
from an astronomy treatise: the earth, the moon, and hecate as the link between them. It is
quiet, precise and academic, set in the typefaces of scientific publishing.

## The mark: a conjunction

- **The moon** is Lua (Portuguese for *moon*), in a navy close to Lua's own, shown in
  phase so it reads as a moon rather than a dot.
- **The earth** is us: the commons, the web and its people, in verdigris.
- **hecate** is the link: three points where the line joining earth and moon crosses her
  dotted orbit. Three for her triple form and for the three roads of the crossroads; a
  node, because the framework's router is where every request finds its way.

The mark is drawn on a 64-unit grid and is anchored to its bottom-left corner: the earth
is always cropped by the edge of its frame, never shown whole.

### Two sizes

| Version | Use | What changes |
|---|---|---|
| `hecate-mark` (full) | 64 px and larger | dotted orbit, phased moon, triple node |
| `hecate-mark-compact` | under 64 px: favicons, toolbars, small avatars | no orbit, heavier lines, a single ring for hecate |

### The name

The name is never written with a capital letter. Every letter sits at the same level:

- **All small caps** (`hecate` set in STIX Two with all small caps, letter-spaced) for
  titles, lockups, banners and covers: `hecate-wordmark-smallcaps`.
- **Lowercase** (STIX Two semibold) inline, in running text that names the project, in
  the CLI and in package names: `hecate-wordmark-lowercase`.

At the start of a sentence, rephrase rather than capitalise ("The hecate CLI…").

### Lockups

| Asset | Use |
|---|---|
| `hecate-logo-horizontal` | default: site header, README, slides |
| `hecate-logo-stacked` | square spaces: covers, splash screens, stickers |
| `hecate-mark` / `-compact` | the mark alone |
| `hecate-mark-mono-ink` / `-mono-white` | single-ink printing, engraving, embossing (moon shown as outline with its shadow) |

Every coloured asset exists for light grounds and `-on-dark` grounds. All text in the SVG
files is outlined, so they render the same everywhere without fonts installed.

### Clear space, sizes, don'ts

- Clear space: the moon's diameter on every side of any lockup.
- Minimum sizes: full mark 64 px; compact mark 16 px; horizontal lockup 160 px wide.
- Don't recolour outside the palette, rotate the mark, show the earth whole, separate the
  moon from the line, add a graticule, outlines, shadows or gradients, or capitalise the name.

## Colour

Two themes with the same token names; every text pair meets WCAG 2.2 AA on
`surface-100` (ratios in each token's usage note).

- **Grounds**: paper (`surface-100` light) and night (`surface-100` dark), with
  `surface-200` and `surface-300` for sidebars, code and raised elements.
- **Text**: `ink`, `ink-muted`.
- **Brand**: `moon` (navy) is the identity colour; `earth` (verdigris) is the single
  accent for links, primary actions and active states; `moonlight` only for the lit
  crescent and soft tints, never for text.
- **States**: `success` and `danger`, always with a label or an icon (success sits close
  to earth in hue).
- **Lines**: `border` for rules, `border-strong` for controls.

No gradients, no glows. Corners are nearly square (2 to 4 px), as on a printed page.

## Typography

| Family | Typeface | Use |
|---|---|---|
| `serif` | STIX Two Text | titles, running text, the wordmark |
| `sans` | Fira Sans | interface: navigation, buttons, parameter tables |
| `mono` | Fira Code | code |

The pairing of scientific publishing (STIX Two) and of LaTeX Beamer's Metropolis theme
(Fira). Running text is set in the serif, as in a paper: pages are numbered like sections
(3.2 Refinement types), defined terms are in italics, definitions and notes may be
introduced in small caps ("Definition 1."). All three typefaces are free (SIL Open Font
License) and on Google Fonts.

## Voice

English, precise, plain. Vocabulary from hecate's glossary (future, reactor, refinement
type, unit of work), linked on first use. Short sentences, active voice, no exclamation
marks, no emoji in documentation.

## Pattern

`pattern-trivium`: the triple node, tiled every 96 px at 12 % of `moon`. For heroes,
covers and empty states; never behind running text.

## Repository and web assets

Put the files in `docs/brand/` of the repository.

- README banner, switching with GitHub's colour scheme:

```html
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="docs/brand/readme-banner-on-dark.svg">
  <img alt="hecate — contract-first web APIs for Lua 5.5" src="docs/brand/readme-banner.svg">
</picture>
```

- `github-social-preview` (1280 × 640), `org-avatar` (500 × 500), `app-icon` (512 × 512):
  GitHub and app stores require PNG; export first:

```sh
rsvg-convert -w 1280 github-social-preview.svg -o github-social-preview.png
rsvg-convert -w 500 org-avatar.svg -o org-avatar.png
```

- `og-card` / `og-card-light` (1200 × 630): default sharing image of the website.
- `favicon`: compact mark on a night square, readable on any browser chrome. For the
  website, an adaptive version (no square, colours following the visitor's scheme) can be
  committed as `favicon.svg`; it needs inline `<style>`, which this asset library
  removes, so it lives here as source:

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 64 64"><style>svg{--n:#1C2766;--e:#2F6F64;--l:#C9CFE6}@media (prefers-color-scheme:dark){svg{--n:#C9CFE6;--e:#5FB0A1;--l:#F5F4EE}}</style><circle cx="10" cy="62" r="33" fill="var(--e)"/><g stroke="var(--n)" stroke-width="3"><line x1="30.41" y1="36.07" x2="32.21" y2="33.79"/><line x1="40.99" y1="22.63" x2="41.12" y2="22.46"/></g><path d="M53.22,22.18 A9.5,9.5 0 0,0 38.56,10.64 A9.5,9.5 0 0,0 53.22,22.18Z" fill="var(--n)"/><path d="M53.22,22.18 A9.5,9.5 0 1,0 38.56,10.64 A9.5,9.5 0 0,1 53.22,22.18Z" fill="var(--l)"/><circle cx="36.6" cy="28.21" r="5.6" fill="none" stroke="var(--n)" stroke-width="3"/></svg>
```

## For agents building hecate's documentation theme

The `hecate.doc` theme (ADR 0012) takes colours, type styles, spacing and radii from
`tokens.json`, both themes, with unchanged names. Running text in `serif`, interface in
`sans`, code in `mono`. The theme is original work: nothing from Lua Web Docs or
Tailwind UI.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="brand/assets/Social/readme-banner-on-dark.svg">
  <img alt="hecate — contract-first web APIs for Lua 5.5" src="brand/assets/Social/readme-banner.svg">
</picture>

# The hecate-framework `.github` repository

This repository holds the organisation-wide files of
[hecate-framework](https://github.com/hecate-framework). The framework itself is
developed in [hecate-framework/hecate](https://github.com/hecate-framework/hecate);
start there if you want to read the code or the specification.

## Contents

| Path | What it is |
|---|---|
| [`profile/README.md`](profile/README.md) | The landing page shown on the [organisation profile](https://github.com/hecate-framework). It introduces hecate and maps where everything lives. |
| [`brand/`](brand) | The visual identity: logos, icons, social images, pattern, design tokens and the brand guide. |
| [`CONTRIBUTING.md`](CONTRIBUTING.md), [`SECURITY.md`](SECURITY.md), [`SUPPORT.md`](SUPPORT.md), [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md) | Default community health files. GitHub shows them on every repository of the organisation that has none of its own, in practice the read-only `hecate-<package>` mirrors. |
| [`.github/ISSUE_TEMPLATE/config.yml`](.github/ISSUE_TEMPLATE/config.yml) | Default issue chooser: on a repository without its own templates, it sends people to the monorepo. |

## Visual identity

The brand guide is [`brand/README.md`](brand/README.md). In brief:

- The mark is a conjunction: the moon (Lua), the earth (the web and its people), and
  hecate as the three-point node on the line between them.
- The name is never capitalised. Use small caps in titles and lowercase in running text.
- `moon` (navy `#1C2766`) is the identity colour and `earth` (verdigris `#2F6F64`) is the
  single accent. Every token, in light and dark themes, is in
  [`brand/tokens.json`](brand/tokens.json).
- Type: STIX Two Text for text, Fira Sans for interface, Fira Code for code.

| Asset | Folder | Use |
|---|---|---|
| Logos and wordmarks | [`brand/assets/Logos`](brand/assets/Logos) | `hecate-logo-horizontal` by default; `-on-dark` variants for dark grounds |
| Icons | [`brand/assets/Icons`](brand/assets/Icons) | `org-avatar.png` for GitHub avatars, `favicon`, `app-icon` |
| Social images | [`brand/assets/Social`](brand/assets/Social) | `github-social-preview.png` for repository settings, `og-card` for the website, `readme-banner` for READMEs |
| Pattern | [`brand/assets/Patterns`](brand/assets/Patterns) | Background for heroes and covers, never behind text |

Every coloured asset ships as SVG (text outlined) and PNG. The kit is stored exactly as
it was exported, including `manifest.json` and the cover component preview, so it can be
compared with later exports.

## Changing the landing page

Edit [`profile/README.md`](profile/README.md). Its images use absolute
`raw.githubusercontent.com` URLs on `main`, because the organisation page does not
resolve paths relative to this repository. Keep the links pointing at the monorepo's
`main` branch, and follow the voice of the brand guide: English, precise, plain, short
sentences, no exclamation marks, no emoji.

## Licence

[MIT](LICENSE).

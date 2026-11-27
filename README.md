# Pi Theme

> Four Catppuccin flavors for [Pi](https://pi.dev), bundled as a theme-only package.

[![CI](https://github.com/pi-contrib/pi-theme/actions/workflows/ci.yml/badge.svg)](https://github.com/pi-contrib/pi-theme/actions/workflows/ci.yml)
[![Release](https://img.shields.io/github/v/release/pi-contrib/pi-theme)](https://github.com/pi-contrib/pi-theme/releases/latest)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

| Theme | Appearance |
| --- | --- |
| `catppuccin-latte` | Light |
| `catppuccin-frappe` | Dark |
| `catppuccin-macchiato` | Dark |
| `catppuccin-mocha` | Dark |

## How it works

Pi Theme is a theme-only package: it ships four JSON theme files and no executable code. Each file maps a Catppuccin palette onto Pi's theme schema; Pi discovers the themes from the installed package and applies the one selected in `/settings` or `~/.pi/agent/settings.json`.

## Requirements

- Pi with theme support; the themes are validated against Pi's published theme schema in CI
- No additional runtime dependencies

## Installation

Install the latest code from GitHub without a registry login:

```sh
pi install git:github.com/pi-contrib/pi-theme
```

Or, after configuring npm authentication for `npm.pkg.github.com` and the `@pi-contrib` scope, install the latest release from GitHub Packages:

```sh
pi install npm:@pi-contrib/pi-theme
```

For a reproducible install, append a release tag (for GitHub) or a version (for npm). Restart Pi and choose a theme in `/settings`, or set it in `~/.pi/agent/settings.json`:

```json
{
  "theme": "catppuccin-mocha"
}
```

## Development

Use Node.js 22 locally or enter the Nix dev shell with `nix develop`:

```sh
curl -fsSL https://pi.dev/schemas/theme.schema.json -o /tmp/pi-theme-schema.json
npx --yes ajv-cli@5.0.0 validate --spec=draft2020 --strict=false \
  -s /tmp/pi-theme-schema.json -d 'themes/*.json'
npm pack --dry-run
```

Release Please creates release PRs. Merging one tags the release and publishes the npm package to GitHub Packages. The repository must allow Actions to create pull requests, and the organization must allow the workflow to publish packages.

## License

MIT. Palettes come from [Catppuccin](https://github.com/catppuccin/catppuccin); the theme JSON is adapted from [Prime Catppuccin Theme](https://github.com/andrestobelem/prime-catppuccin-theme). See [LICENSE](LICENSE).

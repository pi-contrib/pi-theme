# Pi Theme

Four Catppuccin flavors for [Pi](https://pi.dev), bundled as a theme-only package.

| Theme | Appearance |
| --- | --- |
| `catppuccin-latte` | Light |
| `catppuccin-frappe` | Dark |
| `catppuccin-macchiato` | Dark |
| `catppuccin-mocha` | Dark |

## Installation

Once this repository is pushed, install the package from GitHub:

```sh
pi install git:github.com/pi-contrib/pi-theme
```

To pin an installation, append a release tag or commit hash to the source.
Restart Pi and choose a theme in `/settings`, or set it in `~/.pi/agent/settings.json`:

```json
{
  "theme": "catppuccin-mocha"
}
```

## Credits

Adapted from [Prime Catppuccin Theme](https://github.com/andrestobelem/prime-catppuccin-theme)
for Pi's theme schema. The original palette comes from [Catppuccin](https://github.com/catppuccin/catppuccin).
See [LICENSE](LICENSE).

# hacknet-theme

[![Validate Themes](https://github.com/HacknetAOS/hacknet-theme/actions/workflows/ci.yml/badge.svg)](https://github.com/HacknetAOS/hacknet-theme/actions/workflows/ci.yml)

Color presets (`presets/*.toml`) and grid layout tokens (`layout.toml`) for HacknetOS. The `hacknet-theme` compiler (built from [`hacknet-core`](https://github.com/HacknetAOS/hacknet-core)) reads these definitions and generates runtime configurations for Quickshell, foot, GTK3/GTK4, Qt6, and Starship.

## Presets

Presets are installed to `/usr/share/hacknet/themes/`. Switch themes at runtime with `hacknetctl`:

```bash
hacknetctl theme list
hacknetctl theme set ente
```

| Preset ID | Name | Primary Accent | Description |
| :--- | :--- | :--- | :--- |
| `blue` | Hacknet Blue | `#9d7ae0` | Default near-black violet console with lavender accents |
| `ente` | Ente | `#4fb8c8` | Teal console variant |
| `hacknet` | Hacknet Classic | `#00ff00` | Classic green-on-black terminal palette |
| `hellhound` | Hellhound | `#d05548` | Crimson / red tactical console |
| `naix` | Naix | `#d09a48` | Amber console variant |
| `white` | Phosphor White | `#cfcfcf` | Monochrome high-contrast variant |

## Preset Schema

Each preset file defines top-level metadata (`id`, `name`, `description`) and four tables (`[palette]`, `[typography]`, `[effects]`, `[terminal]`):

```toml
id          = "blue"
name        = "Hacknet Blue"
description = "Hacknet default: near-black violet, lavender console."

[palette]
bg          = "#0a0812"
panel       = "#110e1c"
panel_alt   = "#171326"
fg          = "#d6d0e8"
dim         = "#7c7394"
faint       = "#3b354d"
accent      = "#9d7ae0"
accent_dim  = "#4d3878"
accent_glow = "#b99cf0"
alert       = "#e05270"
warn        = "#e0a452"
ok          = "#6bd089"
grid        = "#1c172b"
selection   = "#2b2142"
terminal_fg = "#d6d0e8"

[typography]
mono_family    = "JetBrains Mono"
display_family = "Share Tech Mono"
ui_size_px     = 13
header_size_px = 14
title_size_px  = 22

[effects]
scanlines        = true
scanline_alpha   = 0.05
grid_backdrop    = true
corner_brackets  = true
glow_strength    = 0.35
boot_typewriter  = true

[terminal]
cursor_shape = "block"
cursor_blink = true
padding_px   = 10
```

## Layout Specification

`layout.toml` defines the logical pixel grid (`1920x1080` baseline, `1280x720` minimum, and compact breakpoint `<= 1500px`) installed to `/usr/share/hacknet/layout.toml`.

# MHA iOS — Home Assistant Theme

A Home Assistant theme based on the visual language of the **MHA Widget Hub iOS theme**: native HA theme tokens plus the actual MHA iOS organic wallpaper geometry, translucent surfaces, large rounded cards, subtle borders and shadows, Apple-like typography, blue accenting, and a dedicated dark mode.

## What this is

This repository contains a **native Home Assistant theme**. It uses Home Assistant's supported theme-variable system rather than injecting MHA's web CSS into Home Assistant.

The theme intentionally stays within Home Assistant's native theme system while embedding the MHA wallpaper directly in `lovelace-background`:

- iOS-inspired light and dark palettes
- translucent card/surface colors
- 24px card geometry
- subtle glass-like borders and shadows
- the MHA iOS organic wallpaper's seven original sheet paths
- MHA-style gradients and slow sheet drift
- Apple-system font stack
- iOS-like blue accent
- semantic state colors
- dark-mode counterpart

The wallpaper is embedded as a self-contained SVG data URI, so HACS does not need to install a second `www/` asset.

Native HA themes cannot directly reproduce arbitrary `backdrop-filter`, procedural glass noise, complex reflections, or MHA's custom widget geometry. Those effects require dashboard/card CSS or custom frontend code and are outside this repository's native-theme scope.

## Installation

### HACS

Add this repository to HACS as a **Theme** custom repository, then install **MHA iOS**. HACS stores downloaded themes in Home Assistant's `themes/` directory.

Home Assistant must have theme loading enabled:

```yaml
frontend:
  themes: !include_dir_merge_named themes
```

After installation, reload themes with `frontend.reload_themes` and select **MHA iOS** from your Home Assistant user profile.

### Manual

Copy `themes/mha-ios.yaml` into your Home Assistant `themes/` directory and reload themes.

## Repository layout

```text
mha-ios-theme/
├── themes/
│   └── mha-ios.yaml
├── hacs.json
├── README.md
└── LICENSE
```

The wallpaper is intentionally embedded inside the YAML. This keeps the repository a true single-file HACS theme while preserving the MHA wallpaper without requiring a separate `/local/` asset.

## Source inspiration

The wallpaper geometry is taken from the MHA Widget Hub iOS organic wallpaper asset and its corresponding gradient/animation parameters. This repository adapts those visuals to Home Assistant's native theme system.

MHA Widget Hub remains the source project; this repository is a separate Home Assistant-native adaptation rather than a copy of MHA's application code.

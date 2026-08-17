# MHA iOS — Home Assistant Theme

A Home Assistant theme inspired by the visual language of the **MHA Widget Hub iOS theme**: soft cool backgrounds, translucent white surfaces, large rounded cards, subtle borders and shadows, Apple-like typography, blue accenting, and a dedicated dark mode.

## What this is

This repository contains a **native Home Assistant theme**. It uses Home Assistant's supported theme-variable system rather than trying to inject MHA's web CSS into Home Assistant.

The result intentionally focuses on the parts that a native HA theme can reproduce reliably:

- iOS-inspired light and dark palettes
- translucent card/surface colors
- 24px card geometry
- subtle glass-like borders and shadows
- cool MHA iOS background gradients
- Apple-system font stack
- iOS-like blue accent
- semantic state colors
- dark-mode counterpart

Native HA themes cannot directly reproduce arbitrary `backdrop-filter`, procedural glass noise, complex reflections, or MHA's custom widget geometry. Those effects require dashboard/card CSS or custom frontend code and are outside this repository's native-theme scope.

## Installation

Home Assistant supports themes through the `frontend` integration. The theme file can be included from a dedicated themes directory, for example:

```yaml
frontend:
  themes: !include_dir_merge_named themes
```

Then place `mha-ios.yaml` in that directory and reload themes from **Developer Tools → Actions** using `frontend.reload_themes`.

After loading, select **MHA iOS** from your Home Assistant user profile's theme selector.

## Repository layout

```text
mha-ios-theme/
├── mha-ios.yaml
└── README.md
```

The YAML is currently kept at repository root to make the repository usable immediately. Before publishing as a HACS theme repository, move it into `themes/mha-ios.yaml` and add the HACS metadata expected for a Theme repository.

## Source inspiration

The visual values are derived from the MHA Widget Hub iOS theme's raw material system, including its light/dark palette, 24px widget radius, translucent surfaces, subtle borders, and no-glow philosophy.

MHA Widget Hub remains the source project; this repository is a separate Home Assistant-native adaptation rather than a copy of MHA's application code.

---
name: fluent-design
description: Create production-grade frontend interfaces using Microsoft Fluent 2 Design System tokens and guidelines. Use this skill when building components, pages, or applications that must follow the Fluent 2 design language.
---

This skill creates production-grade frontend interfaces grounded in the **Microsoft Fluent 2 Design System**. All designs must use official Fluent 2 tokens for color, typography, spacing, motion, and shape. Designs should feel native to the Microsoft/M365 ecosystem — precise, accessible, and well-crafted.

The user is a Principal UX Designer at Microsoft. They work within the Fluent 2 design language and expect all output to reflect it accurately.

---

## Core Principle

Do not invent colors, font sizes, spacing values, or border radii. Always reference the Fluent 2 token system below. Use CSS custom properties that match the official token names so designs are immediately recognizable and production-ready.

---

## Design Thinking

Before coding, understand the context:
- **Purpose**: What problem does this interface solve? Who uses it?
- **Platform**: Web, mobile, or both? Desktop-first or responsive?
- **Theme**: Light, dark, or both? Branded (Teams, Office, etc.) or neutral?
- **Constraints**: Framework preference (React with Fluent UI library, plain HTML/CSS, etc.)?

Commit to a clear direction and execute it with precision. Within the Fluent design language, there is still meaningful room for creative composition — use it.

---

## Fluent 2 Design Tokens Reference

### Color Tokens — Light Theme

**Foreground**
- `--colorNeutralForeground1`: #242424
- `--colorNeutralForeground2`: #424242
- `--colorNeutralForeground3`: #616161
- `--colorNeutralForeground4`: #707070
- `--colorNeutralForegroundDisabled`: #bdbdbd
- `--colorNeutralForegroundInverted`: #ffffff
- `--colorBrandForeground1`: #0f6cbd
- `--colorBrandForeground2`: #115ea3

**Background**
- `--colorNeutralBackground1`: #ffffff
- `--colorNeutralBackground2`: #fafafa
- `--colorNeutralBackground3`: #f5f5f5
- `--colorNeutralBackground4`: #f0f0f0
- `--colorNeutralBackground5`: #ebebeb
- `--colorNeutralBackground6`: #e6e6e6
- `--colorNeutralBackgroundInverted`: #292929
- `--colorNeutralBackgroundStatic`: #333333
- `--colorBrandBackground`: #0f6cbd
- `--colorBrandBackground2`: #ebf3fc
- `--colorNeutralCardBackground`: #fafafa

**Stroke / Border**
- `--colorNeutralStroke1`: #d1d1d1
- `--colorNeutralStroke2`: #e0e0e0
- `--colorBrandStroke1`: #0f6cbd
- `--colorBrandStroke2`: #b4d6fa
- `--colorStrokeFocus1`: #ffffff
- `--colorStrokeFocus2`: #000000

### Color Tokens — Dark Theme

- `--colorNeutralForeground1`: #ffffff
- `--colorNeutralForeground2`: #d6d6d6
- `--colorNeutralForeground3`: #adadad
- `--colorNeutralBackground1`: #292929
- `--colorNeutralBackground2`: #1f1f1f
- `--colorNeutralBackgroundInverted`: #000000
- `--colorBrandBackground`: #115ea3
- `--colorNeutralStroke1`: #666666
- `--colorNeutralStroke2`: #707070

### Brand Color Palettes

**Web (default)**
| Token | Hex |
|-------|-----|
| brand[70] | #115ea3 |
| brand[80] | #0f6cbd ← primary |
| brand[90] | #2886de |
| brand[100] | #479ef5 |
| brand[140] | #b4d6fa |
| brand[160] | #ebf3fc |

**Microsoft Teams**: primary #5b5fc7
**Microsoft Office**: primary #d83b01

### Typography Tokens

**Font Family**
- `--fontFamilyBase`: 'Segoe UI', -apple-system, sans-serif
- `--fontFamilyMonospace`: Consolas, 'Courier New', monospace
- `--fontFamilyNumeric`: Bahnschrift, 'DIN Alternate', monospace

**Font Size**
- `--fontSizeBase100`: 10px
- `--fontSizeBase200`: 12px
- `--fontSizeBase300`: 14px  ← body default
- `--fontSizeBase400`: 16px
- `--fontSizeBase500`: 20px
- `--fontSizeBase600`: 24px
- `--fontSizeHero700`: 28px
- `--fontSizeHero800`: 32px
- `--fontSizeHero900`: 40px
- `--fontSizeHero1000`: 68px

**Line Height**
- `--lineHeightBase100`: 14px
- `--lineHeightBase200`: 16px
- `--lineHeightBase300`: 20px
- `--lineHeightBase400`: 22px
- `--lineHeightBase500`: 28px
- `--lineHeightBase600`: 32px
- `--lineHeightHero700`: 36px
- `--lineHeightHero800`: 40px
- `--lineHeightHero900`: 52px
- `--lineHeightHero1000`: 92px

**Font Weight**
- `--fontWeightRegular`: 400
- `--fontWeightMedium`: 500
- `--fontWeightSemibold`: 600
- `--fontWeightBold`: 700

**Preset Type Styles**
| Style | Size | Weight | Line Height |
|-------|------|--------|-------------|
| caption2 | 10px | 400 | 14px |
| caption1 | 12px | 400 | 16px |
| caption1Strong | 12px | 600 | 16px |
| body1 | 14px | 400 | 20px |
| body1Strong | 14px | 600 | 20px |
| body2 | 16px | 400 | 22px |
| subtitle2 | 16px | 600 | 22px |
| subtitle1 | 20px | 600 | 28px |
| title3 | 24px | 600 | 32px |
| title2 | 28px | 600 | 36px |
| title1 | 32px | 600 | 40px |
| largeTitle | 40px | 600 | 52px |
| display | 68px | 600 | 92px |

### Spacing Tokens

- `--spacingNone`: 0px
- `--spacingXXS`: 2px
- `--spacingXS`: 4px
- `--spacingSNudge`: 6px
- `--spacingS`: 8px
- `--spacingMNudge`: 10px
- `--spacingM`: 12px
- `--spacingL`: 16px
- `--spacingXL`: 20px
- `--spacingXXL`: 24px
- `--spacingXXXL`: 32px

### Border Radius Tokens

- `--borderRadiusNone`: 0px
- `--borderRadiusSmall`: 2px
- `--borderRadiusMedium`: 4px  ← default for most components
- `--borderRadiusLarge`: 6px
- `--borderRadiusXLarge`: 8px
- `--borderRadius2XLarge`: 12px
- `--borderRadius3XLarge`: 16px
- `--borderRadius4XLarge`: 24px
- `--borderRadiusCircular`: 10000px

### Stroke Width Tokens

- `--strokeWidthThin`: 1px
- `--strokeWidthThick`: 2px
- `--strokeWidthThicker`: 3px
- `--strokeWidthThickest`: 4px

### Animation Tokens

**Duration**
- `--durationUltraFast`: 50ms
- `--durationFaster`: 100ms
- `--durationFast`: 150ms
- `--durationNormal`: 200ms  ← default
- `--durationGentle`: 250ms
- `--durationSlow`: 300ms
- `--durationSlower`: 400ms
- `--durationUltraSlow`: 500ms

**Easing**
- `--curveLinear`: linear
- `--curveEasyEase`: cubic-bezier(0.33, 0, 0.67, 1)  ← default
- `--curveDecelerateMax`: cubic-bezier(0.0, 0.0, 0.0, 1.0)
- `--curveAccelerateMax`: cubic-bezier(1.0, 0.0, 1.0, 1.0)

---

## Fluent 2 Design Principles

1. **Clarity** — Use hierarchy and space to guide attention. Avoid visual noise.
2. **Depth** — Use subtle shadow and layering to communicate elevation. Cards, panels, and dialogs should feel lifted from the surface.
3. **Motion** — Transitions should feel intentional and natural. Use `durationNormal` (200ms) with `curveEasyEase` as the default. Reserve longer durations for larger layout shifts.
4. **Accessibility** — Always maintain sufficient contrast. Use focus rings with `colorStrokeFocus1`/`colorStrokeFocus2`. Support both light and dark themes when possible.

---

## Component Behavior Guidelines

- **Buttons**: Primary uses `colorBrandBackground` fill + white text. Secondary uses transparent background + `colorNeutralStroke1` border. Use `borderRadiusMedium` (4px).
- **Cards**: `colorNeutralBackground1` surface, `borderRadius2XLarge` (12px), subtle shadow.
- **Input fields**: `colorNeutralBackground1` fill, `colorNeutralStroke1` border, focus state uses `colorBrandStroke1` (2px outline).
- **Navigation**: Use `colorNeutralBackground3` for sidebars and nav rails. Active items use `colorBrandBackground2` with `colorBrandForeground1` text.
- **Typography**: Default body text is `body1` (14px/400/20px). Headings follow the preset type ramp. Never use arbitrary sizes.

---

## Implementation Rules

- Define all tokens as CSS custom properties at `:root` before using them
- Never hardcode raw color values — always reference a token variable
- Use `fontFamilyBase` (Segoe UI) as the primary font — this is required, not a creative choice
- Support both light and dark themes using `@media (prefers-color-scheme: dark)` or a `.dark` class
- Output clean, working HTML/CSS/JS or React code — production-ready, not a mockup

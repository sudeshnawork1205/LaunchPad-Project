# Celestial Velocity Design System

This document outlines the design tokens, colors, typography, and styling guidelines for the **LaunchPad** project. The theme is engineered to evoke the feeling of high-performance aerospace interfaces and the vastness of deep space.

---

## Brand & Style

- **Creative Direction**: *High-Tech Glassmorphism* — A fusion of deep atmospheric depths and precision-milled glass surfaces.
- **Goal**: The UI should feel cinematic yet functional, prioritizing clarity amidst complex data. High-contrast accents against a midnight canvas guide the user's eye toward critical "launch" actions, simulating the HUD of a spacecraft.

---

## 🎨 Color Palette

The color system is optimized for a dark-mode, high-fidelity experience, using luminosity and saturation to define hierarchy.

### Core Brand Colors

| Token | Role | Hex Value | Preview/Description |
| :--- | :--- | :--- | :--- |
| `primary` | Base Text & Structural Highlights | `#C3C6D7` | Muted silver-blue for main readability and primary accents. |
| `secondary` | High-energy propellant | `#EBB2FF` | Neon Purple reserved for primary calls to action and active states. |
| `tertiary` | Technical Highlight | `#2FD9F4` | Cyan-Electric Blue for data visualizations and secondary interactive elements. |
| `background` | The Infinite Void | `#101415` | Base background color for all pages. |
| `surface` | Surface Base | `#101415` | Default surface color. |
| `neutral` | Neutral Base | `#F8FAFC` | Pure off-white for high-readability body text. |

### Surface Hierarchy & Nesting

To maintain a sophisticated, clean aesthetic without cluttered borders, transition between backgrounds using "Tonal Carving":

- **Level 0 (Base)**: `background` (`#101415`)
- **Level 1 (Panels)**: `surface-container-low` (`#191C1E`)
- **Level 2 (Actionable Cards)**: `surface-container-high` (`#272A2C`)
- **Level 3 (Popups/Modals)**: `surface-container-highest` (`#323537`)

### Complete Palette Specification

```json
{
  "background": "#101415",
  "surface": "#101415",
  "surface_bright": "#363a3b",
  "surface_container": "#1d2022",
  "surface_container_low": "#191c1e",
  "surface_container_high": "#272a2c",
  "surface_container_highest": "#323537",
  "surface_container_lowest": "#0b0f10",
  "primary": "#c3c6d7",
  "primary_container": "#0a0e1a",
  "secondary": "#ebb2ff",
  "secondary_container": "#b600f8",
  "tertiary": "#2fd9f4",
  "tertiary_container": "#001115",
  "on_background": "#e0e3e5",
  "on_surface": "#e0e3e5",
  "on_primary": "#2c303d",
  "on_secondary": "#520072",
  "on_tertiary": "#00363e",
  "outline": "#909096",
  "outline_variant": "#46464c",
  "error": "#ffb4ab"
}
```

---

## ✍️ Typography

We employ a triad of typefaces to establish a technical hierarchy:
1. **Space Grotesk** (Headlines): Geometric and structural for a futuristic, engineered feel.
2. **Geist** (Body): Clean, developer-centric legibility for SaaS data and long-form content.
3. **Space Mono** (Data & Labels): Monospaced for technical readouts, coordinates, and metadata.

### Typography Scale

| Token | Font Family | Size | Weight | Line Height | Letter Spacing |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `display-xl` | Space Grotesk | `72px` | `700` (Bold) | `80px` | `-0.04em` |
| `display-xl-mobile` | Space Grotesk | `44px` | `700` (Bold) | `52px` | `-0.02em` |
| `headline-lg` | Space Grotesk | `48px` | `600` (SemiBold) | `56px` | `-0.02em` |
| `headline-md` | Space Grotesk | `32px` | `500` (Medium) | `40px` | `normal` |
| `body-lg` | Geist | `18px` | `400` (Regular) | `28px` | `normal` |
| `body-md` | Geist | `16px` | `400` (Regular) | `24px` | `normal` |
| `label-caps` | Space Mono | `12px` | `700` (Bold) | `16px` | `0.1em` |

---

## 📐 Spacing & Layout

- **Base Unit**: `8px` for consistent alignment.
- **Layout Grid**: 12-column fluid grid system on desktop, collapsing to 4-column on mobile.
- **Desktop Section Padding**: `120px` (generous vertical breathing room to allow 3D assets and glows to bleed).
- **Mobile Section Padding**: `64px`.
- **Gutter**: `24px`.
- **Container Max-Width**: `1280px`.

---

## 🎹 Elevation, Depth & Shapes

- **Backdrop Blurs**: Depth is achieved through backdrop saturation and blurs rather than drop shadows. Floating panels use `backdrop-filter: blur(16px)` and a `10-15%` opacity surface.
- **Neon Glows**: Box shadows on primary buttons and status indicators using the Secondary color with a high spread and low opacity (`20-40%`).
- **Shapes & Corner Radius**:
  - **Standard Cards / Containers**: `1.0rem` (`16px`)
  - **Buttons / Inputs**: `0.5rem` (`8px`)
  - This "medium softness" mimics precision-machined aerospace hardware.

---

## ⚙️ Component Rules

### Buttons
- **Primary**: Solid Neon Purple fill with a subtle white inner-top border (`0.5px`) to simulate a light source. Hover states trigger a purple "bloom" glow.
- **Secondary**: "Ghost" style with a `1px` border and high-blur glass background.

### Input Fields
- Dark, semi-transparent wells with `backdrop-filter: blur(12px)`.
- The bottom border is more prominent than the other three sides to create a "shelf" for text entry.
- On focus, the border glows with the Tertiary Cyan color.

### Status Indicators
- Use `Space Mono` for status labels.
- Status pips feature a pulsing animation:
  - **Online/Active**: Tertiary color (`#2FD9F4`)
  - **Alert/Critical**: Secondary color (`#EBB2FF` / `#BC13FE`)

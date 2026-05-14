---
name: Bodyfit Kissamos
colors:
  surface: '#131313'
  surface-dim: '#131313'
  surface-bright: '#3a3939'
  surface-container-lowest: '#0e0e0e'
  surface-container-low: '#1c1b1b'
  surface-container: '#201f1f'
  surface-container-high: '#2a2a2a'
  surface-container-highest: '#353534'
  on-surface: '#e5e2e1'
  on-surface-variant: '#c4c9ac'
  inverse-surface: '#e5e2e1'
  inverse-on-surface: '#313030'
  outline: '#8e9379'
  outline-variant: '#444933'
  surface-tint: '#abd600'
  primary: '#ffffff'
  on-primary: '#283500'
  primary-container: '#c3f400'
  on-primary-container: '#556d00'
  inverse-primary: '#506600'
  secondary: '#ffb59a'
  on-secondary: '#5a1b00'
  secondary-container: '#ff5e07'
  on-secondary-container: '#531900'
  tertiary: '#ffffff'
  on-tertiary: '#313030'
  tertiary-container: '#e5e2e1'
  on-tertiary-container: '#656464'
  error: '#ffb4ab'
  on-error: '#690005'
  error-container: '#93000a'
  on-error-container: '#ffdad6'
  primary-fixed: '#c3f400'
  primary-fixed-dim: '#abd600'
  on-primary-fixed: '#161e00'
  on-primary-fixed-variant: '#3c4d00'
  secondary-fixed: '#ffdbce'
  secondary-fixed-dim: '#ffb59a'
  on-secondary-fixed: '#370e00'
  on-secondary-fixed-variant: '#802a00'
  tertiary-fixed: '#e5e2e1'
  tertiary-fixed-dim: '#c8c6c5'
  on-tertiary-fixed: '#1c1b1b'
  on-tertiary-fixed-variant: '#474746'
  background: '#131313'
  on-background: '#e5e2e1'
  surface-variant: '#353534'
typography:
  headline-xl:
    fontFamily: Montserrat
    fontSize: 64px
    fontWeight: '900'
    lineHeight: '1.1'
    letterSpacing: -0.04em
  headline-lg:
    fontFamily: Montserrat
    fontSize: 40px
    fontWeight: '800'
    lineHeight: '1.2'
    letterSpacing: -0.02em
  headline-md:
    fontFamily: Montserrat
    fontSize: 24px
    fontWeight: '700'
    lineHeight: '1.3'
  body-lg:
    fontFamily: Inter
    fontSize: 18px
    fontWeight: '400'
    lineHeight: '1.6'
  body-md:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '400'
    lineHeight: '1.6'
  label-sm:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '700'
    lineHeight: '1'
    letterSpacing: 0.1em
  headline-lg-mobile:
    fontFamily: Montserrat
    fontSize: 32px
    fontWeight: '800'
    lineHeight: '1.2'
spacing:
  unit: 8px
  gutter: 24px
  margin-mobile: 16px
  margin-desktop: 48px
  container-max-width: 1280px
---

## Brand & Style

This design system embodies the "hidden gem" of old-school bodybuilding: a place where raw intensity meets professional standards. The aesthetic is rooted in **Industrial Brutalism**, prioritizing function and strength over decorative excess. It evokes the feeling of a basement iron temple—unapologetic, high-performance, and focused—while maintaining a clean, systematic structure that ensures the environment feels welcoming and premium.

The visual narrative is built on a dark mode foundation, utilizing high-contrast borders and subtle grit textures to simulate the tactile nature of cold steel and rubber flooring. This system is designed for a target audience that respects tradition but demands modern usability.

## Colors

The palette is anchored in a high-contrast, dark-first environment. 

- **The Void (Neutral):** Deep black (#0A0A0A) serves as the primary surface color, creating a sense of depth and focus.
- **The Steel (Tertiary):** Charcoal grays (#1A1A1A, #2D2D2D) are used for containers, card backgrounds, and structural elements.
- **The Kinetic (Primary):** 'Safety Yellow' (#CCFF00) is the primary action color. It is used sparingly for high-visibility triggers, progress indicators, and critical call-outs.
- **The Burn (Secondary):** 'Electric Orange' (#FF5C00) serves as a secondary accent for intensity, indicating high-effort metrics, warnings, or specialized membership tiers.
- **The Grit (Borders):** A high-contrast light gray or pure white is used for hairline borders to separate sections without losing the "raw" industrial feel.

## Typography

Typography in this design system is "industrial-strength." 

**Montserrat** is used for all headings in Bold or Black weights. It provides a geometric, assertive presence that mimics traditional gym signage and equipment branding. Letter spacing is tight for large displays to increase the feeling of density and power.

**Inter** is utilized for body text and functional labels. Its systematic, neutral character balances the aggressive nature of the headings, ensuring schedules, workout logs, and instructional content remain highly legible. Functional labels (like muscle groups or weight units) should be set in Inter Bold, Uppercase, with increased tracking to mimic stamped metal plates.

## Layout & Spacing

This design system employs a **Fixed Grid** model for desktop and a fluid single-column model for mobile.

- **Grid:** A 12-column grid is used for desktop layouts with a generous 24px gutter to maintain "breathing room" amidst the intense color palette.
- **Rhythm:** An 8px linear spacing scale dictates all margins and padding. 
- **Structure:** Content is housed in rigid blocks. Alignment should be strictly left-heavy to reinforce the functional, "no-nonsense" aesthetic.
- **Breakpoints:** 
  - Mobile: < 600px (16px margins)
  - Tablet: 600px - 1024px (24px margins)
  - Desktop: > 1024px (Fixed 1280px max-width, centered)

## Elevation & Depth

In this design system, depth is achieved through **Tonal Layers** and **Bold Borders** rather than traditional shadows.

- **Z-Axis:** Surfaces do not "float." Instead, they are stacked. Level 0 is the background (#0A0A0A). Level 1 containers use #1A1A1A.
- **Borders:** Every interactive element or distinct card must feature a 1px or 2px solid border. Use #333333 for subtle separation and the Primary Safety Yellow for active states.
- **Texture:** A subtle, low-opacity "noise" or "grit" overlay should be applied to the main background to eliminate the "flatness" of digital dark modes and evoke a weathered, physical gym environment.
- **Highlighting:** Elevation is signaled by shifting border colors rather than increasing shadow diffusion.

## Shapes

The shape language is **Sharp (0)**. 

To reinforce the industrial, rugged aesthetic, all buttons, cards, and input fields feature 90-degree corners. This evokes the architecture of power racks and weight plates. There are no circles or soft radii in the core UI components, ensuring the design feels "constructed" and architectural.

## Components

### Buttons
Primary buttons use the Safety Yellow background with black Montserrat Bold text. They feature a "thick" 2px black bottom border to simulate a physical toggle. Secondary buttons are transparent with a white 2px border.

### Cards
Cards are defined by their #1A1A1A background and 1px #333333 borders. For "Featured" content (e.g., a specific workout program), the border should switch to Safety Yellow.

### Input Fields
Inputs are dark-filled rectangles with a bottom-only 2px border in gray, which turns Safety Yellow on focus. Label text always sits above the field in uppercase Inter.

### Chips & Tags
Used for muscle groups or equipment types. These are small, rectangular blocks with a stroke-only treatment. When selected, they fill solid with the Primary color.

### Progress Bars
Heavy, thick bars. The "track" is charcoal, and the "fill" is a high-contrast Safety Yellow or Electric Orange. No rounded caps; the ends must be perfectly square.

### Special Element: The "Grit" Overlay
A global CSS noise filter (opacity 0.03) applied to the base layer to create a tactile, non-digital feel across all components.
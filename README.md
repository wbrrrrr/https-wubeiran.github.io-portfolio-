---
name: Precision & Insight
colors:
  surface: '#f9f9ff'
  surface-dim: '#d3daea'
  surface-bright: '#f9f9ff'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f0f3ff'
  surface-container: '#e7eefe'
  surface-container-high: '#e2e8f8'
  surface-container-highest: '#dce2f3'
  on-surface: '#151c27'
  on-surface-variant: '#444748'
  inverse-surface: '#2a313d'
  inverse-on-surface: '#ebf1ff'
  outline: '#747878'
  outline-variant: '#c4c7c7'
  surface-tint: '#5f5e5e'
  primary: '#000000'
  on-primary: '#ffffff'
  primary-container: '#1c1b1b'
  on-primary-container: '#858383'
  inverse-primary: '#c8c6c5'
  secondary: '#4b41e1'
  on-secondary: '#ffffff'
  secondary-container: '#645efb'
  on-secondary-container: '#fffbff'
  tertiary: '#000000'
  on-tertiary: '#ffffff'
  tertiary-container: '#191c1d'
  on-tertiary-container: '#828485'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#e5e2e1'
  primary-fixed-dim: '#c8c6c5'
  on-primary-fixed: '#1c1b1b'
  on-primary-fixed-variant: '#474646'
  secondary-fixed: '#e2dfff'
  secondary-fixed-dim: '#c3c0ff'
  on-secondary-fixed: '#0f0069'
  on-secondary-fixed-variant: '#3323cc'
  tertiary-fixed: '#e1e3e4'
  tertiary-fixed-dim: '#c5c7c8'
  on-tertiary-fixed: '#191c1d'
  on-tertiary-fixed-variant: '#454748'
  background: '#f9f9ff'
  on-background: '#151c27'
  surface-variant: '#dce2f3'
typography:
  display-lg:
    fontFamily: Manrope
    fontSize: 64px
    fontWeight: '800'
    lineHeight: '1.1'
    letterSpacing: -0.02em
  display-lg-mobile:
    fontFamily: Manrope
    fontSize: 40px
    fontWeight: '800'
    lineHeight: '1.2'
    letterSpacing: -0.02em
  headline-md:
    fontFamily: Manrope
    fontSize: 32px
    fontWeight: '700'
    lineHeight: '1.3'
    letterSpacing: -0.01em
  headline-sm:
    fontFamily: Manrope
    fontSize: 24px
    fontWeight: '600'
    lineHeight: '1.4'
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
  label-caps:
    fontFamily: JetBrains Mono
    fontSize: 12px
    fontWeight: '600'
    lineHeight: '1.0'
    letterSpacing: 0.1em
  metric-value:
    fontFamily: Manrope
    fontSize: 48px
    fontWeight: '700'
    lineHeight: '1.0'
    letterSpacing: -0.03em
rounded:
  sm: 0.125rem
  DEFAULT: 0.25rem
  md: 0.375rem
  lg: 0.5rem
  xl: 0.75rem
  full: 9999px
spacing:
  container-max: 1200px
  section-gap-lg: 160px
  section-gap-sm: 80px
  gutter: 32px
  stack-xs: 4px
  stack-sm: 8px
  stack-md: 16px
  stack-lg: 24px
---

## Brand & Style

The design system is engineered to project the persona of a high-level Product Manager who balances analytical rigor with creative intuition. The aesthetic is **Modern Minimalist** with a **Tech-Forward** edge, prioritizing clarity and functional beauty.

The brand personality is anchored in four pillars:
- **Professional:** A foundation of structured layouts and deliberate alignment.
- **Insightful:** Using information density and clear hierarchy to highlight data and strategy.
- **Precise:** Sharp execution with surgical attention to spacing and micro-interactions.
- **Creative:** Subtle uses of color and motion that reveal a deep understanding of user delight.

The visual style utilizes a high-contrast foundation—heavy on whitespace—to allow project narratives and key metrics to command attention without visual noise.

## Colors

The palette is rooted in a monochromatic base to ensure the "Product" (content) remains the focus.
- **Base (Deep Charcoal & White):** Used for primary text and structural surfaces. The pure white background provides the "breathable" canvas required for a minimalist aesthetic.
- **Accent (Electric Indigo):** Reserved exclusively for interactive elements, primary calls-to-action, and data visualization highlights. It signals energy and technological sophistication.
- **Surface (Light Gray):** Subtle fills for secondary sections and cards to create soft separation without hard lines.

## Typography

This design system uses a dual-font approach to balance authority with technical precision:
- **Manrope** is used for headlines and display text. Its geometric yet warm construction feels modern and professional.
- **Inter** provides high legibility for long-form case studies and body descriptions, maintaining a neutral, systematic feel.
- **JetBrains Mono** is introduced as a utility font for labels, categories, and technical metadata, reinforcing the "Tech-Forward" persona.

Text hierarchy is strictly maintained through weight contrast. Display text uses tight tracking to create a "locked-in" professional look.

## Layout & Spacing

The layout follows a **Fixed Grid** philosophy for desktop, transitioning to a fluid model for mobile.
- **The 12-Column Grid:** Desktop content is contained within a 1200px centered track with 32px gutters. This provides a structured framework for complex case studies.
- **Whitespace Strategy:** Sections are separated by generous vertical gaps (up to 160px) to allow the PM’s "thought process" to be digested one piece at a time.
- **Reflow Rules:** On mobile, the grid collapses to 1 column with 20px side margins. Large display headings should scale down proportionally to ensure no word-breaking.

## Elevation & Depth

Depth is conveyed through **Low-Contrast Outlines** and **Ambient Shadows** to avoid a cluttered or "heavy" feel.
- **Interactive Surfaces:** Cards and buttons use an ultra-soft shadow (Indigo-tinted, 4% opacity) that increases in intensity on hover to provide tactile feedback.
- **Structural Outlines:** Subtle 1px borders in `#E5E7EB` define boundaries for input fields and project cards, keeping the interface grounded without looking "boxy."
- **Layering:** High-priority items (like a floating navigation bar) use a backdrop-blur effect (Glassmorphism) to maintain context of the content behind them while providing clear focus.

## Shapes

The shape language is **Soft (Level 1)**, utilizing a 0.25rem (4px) base radius. This creates a crisp, architectural look that feels more "engineered" and professional than fully rounded or pill-shaped designs.

- **Standard Elements:** Buttons and small cards use the 4px radius.
- **Large Containers:** Project feature images and primary containers use 8px (`rounded-lg`) to feel substantial yet restrained.
- **Icons:** Should be stroke-based (2px weight) with slight rounding to match the UI components.

## Components

- **Project Cards:** Large-format cards with a 1px border and 24px internal padding. Images should have a subtle scale-up effect on hover. Metrics (e.g., "15% Conversion Increase") are displayed in `metric-value` style using the Electric Indigo accent.
- **Buttons:**
  - *Primary:* Solid Deep Charcoal background, white text, 4px radius. 
  - *Secondary:* Ghost style with Indigo border and text.
- **Chips / Tags:** Using the `label-caps` typography, these feature a light gray background with zero border to denote skills or categories (e.g., "STRATEGY," "ROADMAPPING").
- **Case Study Lists:** Minimalist vertical lists where each item is separated by a 1px hairline divider. Titles use `headline-sm`.
- **Input Fields:** Clean, underlined or fully outlined with 1px gray, turning Indigo on focus. No heavy fills.
- **Process Stepper:** A custom component for demonstrating "The Product Lifecycle," using thin lines and Indigo circular nodes to show project progression.

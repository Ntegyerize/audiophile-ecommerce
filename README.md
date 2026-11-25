# Audiophile - E-commerce Website

A responsive e-commerce website for an audio equipment brand, built as a Frontend Mentor portfolio project.

## Project Overview

The goal of this project is to recreate the Audiophile e-commerce experience using the supplied Figma designs and design system.

The project focuses on responsive frontend development, reusable UI components, accessibility, visual accuracy and interactive shopping functionality.

## Technologies

- HTML5
- CSS3
- JavaScript

## Design Reference

The project follows the supplied Audiophile Figma designs and design system.

The design system governs:

- Manrope typography
- Brand colors and design tokens
- Button variants and interaction states
- Form elements
- Responsive visual guidelines

Figma is used as the source of truth for layout, composition, spacing, dimensions and asset placement.

## Current Development Status

**In progress.**

### Completed milestones

- Figma design inspection and documentation of the supplied design system.
- Initial project structure and modular CSS architecture.
- Responsive header layout and divider refinements.
- Responsive homepage hero for desktop, tablet and mobile.
- Responsive hero artwork, SVG masks and fluid typography.
- Responsive product category cards for headphones, speakers and earphones.
- ZX9 Speaker featured-product section, including responsive concentric circles and fluid content positioning.
- ZX7 Speaker featured-product section with separate desktop, tablet and mobile background assets.
- YX1 Earphones section with responsive two-card desktop/tablet layouts and a vertically stacked mobile layout.
- Measurement-driven responsive testing against the supplied Figma references.

### Still in progress

- Mobile navigation interaction.
- Remaining homepage content and footer.
- Product category browsing pages.
- Product detail pages.
- Shopping cart and checkout functionality.
- Accessibility review and additional responsive testing.

## Architecture and Development Approach

The project uses a modular stylesheet structure:

- `global.css` - global styles, reset and design tokens.
- `styles/components/` - reusable interface components and homepage sections.
- `styles/pages/` - page-specific composition and layout.

Responsive implementation follows a measurement-driven process:

1. Inspect the relevant Figma frame and component layers.
2. Record actual dimensions and positions.
3. Convert parent-relative and page-relative coordinates into CSS positioning.
4. Implement desktop, tablet and mobile compositions.
5. Verify browser geometry using `getBoundingClientRect()`.
6. Inspect computed styles and visual output at reference and intermediate widths.
7. Introduce fluid CSS interpolation where the design measurements support it.

The supplied design system remains authoritative for colors, typography and component states.

## Project Structure

```text
Audiophile-Project/
├── assets/
│   ├── figma-source/
│   ├── audiophile-logo.svg
│   ├── hero-desktop.png
│   ├── hero-tablet-mobile.png
│   ├── zx7-background-desktop.svg
│   ├── zx7-background-tablet.svg
│   ├── zx7-background-mobile.svg
│   ├── yx1-image-desktop.svg
│   ├── yx1-image-tablet.svg
│   └── yx1-image-mobile.svg
├── docs/
│   ├── DESIGN_SYSTEM.md
│   └── PROJECT_LOG.md
├── scripts/
├── styles/
│   ├── components/
│   │   ├── buttons.css
│   │   ├── category-cards.css
│   │   ├── featured-zx9.css
│   │   ├── featured-zx7.css
│   │   ├── featured-yx1.css
│   │   └── header.css
│   ├── pages/
│   │   └── home.css
│   └── global.css
├── index.html
└── README.md
```

## Running Locally

Clone the repository and open `index.html` in a browser, or use the VS Code Live Server extension.

## Documentation

Development decisions, measurements and lessons learned are recorded in [`docs/PROJECT_LOG.md`](docs/PROJECT_LOG.md).

The visual specification is maintained in [`docs/DESIGN_SYSTEM.md`](docs/DESIGN_SYSTEM.md).

## Author

Developed as a frontend development portfolio project.

# Audiophile Design System

## 1. Design Reference

Source: Frontend Mentor Audiophile Figma Design System.

This document is the visual specification for the Audiophile project. All components and pages must follow these rules.

## 2. Color Palette

| Token | Hex |
|---|---|
| Primary Accent | #D87D4A |
| Primary Hover | #FBAF85 |
| Dark Surface | #101010 |
| Pure Black | #000000 |
| Light Surface | #F1F1F1 |
| Page Background | #FAFAFA |
| Pure White | #FFFFFF |
| Input Border | #CFCFCF |
| Error | #CD2C2C |

## 3. Typography

Font family: Manrope.

Available weights: 400, 500 and 700.

| Style | Size | Weight | Line height | Letter spacing |
|---|---:|---:|---:|---:|
| H1 | 56px | 700 | 58px | 2px |
| H2 | 40px | 700 | 44px | 1.5px |
| H3 | 32px | 700 | 36px | 1.15px |
| H4 | 28px | 700 | 38px | 2px |
| H5 | 24px | 700 | 33px | 1.7px |
| H6 | 18px | 700 | 24px | 1.3px |
| Overline | 14px | 400 | 19px | 10px |
| Sub Title | 13px | 700 | 25px | 1px |
| Body | 15px | 500 | 25px | 0px |

Headings and labels use uppercase text. Body text uses normal sentence case.

## 4. Buttons

All buttons use Manrope Bold, 13px, 1px letter spacing and uppercase text. Border radius is 0px.

### Button 1: Primary Solid

- Default background: #D87D4A
- Default text: #FFFFFF
- Hover background: #FBAF85
- Hover text: #FFFFFF

### Button 2: Secondary Outline

- Default background: transparent
- Border: 1px solid #000000
- Text: #000000
- Hover background: #000000
- Hover text: #FFFFFF

### Button 3: Text / Ghost Link

- Default background: transparent
- Default text: rgba(0, 0, 0, 0.5)
- Chevron: #D87D4A
- Hover text: #D87D4A

## 5. Form Elements

### Text Fields

- Background: #FFFFFF
- Border radius: 8px
- Default border: 1px solid #CFCFCF
- Focus border: 1px solid #D87D4A
- Error border: 2px solid #CD2C2C
- Labels: bold, 12px
- Error text: #CD2C2C

### Radio Selection

- Background: #FFFFFF
- Border radius: 8px
- Default border: 1px solid #CFCFCF
- Hover border: 1px solid #D87D4A
- Selected border: 1px solid #D87D4A
- Selected indicator: #D87D4A

### Number Stepper

- Background: #F1F1F1
- Border radius: 0px
- Default minus/plus opacity: 0.25
- Hover minus/plus color: #D87D4A

## 6. Implementation Rules

1. Use CSS custom properties for design tokens.
2. Do not introduce arbitrary brand colors.
3. Maintain the specified typography scale.
4. Implement all required component states.
5. Use responsive layouts for mobile, tablet and desktop.
6. Maintain visual consistency across all pages.

## 7. Responsive References

Figma homepage reference frames:

- Mobile: 375px
- Tablet: 768px
- Desktop: 1440px

These are reference viewport widths, not prescribed CSS breakpoints.

## 8. Design Authority

The written design specifications above govern colors, typography and component states.

Figma is the reference for composition, spacing, dimensions, assets and responsive layouts.

Any discrepancies must be documented and resolved explicitly rather than silently introducing new design values.
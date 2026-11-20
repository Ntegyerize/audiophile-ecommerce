# Audiophile Development Journal

## Project Overview

- **Project:** Audiophile E-commerce Website
- **Source:** Frontend Mentor
- **Technologies:** HTML5, CSS3 and JavaScript 
- **Status:** In development  
- **Start date:** 17 November 2026

---

## Development Entry 01 – Project Foundation

### Objective

Establish the project structure, inspect the Figma design and prepare the development environment.

### Work completed

- Inspected the Audiophile Figma design.
- Identified desktop, tablet and mobile homepage frames.
- Examined the supplied design system.
- Established the initial HTML document.
- Loaded the Manrope font.
- Created a modular CSS folder structure.
- Added the initial responsive header markup and styling.
- Initialized the local Git repository.
- Created the initial README and project documentation files.

### Technical decisions

**CSS architecture**

Separate global styles, component styles and page-specific styles.

**Header layout**

Use CSS Grid for the main header arrangement and Flexbox for the horizontal navigation links.

**Responsive design**

Use a desktop navigation layout and switch to a hamburger navigation layout on smaller screens, following the supplied Figma references.

**Design consistency**

Use the supplied design system as the authority for colors, typography and component states.

### Lessons learned

- Difference between Flexbox and CSS Grid.
- Why equal spacing does not necessarily produce true horizontal centering.
- How a centered maximum-width container works.
- How responsive navigation changes between desktop and mobile.
- How Git staging and whitespace checks work.

### Outstanding work

- Verify the header visually against Figma at all three reference widths.
- Implement the mobile navigation interaction.
- Complete the homepage sections.
- Implement shopping cart functionality.
- Test accessibility and responsive behavior.

### Next milestone

Finish and validate the responsive header, then implement the mobile navigation menu.

---

## Development Entry 02 – Responsive Homepage Hero and Header Refinement

**Date:** 20 November 2026  
**Milestone:** Homepage hero composition and responsive header divider completed.

### Objective

Recreate the Audiophile homepage hero across desktop, tablet and mobile reference layouts, then make the transitions between those layouts deliberate and robust at intermediate viewport widths.

### Design references used

The supplied Figma homepage references were treated as composition targets:

- Desktop: 1440px viewport; hero background is 729px high.
- Tablet: 768px viewport; hero background is 729px high.
- Mobile: 375px viewport; hero background is 600px high.

Figma remained the source of truth for composition, image placement, spacing and dimensions. The written design system remained authoritative for colors, typography and component states.

### Work completed

- Replaced the original tiny placeholder hero images with the supplied high-resolution Figma artwork.
- Implemented separate desktop, tablet and mobile artwork layers so each composition can use its corresponding SVG mask.
- Recreated the desktop artwork placement using viewport-relative geometry.
- Implemented the centered tablet artwork composition and the mobile artwork composition.
- Centered the hero content at the artwork composition breakpoint.
- Made the hero heading fluid between the mobile and desktop typography sizes using `clamp()`.
- Used a maximum-width container with side gutters so hero content can shrink when the viewport becomes narrower.
- Made the hero content's vertical top spacing fluid between the tablet and mobile reference values.
- Interpolated the tablet-to-mobile artwork dimensions, position and mask alignment while preserving the image's proportions.
- Made the hero/background height and mask height adapt between the tablet and mobile reference heights.
- Refined the header divider so it follows the content frame on desktop and tablet, while spanning the full viewport on mobile.
- Kept the navigation breakpoint separate from the hero artwork breakpoint because navigation fit and image composition are different layout concerns.

### Responsive art-direction decision

An initial attempt used fluid interpolation to move and resize the desktop artwork gradually into the tablet composition. That produced intermediate positions that did not represent a deliberate design at widths such as 900px. A crossfade was also explored, but it did not solve the underlying composition and geometry mismatch by itself.

The final approach is based on available space:

1. Preserve the right-aligned desktop artwork while the desktop composition has enough horizontal clearance.
2. At the selected 1072px hero breakpoint, switch immediately to the centered composition.
3. Use the tablet reference artwork size (approximately 768.215 × 960px) as the centered composition size from 1072px down to 768px. The image remains centered; it does not gradually migrate horizontally.
4. Below 768px, use the tested fluid tablet-to-mobile geometry so the centered artwork scales down towards the mobile reference composition.
5. Use the mobile artwork mask/composition at the mobile art-direction breakpoint.

The 1072px hero breakpoint was chosen from measured desktop clearance. At that width, the desktop artwork's left edge and the hero text container's right edge leave approximately 32px of space. The measurements were:

| Viewport | Gap between hero text and desktop artwork |
|---:|---:|
| 1100px | 43.67px |
| 1080px | 35.20px |
| 1072px | 31.81px |
| 1050px | 22.50px |
| 1024px | 11.49px |

This made 1072px a reasoned composition breakpoint rather than an arbitrary tablet label. The header/navigation breakpoint remains 1023px, and the mobile composition breakpoint remains 599px. These breakpoints serve different purposes and are not required to be identical.

### Measured responsive behavior

**Centered artwork from 1072px to 768px**

The centered tablet artwork was kept at approximately 768.215px wide and 960px high. Its horizontal position changes only to remain centered in the viewport:

| Viewport | Image left | Image width | Image height |
|---:|---:|---:|---:|
| 1072px | 151.40px | 768.21px | 960px |
| 1024px | 127.40px | 768.21px | 960px |
| 900px | 65.40px | 768.21px | 960px |
| 768px | -0.60px | 768.21px | 960px |

The image's document top was verified at approximately -37px, matching the tablet reference position. Negative `getBoundingClientRect().top` values during testing were interpreted relative to the scroll position, not as incorrect document positioning.

**Tablet-to-mobile scaling**

The artwork was measured at several widths to verify gradual scaling and positioning:

| Viewport | Image left | Image top | Image width | Image height |
|---:|---:|---:|---:|---:|
| 768px | -0.60px | -36.99px | 768.21px | 960px |
| 700px | -18.06px | -28.10px | 735.29px | 918.89px |
| 600px | -43.72px | -15.04px | 686.88px | 858.44px |
| 480px | -74.52px | 0.61px | 628.78px | 785.91px |
| 375px | -101.39px | 14.28px | 578.11px | 722.64px |

The artwork retained its approximately 4:5 aspect ratio. Mask positioning was also adjusted to follow the interpolated artwork geometry.

**Hero background height**

The background height was made fluid between the 375px mobile reference (600px high) and the 768px tablet reference (729px high). At 600px and 598px viewports, for example, the measured heights were approximately 673.85px and 673.20px respectively, avoiding the previous 129px jump at the mobile composition breakpoint.

**Hero content**

- The hero content uses a maximum width of 379px and 24px side gutters where space is limited.
- The description is constrained to a maximum width of 349px.
- The hero content switches to centered alignment at the 1072px artwork composition breakpoint.
- The heading uses `clamp()` to scale between the mobile and desktop reference sizes. Browser measurements confirmed approximately 36px at 375px, 53.42px at 717px and the 56px maximum at 960px.
- The content top spacing scales between the tablet and mobile reference values (102px and 108px).
- Text wrapping is left to normal document flow rather than positioning each text element independently.

**Header divider**

The divider follows the header content width on desktop and tablet, and spans the full viewport on mobile. The measured target widths are approximately 1110px on desktop, 689px on tablet and 100% on mobile.

### Important debugging discoveries

- `window.innerWidth` can differ slightly from the computed CSS viewport width in the browser's responsive device emulation. For example, the window could report 599px while the CSS width was 599.333px, meaning `(max-width: 599px)` correctly remained false. `getComputedStyle(document.documentElement).width` and `matchMedia()` were used to verify the actual media-query state.
- `getBoundingClientRect()` reports coordinates relative to the visible viewport. To calculate a document-relative vertical position, add `window.scrollY` to the returned `top` value.
- A `translateX(-50%)` transform offsets an element by half of its own width. Combined with `left: 50%`, it centers the element; it does not by itself resize the image.
- `clamp()` is appropriate when a property should interpolate between bounds. `min()` is useful for maximum-width containers with fixed gutters. Not every responsive property needs a fluid formula.
- A visually smooth resize is not automatically a good responsive design. Intermediate widths should have deliberate compositions, not merely be halfway between two reference designs.
- Different responsive concerns can have different breakpoints: hero art direction, navigation collapse and mobile artwork composition are separate decisions.

### Lessons learned

- Measure the actual available space before selecting a breakpoint.
- Preserve an established composition while it has sufficient room; change art direction when it no longer fits.
- Once a new composition is selected, scale within that composition rather than gradually migrating it across the page.
- Keep image proportions intact and align SVG mask geometry with the image and clipping region.
- Validate both the measured CSS geometry and the visual result at reference and intermediate widths.
- Diagnose the real cause of a visual jump before adding animation or more overrides.

### Outstanding work

- Implement and test the mobile navigation interaction.
- Continue building the remaining homepage sections.
- Test the completed hero at additional narrow and intermediate widths, including 320px, and review text contrast over the artwork.
- Perform an accessibility pass, including keyboard navigation, reduced-motion behavior and semantic structure.
- Continue with the remaining product, cart and checkout functionality.

### Next milestone

Build the homepage category/product sections while preserving the established design system and responsive composition principles.

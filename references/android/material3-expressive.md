# Material 3 and Material 3 Expressive

Read this for Android visual language, theming, product identity, or requests for expressive UI.

## 1. Use expression to improve function

Material 3 Expressive expands Material 3 through deliberate use of **color, shape, size, motion, typography, and containment**. These tools should direct attention, communicate grouping and state, shorten recognition time, and create an emotion appropriate to the product.

Expressive does not mean loud. A financial or medical product may be calm and precise; a music or fitness product may use stronger contrast, motion, and shape. Choose an emotional target from the product instead of applying the same colorful preset everywhere.

## 2. Establish emphasis before decoration

- Decide which one or two elements deserve the strongest emphasis on a screen.
- Use size and containment to make primary actions easier to locate, not to enlarge every control.
- Use shape contrast to distinguish role or state; random shape variety creates noise.
- Use color contrast to communicate hierarchy, selection, status, or action.
- Use motion to connect cause and result, direct attention, and confirm state.
- If everything is expressive, nothing is prominent.

## 3. Color system

- Build light and dark semantic color schemes around Material roles such as primary, secondary, tertiary, surface, container, error, and their `on-*` content roles.
- Use dynamic color when it supports personalization and product intent, with a designed brand fallback for devices or contexts where it is unavailable.
- Do not hardcode text colors against individual surfaces; pair semantic container and content roles.
- Use tertiary and container roles intentionally rather than creating unrelated accent colors.
- Avoid too many theme sources in one screen. Establish one dominant dynamic or brand theme and apply local content-derived color sparingly.
- Verify contrast and meaning across light, dark, dynamic, high-contrast, and manufacturer-influenced environments.

## 4. Typography

- Use Material type roles by function: display, headline, title, body, and label.
- Build hierarchy through size, weight, width, line height, and placement, not size alone.
- Variable-font axes can provide identity or motion feedback when legibility and layout stability remain intact.
- Use expressive display styles only for short, prominent content. Keep operational labels and dense body content highly legible.
- Use scalable `sp` units and allow wrapping, font scale, localization, and user-selected fonts where applicable.

## 5. Shape

- Define a coherent shape family and scale; do not assign a unique radius to every component.
- Use rounder, cut, angular, or asymmetric shapes only when they support the intended character and remain compatible with component behavior.
- Let outer containers and inner elements relate to each other; use shape to communicate grouping, hierarchy, and state.
- Reserve shape morphing for meaningful transitions or direct feedback.
- Do not turn every element into a pill or an oversized floating capsule.

## 6. Containment and surfaces

- Use a container when it defines a real group, hit area, state, or elevation relationship.
- Prefer open layout, spacing, and type hierarchy when a surface adds no meaning.
- Distinguish adjacent groups with tonal surface roles before adding strong borders and shadows.
- Use elevation to clarify overlap and temporary surfaces, not to make every card appear detached.

## 7. Motion

- Expressive motion can include responsive springs, coordinated movement, and purposeful shape morphing.
- Match motion strength to the product, action importance, and distance traveled.
- Keep state changes reversible or cancellable when the gesture is reversible.
- Preserve reduced-motion alternatives and stable frame performance.

## 8. Anti-template check

Reject a design that merely combines:

- the default Material purple palette;
- large friendly type;
- many rounded cards;
- a floating toolbar or FAB;
- playful spring motion;
- arbitrary colorful shapes.

Those are ingredients, not a concept. The final hierarchy, content treatment, and emotional tone must be specific to the product.

## Official sources

- [Material Design 3](https://m3.material.io/)
- [Material 3 in Compose](https://developer.android.com/develop/ui/compose/designsystems/material3)
- [Android themes](https://developer.android.com/design/ui/mobile/guides/styles/themes)
- [Expressive design — Google Design research](https://design.google/library/expressive-material-design-google-research)
- [Material Theme Builder and Android design kits](https://developer.android.com/design/ui/mobile)

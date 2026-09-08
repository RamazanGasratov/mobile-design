# Android design foundations

Read this for every Android design, implementation, or review task before applying more specialized Android references.

## 1. Design for Android, not for an abstract phone

- Preserve Android's system behaviors: back, home, overview, gesture navigation, notifications, sharing, permissions, text selection, keyboards, and system surfaces.
- Do not port iOS navigation, sheets, toolbar placement, Liquid Glass, or Apple-specific gestures into Android unchanged.
- Treat manufacturer differences, navigation modes, cutouts, font scale, display size, theme, and input devices as normal operating conditions.
- Prefer familiar Android and Material components for conventional interactions. Customize them through a coherent product theme before replacing their behavior.

## 2. Start from app anatomy

Android screens contain three interacting regions:

- **System bars:** status, caption, and navigation regions controlled partly by the system.
- **Navigation region:** app-level destinations and access to important actions.
- **Body:** the product's content and task-specific interactions.

Body backgrounds and scrolling content can extend behind system and navigation regions. Important text and controls must remain clear of insets, cutouts, gesture zones, hinges, and the on-screen keyboard.

## 3. Product identity and system familiarity

- Express identity through content, color roles, typography, shape, imagery, data visualization, voice, and purposeful motion.
- Do not ship the unmodified purple Material baseline or a copied Google-app appearance as the product's brand.
- Do not replace familiar Android behavior solely to appear unique.
- Define the emotional intent of the product, then choose how expressive or quiet its theme should be.
- A custom design system can extend or replace parts of Material, but it still must respect Android behavior, accessibility, adaptivity, and system integration.

## 4. Structure and hierarchy

- Make the primary task and most important content immediately identifiable.
- Use placement, scale, grouping, type, color roles, and containment to direct attention.
- Containment represents a meaningful group or interaction; do not wrap every section in a card.
- Keep controls near the content they affect and distinguish screen-level actions from item-level actions.
- Use progressive disclosure for secondary actions and detail without hiding essential workflows.
- Preserve state and task continuity through configuration changes, resizing, folding, and backgrounding.

## 5. System preferences

- Follow the user's light, dark, dynamic color, contrast, font scale, display scale, animation, and accessibility preferences where supported.
- Provide a deliberate brand fallback when dynamic color is unavailable or inappropriate.
- Never require one fixed theme for basic usability.
- Use semantic roles rather than hardcoded colors so meaning survives theme changes.

## 6. Input and feedback

- Design for touch first on phones, but support keyboard, mouse, trackpad, stylus, D-pad, Switch Access, and voice where the form factor or task makes them relevant.
- Provide immediate visual feedback on interaction and expose clear pressed, focused, selected, disabled, loading, success, and error states.
- Do not make swipe, drag, long-press, or hover the only way to perform an essential action.
- Keep controls away from system gesture regions or handle gesture conflicts through the platform APIs.

## 7. Quality baseline

Before finishing an Android design, verify:

- It works edge to edge without obscuring critical UI.
- It supports system back and predictive back where applicable.
- It adapts to the app window rather than assuming a specific device model.
- It has a coherent light, dark, dynamic, and fallback color strategy.
- It uses at least 48dp interactive targets and scalable text.
- It remains understandable with TalkBack, keyboard focus, increased text size, and animations reduced.
- Product identity comes from intentional content and theming, not arbitrary component replacement.

## Official sources

- [Android Design for mobile](https://developer.android.com/design/ui/mobile)
- [App anatomy](https://developer.android.com/design/ui/mobile/guides/layout-and-content/app-anatomy)
- [Layout basics](https://developer.android.com/design/ui/mobile/guides/layout-and-content/layout-basics)
- [Themes](https://developer.android.com/design/ui/mobile/guides/styles/themes)
- [Core app quality guidelines](https://developer.android.com/develop/adaptive-apps/quality-guidelines/core-app-quality)

---
name: mobile-design
description: Design, implement, or review distinctive mobile interfaces using platform-native patterns. Use for iOS, iPadOS, Apple-style mobile UI, Liquid Glass, mobile interaction, navigation, accessibility, responsive layouts, or requests to avoid generic AI-generated app design. Currently contains detailed Apple guidance and is structured for future Android guidance.
---

# Mobile Design

Create mobile interfaces that feel native to their platform and specific to their product. Platform conventions define behavior; the product's content, audience, and purpose define character.

## Route the task

Identify the target before making visual decisions.

- For iOS or iPadOS work, read [references/apple-platform.md](references/apple-platform.md).
- When Liquid Glass is requested, visible in a reference, or available in the target SDK, also read [references/liquid-glass.md](references/liquid-glass.md).
- When creating or substantially redesigning a screen, read [references/anti-template.md](references/anti-template.md).
- For gesture-driven UI, transitions, sheets, carousels, or motion review, read [references/motion.md](references/motion.md).
- For SwiftUI, UIKit, or a web prototype of an Apple interface, read [references/apple-implementation.md](references/apple-implementation.md).
- Android-specific guidance is intentionally not included yet. If the target is Android, preserve the shared principles here, inspect the project's existing design system, and state that the platform reference still needs to be added instead of pretending Apple conventions are Android conventions.

If no platform is stated, infer it only from strong evidence such as repository technology, supplied screenshots, or device context. Otherwise state the platform assumption explicitly or ask when choosing the wrong platform would materially change the result.

## Working method

### 1. Establish the product logic

Before styling, determine:

- the primary user and their context;
- the single most important task on this screen;
- the content that deserves the most visual area;
- primary, secondary, and destructive actions;
- navigation depth and expected return path;
- device classes, orientations, text sizes, and input methods that must work.

Do not invent a dashboard, card grid, hero section, or floating toolbar before the information architecture requires one.

### 2. Inspect before replacing

When working in an existing product, first inspect its components, tokens, navigation model, typography, icon system, platform APIs, and nearby screens. Reuse coherent foundations. Remove accidental inconsistency, but do not erase intentional brand character merely to make the result look more like a system demo.

### 3. Define a specific visual thesis

Write one internal sentence that connects the product to the visual treatment, for example: “A field recorder should feel immediate, dark, and instrument-like, with the live waveform owning the screen.” Use it to decide density, color, shape, type, and motion.

The thesis must come from the product, not from a fashionable effect. If the same screen could become a finance, fitness, or AI app by swapping the logo and accent color, it is too generic; revise its hierarchy and content expression.

### 4. Build the content layer first

Lay out real content, states, and actions before decoration. Establish hierarchy through placement, scale, grouping, typography, and progressive disclosure. Add materials, tint, shadow, and motion only when they clarify structure, interactivity, or continuity.

### 5. Apply platform behavior

Prefer standard platform containers and controls when they express the intended interaction. Match platform expectations for navigation, sheets, search, destructive actions, selection, keyboard behavior, pointer behavior, and accessibility. A native-feeling app can still be distinctive through content, composition, imagery, color, and purposeful custom interactions.

### 6. Design complete states

Include the states relevant to the task: loading, empty, populated, error, offline, disabled, selected, pressed, focused, editing, confirmation, and recovery. Avoid polished happy paths that collapse when content is long, missing, localized, or enlarged.

### 7. Validate the result

Before finishing, verify:

- The primary task is obvious without explanatory copy.
- Content dominates chrome.
- Every visual group corresponds to a real conceptual group.
- Repeated components are consistent; unique elements are intentionally unique.
- Controls remain usable with long localization and large text.
- Touch targets, contrast, labels, focus order, reduced motion, and reduced transparency are covered.
- Motion explains cause, destination, or state instead of decorating idle UI.
- The result still has product identity with effects, gradients, and mockup imagery removed.

## Non-negotiable boundaries

- Do not reproduce a screenshot mechanically when it conflicts with platform behavior or accessibility; preserve its intent and flag the adaptation.
- Do not use Liquid Glass, blur, gradients, rounded cards, pills, or floating controls as a default visual language.
- Do not apply glass to ordinary content containers merely to make them look premium.
- Do not hide core actions behind novelty gestures without a visible or conventional alternative.
- Do not hardcode a single phone size. Respect safe areas, resizing, orientation, and text expansion.
- Do not claim a CSS blur or custom shader is Apple's Liquid Glass. Call it an approximation.
- Do not invent current platform APIs. Check the installed SDK or current official documentation when implementation accuracy matters.

## Deliverable standard

For design work, explain only the few decisions that materially shape the result. For implementation work, produce working platform-appropriate code and verify it. For review work, prioritize issues by user impact and point to the violated principle, not personal taste.

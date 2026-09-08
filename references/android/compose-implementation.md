# Jetpack Compose implementation guidance

Read this when implementing Android design in Jetpack Compose. Use the project's installed Android and Compose versions as the source of truth for API availability.

## 1. Inspect the project before changing UI

- Identify the minimum and target SDK, Compose BOM or individual versions, Material 3 version, navigation stack, adaptive libraries, and supported form factors.
- Reuse the existing theme, design tokens, components, state architecture, and dependency policy.
- Do not migrate Views to Compose, replace navigation, or add a design-system dependency merely to apply this skill.
- Treat Material 3 Expressive APIs as version-dependent; verify current names, stability, and opt-ins in the installed library.

## 2. Theme through semantic roles

- Define light and dark `ColorScheme`, `Typography`, and `Shapes` at the app theme boundary.
- Use `MaterialTheme.colorScheme`, `MaterialTheme.typography`, and `MaterialTheme.shapes` inside components instead of hardcoded visual values.
- Use dynamic light and dark color schemes on supported Android versions when personalization fits the product, with an intentional fallback scheme.
- Keep content colors paired with their semantic containers; avoid guessing contrast from arbitrary hex values.
- When the installed Material 3 version exposes motion theming, select or customize its motion scheme centrally instead of scattering unrelated easings and springs.

## 3. Prefer semantic Material components

- Start with Material 3 `Scaffold`, app bars, navigation components, buttons, fields, sheets, dialogs, menus, snackbars, lists, and progress indicators.
- Customize through component parameters and theme roles before drawing replacements.
- Hoist state so reusable components receive data and events rather than owning product state invisibly.
- Keep one source of truth for selection, expansion, navigation, loading, and validation state.
- Preserve stable keys and item identity in lazy layouts.

## 4. Edge to edge and insets

- Design edge to edge and use the project's platform setup rather than adding opaque status or navigation bar backgrounds by habit.
- Consume `Scaffold` content padding or the relevant `WindowInsets` exactly where content needs protection.
- Do not apply the same inset repeatedly at nested levels.
- Protect critical controls from system bars, display cutouts, hinges, gesture regions, and the software keyboard while allowing suitable backgrounds and scrolling content behind them.
- Recalculate from the current window; do not cache dimensions from launch.

## 5. Adaptive Compose

- Use window size and posture information to choose layout behavior at runtime.
- Prefer the official adaptive navigation and canonical-layout APIs when they fit the information architecture.
- A navigation bar, rail, or drawer may change with available width, but destination meaning and state must remain stable.
- Use list-detail or supporting-pane scaffolds for genuine content relationships, not simply because the window is wide.
- Preserve state through resize, rotation, fold, multi-window, and process recreation using the appropriate state holder and saved-state boundary.

## 6. Navigation and back

- Model destinations and arguments explicitly and keep routing separate from individual visual components.
- Use AndroidX Navigation support appropriate to the project before building a custom back stack.
- Allow transient surfaces to dismiss before leaving the underlying destination.
- Integrate predictive back through supported platform or AndroidX APIs; do not intercept Back globally unless the feature has a real reason.
- Keep deep links and restored destinations able to produce a coherent back experience.

## 7. Accessibility semantics

- Prefer built-in controls and modifiers that already expose roles and actions.
- Add `contentDescription` only where visible text or existing semantics do not already name the element.
- Use semantics for role, state, value, heading, collection structure, pane changes, errors, custom actions, and focus only when they match the visible behavior.
- Merge or clear descendant semantics deliberately; careless merging can hide actions or create repetitive announcements.
- Make custom drawing interactive only after adding a real target, semantics, keyboard focus, and an alternative to complex gestures.
- Use scalable text and keep the actual hit area at least 48dp even when the icon is smaller.

## 8. Motion in Compose

- Use `animate*AsState` for a single value, `Transition` for coordinated state, `AnimatedVisibility` for appearance, `AnimatedContent` for content replacement, and `Animatable` or gesture APIs when interruption and velocity matter.
- Keep transition state derived from product state instead of triggering unrelated animations from composition side effects.
- Use stable keys and intentional content transforms so ordinary recomposition does not look like navigation.
- Retarget running animation from its current state; avoid resetting to a hardcoded start value after interruption.
- Check the system animation-scale preference and provide a meaningful reduced-motion result.

## 9. Performance and composition

- Keep composables focused and move expensive calculation, parsing, and I/O outside composition.
- Pass stable data where practical, avoid unnecessary state reads high in the tree, and derive values with `derivedStateOf` only when it prevents genuinely expensive or frequent recomposition.
- Use lazy containers for large collections and provide stable item keys.
- Avoid measuring the same content repeatedly, nesting unconstrained scroll containers, or animating large layout subtrees when a local transform communicates the change.
- Profile before adding caches or stability annotations; do not use them to conceal mutable or incorrectly modeled state.

## 10. Implementation review

- Does the implementation use semantic theme roles and standard components before custom drawing?
- Are window changes, insets, keyboard, hinges, and edge-to-edge handled at the correct layer?
- Do navigation, Back, predictive back, and transient surfaces follow Android expectations?
- Do semantics, focus, scalable text, and 48dp targets match the visible interaction?
- Are expressive APIs supported by the installed dependencies and used for product meaning rather than novelty?
- Can motion be interrupted and reduced without losing state or meaning?

## Official sources

- [Material 3 in Compose](https://developer.android.com/develop/ui/compose/designsystems/material3)
- [Compose Material 3 Adaptive](https://developer.android.com/develop/ui/compose/layouts/adaptive)
- [Accessibility in Jetpack Compose](https://developer.android.com/develop/ui/compose/accessibility)
- [Animation in Jetpack Compose](https://developer.android.com/develop/ui/compose/animation/introduction)
- [Edge-to-edge in Compose](https://developer.android.com/develop/ui/compose/system/insets)
- [Navigation with Compose](https://developer.android.com/develop/ui/compose/navigation)
- [Predictive back](https://developer.android.com/guide/navigation/custom-back/predictive-back-gesture)


# Polish an existing mobile interface

Use this reference for visual cleanup, inconsistent styling, or a mobile screen described as generic or unfinished. It complements the platform references; it does not replace their interaction, accessibility, typography, or component guidance. A request for a review produces findings, while a request to implement improvements authorizes changes within that scope.

## Inspect the experience, then choose the intervention

Start with the requested screen or component, its implementation, and the design resources it actually uses. Identify the task, the information needed to complete it, and the elements already working well. Inspect a running native screen when available; source code alone cannot establish clipping, perceived density, or contrast over changing content. If rendering is unavailable, explain the limitation and keep visual conclusions provisional. A screenshot can reveal appearance, but does not prove gesture behavior, accessibility semantics, or loading behavior.

For each actionable finding, record the location, observed problem, effect on the user, and smallest useful correction. For example: “Transaction rows mix icon widths, so names start at different positions; give the leading content a shared alignment slot.” Prefer specific evidence over labels such as “looks AI-generated.”

Choose the scope from those findings:

- **Already coherent:** say so. Do not manufacture defects or redesign the screen to demonstrate activity.
- **Local inconsistencies:** correct only the affected components, using the current product's tokens and patterns.
- **Competing hierarchy or repeated structural problems:** describe the proposed direction and the affected areas before implementing a broader revision. Keep it within the user's authorized scope; ask only when resolving an ambiguity would materially change the product, brand, or information architecture. Follow any repository approval requirements without inventing a separate approval gate.

For a broader revision, explain what people should notice first and how the treatment serves this product. For a small fix, a brief statement of the intended correction is enough. Preserve decisions already agreed with the user.

## Protect meaning while changing presentation

- Keep actions, destinations, permissions, status distinctions, and content relationships intact unless changing them is part of the request. A calmer screen must still expose the information needed to use it.
- Keep established brand assets and recognizable content. A particular hue, font, gradient, or illustration is not a defect by itself.
- Reuse semantic tokens and components. Before adjusting a shared token, inspect its consumers; use a local correction if the problem is local, and check affected screens when a shared correction is justified.
- Preserve actual product facts and data. Use representative fixtures for visual checks, clearly distinguish them from real results, and flag questionable claims instead of inventing replacements.
- Keep the work in the app's native stack. A browser reconstruction is appropriate only when a prototype is the requested deliverable; it is not evidence that the native screen works.

## Restore the reading path

Resolve content grouping and priority before tuning decorative effects. If the title, illustration, metrics, and primary action compete, decide which one serves the current task and reduce the weight of the others. A recording view may center on the live signal; a history view may center on a readable timeline. Do not add a hero, chart, or large illustration solely to create a focal point.

- Put controls near the content they affect. Keep frequent actions discoverable and reachable rather than removing them for visual simplicity.
- Use containers for a real group, interaction, or state. Remove redundant wrapping when spacing and a heading already communicate the relationship.
- Let different kinds of content have different layouts. Keep equivalent rows consistent; do not force photos, summaries, and forms into the same card shape.
- Size charts and summaries according to their role in a decision. Keep real comparisons, units, periods, and accessible descriptions; do not introduce graphs or reorder data just for visual variety.
- Tighten vague labels using the product's established vocabulary. Preserve recovery instructions, comparison context, units, and information needed to choose an action. Let copy length inform layout before fixing dimensions.

## Repair geometry without constraining content

- Align repeated leading elements, text baselines, and trailing values with layout guides or shared component structure. Avoid per-row offsets that compensate for inconsistent internals.
- Use the project's spacing scale for custom content. Where none exists, introduce a small reusable set of values that fits the platform. Do not impose a pixel grid on system controls, safe areas, font metrics, or accessibility layouts.
- Keep related content closer than unrelated sections. Diagnose an oversized gap by its purpose instead of shrinking every gap at once.
- Use consistent minimum dimensions for comparable controls, while allowing text-bearing rows and cards to grow with content and text size. Preserve platform touch targets even when the visible icon is small.
- Relate the shapes of nested custom containers to their spacing. Judge the visible result; do not override native component geometry with a universal radius formula.
- Check alignment and spacing in right-to-left layouts where supported. Use directional layout and appropriate symbol mirroring rather than assuming every leading edge is on the left.

## Control emphasis with the platform's visual system

- Keep navigation and routine controls subordinate to the task content. Place distinctive imagery, data treatment, or rich color where it helps identify or understand the product.
- Use the platform's semantic surface and content roles. Maintain selection, destructive-action, warning, success, and focus meanings; simplification must not flatten them into one accent color.
- Keep compatible Material color roles and intentional dynamic color on Android. On Apple platforms, preserve adaptive colors and appropriate native materials. A restrained design does not require replacing either with fixed gray values.
- Remove decoration when it competes with reading, masks state, or lacks a product purpose. Treat gradients, glows, texture, shadows, and colored backgrounds as contextual choices, not automatic failures.
- Preserve text and control contrast in every relevant appearance. Avoid making separators, secondary labels, or focus indicators illegible merely to make them quieter. Translucent surfaces need checks over representative content.
- Keep typographic roles consistent and scalable: system text styles and Dynamic Type on Apple platforms, appropriate Material roles and scalable text on Android. Use weight as well as size and placement when it helps hierarchy; do not enforce an arbitrary font-weight ceiling.
- Format equivalent numbers consistently with locale-aware units, currencies, and precision. Stable digit widths can help changing values and aligned columns, but must not change numerical meaning or conceal required precision.

## Make details communicate their role

- Use a coherent, platform-appropriate symbol vocabulary for controls. Match optical alignment and weight to adjacent text; retain platform-recognizable action symbols rather than importing a web icon set by default.
- Replace decorative emoji in functional controls when they create ambiguity or inconsistent rendering. Preserve emoji that are actual messages, reactions, category choices, or intentional product content.
- Keep action labels specific and short enough to scan, while allowing wrapping and localization. Sentence case is a useful default for custom labels; follow the language, brand, and native component conventions rather than imposing a universal capitalization rule.
- Remove repetitive marketing language when it obscures the task. Preserve the product's intentional tone and useful contextual messages; a greeting or enthusiastic phrase is not automatically a usability defect.
- Keep badges only when they communicate relevant state or information. Do not remove unread counts, plan restrictions, or warning indicators merely because decorative badges are common in templates.
- Keep imagery tied to actual content or a useful state, such as explaining an empty collection. Do not generate assets or add media-generation dependencies solely to finish a routine polish pass.

## Preserve responsive interaction

Evaluate motion by its trigger and purpose. Remove idle effects that repeatedly compete for attention without conveying change. Keep useful progress, live-state, press, focus, selection, and completion feedback, with accessible alternatives where needed.

Do not transfer browser-specific animation restrictions to native UI. Native springs, coordinated layout transitions, and purposeful Material motion can preserve continuity. Follow [Apple motion](motion.md) or [Android motion](android/motion.md) for interruption, velocity, reduced motion, and performance. Choose behavior by the interaction instead of forcing every transition onto one easing curve or duration.

When a surface or label changes size, verify the surrounding layout and focus behavior. Keep state understandable when animations are reduced or disabled. Changes to visual emphasis must not silently remove relevant haptic or audio feedback, or make either the only way to understand an outcome.

## Verify the improvement

Compare before and after with the same content, state, viewport, text scale, and appearance. Then exercise the variations affected by the change: long or missing content, localization, large text, light and dark appearance, and relevant loading, empty, error, selected, or disabled states. Check touch targets, accessible names and values, reading order, and reduced-motion behavior when the edited component involves them.

Revisit each initial finding. Confirm that the correction solved its stated problem and that shared components remain coherent. Use the available build and runtime checks for implementation changes; do not describe screenshot inspection as functional verification.

Report the few meaningful changes, what was checked, and any unresolved limitation. If no improvement was warranted, explain that outcome. A successful polish pass may leave most of the screen intact.

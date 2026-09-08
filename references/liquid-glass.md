# Liquid Glass — Apple guidance from 2025 onward

Read this reference whenever Liquid Glass is requested, implemented, or reviewed.

## 1. Treat it as a layer, not a theme

Liquid Glass is a dynamic material for the **functional UI layer**: navigation and important controls floating above content. It is not a universal surface treatment, card style, or background texture.

Use this order:

1. Design the content and information architecture.
2. Identify the small set of top-level controls that must remain available above the content.
3. Use system-provided Liquid Glass for those controls where possible.
4. Add custom glass only for an interaction the standard system cannot express.

If a design begins by making every rectangle translucent, restart from the content layer.

## 2. Hierarchy

- Maintain one intelligible functional layer above content.
- Do not use Liquid Glass for ordinary content backgrounds, feed cards, list rows, article panels, or decorative frames.
- The limited exception in Apple's HIG is a transient interactive element within content, such as an activated slider or toggle.
- Avoid glass stacked on glass. When a presentation replaces or covers glass controls, remove, merge, or visually recede the controls beneath it.
- Let content pass underneath floating bars when the system pattern supports it. Use system scroll-edge treatment to maintain legibility instead of adding hard dividers.

## 3. Adaptivity and accessibility

- Liquid Glass must adapt to content behind it, light and dark environments, preferred glass appearance, increased contrast, and reduced transparency.
- Do not rely on one fixed translucent fill, border, or shadow to remain legible everywhere.
- Use the regular variant by default.
- Use clear glass only over visually rich media where it remains legible and the clearer treatment has a purpose.
- Test over the brightest, darkest, busiest, and lowest-contrast real content states, not only a curated hero mockup.
- Provide an opaque or standard-material alternative when transparency or performance makes glass inappropriate.

## 4. Restraint, color, and tint

- Limit glass to important floating controls and navigation.
- Tint communicates prominence, selection, or status. Do not tint every control.
- Prefer spacing and semantic grouping over separate glass capsules around each neighboring icon.
- Move broad brand color into the content layer, where it can scroll and inform the glass naturally.
- Do not manufacture colorful gradients solely to make glass look dramatic.

## 5. Shape and harmony

- Choose rounded floating forms that fit the control, input method, container, and device geometry.
- Preserve concentric relationships between nested corners and surrounding hardware or window curves.
- Capsules suit compact controls; larger components often need rounded rectangles. Do not force every surface into the same pill.
- Nearby glass elements that belong together should share a rendering container so sampling, merging, and morphing remain coherent.

## 6. Dynamics

- Interactive glass can respond to touch or pointer input with system-provided highlight, scale, bounce, shimmer, or lensing.
- Morphing must explain a relationship: a toolbar button becoming a menu, a compact control expanding, or related controls merging and separating.
- Use system materialize and dematerialize transitions where available instead of treating glass as a plain opacity layer.
- Keep transformations interruptible and continue from the live presentation state.
- Do not add constant ambient shimmer or distortion; interactivity is the source of dynamism.

## 7. Native implementation preference

Standard navigation, bars, sheets, menus, controls, and presentations adopt the current design automatically when built with a supporting SDK. Prefer them before custom effects.

For SwiftUI custom UI on supporting SDKs:

- Apply `glassEffect(_:in:)` after other appearance-affecting modifiers.
- Add `.interactive()` only to elements that are actually interactive.
- Use `GlassEffectContainer` for multiple nearby effects to improve performance and enable coherent merging.
- Use `glassEffectID`, `glassEffectTransition`, or `glassEffectUnion` only when identity or morphing is meaningful.
- Limit simultaneously rendered custom effects; many containers or independent effects can degrade performance.

Verify the exact API and availability against the project's installed SDK and deployment target. Provide fallbacks rather than inventing compatibility.

## 8. Web and cross-platform prototypes

A web recreation can approximate the hierarchy and responsive behavior, but it is not Apple's material. Call it “glass-inspired” or “Liquid Glass-inspired.”

- Build a separate floating control layer above content.
- Use `backdrop-filter`, translucent fills, subtle edges, adaptive shadows, and restrained specular treatment as an approximation.
- Provide solid or more opaque fallbacks for unsupported blur, reduced transparency, increased contrast, and busy backgrounds.
- Avoid expensive full-screen filters and a separate backdrop blur on every item.
- Do not simulate refraction so aggressively that text or underlying content becomes distorted.

## 9. Failure patterns

Reject or revise designs with these symptoms:

- every card, row, and button uses glass;
- a blurred gradient background exists only to advertise the glass;
- multiple independent glass layers overlap without hierarchy;
- controls disappear over changing content;
- glass is placed in the content layer with no transient interactive purpose;
- all controls are capsules regardless of role;
- fixed translucent colors ignore system appearance and accessibility;
- custom glass replaces a standard component without product benefit;
- the material is visually elaborate but does not respond to interaction.

## 10. Final audit

- Can you point to one content layer and one functional layer?
- Is each glass element navigation, an important control, or a justified transient interaction?
- Would removing half the glass improve focus? If yes, remove it.
- Are contrast and hierarchy stable across real content and accessibility settings?
- Do related glass elements group or morph coherently?
- Does the interface remain recognizably this product without the material effect?

## Official sources

- [Materials — HIG, Liquid Glass guidance added and updated in 2025](https://developer.apple.com/design/human-interface-guidelines/materials)
- [Meet Liquid Glass — WWDC25](https://developer.apple.com/videos/play/wwdc2025/219/)
- [Liquid Glass technology overview](https://developer.apple.com/documentation/technologyoverviews/liquid-glass)
- [Applying Liquid Glass to custom SwiftUI views](https://developer.apple.com/documentation/SwiftUI/Applying-Liquid-Glass-to-custom-views)
- [Build a SwiftUI app with the new design — WWDC25](https://developer.apple.com/videos/play/wwdc2025/323/)
- [Build a UIKit app with the new design — WWDC25](https://developer.apple.com/videos/play/wwdc2025/284/)
- [Communicate your brand identity on iOS — WWDC26](https://developer.apple.com/videos/play/wwdc2026/251/)

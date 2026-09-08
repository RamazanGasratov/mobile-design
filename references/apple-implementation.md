# Apple implementation guidance

Use this reference when turning Apple-platform design into SwiftUI, UIKit, or a web prototype.

## 1. Before coding

- Identify the platform, minimum OS, installed SDK, UI framework, and supported device classes.
- Inspect existing design tokens, components, navigation, and compatibility helpers.
- Prefer the project's current framework. Do not migrate UIKit to SwiftUI or add a third-party animation library merely to apply this skill.
- Verify APIs against the installed SDK or current Apple documentation; availability and appearance evolve.

## 2. SwiftUI

- Prefer semantic system structures such as `NavigationStack`, `NavigationSplitView`, `TabView`, `Toolbar`, `Menu`, sheets, and standard controls.
- Let components adopt current system appearance before adding backgrounds or custom materials.
- Use semantic colors and system text styles. Support Dynamic Type and accessible labels without duplicating visible labels.
- Keep view identity stable during transitions and state ownership appropriate to the feature.
- Test compact and regular widths, iPad window resizing, portrait and landscape, keyboard, pointer, and relevant accessibility environment values.

For justified custom Liquid Glass on supporting SDKs:

```swift
Text("Record")
    .font(.headline)
    .padding(.horizontal, 18)
    .padding(.vertical, 12)
    .glassEffect(.regular.interactive())
```

- Use the default capsule only when it fits the control.
- Place related glass views in `GlassEffectContainer`.
- Give effects stable identifiers only when their morphing relationship matters.
- Apply `glassEffect` after modifiers that establish appearance.
- Use availability checks and a coherent fallback for older deployment targets. Verify the version against the project's toolchain rather than guessing it.

## 3. UIKit

- Prefer system navigation bars, tab bars, split views, search, menus, presentations, and controls.
- Remove legacy custom backgrounds and separators only after verifying resulting hierarchy and compatibility.
- Use `UIVisualEffectView` with `UIGlassEffect` for justified custom controls on supporting SDKs.
- Use `UIGlassContainerEffect` for related neighboring effects instead of independently sampling each element.
- Maintain trait, content-size-category, contrast, and reduced-transparency adaptation.
- Preserve system gestures and interactive transitions when supplying custom animators.

## 4. Web prototypes and Apple-inspired web UI

Web output should reproduce design reasoning and interaction hierarchy, not claim native material fidelity.

- Use semantic HTML and real controls before visual styling.
- Separate content and floating control layers in the DOM and stacking model.
- Use CSS custom properties for opacity, tint, edge, shadow, and fallback values.
- Gate blur with feature queries and accessibility media queries where available.
- Use Pointer Events and pointer capture for direct manipulation.
- Use `requestAnimationFrame` or a retargetable motion library for gesture-driven animation.
- Keep filters localized. A blur on every card is neither performant nor faithful to Liquid Glass hierarchy.

Example fallback structure:

```css
.floating-controls {
  background: color-mix(in srgb, Canvas 82%, transparent);
  border: 1px solid color-mix(in srgb, CanvasText 14%, transparent);
  box-shadow: 0 8px 28px rgb(0 0 0 / 0.14);
}

@supports (backdrop-filter: blur(1px)) {
  .floating-controls {
    background: color-mix(in srgb, Canvas 58%, transparent);
    backdrop-filter: blur(20px) saturate(140%);
  }
}

@media (prefers-reduced-motion: reduce) {
  .floating-controls { transition: opacity 160ms linear; }
}

@media (prefers-contrast: more) {
  .floating-controls {
    background: Canvas;
    border-color: CanvasText;
    backdrop-filter: none;
  }
}
```

Treat numerical values as local starting points. Tune against actual content and do not advertise the result as Apple's implementation.

## 5. Verification

- Build with the project's supported toolchain.
- Exercise navigation, presentation, rotation, resizing, keyboard, pointer, and gesture cancellation.
- Test light and dark appearance, large text, VoiceOver order, Increase Contrast, Reduce Transparency, and Reduce Motion.
- Profile custom glass and interactive animation on real target hardware when performance matters.
- Compare behavior and hierarchy with current platform components, not only a static screenshot.

## Official sources

- [Liquid Glass technology overview](https://developer.apple.com/documentation/technologyoverviews/liquid-glass)
- [Applying Liquid Glass to custom SwiftUI views](https://developer.apple.com/documentation/SwiftUI/Applying-Liquid-Glass-to-custom-views)
- [Build a SwiftUI app with the new design — WWDC25](https://developer.apple.com/videos/play/wwdc2025/323/)
- [Build a UIKit app with the new design — WWDC25](https://developer.apple.com/videos/play/wwdc2025/284/)
- [What's new in SwiftUI — WWDC26](https://developer.apple.com/videos/play/wwdc2026/269/)

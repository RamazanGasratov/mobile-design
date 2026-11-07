# Mobile Design

A Codex skill for designing, implementing, polishing, and reviewing distinctive platform-native mobile interfaces for Apple and Android platforms.

`mobile-design` helps an AI agent avoid two common failures: copying one platform's conventions onto another and producing generic layouts made from interchangeable cards, gradients, pills, and floating controls. It starts from the product's real content and task, then applies the appropriate platform guidance.

## What it covers

| Area | Apple platforms | Android |
| --- | --- | --- |
| Design language | Apple HIG principles and Liquid Glass | Material 3 and Material 3 Expressive |
| Navigation | iOS and iPadOS navigation and presentation | Android navigation, predictive back, and system bars |
| Layout | Safe areas, size classes, and iPad windows | Adaptive windows, tablets, foldables, and multi-pane layouts |
| Interaction | Direct manipulation and interruptible physical motion | Material motion, gesture feedback, and reduced motion |
| Accessibility | Dynamic Type and Apple accessibility settings | TalkBack, scalable content, keyboard focus, and 48dp targets |
| Implementation | SwiftUI, UIKit, and Apple-inspired web prototypes | Jetpack Compose and Compose Material 3 Adaptive |

Shared guidance keeps the result specific to the product rather than a reusable “AI app” template. Apple and Android rules stay in separate references so their behaviors and visual systems are not mixed.

## Design position

- Platform conventions define behavior; the product defines character.
- Content and hierarchy come before materials, effects, and decoration.
- Liquid Glass belongs mainly to Apple navigation and control layers, not every content container.
- Material 3 Expressive uses color, shape, size, motion, typography, and containment with purpose; expressive does not automatically mean loud.
- Native components are the starting point, not a limit on product identity.
- Accessibility, adaptivity, complete states, and reduced-motion behavior are part of the design.
- Existing screens receive changes proportional to observed problems: preserve coherent work, correct local inconsistencies, and explain broader revisions before implementing them within the requested scope.

## Polish an existing screen

The skill can inspect an existing interface, identify concrete visual problems, and improve its reading order, spacing, emphasis, labels, and feedback. It preserves product meaning, established branding, and platform behavior, including native springs, scalable typography, semantic colors, and accessibility.

```text
$mobile-design Polish this iOS screen while preserving its navigation and brand.
$mobile-design Review this Android screen's visual consistency and explain the smallest useful corrections.
```

Review requests produce findings. Implementation requests apply scoped improvements and compare equivalent states before and after, with limitations stated when native rendering or runtime checks are unavailable.

## Install

Clone the repository into the Codex skills directory:

```bash
git clone https://github.com/RamazanGasratov/mobile-design.git ~/.codex/skills/mobile-design
```

Restart or reload Codex if the skill does not appear immediately.

Invoke it explicitly:

```text
$mobile-design Design or review this mobile interface for its target platform.
```

Codex can also select the skill automatically when a request clearly concerns iOS, iPadOS, Android, Liquid Glass, Material 3 Expressive, SwiftUI, UIKit, Jetpack Compose, mobile navigation, accessibility, or adaptive layout.

## Update

Pull the newest version from GitHub:

```bash
cd ~/.codex/skills/mobile-design
git pull
```

## Repository structure

```text
mobile-design/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── anti-template.md
    ├── apple-implementation.md
    ├── apple-platform.md
    ├── liquid-glass.md
    ├── motion.md
    ├── visual-polish.md
    └── android/
        ├── accessibility.md
        ├── adaptive-layout.md
        ├── components.md
        ├── compose-implementation.md
        ├── foundations.md
        ├── material3-expressive.md
        ├── motion.md
        └── navigation.md
```

`SKILL.md` contains the shared workflow and routes the agent only to references relevant to the current platform and task. This keeps the active context focused instead of loading one long design manual.

## Sources

The guidance is structured from maintained public platform documentation, including:

- [Apple Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/)
- [Apple Developer videos](https://developer.apple.com/videos/)
- [Android Design for mobile](https://developer.android.com/design/ui/mobile)
- [Material Design 3](https://m3.material.io/)
- [Material Design 3 in Compose](https://developer.android.com/develop/ui/compose/designsystems/material3)
- [Android adaptive apps](https://developer.android.com/develop/adaptive-apps)

Individual reference files link to the specific documentation and sessions used for their recommendations.

## Contributing

Contributions are welcome. Keep additions focused and actionable:

- cite the current official platform source;
- keep Apple- and Android-specific guidance separate;
- summarize recommendations instead of copying entire documentation pages;
- explain how a recommendation changes a design or implementation decision;
- avoid universal rules based on one app, visual trend, or isolated failure.

## Independence

This is an independent project and is not affiliated with or endorsed by Apple Inc. or Google LLC.

Apple, iOS, iPadOS, SwiftUI, and Liquid Glass are trademarks or terms associated with Apple Inc. Android, Jetpack Compose, Material Design, and Material 3 are trademarks or terms associated with Google LLC.

## License

Released under the MIT License. See [LICENSE](LICENSE).

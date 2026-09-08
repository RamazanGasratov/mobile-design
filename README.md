# Mobile Design skill

An independent Codex skill for designing, implementing, and reviewing distinctive platform-native mobile interfaces.

The current release covers Apple and Android platforms. Apple guidance is based on WWDC25, the maintained Human Interface Guidelines, and WWDC26. Android guidance is based on the maintained Android Design portal, Material 3 Expressive, adaptive app guidance, and current Compose Material 3 documentation.

Apple coverage includes:

- iOS and iPadOS information architecture and interaction;
- the eight Apple design principles introduced in the 2026 HIG;
- correct, restrained use of Liquid Glass;
- product-specific brand expression without generic “AI-generated” layouts;
- direct manipulation, interruptible motion, momentum, and accessibility;
- SwiftUI, UIKit, and web prototypes of Apple-style interfaces.

Android coverage includes:

- Material 3 and Material 3 Expressive visual systems;
- Android-native components, navigation, predictive back, and edge-to-edge layout;
- adaptive layouts for phones, tablets, foldables, and resizable windows;
- accessibility and input beyond touch;
- motion principles and Jetpack Compose implementation guidance.

Platform files remain separate so the agent never substitutes Apple conventions for Android conventions.

## Install

Clone the repository into your Codex skills directory:

```bash
git clone https://github.com/RamazanGasratov/mobile-design.git ~/.codex/skills/mobile-design
```

Restart or reload Codex if the skill does not appear immediately. Invoke it explicitly with `$mobile-design`, or let Codex select it automatically for relevant mobile design tasks.

## Structure

```text
mobile-design/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── anti-template.md
    ├── apple-implementation.md
    ├── apple-platform.md
    ├── android/
    │   ├── accessibility.md
    │   ├── adaptive-layout.md
    │   ├── components.md
    │   ├── compose-implementation.md
    │   ├── foundations.md
    │   ├── material3-expressive.md
    │   ├── motion.md
    │   └── navigation.md
    ├── liquid-glass.md
    └── motion.md
```

`SKILL.md` contains the shared workflow and routes the agent to focused references only when they apply. Apple principles, Android principles, platform materials, anti-template guidance, motion, accessibility, adaptive layout, and implementation remain separate instead of loading one unstructured wall of instructions.

## Sources and independence

This is an independent project and is not affiliated with or endorsed by Apple Inc. or Google LLC. Platform guidance is summarized from public Apple and Google design and developer documentation linked from the reference files.

Apple, iOS, iPadOS, SwiftUI, and Liquid Glass are trademarks or terms associated with Apple Inc.

Android, Jetpack Compose, Material Design, and Material 3 are trademarks or terms associated with Google LLC.

## License

MIT. See [LICENSE](LICENSE).

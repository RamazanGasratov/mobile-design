# Mobile Design skill

An independent Codex skill for designing, implementing, and reviewing distinctive platform-native mobile interfaces.

The current release focuses on Apple platforms and incorporates Apple's design guidance from WWDC25, the maintained Human Interface Guidelines, and WWDC26. It covers:

- iOS and iPadOS information architecture and interaction;
- the eight Apple design principles introduced in the 2026 HIG;
- correct, restrained use of Liquid Glass;
- product-specific brand expression without generic “AI-generated” layouts;
- direct manipulation, interruptible motion, momentum, and accessibility;
- SwiftUI, UIKit, and web prototypes of Apple-style interfaces.

The skill is structured so Android guidance can be added later without mixing Apple and Android conventions.

## Install

Clone the repository into your Codex skills directory:

```bash
git clone <repository-url> ~/.codex/skills/mobile-design
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
    ├── liquid-glass.md
    └── motion.md
```

`SKILL.md` contains the shared workflow and routes the agent to focused references only when they apply. This keeps Apple principles, Liquid Glass, anti-template checks, motion, and implementation guidance separate instead of loading one unstructured wall of instructions.

## Add Android guidance

Add `references/android-platform.md` and, if necessary, `references/android-implementation.md`. Then update the routing section and frontmatter description in `SKILL.md`.

Keep shared product-specificity and accessibility guidance in `SKILL.md`. Keep Material Design and Android-specific patterns in the Android references so the agent never substitutes Apple conventions for Android conventions.

## Sources and independence

This is an independent project and is not affiliated with or endorsed by Apple Inc. Apple-platform guidance is summarized from public Apple Human Interface Guidelines, Apple Developer documentation, and WWDC sessions linked from the reference files.

Apple, iOS, iPadOS, SwiftUI, and Liquid Glass are trademarks or terms associated with Apple Inc.

## License

MIT. See [LICENSE](LICENSE).

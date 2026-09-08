# Apple platform design — 2025–2026

Use this reference for iOS and iPadOS design, implementation, and review. It prioritizes Apple's 2025 Liquid Glass system guidance and 2026 design and branding guidance.

## 1. Foundation: eight principles (Apple, 2026)

Use these as decision tools, not as a visual checklist.

1. **Purpose:** identify what people value; every feature must justify the time, attention, and trust it asks from them.
2. **Agency:** let people choose and explore without unnecessary gates; provide undo and recovery; confirm only meaningfully destructive actions.
3. **Responsibility:** act in people's interests, request private data in context, explain why it is needed, and anticipate harmful outcomes.
4. **Familiarity:** preserve known meanings, behavior, placement, and metaphors so people can predict results.
5. **Flexibility:** adapt to different people, abilities, devices, sizes, orientations, and input methods; support personalization when one arrangement cannot fit everyone.
6. **Simplicity:** remove friction rather than merely hiding functionality. Use clear hierarchy, plain language, few steps, and enough context for informed decisions.
7. **Craft:** treat typography, alignment, performance, responsiveness, rotation, accessibility, and every state as part of perceived quality; iterate as platforms evolve.
8. **Delight:** choose an intended feeling and earn it through the other seven principles. Do not add confetti or ornamental motion as a substitute.

When principles conflict, explain the tradeoff in terms of the person and task. Apple does not present them as a formula with one universal answer.

## 2. Current system model (Apple, 2025–2026)

Think of the app as two distinct layers:

- **UI layer:** global navigation and actions, commonly expressed by native tab bars, toolbars, search, menus, and presentations.
- **Content layer:** the product's features, information, media, words, data visualizations, and the best place for brand expression.

Keep the UI layer familiar and place product personality primarily in content. A native tab bar does not make an app generic; generic content, hierarchy, and voice do.

## 3. Hierarchy, harmony, consistency (Apple, 2025)

- **Hierarchy:** content is primary; navigation and controls form a distinct functional layer above it.
- **Harmony:** UI geometry relates to device geometry, window geometry, content, and input method. Use concentric rounded relationships rather than arbitrary radii.
- **Consistency:** structure and familiar actions carry across devices while layouts adapt to each context.

Express hierarchy through layout, grouping, spacing, type, and prominence before adding backgrounds, dividers, borders, or effects.

## 4. Native foundation, bespoke content (Apple, 2026)

- Use standard components for conventional tasks; people already know their behavior, accessibility, and placement.
- Build custom components where they meaningfully improve a product-specific task or make unique content easier to understand.
- Do not rebuild utilitarian controls merely for branding; custom versions age quickly and add maintenance without strengthening identity.
- A custom component should still respect platform metrics, placement, interaction, presentation, and accessibility.
- Keep logos restrained. People already know which app is open; persistent large logos often displace more useful content.

## 5. Brand expression (Apple, 2026)

Express brand through the content layer:

- real imagery, video, illustration, data visualization, domain-specific views, and words;
- deliberate voice and tone connected to how the product should feel;
- transitions that connect content and clarify interaction;
- meaningful color, flexible typography, and recognizable iconography.

Do not force visual identity to be identical across web, Android, and iOS. Preserve the brand's meaning while adapting behavior and conventions to iOS.

### Color

- Move large brand-color moments into scrollable content rather than solid top and bottom bars.
- Use accent or tint color to communicate action, selection, status, and feedback.
- Exercise restraint so color retains meaning.
- Support Dark Mode and other appearance preferences with a deliberately tested palette.

### Typography

- Prefer system text styles so Dynamic Type, legibility, and platform metrics work automatically.
- Custom fonts are valid brand tools, but must scale, wrap, and remain legible at accessibility sizes.
- Use size, weight, width, placement, and spacing together; a giant marketing heading is rarely appropriate in a repeated utility workflow.
- Keep critical labels, totals, warnings, and recovery actions visible without truncation.

### Iconography

- Use SF Symbols for familiar actions when they fit. Custom iconography is welcome when it is recognizable, cohesive, clear at small sizes, and respects platform meanings.
- Preserve conventional symbols for actions whose icons differ by platform, such as sharing.
- Label unfamiliar icons; decoration does not excuse ambiguity.

## 6. Structure and navigation

- Start with the content people came for, then add only the navigation and controls needed to act on it.
- Choose navigation from the information architecture, not from visual preference.
- Use tabs for a small set of frequently switched peer destinations; do not put task actions in the navigation model.
- Use hierarchical navigation for drill-down content and preserve system back behavior and gestures.
- Make search easy to find when discovery is central, but do not add a decorative search field to every home screen.
- Use modals for focused, self-contained tasks. Avoid deep stacks of presentations.
- Anchor menus, popovers, sheets, and transitions to the control or content that caused them when the platform provides that relationship.
- Keep a clear way back or out and preserve task state across resize, rotation, and related device contexts.

## 7. Layout and adaptation

- Let important content extend edge to edge where appropriate while keeping interactive content inside safe areas and readable margins.
- Keep touch targets at least 44 by 44 points even when the visible glyph is smaller.
- Align controls with the content they modify; proximity should reveal scope.
- Accommodate current system control sizes instead of forcing legacy fixed heights around them.
- iPhone favors a focused vertical path and reachable controls.
- iPad must work as a resizable app, not merely a large iPhone. Use additional width for persistent context, sidebars, inspectors, or parallel content only when it improves the task.
- Support portrait, landscape, narrow and wide iPad windows, keyboard, pointer, and touch when relevant.
- Preserve the product's anatomy across devices: the same information model and action meanings, reorganized for available space.

## 8. Writing and naming (Apple, 2026)

Names for tabs, menus, settings, and features should:

- **belong:** fit the product and sit coherently beside related names;
- **set correct expectations:** help people predict what they will find or what an action will do;
- **work everywhere:** remain usable across languages, markets, devices, and contexts.

Prefer specific nouns for destinations and direct verbs for actions. Test names in the actual interface, not in isolation.

## 9. Feedback and accessibility

- Show press feedback immediately, progress for non-immediate work, and completion when the outcome would otherwise be invisible.
- Make destructive actions distinguishable and recoverable where possible.
- Provide accessible labels and values, logical focus order, sufficient contrast, and alternatives to color-only meaning.
- Support Dynamic Type, VoiceOver, Switch Control, Reduce Motion, Reduce Transparency, and Increase Contrast as relevant.
- Haptics and sound should correspond to a meaningful event, synchronize with the visual response, and respect system settings.

## 10. Review checklist

- What is the UI layer and what is the content layer?
- Does content receive more space and attention than chrome?
- Is brand identity expressed through the product's content rather than redesigned utility controls?
- Does each custom control solve a product-specific need better than the standard one?
- Can people predict where an action leads and how to recover or return?
- Does the screen remain coherent with glass and color removed?
- Does it work at large text sizes, in Dark Mode, and in a narrow iPad window?
- Are names specific, expectation-setting, and localization-ready?

## Official sources

### 2026

- [Principles of great design — WWDC26](https://developer.apple.com/videos/play/wwdc2026/250/)
- [Design principles — Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/design-principles)
- [Communicate your brand identity on iOS — WWDC26](https://developer.apple.com/videos/play/wwdc2026/251/)
- [Craft clear names for features and labels — WWDC26](https://developer.apple.com/videos/play/wwdc2026/290/)
- [What's new in Design — WWDC26 guide](https://developer.apple.com/wwdc26/guides/design/)

### 2025 and maintained HIG

- [Get to know the new design system — WWDC25](https://developer.apple.com/videos/play/wwdc2025/356/)
- [Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/)
- [Designing for iOS](https://developer.apple.com/design/human-interface-guidelines/designing-for-ios/)
- [Layout](https://developer.apple.com/design/human-interface-guidelines/layout)
- [Typography](https://developer.apple.com/design/human-interface-guidelines/typography)

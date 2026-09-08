# Android accessibility

Read this for accessibility work and whenever designing custom controls, dense interfaces, data visualization, media, forms, or gesture-heavy interactions.

## 1. Accessibility is part of the interaction model

- Define what each element is, what it says, what state it has, and what action it performs before styling it.
- Preserve the same task and information for TalkBack, Switch Access, Voice Access, keyboard, mouse, magnification, and large-text users.
- Use standard Material and Android controls where possible because they already expose familiar roles, actions, states, and focus behavior.
- A custom control must provide the semantics and interaction behavior of the native role it replaces.

## 2. Touch and input targets

- Keep interactive targets at least 48dp by 48dp, including icon-only controls.
- The visible glyph may be smaller than the target; expand the interactive area without creating overlapping targets.
- Leave enough separation to prevent accidental activation, especially for destructive or frequently repeated actions.
- Do not make drag, swipe, long-press, multi-touch, hover, or precise timing the only path to an essential action.
- Provide keyboard focus, activation, and logical traversal for interfaces used on tablets, foldables, ChromeOS, desktop windows, TVs, or connected keyboards.

## 3. Semantics and labels

- Give icon-only controls concise, action-oriented accessible labels. Do not repeat nearby visible text unnecessarily.
- Exclude purely decorative imagery from the accessibility tree.
- Expose role, selected or checked state, expanded state, value, errors, and available actions when they affect understanding.
- Group children when they form one understandable control; keep them separate when users need to inspect or operate them independently.
- Make headings, lists, collections, dialogs, panes, and live updates identifiable through platform semantics.
- Keep announcements brief and reserved for meaningful changes; constant announcements make the interface unusable.

## 4. Reading and focus order

- Make visual, reading, keyboard, and TalkBack order follow the same logical task sequence.
- Do not rely on absolute coordinates or drawing order when an adaptive layout changes pane position.
- Move focus deliberately when opening or closing a dialog, sheet, or new pane, then return it to a sensible origin.
- Keep focus visible and never use color alone to indicate focus, selection, validation, or status.

## 5. Text and scaling

- Use scalable text units and allow the user's font scale.
- Let labels wrap or reflow; do not clip, overlap, or replace important text with unexplained icons when text grows.
- Avoid fixed-height text containers unless their content is strictly controlled and remains readable at supported scales.
- Keep line length, spacing, and hierarchy readable in both compact and expanded layouts.
- Use plain, specific labels and error messages that explain how to recover.

## 6. Color, contrast, and non-color cues

- Meet at least 4.5:1 contrast for normal text and 3:1 for large text against its background.
- Provide at least 3:1 contrast for essential graphical objects, component boundaries, and focus indicators where contrast is required to identify them.
- Pair color with text, iconography, shape, pattern, or position for errors, status, charts, and selection.
- Check light, dark, dynamic color, high-contrast preferences, disabled states, imagery, and translucent surfaces independently.
- Do not lower opacity until important content or controls become difficult to identify.

## 7. Motion, time, and media

- Follow the system preference for reduced or removed animation.
- Replace large spatial movement, flashing, parallax, or repeated decorative motion with a quieter state change while preserving meaning.
- Avoid flashes that can trigger photosensitive reactions.
- Do not require rapid responses; allow users to extend or disable nonessential time limits.
- Provide captions or transcripts for meaningful audio and spoken content, and text alternatives for informative imagery.

## 8. Errors and destructive actions

- Associate an error with the relevant field or control and explain the correction in text.
- Keep entered data when validation fails.
- Distinguish destructive actions by wording and hierarchy, not red color alone.
- Offer undo or confirmation when the cost of accidental activation is high and recovery is possible.

## 9. Accessibility review

- Can the task be completed without sight, color perception, precise touch, complex gestures, or animation?
- Are all targets at least 48dp and separated clearly?
- Do semantic role, label, state, value, and actions match what is visible?
- Does focus follow the task across resizing, panes, and transient surfaces?
- Does content survive font scaling, localization, dark theme, dynamic color, and increased contrast?

## Official sources

- [Android accessibility design guidance](https://developer.android.com/design/ui/mobile/guides/foundations/accessibility)
- [Build accessible apps](https://developer.android.com/guide/topics/ui/accessibility/apps)
- [Accessibility in Jetpack Compose](https://developer.android.com/develop/ui/compose/accessibility)
- [Core app quality guidelines](https://developer.android.com/develop/adaptive-apps/quality-guidelines/core-app-quality)


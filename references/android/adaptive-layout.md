# Android adaptive layout

Read this for tablets, foldables, landscape, multi-window, desktop windowing, or any interface expected to resize.

## 1. Adapt to the window

- Base layout decisions on the current app window size, available space, posture, and input capabilities — not a hardcoded device model or physical screen diagonal.
- Expect the window to change at runtime through rotation, split screen, desktop windowing, folding, or unfolding.
- Do not lock orientation, aspect ratio, or resizability to avoid layout work.
- Preserve content position, entered text, selection, media state, and task progress through configuration changes.

## 2. Use space to improve the task

- Do not stretch a phone column and enlarge whitespace across a tablet.
- Add useful context, persistent tools, side-by-side relationships, or more efficient navigation only when they improve the workflow.
- Keep line lengths readable and controls reachable; expanded width does not require every element to expand.
- Reposition dialogs, menus, toolbars, and primary actions for the active window and posture.

## 3. Canonical layouts

Choose from the content relationship:

- **List-detail:** a collection and its selected detail; stack on compact windows and show side by side when space allows.
- **Feed:** varied or repeated content arranged to use width and hierarchy effectively; change columns and item emphasis without losing reading order.
- **Supporting pane:** primary content with contextual tools, settings, metadata, or secondary content that supports the main task.

Canonical layouts are starting structures, not visual templates. Product content still determines density, emphasis, and brand treatment.

## 4. Adaptive navigation

- Use bottom navigation when compact width and reachability make it appropriate.
- Move to a rail or drawer when additional width makes persistent leading navigation clearer.
- Preserve destination meaning, order, labels, state, and back-stack expectations when navigation changes form.
- Avoid displaying both compact and expanded navigation simultaneously.

## 5. Foldables and postures

- Treat hinges, folds, cutouts, and occluding regions as layout boundaries or gutters when content could be obscured.
- Do not place critical text or controls across a hinge.
- Use tabletop, book, or cover postures only when they offer a meaningful product-specific experience.
- A foldable can change between compact, medium, and expanded conditions instantly; keep transitions and state continuous.

## 6. Edge to edge and insets

- Draw appropriate backgrounds and scrolling content behind system bars.
- Inset critical controls, text, and gestures away from system bars, cutouts, hinges, and navigation gesture regions.
- Apply protection per pane when adjacent panes have different backgrounds; do not stack multiple scrims or gradient protections.
- Account for the on-screen keyboard without permanently reserving empty space.

## 7. Input beyond touch

- Provide visible focus, logical traversal, keyboard activation, hover where useful, right-click or context menus, scroll-wheel behavior, and shortcuts for frequent desktop-style actions.
- Keep targets usable for touch even when a pointer is available.
- Ensure custom-drawn interactive elements are focusable and expose semantics.

## 8. Adaptive review

- Does the UI respond to the current window instead of identifying “phone” or “tablet” once?
- Does added space expose useful relationships instead of empty margins?
- Is state preserved across rotation, resize, fold, and multi-window changes?
- Are navigation and presentations appropriate at compact, medium, and expanded sizes?
- Are hinges, cutouts, system bars, keyboard, and gesture insets handled?
- Can keyboard, mouse, trackpad, stylus, and touch users complete relevant workflows?

## Official sources

- [Adaptive Apps](https://developer.android.com/develop/adaptive-apps)
- [Canonical layouts](https://developer.android.com/develop/ui/views/layout/canonical-layouts)
- [Adaptive do's and don'ts](https://developer.android.com/develop/adaptive-apps/guides/adaptive-dos-and-donts)
- [Postures and orientation](https://developer.android.com/design/ui/mobile/guides/layout-and-content/postures-and-orientation)
- [Adaptive app quality guidelines](https://developer.android.com/guide/topics/large-screens/tier-2-overview)

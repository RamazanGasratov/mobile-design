# Android navigation

Read this for Android information architecture, destination navigation, app bars, system bars, deep links, or back behavior.

## 1. Separate destinations from actions

- Primary navigation moves between peer destinations that represent the app's main areas.
- Buttons, FABs, toolbars, tabs within content, and menus perform actions or change local context; do not place them in destination navigation.
- Keep destination names, order, and meaning stable across window sizes even when the navigation component changes.
- Preserve destination state when users switch between top-level areas unless the product explicitly requires a reset.
- Keep primary navigation present on parent destinations; on deeper child destinations, prioritize clear Up and Back behavior over repeating every top-level control.
- Avoid lateral slide motion between peer primary destinations because it implies a parent-child direction that does not exist.

## 2. Choose the navigation structure from the product

- Keep the primary hierarchy shallow enough that users can predict where content lives.
- Use a navigation bar for three to five primary destinations at the same hierarchy level in compact windows.
- Use a navigation rail when additional width supports persistent leading navigation.
- Use a drawer for a larger hierarchy or destinations that do not all deserve equal persistent emphasis.
- Use tabs for sibling views inside one destination, not as a replacement for the app's primary navigation.
- Do not add a hamburger menu, bottom bar, rail, and tabs to the same level of hierarchy.

## 3. Back and up are different

- **System Back** returns through the user's chronological history and dismisses the current transient surface when appropriate.
- **Up** moves to the logical parent in the app hierarchy and is represented by the app bar navigation action when needed.
- Do not override Back to behave like Home or Up merely to simplify routing.
- Keep platform back gestures available; avoid horizontal gestures that compete with the system edge unless the interaction is essential and the conflict is handled deliberately.
- A deep link must build a coherent destination and back experience rather than exposing an isolated screen with nowhere sensible to go.

## 4. Predictive back

- Support predictive back so the user can preview the destination or dismissal before committing.
- Let the visual preview reflect the actual result: previous destination, home, or closing a modal surface.
- Preserve gesture progress, cancellation, and completion rather than replacing the interaction with a fixed canned animation.
- Use platform and Navigation APIs before implementing custom back animation.
- Keep unsaved-work handling explicit. Do not surprise users with a destructive exit after the preview.

## 5. App bars and contextual navigation

- Use the top app bar to communicate the current screen, provide Up when necessary, and expose only high-value screen-level actions.
- Keep item actions near their items and selection-mode actions in a contextual app bar or equivalent contextual surface.
- Collapse large app bars only when the transformation preserves orientation and content priority.
- Search may be an app-bar action, an expanded search surface, or a destination depending on its importance and scope.

## 6. Modal and transient destinations

- Menus, dialogs, sheets, and other temporary surfaces should dismiss before Back leaves their underlying destination.
- Use a dialog for a short decision, a sheet for focused supplemental content or actions, and a full destination for durable or multi-step work.
- Preserve the user's context when a modal closes.
- Do not stack multiple modal surfaces when a single destination or progressive disclosure would be clearer.

## 7. System bars and edge-to-edge navigation

- Treat status and navigation bars as system-owned regions whose appearance responds to the content behind them.
- Allow appropriate backgrounds and scrolling content to extend edge to edge, then keep critical content inside the relevant insets.
- Maintain icon contrast without placing unnecessary opaque bars behind system UI.
- Keep touch controls and custom gestures clear of gesture-navigation zones.
- On multi-pane layouts, protect each pane according to its own background instead of applying one heavy scrim across the whole window.

## 8. Navigation review

- Can every navigation element be classified as a destination, local view switch, or action?
- Does Back follow user history while Up follows hierarchy?
- Does predictive back preview the real outcome and remain cancellable?
- Do compact and expanded layouts preserve the same destination model?
- Are deep links, transient surfaces, system bars, and gesture regions handled coherently?

## Official sources

- [Layouts and navigation patterns](https://developer.android.com/design/ui/mobile/guides/layout-and-content/layout-and-nav-patterns)
- [Translate designs to Android](https://developer.android.com/design/ui/mobile/guides/foundations/translate-designs)
- [Predictive back design](https://developer.android.com/design/ui/mobile/guides/patterns/predictive-back)
- [System bars](https://developer.android.com/design/ui/mobile/guides/foundations/system-bars)
- [Edge-to-edge design](https://developer.android.com/design/ui/mobile/guides/layout-and-content/edge-to-edge)
- [Material 3 navigation components](https://m3.material.io/components/navigation-bar/overview)

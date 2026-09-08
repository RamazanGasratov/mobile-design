# Android and Material components

Read this when selecting, customizing, implementing, or reviewing Android controls and surfaces.

## 1. Choose by role, not appearance

Start from the interaction and semantic role, then select the closest Material 3 component. Preserve its expected states, semantics, touch behavior, theming, and adaptive behavior before customizing visuals.

Create a custom component only when the product has a repeated interaction or content form that standard components cannot express well. A custom component is responsible for focus, keyboard, TalkBack, state, touch target, theming, motion, and disabled behavior.

## 2. Navigation components

- Use a navigation bar for a small number of primary peer destinations in compact windows.
- Use a navigation rail or drawer when the window and information architecture need more persistent navigation.
- Switch navigation form based on window size and available space, not device name.
- Keep task actions out of destination navigation.
- Show labels when icons are not universally understood. Preserve selection state and destination state.

## 3. App bars and toolbars

- Use a top app bar for screen identity, navigation, and a small number of screen-level actions.
- Move infrequent actions into an overflow menu instead of shrinking targets or filling the bar with icons.
- Use bottom app bars or floating toolbars only when their actions benefit from reachability and remain distinct from destination navigation.
- Collapse or transform bars on scroll only when it increases content focus without hiding essential context.

## 4. Buttons and primary actions

- Use one dominant action treatment within a local context.
- Choose filled, tonal, elevated, outlined, or text emphasis from action priority and surface context.
- Use a FAB only for a high-value, frequent action strongly associated with the current screen or top-level workflow.
- Do not add a FAB because the layout feels empty.
- Prefer a text label when an icon alone is ambiguous. Keep the full interactive target at least 48dp.

## 5. Selection and input

- Use checkboxes for independent multiple selection, radio buttons for one choice from a visible group, switches for immediate binary settings, and sliders for values along a range.
- Use chips for compact actions, suggestions, filters, or user-entered entities according to the component's role; do not use chips as generic small buttons.
- Use text fields with persistent or recoverable labels, clear error association, correct keyboard type, and visible focus.
- Do not use placeholder text as the only field label.

## 6. Lists, cards, and content containers

- Prefer lists or open layouts for homogeneous content; use cards when items need clear containment, separate actions, mixed media, or an elevation relationship.
- Avoid nested cards and card-per-section layouts.
- Make the whole row or card clickable only when it has one clear destination. Separate multiple actions with explicit targets and semantics.
- Preserve stable item identity, readable scanning order, and state during updates.

## 7. Sheets, dialogs, menus, and snackbars

- Use menus for compact contextual choices, sheets for focused supplemental content or actions, and dialogs for decisions requiring interruption.
- Avoid dialogs for passive information or long multi-step tasks.
- Keep destructive actions explicit and visually distinct; provide undo when recovery is practical.
- Use snackbars for brief, nonblocking feedback with at most one useful action.
- Anchor contextual surfaces to their cause and preserve system back dismissal.

## 8. Progress and empty states

- Use determinate progress when progress is measurable; use indeterminate progress only when it is not.
- Keep loading indicators close to the content or action they represent.
- Empty states should explain the state and offer the next relevant action, not fill space with generic illustration and marketing copy.
- Preserve layout stability where possible when content replaces loading UI.

## 9. Component review

- Is this the correct semantic component for the interaction?
- Is its visual emphasis proportional to action priority?
- Does it expose pressed, focused, selected, disabled, loading, error, and accessibility states as relevant?
- Does it work with dynamic color, dark theme, font scaling, keyboard, TalkBack, and 48dp targets?
- Would standard Material behavior be clearer than the customization?

## Official sources

- [Material Components overview](https://developer.android.com/design/ui/mobile/guides/components/material-overview)
- [Material Design 3 components](https://m3.material.io/components)
- [Android Design for mobile](https://developer.android.com/design/ui/mobile)
- [Material 3 in Compose](https://developer.android.com/develop/ui/compose/designsystems/material3)

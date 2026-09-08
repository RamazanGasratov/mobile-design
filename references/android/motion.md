# Android motion

Read this for Android transitions, gestures, state changes, loading feedback, or Material 3 Expressive motion.

## 1. Give motion a job

Use motion to:

- connect an action with its result;
- preserve spatial and object continuity;
- show where content came from or went;
- direct attention to a meaningful change;
- communicate hierarchy, state, progress, or interruption;
- add product character after clarity is secured.

Remove motion that only delays the task, repeats without new information, or makes every element compete for attention.

## 2. Match expression to context

- Use stronger motion for high-value, positive, or identity-defining moments.
- Use restrained motion for dense tools, frequent operations, serious decisions, errors, and safety-critical workflows.
- Coordinate color, shape, typography, containment, and motion around the same emotional intent.
- Expressive motion can feel calm, precise, energetic, playful, or confident; it does not always mean bouncy.
- Keep recurring interactions faster and quieter than first-use or milestone moments.

## 3. Preserve continuity

- When an item opens into detail, let position, scale, shape, or shared content reveal their relationship.
- When navigation moves between unrelated destinations, avoid implying a false physical relationship.
- Anchor menus, sheets, and contextual controls to the element or edge that caused them.
- Keep stable elements stable. Do not animate the entire screen when only one state changed.
- Prefer coordinated transformations over unrelated fade-and-slide presets applied to every component.

## 4. Gesture-driven motion

- Couple visual progress directly to drag or back-gesture progress.
- Account for velocity as well as distance when deciding whether a gesture completes.
- Allow interruption, reversal, and cancellation without jumping to a stale animation state.
- When released, continue from the current position and velocity toward the new target.
- Provide an obvious non-gesture alternative for essential actions.
- Avoid competing with Android's back and home gesture regions.

## 5. Timing and easing

- Choose timing from distance, scale, complexity, and frequency rather than one global duration.
- Use deceleration when an element enters or responds to input, acceleration when it exits, and smooth symmetric changes for reversible state transitions when appropriate.
- Use spring behavior when physical continuity and interruption matter; tune it to settle decisively without gratuitous oscillation.
- Stagger only when order helps users understand hierarchy. Decorative cascades slow scanning.
- Avoid hardcoding a single easing curve across navigation, micro-feedback, and large container transformations.

## 6. Material 3 Expressive motion

- Start from the current Material motion scheme when the library and product support it, then tune only where product meaning requires a difference.
- Use expressive motion to emphasize the selected destination, primary action, important state transition, or direct manipulation—not every surface.
- Shape morphing should reveal continuity or state, not display technical novelty.
- Component motion and custom transitions should feel like one system with consistent energy and settling behavior.
- Verify experimental or newly introduced expressive APIs against the installed Material 3 version before naming them in code.

## 7. Reduced motion and accessibility

- Respect the platform animation-scale and accessibility preferences.
- Keep the state change immediate and understandable when large movement is removed.
- Substitute opacity, color, or a short local transition only when it does not create another accessibility problem.
- Avoid flashing, large parallax, auto-moving backgrounds, and never-ending decorative animation.
- Do not use motion as the only signal for completion, failure, selection, or hierarchy.

## 8. Performance and stability

- Animate transforms, clipping, color, and other properties with an understood rendering cost.
- Avoid repeated layout work, unnecessary blur, large offscreen layers, and simultaneous animations outside the user's focus.
- Keep lazy-list item identity stable so updates do not animate as unrelated removals and insertions.
- Degrade decorative effects before dropping interaction frames.
- Motion quality includes correct cancellation, lifecycle handling, and state restoration—not only smooth playback.

## 9. Motion review

- What information or relationship does each animation communicate?
- Does the motion begin from the user's action or the changed object?
- Can interactive motion be interrupted, reversed, or cancelled cleanly?
- Is the expressive energy appropriate to the product and frequency of use?
- Is the result understandable with animation reduced or removed?
- Do custom transitions agree with Material components and predictive back?

## Official sources

- [Material 3 motion](https://m3.material.io/styles/motion/overview)
- [Material 3 Expressive in Compose](https://developer.android.com/develop/ui/compose/designsystems/material3)
- [Animation in Jetpack Compose](https://developer.android.com/develop/ui/compose/animation/introduction)
- [Predictive back design](https://developer.android.com/design/ui/mobile/guides/patterns/predictive-back)
- [Expressive design — Google Design research](https://design.google/library/expressive-material-design-google-research)


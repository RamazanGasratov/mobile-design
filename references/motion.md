# Motion and interaction

Use this reference for gestures, direct manipulation, transitions, sheets, carousels, and motion review. The physical interaction principles are retained from Apple's earlier fluid-interface guidance; apply them within the 2025–2026 content/UI-layer model.

## 1. Response first

- Show press or touch feedback on contact, not only after activation.
- Track direct manipulation continuously and one-to-one with the pointer or finger.
- Preserve the grab offset instead of snapping the object center to the pointer.
- Use pointer or gesture capture so tracking continues beyond the original bounds.
- Add a small intent threshold before committing ambiguous drag directions, then remove lag once intent is known.

## 2. Make motion interruptible

Any interactive transition must be reversible while it is moving.

- Never disable relevant input merely because an animation is running.
- Begin a retargeted animation from the live presentation value, not the previous logical start or destination.
- Preserve or blend current velocity when direction changes; a hard velocity reset creates a visible seam.
- Use independent motion values for axes with different displacement or velocity.
- Prefer a spring or another retargetable system over fixed keyframes for gesture-driven motion.

## 3. Hand off velocity

When a drag ends, the settling animation should inherit the release velocity. Some APIs accept absolute points or pixels per second; others expect velocity normalized by remaining distance:

```text
relative velocity = gesture velocity / (target - current)
```

Check the animation API's units. Do not copy a normalized value into an API that expects absolute velocity.

## 4. Project momentum

Choose a landing target from where the gesture is heading, not only from its release position. For exponential deceleration, a useful projection is:

```text
projected distance = (velocity / 1000) * rate / (1 - rate)
projected endpoint = current position + projected distance
```

A rate near `0.998` produces long, scroll-like projection; a lower rate such as `0.99` settles sooner. Treat these as starting points and match the platform or component behavior.

Snap to the appropriate target near the projected endpoint, then pass the original release velocity into the settling spring.

## 5. Springs

Think in damping and response rather than fixed duration:

- Start ordinary UI movement critically damped or nearly so, without decorative overshoot.
- Allow modest bounce only when the preceding gesture carried momentum or the physical metaphor supports it.
- Shorter response feels faster but must not sacrifice legibility or continuity.
- Retarget the same spring instead of replacing it with a disconnected animation.

Reasonable tuning starts, not universal constants:

| Interaction | Damping ratio | Response |
| --- | ---: | ---: |
| Reposition or settle | `1.0` | `0.3–0.4s` |
| Momentum-driven release | `~0.8` | `0.3–0.4s` |
| Sheet or drawer settle | `0.8–1.0` | `~0.3s` |

## 6. Boundaries and spatial logic

- At a boundary, use progressive resistance while maintaining contact instead of a frozen hard stop.
- Make entrance and exit paths spatially consistent. A surface should return toward the source or edge it came from.
- Set transition origins from the triggering control when that relationship matters.
- Let intermediate frames indicate the destination: expansion, compression, and direction should explain the resulting state.
- Avoid full-screen motion for small state changes.

A common rubber-band approximation is:

```text
resisted = (overshoot * dimension * constant) /
           (dimension + constant * abs(overshoot))
```

Start around `0.55` for the constant, then tune in context.

## 7. Brand and content motion (Apple, 2026)

- Use motion primarily in the content layer to reinforce product identity and content hierarchy.
- Connect a tap target to its destination so the transition preserves context.
- Use native presentation and navigation motion for conventional behavior.
- Custom motion must serve the task and maintain frame-rate quality; dropped frames damage perceived product quality.
- Choose the intended feeling — calm, confident, energetic, precise — and keep timing and physicality coherent with it.

## 8. Multimodal feedback

- Trigger visual, sound, and haptic feedback from the same meaningful event.
- Keep them perceptually synchronized.
- Reserve stronger feedback for commit, snap, success, warning, or error states.
- Respect system settings and never require sound or haptics to understand state.

## 9. Reduced motion

- Replace large slides, parallax, elastic overshoot, and zoom with short fades, color changes, or immediate state changes.
- Keep small, gentle transitions when they materially aid orientation.
- Avoid ambient looping motion and abrupt large brightness changes.
- Test interruption and focus order with animations disabled.

## 10. Motion audit

- What caused the motion?
- What relationship or state does it explain?
- Can the person interrupt and reverse it?
- Does it begin from the visible state and inherit velocity?
- Is feedback immediate at contact?
- Does reduced motion retain understanding?
- Would removing the motion harm comprehension or identity? If not, consider removing it.

## Official sources

- [Communicate your brand identity on iOS — WWDC26](https://developer.apple.com/videos/play/wwdc2026/251/)
- [Principles of great design — WWDC26](https://developer.apple.com/videos/play/wwdc2026/250/)
- [Meet Liquid Glass — WWDC25](https://developer.apple.com/videos/play/wwdc2025/219/)
- [Designing Fluid Interfaces — WWDC18, retained for interaction physics](https://developer.apple.com/videos/play/wwdc2018/803/)

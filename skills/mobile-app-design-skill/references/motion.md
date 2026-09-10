# Purposeful motion

Use native navigation and control motion first. Frequent interactions should
remain immediate; reserve expressive motion for infrequent moments that earn it.
Choose timing and easing by the interaction, then inspect it in context.

## Custom gesture motion

Use the installed animation and gesture system. In React Native with Reanimated,
keep continuous gesture updates on the UI thread with shared values and worklets;
verify the installed version's APIs. Cross to application state for discrete
effects rather than every frame.

Start from the live position when grabbed, preserve release velocity, and choose
the destination using distance and directional momentum. Allow interruption
mid-animation. Complete a dismissal before unmounting the animated content;
cancellation and repeated gestures must settle into a valid state.

Prefer transform and opacity where they express the effect. Use supported layout
animation when layout itself must change. Avoid replaying entrance effects on
recycled rows or ordinary back navigation. Tie keyboard-following UI to the
platform's keyboard progress through the framework's supported integration.

## Accessibility and inspection

Respect system Reduce Motion settings, replacing custom spatial effects with
reduced or non-spatial feedback. The information conveyed by motion must remain
available when animation is reduced.

Record the whole affected flow, including interruption, reverse direction, and
keyboard appearance/dismissal. Watch at full speed for feel and inspect frames
around suspected flashes, jumps, or discontinuities. A recording shows artifacts;
use profiling for frame-time claims. See [performance](performance.md) for the
measurement loop and [simulator loop](simulator-loop.md) for completion checks.

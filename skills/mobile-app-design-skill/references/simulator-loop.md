# Runtime verification

Use the project's existing launch and test workflow on the requested platform.
Start with the affected route on a primary target, then check a smaller supported
screen. Add other OS/device profiles when the app supports them and the change
can affect their behavior. Save evidence under `docs/verification/<feature>/`.

## Loop

1. Launch and navigate to the changed state. Capture and open a screenshot;
   compare it against the intended hierarchy and chosen reference patterns.
2. Exercise the changed flow, including its entry, exit, and applicable checks
   below. Record motion through transitions, sheets, and keyboard interactions.
3. Inspect at full speed and around suspicious frames. Fix observed defects and
   rerun affected checks; broaden only when a shared change could regress siblings.
4. Record the device/build, states exercised, results, and any unverified checks.
   Retain or add a small regression check when behavior warrants it, using the
   project's existing testing tools.

## Applicable checks

- **Layout:** safe areas, status/navigation bars, bottom actions, overflow, long
  content, small displays, and rotation/tablet layouts when supported.
- **States:** populated, loading, empty, error, retry, and pending submission;
  rapid taps cannot double-submit or corrupt navigation.
- **Accessibility:** supported themes and contrast, larger text without clipping,
  readable labels, platform touch targets, screen-reader focus and actions,
  keyboard reachability, and Reduce Motion.
- **Navigation:** push/pop, tabs, deep links, cold start, modal cancel/dismiss,
  system back and edge gestures. After completed state changes, back cannot expose
  obsolete entry screens. Contextual actions return to the expected place.
- **Motion:** continuous gesture tracking, velocity on release, interruption,
  sheet/scroll handoff, keyboard entry/exit, and absence of visible flashes or
  layout jumps. Use profiling for performance claims.
- **Persistence:** background/foreground and relaunch preserve intended state;
  offline or failed actions show a recoverable outcome without losing user work.

Finish when applicable checks pass and observed defects are resolved. If runtime,
recording, or a supported device is unavailable, finish independent implementation
and static checks, then name the remaining verification gap. Claim only inspected
layout, exercised behavior, and measured performance.

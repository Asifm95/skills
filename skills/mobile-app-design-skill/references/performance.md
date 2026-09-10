# Measure, fix, remeasure

Capture a baseline for the actual slow interaction on a representative target
device. Change the part the measurement identifies, repeat the same measurement,
and report the difference with build mode and device. Use release builds for
performance conclusions; simulator and development measurements are diagnostic.

| Symptom | Investigate |
|---|---|
| Typing lag | Expensive siblings, broad subscriptions, derived filtering; isolate the input's updates before changing its control model. |
| Scrolling jank | Virtualization for long lists, stable item identity, image sizes/decoding, and recycled item state. |
| Transition hitch | Main/UI and JS thread work, destination rendering, image decode, and per-frame crossings between runtimes. |
| Slow startup | Required first paint work versus deferrable initialization; measure cold start separately from warm navigation. |
| Growing memory | Retained listeners, subscriptions, timers, images, and route state after repeated navigation. |

Reuse the installed list, image, and data libraries when adequate. Memoization,
store changes, library swaps, and preload strategies need evidence of benefit.
Avoid speculative prefetches that trigger side effects or unnecessarily fetch
sensitive data. Scope caching and retry policy to the layer that already owns it.

Set performance targets appropriate to supported devices and refresh rates. If
none exist, start by checking for sustained responsive input and smooth scrolling
and transitions; record actual frame timings and startup time before promising a
numeric target. Absence of a visible stutter is not an FPS measurement.

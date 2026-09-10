# App artwork

Reuse suitable project assets and native symbols first. Generate artwork when it
serves a concrete screen need and the user's scope includes it. Use the available
image-generation skill and tool for generation or edits.

Define one style family, palette tied to app tokens, lighting, subject treatment,
and composition rules for the set. Build each prompt from that style plus the
subject, intended placement, background, and required negative space. Keep UI text
and functional controls in the app's layout so they remain accessible and localizable.

Generate at the required display density: 200 pt at 3x needs 600 source pixels.
Inspect the result before generating further variants. Use transparent artwork or
a deliberate theme-compatible surface; inspect edges for halos in supported themes.
Export only needed sizes and formats, check compressed file size and on-device
sharpness, and verify that cropping preserves the focal point with safe areas.

Competitor screenshots are research references; use original or authorized assets
for the product. Keep temporary assets under `docs/` according to project rules,
and place shipped assets in the app's established asset directory. For app icons
or store artwork, check the current target platform specifications before export.

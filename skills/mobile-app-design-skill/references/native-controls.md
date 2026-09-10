# Native controls and forms

Choose the existing native control or wrapper that matches the target platform.
For Expo, consult the available Expo UI guidance and installed SDK before selecting
a package. Use standard switches, pickers, sliders, menus, alerts, share sheets,
search, and refresh controls wherever their behavior fits.

## Forms

- Persistent labels, appropriate keyboard and autofill hints, clear required fields.
- Return-key focus chaining; final submission from the expected action.
- Validation at the field's appropriate interaction point, with specific errors
  associated with the field and preserved user input after failure.
- A tested keyboard avoidance strategy; verify first and last fields, multiline
  text, validation messages, and keyboard dismissal on the smallest target screen.
- Announce errors and status changes accessibly; provide visible focus and press
  feedback. Avoid duplicate haptics when the native control already supplies them.

## Sheets and menus

Use content-derived or platform detents. Verify drag/scroll handoff with the sheet
implementation's supported scroll container, keyboard behavior, backdrop dismissal,
focus restoration, and cancellation. Item actions belong near their item in a
native menu. Use confirmation or undo appropriate to a destructive action.

## Custom controls

Build a custom control only for behavior the existing controls cannot express.
Specify its accessible role, name, value, focus behavior, disabled and pressed
states, keyboard/screen-reader actions, and touch target before polishing motion.
Honor platform conventions: normally at least 44 pt on iOS and 48 dp on Android.
Test labels at larger text sizes and with longer localized content.

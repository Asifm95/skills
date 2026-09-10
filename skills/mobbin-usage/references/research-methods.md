# Research methods

## Flows

Search one journey at a time, such as "onboarding that asks for goals before
showing a personalized plan". Compare the purpose and order of steps, input
required, value delivered, optional exits, and completion. Select relevant flows
before inspecting their full sequences; the preview gallery is for shortlisting.
Use the parent skill's coverage rules for every journey claim. A flow's recorded
screens describe one captured path, not every possible branch of the app.

End with a proposed sequence and rationale, citing each source flow. State where
presentation, skip behavior, gestures, or timing still needs live verification.

## Components

Use `search_screens` with a component in context: "workout summary with a prominent
duration, weekly chart, and a bottom share button". Compare hierarchy, active and
inactive treatments, labels, density, placement, and surrounding content. Native
control semantics come from the target platform, even when the reference uses a
custom treatment. End with a component decision and the states it must support.

## Website sections

Use `search_sections` for a bounded website region: "pricing section with monthly
and annual billing and a plan comparison table". Use `search_screens` with `web`
when the question concerns a whole page; `search_flows` with `web` for a journey.
These results support web research independently of the native mobile design skill.

## User-supplied Mobbin links or collections

Use the user's selections as the starting point. The MCP has no direct URL/ID
lookup or collection reader. If an available browser can open the supplied link,
inspect it there. Otherwise request the relevant screenshot or screen description
when exact matching matters; descriptive search may find alternatives but cannot
guarantee the selected screen. Identify alternatives as alternatives.

## Evidence quality

Choose examples for relevance and visible execution. Library inclusion, search
ordering, and app fame do not establish revenue, conversion, accessibility, or
usability performance. Report these as unknown unless separately sourced. Extract
patterns appropriate to the brief; an observed paywall or long onboarding is not
by itself a reason to add one.

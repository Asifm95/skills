---
name: mobbin-usage
description: Research UI references with the Mobbin MCP when finding screens, comparing user flows, studying components or website sections, or grounding a mobile app design in shipped examples.
license: MIT
---

# Mobbin usage

Turn inspected screens into design decisions. This skill owns research;
[mobile-app-design-skill](../mobile-app-design-skill/SKILL.md) owns mobile design,
implementation, and verification. Load that companion when the task reaches
design or implementation; research-only requests end with findings.

## 1. Frame the research

Name the screen, journey, or component decision the research must resolve.
Start with references the user supplied. Choose a playbook:

| Task | Read |
|---|---|
| New mobile app or feature | [Build from scratch](references/build-from-scratch.md) |
| Improve an existing screen | [Improve a screen](references/improve-a-screen.md) |
| Compare flows, components, website sections, or supplied links | [Research methods](references/research-methods.md) |

Discover the connected Mobbin tools and read their live schemas before calling
them. The names below are logical tool names; the host may add a namespace.
If Mobbin is unavailable, report that limitation and continue with supplied
references and explicitly labeled design assumptions where useful. Authentication
failures require a connection fix; honor server retry guidance for transient errors.

## 2. Search for a decision

| Tool | Use and significant constraints |
|---|---|
| `search_screens` | One screen or component in context. Start with `mode: "standard"`; use `"deep"` for nuanced relationships or weak initial matches. Additional results use `exclude_screen_ids`, not pages or cursors. |
| `search_flows` | One multi-step journey. Results include `screen_count`, ordered screen positions, and per-screen image URLs. Additional pages use `page` and `has_next_page`; maximum page is 20. |
| `search_sections` | One website section, such as pricing or a hero. Uses `page` and `has_next_page`; has no platform parameter. |

- Screens and flows accept `platform: "ios"` or `"web"`. Use `ios` for native
  mobile research. For an Android target, identify iOS examples as structural
  references and adapt controls and navigation to Android conventions.
- Describe one intent in plain language: visible elements and their relationships
  for screens, steps for flows. Put platform in its parameter. To focus on an
  app, include its name in the query. Concrete UI descriptions work better than
  style adjectives, negations, or disconnected keywords.
- Set `task_intent` to one short English sentence describing the overall task;
  keep it identical across all calls for that task. Use an abstract summary that
  excludes personal data, verbatim messages, file contents, and conversation history.
- Start with a small batch, typically 4 screens or 2 flows; increase coverage
  only to resolve a remaining question. Use `image_format: "jpg"` if the viewer
  cannot display WebP. Follow the live schema if these options change.

Mobbin's current tools do not expose app revenue/rankings, a complete app-screen
catalog, credit balances, boards, similar-screen lookup, or direct retrieval by
screen ID. Search relevance is evidence of fit, not commercial success.

## 3. Inspect the evidence

Look at the returned images before describing a screen. In tool orchestration,
forward image content to the model's image viewer as well as reading metadata.
Separate app UI from any Mobbin attribution frame.

Flow previews are evenly spaced samples. Use `screens[].position` to identify
which steps you actually saw. For an end-to-end claim, inspect every returned
step through an available image viewer or browser. If access or image resolution
prevents that, mark the study as partial and name the uninspected positions.
Static screens establish visible layout and captured order; motion, gestures,
back behavior, and conditional branches remain hypotheses until observed.

Keep each cited example tied to a concrete decision: what is visible, what pattern
it suggests, and how that applies to the user's product. Mark measurements from
screenshots as estimates unless scale is established.

## 4. Deliver the synthesis

Research is complete when each scoped design question has an inspected example
and a decision, or a stated evidence gap. Search further when another result could
change a decision; stop when results repeat or accessible evidence is exhausted.

Always link each screen you mention to its returned `mobbin_url`; cite flows and
sections with their returned canonical links too. Flow screen entries have no
canonical URL field: cite the parent flow and screen position unless a separate
screen result supplies a link. `image_url` is media, not a source citation.

For a multi-step build or reusable study, save one working note under
`docs/research/<topic>.md`: questions, queries and platform, IDs and canonical links,
positions inspected, observations, adopted patterns, and unresolved gaps. Keep
small research answers inline. Media URLs expire after 30 days; durable notes
retain canonical links and queries. Re-run the relevant search for fresh media,
matching IDs where possible; a rerun may return different results.

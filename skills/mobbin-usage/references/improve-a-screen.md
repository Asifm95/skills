# Improve a screen

1. **Diagnose.** Inspect the supplied screenshot or run the existing screen when
   possible. Name the concrete deficits: competing headings, unclear primary
   action, cramped keyboard layout, inaccessible contrast, or confusing back
   behavior. Distinguish visible defects from behavior that still needs testing.
   Done: the improvement targets can be checked against the current screen.
2. **Search those deficits.** Describe the screen's job and relevant elements to
   `search_screens`. Inspect the first small batch; refine the query or use `deep`
   when relevance is weak. Use `exclude_screen_ids` for additional candidates.
   For a transition or surrounding journey, use `search_flows` and the parent
   skill's flow coverage rules. Done: select the examples that resolve the targets,
   recording a reason and citation for each, or explain the evidence gap.
3. **Specify the change.** Set hierarchy, placement, control choice, spacing,
   semantic color roles, and affected states. Reuse the app's design language and
   preserve intended behavior. Label proposed motion separately from static
   reference observations. Done: each diagnosed deficit has a concrete change.
4. **Implement and compare.** Follow
   [mobile-app-design-skill](../../mobile-app-design-skill/SKILL.md), comparing the
   result against the baseline and chosen references. Exercise the entry and exit
   of the surrounding flow, including back and dismissal. Done: the named deficits
   are resolved without observed regressions; report checks that could not run.
   A critique-only request ends after the proposed changes and cited rationale.

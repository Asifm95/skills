# Build from scratch

1. **Bound the product.** Identify the primary user job, target platform, requested
   screens, and constraints from the brief and existing project. Research should
   improve that scope; competitor features are candidates, not requirements.
   Done: the initial screen list and consequential unknowns are explicit.
2. **Study the journey.** Search the main journey with `search_flows`; search its
   decisive screens separately with `search_screens`. Compare relevant examples
   across apps when available. Inspect the steps needed to understand first value,
   requested input, progress, permission timing, and completion. Apply the evidence
   and coverage rules in the parent skill.
   Done: each product decision has supporting observations or a named gap.
3. **Synthesize a design brief.** Record hierarchy, navigation, component choices,
   typography, color roles, and state handling. For each route define its job,
   presentation, entry/exit, and back behavior. Distinguish observed reference
   behavior from proposed behavior. Reuse an existing spec; otherwise put the brief
   in `docs/design/<feature>.md`. Resolve consequential missing requirements with
   the user while continuing independent work; make routine choices within scope.
   Done: every requested screen has a buildable role and its major states.
4. **Build and verify.** Read
   [mobile-app-design-skill](../../mobile-app-design-skill/SKILL.md) and implement
   the agreed scope. Return to Mobbin only for concrete gaps discovered during
   implementation. Use the companion's verification loop for each changed flow.
   Done: requested behavior works, observed defects are resolved, and remaining
   environmental limits are reported. For a design-only request, deliver the
   design brief and cited evidence without starting implementation.

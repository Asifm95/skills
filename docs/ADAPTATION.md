# Mobile design skills adaptation

Source: [Appllama/appllama-skills](https://github.com/Appllama/appllama-skills),
commit `dd5caaec3d5d50ad7fc0324da238119c6b7c3707`, inspected September 10, 2026.
The repository retains the upstream Git history; the original project is recorded
as the `upstream` remote.

## Structure

The upstream repository contains two skills: `appllama-usage`, with three research
playbooks and Codex tool metadata, and `appllama-app-design-skill`, with five
implementation references. Root Claude/Cursor plugin manifests and two MCP config
files package the Appllama connection. Those provider configurations are not part
of this adaptation. Mobbin research uses an already connected MCP; the mobile
design skill also works without Mobbin or the research companion installed.

This portable pair keeps the same division of responsibility:

- [mobbin-usage](../skills/mobbin-usage/SKILL.md): Mobbin tools, evidence rules, and three
  playbooks for new apps, existing screens, and focused research.
- [mobile-app-design-skill](../skills/mobile-app-design-skill/SKILL.md): native design and
  implementation, with five references for controls, motion, performance, assets,
  and runtime verification.

Install `mobile-app-design-skill` on its own, or keep both directories as siblings
to enable the optional research links. Invoke `$mobile-app-design-skill` for
design/build work or `$mobbin-usage` for research. Both permit normal model discovery.

## Adaptation decisions

| Upstream behavior | Mobbin adaptation |
|---|---|
| Find revenue-ranked apps and enumerate their screens | Search task-relevant screens and flows; make no ranking or full-catalog claims. |
| Credit checks, boards, taxonomy, similar-screen and ID lookup | Omitted because the connected Mobbin tools do not expose these operations. |
| Keyword/semantic searches and cursor pagination | Standard/deep screen search with exclusions; page-based flows and sections. |
| Study every screen in top apps and fixed 30+30 boards | Inspect enough relevant evidence to resolve scoped decisions; full-journey claims require full step inspection. |
| Media expires in about an hour | Current Mobbin schema documents 30 days; retain canonical links and search queries. |
| Reference videos inform motion | Current tools expose images; distinguish visual observations from inferred interaction behavior. |
| Detailed native design and implementation rules | Preserve the upstream SKILL.md wording, package defaults, motion specifics, and simulator quality bar. |
| Reference research as a completion requirement | Use Mobbin when available; otherwise use supplied references, the existing design system, or explicit assumptions from the brief and platform conventions. |
| Research always ends in a build | Research-only and design-only requests finish at their requested deliverable. |

The design SKILL.md restores upstream content with changes limited to identity,
optional Mobbin research, evidence limits, and the related fallback wording in
navigation, styling, and the completion checklist. The implementation references
retain the native controls, navigation, purposeful
motion, cohesive artwork, and simulator loop themes. They avoid caching volatile
framework snippets and route version-specific choices to installed APIs and the
applicable framework guidance. Upstream MIT notices are included in each skill.
This is a custom adaptation, not an official Appllama or Mobbin package.

## Validation

All three connected Mobbin tools were called with small batches, their returned
images inspected, and the live schemas used for the tool map:

- `search_screens`: [Lifesum screen](https://mobbin.com/screens/0d8ee219-4985-4bfd-85c2-dab08d6809f9),
  one inline image and canonical screen link.
- `search_flows`: [Me+ onboarding](https://mobbin.com/flows/627c7d90-e2f1-4d68-9db2-bf140530de34),
  30 ordered screen entries but only five inline previews, at positions 1, 8, 16,
  23, and 30. This was a response-shape check, not a full-flow study.
- `search_sections`: [Linear pricing](https://mobbin.com/sites/sections/be148265-d2a2-4e94-82dc-15ecf2b44896),
  one inline image, a canonical section link, and page metadata.

Both skills pass the skill frontmatter validator, and all repository reference
links resolve. Skills CLI 1.5.25 discovers exactly the two custom skills. Isolated
project installs for Codex passed for the mobile design skill alone and for the
pair using `--copy`; every installed skill file matches its source, including
references and licenses. No global installation was made during these checks.

These checks validate packaging and live tool compatibility; they do not
establish that an app built with these skills has passed runtime verification.

# Mobile design skills

Agent skills for building native-feeling mobile apps and researching real UI
patterns. Install with the [skills CLI](https://github.com/vercel-labs/skills).

| Skill | Purpose |
|---|---|
| [mobile-app-design-skill](skills/mobile-app-design-skill/SKILL.md) | Detailed Expo / React Native design guidance: native controls, navigation, visual consistency, motion, and simulator verification. Works independently of Mobbin. |
| [mobbin-usage](skills/mobbin-usage/SKILL.md) | Research screens, flows, and website sections using a connected Mobbin MCP, with image inspection and source citations. |

## Install

From a local clone, run this in the project where you want to use the skills:

```sh
npx skills add /path/to/skills --skill mobile-app-design-skill
```

To install both skills:

```sh
npx skills add /path/to/skills --skill mobile-app-design-skill mobbin-usage
```

After publishing this repository to GitHub, replace `OWNER` with its GitHub owner:

```sh
npx skills add OWNER/skills --skill mobile-app-design-skill
npx skills add OWNER/skills --skill mobile-app-design-skill mobbin-usage
```

Add `-g` for a user-wide installation, `-a codex` (or another supported agent)
to select an agent, and `-y` for non-interactive installation. Preview the available
skills without installing:

```sh
npx skills add OWNER/skills --list
```

Each skill bundles its own references and license. Installing both keeps their
relative cross-links available. The mobile design skill can be installed alone;
it continues from supplied references, the existing design system, or platform
conventions when Mobbin or the research companion is unavailable.

## Use

```text
Use $mobile-app-design-skill to build a habit tracker with native navigation
and verify the onboarding flow in the simulator.

Use $mobile-app-design-skill to improve this screen's hierarchy and motion.

Use $mobbin-usage to compare onboarding flows and explain the patterns with
links to the screens you inspected.
```

Mobbin research requires the Mobbin MCP to be connected in your agent. Installing
these skills does not configure an MCP server. Both skills support automatic
selection as well as explicit invocation.

## Contributing

Put each skill in `skills/<skill-name>/SKILL.md` with `name` and `description`
YAML frontmatter. Bundle supporting files inside that skill directory, and keep
optional companion links conditional so independently installed skills still work.
Keep research and adaptation notes under `docs/`.

Check discovery from the repository root before publishing changes:

```sh
npx skills add . --list
```

## Attribution and license

Adapted from [Appllama/appllama-skills](https://github.com/Appllama/appllama-skills).
The mobile design entrypoint preserves its detailed design guidance, with optional
Mobbin research and a standalone fallback. See [adaptation notes](docs/ADAPTATION.md)
for provenance and capability differences.

[MIT](LICENSE). Original copyright notices are preserved, including in each
installable skill. This is a custom adaptation, not an official Appllama or Mobbin
package; their names and branding remain their owners' property.

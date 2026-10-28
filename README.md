# UI design principles

A reusable skill that translates architectural design principles into rules for designing, modifying, and reviewing web, app, and game interfaces.

It adapts principles of spatial organization, hierarchy, axes and datums, proportion, rhythm, and the relationship between solid and empty space to UI layout. Coding agents use these rules to prioritize the primary workspace, organize supporting regions, establish alignment, and check the resulting interface. Project-specific decisions are recorded in `DESIGN.md` for later work to follow and verify.

## What it covers

- Primary regions get the position, space, and visibility needed for observation and interaction. Secondary regions support them.
- Alignment uses explicit references: frame edges, text edges, baselines, centers, and visible artwork.
- Grouping, proportion, empty space, rhythm, and control boundaries reflect content and function.
- Responsive changes preserve roles, priorities, and context.
- Reviews distinguish measured results, image observations, and untested assumptions.

The skill does not prescribe a visual style, framework, or universal spacing scale. It preserves project constraints and authorization boundaries.

## Files and languages

| File | Purpose |
| --- | --- |
| [SKILL.md](SKILL.md) | Vietnamese skill entrypoint |
| [SKILL.en.md](SKILL.en.md) | Full English translation |

## Use

For a skill-compatible agent, place `SKILL.md` in a `ui-design-principles` folder under that agent's skill directory. To use English, copy the contents of `SKILL.en.md` into the installed folder's `SKILL.md`. Keep one active language version per installation.

You can also provide either file directly to an agent with a scoped request, for example:

> Review this screen using UI design principles. Check the primary workspace, secondary panels, alignment, and visibility. Report findings without editing files.

Follow your agent's installation and permission rules. Installing the skill does not authorize it to modify unrelated files, install dependencies, or publish changes.

## Project design rules

Before working on a UI, the skill reads the project's `DESIGN.md`. If the file is missing and writing is authorized, it creates one from agreed requirements and inspected project evidence.

Confirmed rules remain separate from unconfirmed observations. Later work checks the UI against those rules. Updates record approved decisions or missing confirmed rules; they do not rewrite the rules to excuse UI defects. Review results are reported separately.

## Verification limits

The skill requires agents to report what they actually inspected or tested. A document check does not establish that a live interface is usable, accessible, or visually correct. Results depend on the agent, available tools, and project evidence.

## About us

Maintained by [sefxvn16 (Seafox)](https://github.com/sefxvn16). This repository contains the UI design principles skill and its English translation for use with coding agents.

## License

[MIT](LICENSE). Copyright (c) 2026 Seafox (sefxvn16).

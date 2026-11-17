# UI design principles

[English](README.md) | [Tiếng Việt](README.vi.md)

A reusable skill that translates architectural design principles into rules for designing, modifying, and reviewing web, app, and game interfaces.

It adapts principles of spatial organization, hierarchy, axes and datums, proportion, rhythm, and the relationship between solid and empty space to UI layout. Coding agents use these rules to prioritize the primary workspace, organize supporting regions, establish alignment, and check the resulting interface. Project-specific decisions are recorded in `DESIGN.md` for later work to follow and verify.

## What it covers

- Establish the intended users: age group, country/region, language, cultural context, and familiarity with technology. Ask only for missing information that could change a design decision, without inferring preferences from demographics alone.
- Set the level of intervention (local change, refinement, redesign, review) and the screen type (Operate, Read, Persuade, Experience, Play), which determines density, repetition, and layout freedom.
- Primary regions get the position, space, and visibility needed for observation and interaction. Secondary regions support them, and the reading path follows the action path.
- Alignment uses explicit references: frame edges, text edges, baselines, centers, and visible artwork. Structure comes from shared axes rather than borders; side-by-side columns end on a shared bottom line; tables keep labels and numbers on fixed edges.
- Platform-specific rules live in separate files read only when needed: `references/desktop.md` (mouse, trackpad, keyboard on Windows/macOS) and `references/touch.md` (tablet and mobile touch).
- Spacing follows a fixed order (within a group < between groups < between regions); every large empty area has a nameable role; containers express a scope.
- Responsive changes inherit project breakpoints and preserve roles, priorities, and context. Variable content, states, overlays, and scroll regions are checked for clipping, obscuring, and layout shift.
- Mandatory numeric thresholds come only from public standards (WCAG target size, contrast, visible focus) or the project's `DESIGN.md`.
- Verification uses named tests (squint, skeleton, 5-second, task path, edges and layers) and same-condition before–after comparison. Review findings record location, reference, observation → consequence → remedy, P0–P3 severity, and evidence type.

Each rule states its condition, required behavior, exceptions, and signs of failure. The skill does not prescribe a visual style, framework, or universal spacing scale. It preserves project constraints and authorization boundaries.

## Files and languages

| File | Purpose |
| --- | --- |
| [SKILL.md](ui-design-principles/SKILL.md) | Vietnamese skill entrypoint |
| [SKILL.en.md](ui-design-principles/SKILL.en.md) | Full English translation |
| [references/desktop.md](ui-design-principles/references/desktop.md), [desktop.en.md](ui-design-principles/references/desktop.en.md) | Desktop rules (mouse, trackpad, keyboard), Vietnamese and English |
| [references/touch.md](ui-design-principles/references/touch.md), [touch.en.md](ui-design-principles/references/touch.en.md) | Touch rules (tablet, mobile), Vietnamese and English |
| [README.vi.md](README.vi.md) | Vietnamese documentation |

## Use

For a skill-compatible agent, copy the whole `ui-design-principles` folder (including `references/`) into that agent's skill directory. To use English, copy the contents of `SKILL.en.md` into the installed folder's `SKILL.md`; the English entrypoint points to the `*.en.md` reference files. Keep one active language version per installation.

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

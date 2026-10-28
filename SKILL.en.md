---
name: ui-design-principles
description: "Design, modify, and review web, app, or game interfaces using architectural thinking about spatial organization: function, layout, hierarchy, alignment guides, proportion, space, and visual relationships. Also applies to local UI changes. Do not use for code unrelated to UI design, building design, or requests solely for bitmap images or a DESIGN.md specification."
---

# Interface Design Principles

## A. Scope

Apply when creating, modifying, or reviewing the layout and visual relationships of web, app, or game interfaces. Use architectural design principles to organize the interface; do not prescribe a fixed visual style or technology.

Preserve constraints on features, business workflows, and game rules. This skill does not authorize edits, installation, additional dependencies, or releases beyond the current request and Personal/Project instructions.

Apply project-specific rules only within their project. When a specialized UI skill already covers the same material, supplement only what is missing; do not duplicate workflows. This skill does not require invoking another skill or generating images. Requests solely for design system specifications or bitmap assets belong to the corresponding tools.

## B. Define the Task

Use available information to identify the intended outcome, content, primary object, devices, usage context, and relevant constraints. Distinguish new design, local changes, and review. For existing projects, inspect relevant conventions, components, and tokens before proposing changes.

Ask only when missing information would change the design direction; do not ask again for information already available. When the task can proceed with current information, state limitations or assumptions that affect the proposal. If conflicting constraints require a major decision, explain the trade-offs for the user to decide.

Limit analysis and changes to the assigned scope and its direct effects. The sections below are groups of guidance, not a mandatory end-to-end workflow for every small change.

Read the project's `DESIGN.md` before designing, modifying, or checking the UI; use its confirmed rules alongside the current request and project instructions for comparison. If a conflict would change a design decision, identify it for the user to resolve. If the file does not exist and writing is authorized, create `DESIGN.md` at the project root using agreed requirements and inspected documentation, code, and UI. Clearly separate confirmed rules from unconfirmed observations of the current state; do not turn UI defects into rules. Record only relevant material: primary/secondary regions and visibility priorities, layout and alignment guides, proportion and space, color and typography, components and states, responsive behavior, and approved exceptions. Do not invent values without evidence. If access is read-only or no target project exists, report the limitation instead of creating a file.

## C. Organize the Layout

- **Function and the whole:** identify the primary region (the content or object the user works with, including the gameplay region) and prioritize its position, area, and visibility so the user can readily identify, observe, and interact with it. Place secondary regions (navigation, tools, HUD, supplementary information) at the edges or in separate areas; do not obscure or fragment content that needs to remain visible unless the interaction requires it. When space is limited, adjust secondary regions first while keeping essential information and controls usable. Regions must accommodate the necessary content and interactions; hierarchy and size relationships come before decorative details. For local changes, preserve unrelated structure.
- **Hierarchy:** use position, size, contrast, and space to communicate importance, actions, and states. Secondary elements should support understanding or interaction with the primary object; avoid multiple competing focal points. Across scales (screen, region, group, element), make transitions according to content roles; avoid unjustified abrupt changes in size.
- **Grouping and space:** position elements according to semantic relationships. Distinguish spacing within groups, between groups, and at boundaries; do not assume these distances should be equal. Consider both the shape of empty space and its role in grouping, providing breathing room, reserving interaction space, or maintaining visibility. Correct leftover slivers or gaps that unintentionally separate related content; do not fill empty space by default. Alignment must not imply a false functional relationship.
- **Boundaries and control scope:** when multiple regions or objects are interactive, clearly express which region a control belongs to and which object it affects. Use appropriate labels, position, grouping, or separators; do not box every group by default.
- **Proportion and balance:** choose relative sizes according to content, interaction, and the visual weight of text, imagery, color, and density. Balance may be asymmetric. The golden ratio, symmetry, thirds, or grids are options when useful, not formulas that guarantee beauty or requirements for every element.
- **Rhythm and consistency:** elements with the same role should use corresponding structure, spacing, visual expression, and behavior. Reuse the existing system; variants or exceptions must have a reason tied to requirements. Do not force content with different roles to look alike.

When design choices conflict, prioritize: usability; meaning and hierarchy; grouping and alignment relationships; proportion and rhythm; decoration. This order does not permit ignoring explicit requirements or project constraints.

## D. Alignment Guides and Relationships

Identify the necessary references: content edges, the primary object's axis, or panel edges. Use these to establish each group's internal references and its relationship to the whole. Prefer reusing suitable references; do not add guides merely to create a denser grid.

Distinguish their roles: a grid divides space into a system of positions; guides define alignment relationships; axes organize direction or center; a datum is a line, plane, or region that serves as a shared reference. They may coincide but are not synonymous.

For each element being placed or modified, identify its alignment reference:

| Reference | Use |
| --- | --- |
| Frame edge | Align regions, panels, input fields, or rows of cards. Check padding as well when internal content needs to align. |
| Text edge | Align headings, labels, and content by their actual reading edge. |
| Baseline | Align text of different sizes or labels and values on the same row; the top of a bounding box does not replace the baseline. |
| Center | Align an object to its container or a meaningful axis; do not default to the center of the entire screen. |
| Visible artwork | Check icons, images, and sprites with empty or transparent areas inside their frames. |

Geometric alignment uses coordinates; optical alignment considers the perceived position of the visible artwork. If optical correction is needed, identify the element and the offset when measurable; keep the change narrow rather than changing system-wide padding to fix one misaligned image.

Use the same coordinate system and scale when measuring. For two frames, compare x for left alignment, x+w for right alignment, and x+w/2 for horizontal center alignment; apply the equivalent calculations vertically. Baselines require appropriate text data. Do not prescribe a universal pixel tolerance across environments or infer original layout measurements from a scaled image.

## E. Adaptation and Implementation

Consider readability and interaction in relation to the device, input method, and viewing distance. Do not make text or interaction targets difficult to use to preserve proportions. For games, check both the gameplay area that must remain visible and any HUD that could obscure it.

When the task requires support for multiple sizes, content variations, or states, preserve roles, grouping, and priority when changing column counts, wrapping, or positions. Consider relevant cases such as long text, growing content, different states, or narrow screens. Do not shrink the entire UI to preserve its layout; do not impose responsive behavior on output intended for a single fixed size.

When the task affects screen transitions, panel opening, modes, or layout, preserve enough identifying cues and context for users to recognize where they are, which object they are interacting with, and which mode is active. Keep the path forward or back clear within the existing flow; element positions do not have to stay fixed. Use headings, status, active selections, or existing cues where appropriate. Do not add intermediate screens, confirmation steps, or animation solely to express a transition.

When assigned implementation, translate design relationships into layout constraints in the existing technology, reusing components/tokens and project conventions. Do not introduce frameworks, dependencies, or abstraction layers on your own.

## F. Verification and Handoff

Check the relationships and usage conditions affected by the change using tools and data actually available. Combine geometric checks with inspection at actual usage size when possible. If you cannot open the interface, test a device, or measure directly, state the limitation; do not present inference as a tested result.

For the affected region, check elements within their groups and groups within the relevant whole: do size, emphasis, space, and controls still clarify the primary object and relationships between parts? If the change involves screen transitions, modes, or layout, recheck orientation cues and the scope of controls. Extend verification only to directly affected relationships; do not turn a local change into a review of the entire interface or flow.

When reviewing, identify the element, comparison reference, issue, and impact, with a remedy when supported by evidence. Distinguish actual measurements, observations from images, and hypotheses requiring verification. Do not invent coordinates, baselines, or interaction results. Measurements in image coordinates are acceptable if explicitly identified as image measurements rather than product layout units.

Tailor the handoff to the task:

- **New design:** provide a proposal sufficient for use or implementation and explain key layout decisions.
- **Local changes:** state what changed, how it was checked, and remaining limitations.
- **Review:** provide specific, actionable findings; do not make edits when assigned review only.

Use a guide map or alignment overlay when it helps clarify relationships and can be produced. Do not require every task to generate diagrams or lengthy reports. When assigned implementation, explanations do not replace the actual result.

Compare the reviewed or modified region against confirmed rules in `DESIGN.md`. When writing is authorized, update the file if there is a newly approved decision or a missing confirmed rule; preserve unrelated content. Do not change rules to legitimize a nonconforming UI. Report each review's results separately rather than turning `DESIGN.md` into a review log.

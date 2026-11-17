---
name: ui-design-principles
description: "Design, modify, and review web, app, or game interfaces using architectural thinking about spatial organization: function, layout, hierarchy, alignment guides, proportion, space, and visual relationships. Also applies to local UI changes. Do not use for code unrelated to UI design, building design, or requests solely for bitmap images or a DESIGN.md specification."
---

# Interface Design Principles

## A. Scope

Apply when creating, modifying, or reviewing the layout and visual relationships of web, app, or game interfaces. Use architectural design principles to organize the interface; do not prescribe a fixed visual style or technology.

Preserve constraints on features, business workflows, and game rules. This skill does not authorize edits, installation, additional dependencies, or releases beyond the current request and Personal/Project instructions.

Apply project-specific rules only within their project. When a specialized UI skill already covers the same material, supplement only what is missing; do not duplicate workflows. This skill does not require invoking another skill or generating images. Requests solely for design system specifications or bitmap assets belong to the corresponding tools.

**How to read the rules:** each rule states its condition, required behavior, exceptions, and signs of failure. Mandatory numeric values come only from public standards (WCAG) or from `DESIGN.md`/project conventions. Any other number in this skill is a signal to re-examine, not an automatic failure. Skipping or exceeding a rule requires a reason that fits in one sentence and is tied to a specific requirement or constraint. Do not use "reasonable", "balanced", or "beautiful" as criteria unless paired with a testable relationship or task.

## B. Define the Task

**Intended users:** use the facts already available to identify the user characteristics that affect the task: age group, country/region, language, cultural context, and familiarity with technology. Ask only for what is missing when the answer could change a design decision within the assigned scope. For new designs with unknown users, ask before choosing a direction; for local changes, do not require a complete user profile. Use this information to guide presentation, density, typography, color, icons, and interaction; do not infer preferences solely from age or nationality.

Use available information to identify the intended outcome, content, primary object, devices, usage context, and relevant constraints. For existing projects, inspect relevant conventions, components, and tokens before proposing changes.

**Platform and input:** identify the target devices, input methods (mouse, trackpad, keyboard, touch), and screen orientation. When the task touches controls, target sizes, or layout that depends on screen size, also read the matching platform file; a local change that touches none of these does not need it.

| Product uses                                      | Also read                                   |
| ------------------------------------------------- | ------------------------------------------- |
| Mouse, trackpad, keyboard (Windows, macOS)        | `references/desktop.en.md`                  |
| Touch (tablet, mobile)                            | `references/touch.en.md`                    |
| Both (responsive web, tablet with a keyboard)     | Both files                                  |

**Level of intervention:** determine one level for the task before making changes.

| Level        | When                                                     | May change                                            | Must preserve                                   |
| ------------ | -------------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------- |
| Local change | The request names a specific element, region, or defect  | The assigned region and its direct relationships      | Structure, identity, and rules outside the region |
| Refinement   | The request asks to improve an existing screen or flow   | Layout, hierarchy, and spacing within the existing system | Visual identity, components/tokens, flow    |
| Redesign     | The request explicitly asks to change direction or identity | Structure and identity                             | Features, business workflows, game rules        |
| Review       | The request asks only for feedback                       | Nothing                                               | Everything                                      |

Do not mix refinement and redesign in the same task. If the request does not state a level, choose the lowest level that satisfies it and state the assumption; if that level is insufficient, explain why and ask. Failure: being assigned one panel and changing tokens shared across the whole application.

**Screen type:** assign each screen (or each region, if a screen contains several types) to one type; the type determines density, repetition, and layout freedom.

| Type        | Examples                                   | Density                                                   | Position and repetition                                                              | Asymmetry                         |
| ----------- | ------------------------------------------ | --------------------------------------------------------- | ------------------------------------------------------------------------------------ | --------------------------------- |
| Operate     | Dashboards, admin, tools, multi-step forms | High when the task requires continuous comparison or interaction | Controls with the same role keep their position across screens; repeating structure for the same role is correct | Only when it reflects region roles |
| Read        | Documentation, articles, help              | Prioritize a continuous reading line                      | Headings and sections repeat consistently                                            | Only when it reflects region roles |
| Persuade    | Landing pages, product pages               | Follows each section's argument                           | Adjacent sections with different roles do not share a layout                        | Allowed                           |
| Experience  | Portfolios, showcases                      | Follows the pacing of the presentation                    | Deliberate variation                                                                 | Allowed                           |
| Play        | Gameplay, HUD, game menus                  | Gameplay prioritizes visibility; HUD is minimal and at the edges | HUD and controls keep their position within a play mode                       | Per the game rules                |

Determine the type per screen, not per product: an app's landing page is Persuade, while a working screen inside the app is Operate. When unsure, choose based on the user's primary task on that screen and state the assumption.

Ask only when missing information would change the design direction; do not ask again for information already available. When the task can proceed with current information, state limitations or assumptions that affect the proposal. If conflicting constraints require a major decision, explain the trade-offs for the user to decide.

Limit analysis and changes to the assigned scope and its direct effects. The sections below are groups of guidance, not a mandatory end-to-end workflow for every small change.

Read the project's `DESIGN.md` before designing, modifying, or checking the UI; use its confirmed rules alongside the current request and project instructions for comparison. If a conflict would change a design decision, identify it for the user to resolve. If the file does not exist and writing is authorized, create `DESIGN.md` at the project root using agreed requirements and inspected documentation, code, and UI. Clearly separate confirmed rules from unconfirmed observations of the current state; do not turn UI defects into rules. Record only relevant material: screen types, primary/secondary regions and visibility priorities, layout and alignment guides, proportion, spacing scale and space, layout breakpoints, color and typography, components and states, responsive behavior, and approved exceptions. Do not invent values without evidence. If access is read-only or no target project exists, report the limitation instead of creating a file.

## C. Organize the Layout

- **Function and the whole:** identify the primary region (the content or object the user works with, including the gameplay region) and prioritize its position, area, and visibility so the user can readily identify, observe, and interact with it. Place secondary regions (navigation, tools, HUD, supplementary information) at the edges or in separate areas; do not obscure or fragment content that needs to remain visible unless the interaction requires it. When space is limited, adjust secondary regions first while keeping essential information and controls usable. Regions must accommodate the necessary content and interactions; hierarchy and size relationships come before decorative details. For local changes, preserve unrelated structure.
- **Reading path and action path:** when placing or reordering regions, identify the sequence of the primary task: where it starts, what must be read to decide, which control carries out the decision, and where the result appears. Place the information needed for a decision before or in the same region as the control that carries it out; feedback appears near the point of interaction or where the user is looking. Exceptions: multiple parallel work regions are valid; the order need not strictly match left→right, top→bottom. Failure: the confirm button comes before the summary that must be read; the user has to leave a group for an unrelated region and come back to finish.
- **Hierarchy:** use position, size, contrast, and space to communicate importance, actions, and states. Each screen has one primary focal point: the element still seen first in the squint test (F). Each decision point (a form, dialog, card, or toolbar row) has at most one primary action; other actions are secondary. Operate screens may have several parallel decision points, each still with only one primary action. Secondary elements should support understanding or interaction with the primary object. Across scales (screen, region, group, element), each level must be distinguishable from the adjacent level, and a containing level must not be weaker than the level it contains. Use few text levels, usually 3 to 4 (for example title; name or item heading; label; caption); create levels with size, weight, and position, and do not add color solely to express hierarchy. Failure: two heading levels with different roles look the same; a group heading stands out more than the heading of the region containing it; every line has its own text size.
- **Grouping and spacing:** position elements according to semantic relationships. Spacing follows a mandatory order: within a group < between groups < between regions. A heading sits closer to the content it introduces than to the content above: the space from the heading to its content is smaller than the space from the preceding content to the heading. Take values from the project's spacing scale; if there is none, use one consistent scale and record it in `DESIGN.md` when writing is authorized. Alignment must not imply a false functional relationship. Failure: the space between two groups is equal to or smaller than the space within a group; a heading is equidistant from the content above and below.
- **Space with a role:** every large empty area must have a nameable role: separating groups, providing a rest, reserving interaction space, maintaining visibility, or leaving room for variable content. A **hole** is an empty area with none of these roles. A **sliver** is a narrow leftover gap with no role, or one that separates two related elements. Fix them by changing the size or position of the related regions; do not fill them with content. Signal to re-examine: an empty area with no role that is about 40% of the screen height or more.
- **Density and containers:** choose density according to the screen type (B) and the information that must be observed, compared, and acted on within the same task; data that must be compared stays within the same field of view. Every element must answer: if it were removed, what information or action for the task would the user lose? If it cannot answer, remove it or move it to a see-more layer. Do not add data, sections, or secondary regions merely to fill space; do not invent figures, customers, or quotes, and label sample data as sample. Do not hide essential data in tabs, modals, or collapsed sections merely to look spacious. Group by spacing first; add frames, backgrounds, or rules only when spacing cannot distinguish the groups. Each container (frame, card, panel) expresses one unit of content, one scope of interaction, or one state; nested containers are valid when each level has its own scope. Failure: a card nested in a card with the same scope; data that must be compared is split across cards that must be opened one at a time.
- **Boundaries and control scope:** when multiple regions or objects are interactive, clearly express which region a control belongs to and which object it affects. Use appropriate labels, position, grouping, or separators; do not box every group by default.
- **Proportion and balance:** choose relative sizes according to content, interaction, and the visual weight of text, imagery, color, and density. Balance may be asymmetric within the limits of the screen type. The golden ratio, symmetry, thirds, or grids are options when useful, not formulas that guarantee beauty or requirements for every element. Size follows the role of the position: a more important position is larger; slots with the same role keep the same size whether filled or empty. Failure: an empty slot shrinks and breaks the row rhythm; a secondary slot is larger than the primary one only because it has content.
- **Rhythm and consistency:** elements with the same role should use corresponding structure, spacing, visual expression, and behavior. Reuse the existing system; variants or exceptions must have a reason tied to requirements. Do not force content with different roles to look alike. Within a column or list of the same role, the spaces between rows are equal; row dividers (if any) sit in the middle of that space. Failure: a divider hugs the row above; row spacing varies without following groups.

When design choices conflict, prioritize: usability; meaning and hierarchy; grouping and alignment relationships; proportion and rhythm; decoration. This order does not permit ignoring explicit requirements or project constraints.

## D. Alignment Guides and Relationships

Identify the necessary references: content edges, the primary object's axis, or panel edges. Use these to establish each group's internal references and its relationship to the whole. Prefer reusing suitable references; do not add guides merely to create a denser grid.

**Number of primary alignment edges:** list the left edges where multiple regions or groups of the screen begin (for right-to-left scripts, use right edges). When there are more than 3, each edge must be tied to a nameable role, such as the navigation edge, content edge, or secondary-column edge; an edge without a role moves to the nearest edge that has one. Two edges that are close but not coincident, without a reason (indentation to express level, optical alignment), are a near-miss alignment error. Failure: a heading, paragraph, and button in the same group start at three edges a few pixels apart.

**Axis before frame:** the structure of a group or column comes from a shared alignment axis (heading, image, name, and bar on one edge), not from a surrounding border. Add frames only under the conditions in C (Density and containers). Failure: elements inside a frame start at different edges, and the frame was added to mask the misalignment.

**Shared bottom line:** when columns or panels placed side by side hold different amounts of content, choose one element as the bottom reference; each column ends on that line or on a deliberate shared row. Distribute the difference into the spaces between rows while keeping the spacing order in C. Exceptions: independently scrolling columns, or flowing content (articles, feeds). Failure: a short column stops arbitrarily; the bottoms of two adjacent columns are a few pixels apart.

**Tables and label–value pairs:** labels align to one reading edge; numbers align to a shared edge per column (usually the right edge for left-to-right scripts). A number's secondary part (difference, bonus) has its own position next to the main number; rows without a secondary part leave that position empty, and the main number does not shift. Failure: the total shifts left on rows that have a bonus.

Distinguish their roles: a grid divides space into a system of positions; guides define alignment relationships; axes organize direction or center; a datum is a line, plane, or region that serves as a shared reference. They may coincide but are not synonymous.

For each element being placed or modified, identify its alignment reference:

| Reference       | Use                                                                                                                      |
| --------------- | ------------------------------------------------------------------------------------------------------------------------ |
| Frame edge      | Align regions, panels, input fields, or rows of cards. Check padding as well when internal content needs to align.       |
| Text edge       | Align headings, labels, and content by their actual reading edge.                                                        |
| Baseline        | Align text of different sizes or labels and values on the same row; the top of a bounding box does not replace the baseline. |
| Center          | Align an object to its container or a meaningful axis; do not default to the center of the entire screen.               |
| Visible artwork | Check icons, images, and sprites with empty or transparent areas inside their frames.                                    |

Geometric alignment uses coordinates; optical alignment considers the perceived position of the visible artwork. If optical correction is needed, identify the element and the offset when measurable; keep the change narrow rather than changing system-wide padding to fix one misaligned image.

Use the same coordinate system and scale when measuring. For two frames, compare x for left alignment, x+w for right alignment, and x+w/2 for horizontal center alignment; apply the equivalent calculations vertically. Baselines require appropriate text data. Do not prescribe a universal pixel tolerance across environments or infer original layout measurements from a scaled image.

## E. Adaptation and Implementation

Consider readability and interaction in relation to the device, input method, and viewing distance. Do not make text or interaction targets difficult to use to preserve proportions. For games, check both the gameplay area that must remain visible and any HUD that could obscure it. Minimum thresholds, unless the project commits to a higher level:

- **Target size:** at least 24×24 CSS px, or equivalent spacing from adjacent controls (WCAG 2.2, 2.5.8). Touch thresholds are in `references/touch.en.md`.
- **Contrast:** normal text 4.5:1; large text (from 24px, or from 18.66px bold) 3:1; UI components and graphics needed for recognition 3:1 (WCAG 1.4.3, 1.4.11). This skill sets thresholds only; it does not prescribe color choices.
- **Not color alone:** information, states, and errors must also use text, shape, position, or icons (WCAG 1.4.1).
- **Visible focus:** controls that receive keyboard focus must show a visible focus indicator (WCAG 2.4.7).

**Layout breakpoints:** inherit the project's breakpoints if they still serve the content and interactions. Add or change one only when one of these conditions occurs: content overlaps or is clipped; label–value relationships become unclear; essential controls are no longer usable. If the project has no breakpoints, place a breakpoint where the content starts to break, not according to a list of devices. Do not infer input method from width; input-specific rules are in the platform files (B). A narrow screen is a layout rearranged by priority, not a scaled-down wide layout. When changing column counts, wrapping, or positions, preserve roles, grouping, priority, and the reading path. Do not shrink the entire UI to preserve its layout; do not impose responsive behavior on output intended for a single fixed size.

**Variable content and states:** for regions whose content or state varies within existing functionality, select the cases that could change the layout: long text (translations, long names), 0/1/many items, empty, loading, error, partial data, add/remove/reorder. For each case, keep the grouping, control scope, alignment references, and selected object clear. A region keeps its expected size when moving between loading and loaded; content appearing or disappearing must not push another control into the spot the user is about to act on. A region's error appears within that region, with a recovery path per the existing flow. Exceptions: not every UI must have every state; do not add retry, sorting, or new flows on your own; deliberate repositioning for the task is still allowed. Failure: data finishing loading pushes another button under the pointer; removing a middle card makes the remaining tools look as if they belong to another card.

**Overlays and scroll regions:** when there are scroll regions, fixed/sticky elements, or overlays (menus, popovers, tooltips, modals, drawers), identify which region scrolls, which is anchored, and which layer covers which. Required: an overlay is not clipped by its container and shows all its content or scrolls internally; anchored elements do not obscure the focused control, the point of interaction, or the path forward (WCAG 2.4.11); a layer that blocks the background has a clear way to close; do not create two nested scroll regions in the same direction unless needed. Exceptions: a modal that intentionally blocks the background per the existing flow is valid; do not require a specific portal or API. Failure: a menu opened at the bottom of a panel loses its lower items to clipping; a sticky bar covers the field being typed in.

**Orientation during transitions:** when the task affects screen transitions, panel opening, modes, or layout, preserve enough identifying cues and context for users to recognize where they are, which object they are interacting with, and which mode is active. Keep the path forward or back clear within the existing flow; element positions do not have to stay fixed. Use headings, status, active selections, or existing cues where appropriate. Do not add intermediate screens, confirmation steps, or animation solely to express a transition.

When assigned implementation, translate design relationships into layout constraints in the existing technology, reusing components/tokens and project conventions. Do not introduce frameworks, dependencies, or abstraction layers on your own.

## F. Verification and Handoff

Check the relationships and usage conditions affected by the change using tools and data actually available. Combine geometric checks with inspection at actual usage size when possible. If you cannot open the interface, test a device, or measure directly, state the limitation; do not present inference as a tested result.

For the affected region, check elements within their groups and groups within the relevant whole: do size, emphasis, space, and controls still clarify the primary object and relationships between parts? If the change involves screen transitions, modes, or layout, recheck orientation cues and the scope of controls. Extend verification only to directly affected relationships; do not turn a local change into a review of the entire interface or flow.

**Tests:** choose tests according to the scope of the change.

| Test        | Method                                                                                          | Passes when                                                                                       |
| ----------- | ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Squint      | Blur or shrink a screenshot until the text is unreadable                                        | The primary region, secondary regions, and major groups are still recognizable in priority order; the primary focal point is seen first |
| Skeleton    | Replace text with plain blocks                                                                  | Hierarchy and grouping still read from position, size, and space                                  |
| 5-second    | Look at the screen for about 5 seconds, then answer                                             | Can say what the screen is, what the primary object is, and where the next action is              |
| Task path   | Walk through a representative task with the input methods in scope (mouse, touch, keyboard)     | Focus follows the task sequence and is always visible; no information needed for a decision is skipped |
| Edges and layers | Open overlays near container edges; scroll past anchored regions; view both sides of each relevant breakpoint | Nothing is clipped, obscured, or overlapping                                       |

State which tests were run on the real interface and which were only inferred from code or images. A 5-second test answered by the agent itself is recorded as a self-assessment, not a user test.

**Before and after:** when modifying an existing UI and the interface can be opened, record the affected region before the change with screenshots or suitable measurements. Compare after the change at the same viewport size, data, state, and scroll position when these affect the result. Identify the relationships that changed, the direct relationships that must be preserved, and the interactions rechecked. If conditions cannot be kept identical, state the differences and the limits of the comparison. New designs do not require a before image. Failure: comparing a desktop before-screenshot with a mobile after-screenshot and concluding the layout improved.

**Review:** each finding records all of the following.

- **Location:** the element or region.
- **Reference:** a rule of this skill, `DESIGN.md`, WCAG, or an element with the same role.
- **Observation → consequence → remedy:** give the remedy only when supported by evidence.
- **Severity:** P0 blocks the task, causes data loss, or is inaccessible; P1 can be completed but is error-prone or requires seeking help; P2 slows the user, causes temporary confusion, or deviates from the system; P3 visual deviation with no effect on the task.
- **Evidence:** actual measurement, observation from an image, or a hypothesis to verify.

Order findings from P0. Suggested fix order: P0; missing states; system deviations; visual inconsistencies. Briefly note "What is working" so that correct parts are not broken during fixes. Do not assign an overall score. Do not invent coordinates, baselines, or interaction results. Measurements in image coordinates are acceptable if explicitly identified as image measurements rather than product layout units.

Tailor the handoff to the task:

- **New design:** provide a proposal sufficient for use or implementation and explain key layout decisions, including the chosen screen type.
- **Local changes and refinement:** state what changed, the tests run, the before–after results, and remaining limitations.
- **Review:** provide findings in the format above; do not make edits when assigned review only.

Use a guide map or alignment overlay when it helps clarify relationships and can be produced. Do not require every task to generate diagrams or lengthy reports. When assigned implementation, explanations do not replace the actual result.

Compare the reviewed or modified region against confirmed rules in `DESIGN.md`. When writing is authorized, update the file if there is a newly approved decision or a missing confirmed rule; preserve unrelated content. Do not change rules to legitimize a nonconforming UI. Report each review's results separately rather than turning `DESIGN.md` into a review log.

# Verification: tests, before–after, review

Read when checking a change, comparing before and after, or reviewing. The scope of verification and the handoff are in section F of `SKILL.md`.

## Tests

Choose tests according to the scope of the change.

| Test        | Method                                                                                          | Passes when                                                                                       |
| ----------- | ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Squint      | Blur or shrink a screenshot until the text is unreadable                                        | The primary region, secondary regions, and major groups are still recognizable in priority order; the primary focal point is seen first |
| Skeleton    | Replace text with plain blocks                                                                  | Hierarchy and grouping still read from position, size, and space                                  |
| 5-second    | Look at the screen for about 5 seconds, then answer                                             | Can say what the screen is, what the primary object is, and where the next action is              |
| Task path   | Walk through a representative task with the input methods in scope (mouse, touch, keyboard)     | Focus follows the task sequence and is always visible; no information needed for a decision is skipped |
| Edges and layers | Open overlays near container edges; scroll past anchored regions; view both sides of each relevant breakpoint | Nothing is clipped, obscured, or overlapping                                       |

State which tests were run on the real interface and which were only inferred from code or images. A 5-second test answered by the agent itself is recorded as a self-assessment, not a user test.

## Before and after

When modifying an existing UI and the interface can be opened, record the affected region before the change with screenshots or suitable measurements. Compare after the change at the same viewport size, data, state, and scroll position when these affect the result. Identify the relationships that changed, the direct relationships that must be preserved, and the interactions rechecked. If conditions cannot be kept identical, state the differences and the limits of the comparison. New designs do not require a before image. Failure: comparing a desktop before-screenshot with a mobile after-screenshot and concluding the layout improved.

## Review

Each finding records all of the following.

- **Location:** the element or region.
- **Reference:** a rule of this skill, `DESIGN.md`, WCAG, or an element with the same role.
- **Observation → consequence → remedy:** give the remedy only when supported by evidence.
- **Severity:** P0 blocks the task, causes data loss, or is inaccessible; P1 can be completed but is error-prone or requires seeking help; P2 slows the user, causes temporary confusion, or deviates from the system; P3 visual deviation with no effect on the task.
- **Evidence:** actual measurement, observation from an image, or a hypothesis to verify.

Order findings from P0. Suggested fix order: P0; missing states; system deviations; visual inconsistencies. Briefly note "What is working" so that correct parts are not broken during fixes. Do not assign an overall score. Do not invent coordinates, baselines, or interaction results. Measurements in image coordinates are acceptable if explicitly identified as image measurements rather than product layout units.

Use a guide map or alignment overlay when it helps clarify relationships and can be produced. Do not require every task to generate diagrams or lengthy reports. When assigned implementation, explanations do not replace the actual result.

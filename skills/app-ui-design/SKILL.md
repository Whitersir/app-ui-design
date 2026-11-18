---
name: app-ui-design
description: Aesthetic-first UI design for websites, web apps, desktop, mobile, and terminal interfaces. Use when building, redesigning, polishing, or reviewing any user-facing interface, including landing pages, dashboards, admin panels, Electron/Tauri, Flutter, React Native, SwiftUI, Qt, and TUI apps. Default design skill for UI work; combines visual taste rules with platform usability checks.
---

# UI Design with Taste

Ground the visual direction in the product. Use the platform's familiar interactions and judge visual quality on the rendered interface whenever possible.

## Workflow

Route by scope first. A **review** stops after inspection: produce findings and proposed fixes ranked by impact, no edits. A **polish or small change** keeps the existing visual system and tokens — skip steps 2–4, run steps 5–8. Only a **new build or redesign** runs the full workflow.

1. Read the existing UI, components, design tokens, and real content first. A redesign changes the visual language but preserves working flows, content, and data. Follow a named design skill or supplied design system when the user requires one. If the screen is already good, say so and propose small refinements instead of forcing a redesign.
2. Ground the design in the subject: name what the product is, who uses it, and its one primary action. Derive the palette and visual material from the subject's own world (its industry, materials, content), not from habit. Pick ONE style direction from [Style recipes](references/styles.md) as scaffolding and state it in one sentence. Mirror test: if a neighboring product in the same category would get this exact combination, change one decision and say which. When the user supplies reference screenshots or sites, extract their system — palette roles, type contrast, spacing, density, motion feel — never their content, code, or signature effect.
3. Inventory the material: what is real (given facts, numbers, assets) and what is absent (logos, quotes, metrics nobody supplied). Absent proof stays absent — never invent metrics, testimonials, or customer logos; label stand-in images as stand-ins.
4. Define or reuse design tokens for the target platform before building UI. Adapt the recipe's hierarchy, spacing, and color roles to the product. Include radius and elevation for surfaces that use them. Then review the plan against the brief before coding: any part that reads like the default you would produce for any similar project gets revised, and say what changed.
5. Build with real copy and realistic data: uneven names, long labels, empty cells, 3-digit counts. Lorem ipsum and perfectly uniform fake data hide the layout problems that matter. Write copy as design: buttons are a verb plus an object ("Save changes", not "Submit"), an action keeps its name through the flow (Publish → Published), errors say what happened and what to do next without apologizing.
6. Check the changed surface against [Anti-patterns](references/anti-patterns.md) using the entries relevant to its platform and the current scope. Give the brief, accessibility requirements, the existing design system, and native conventions precedence over aesthetic defaults. Limit a polish pass to the requested surface.
7. Render and look whenever the environment allows. Screenshot the result (use the webapp-testing skill for web UI, the app's normal entry point or preview for apps). Critique against the hierarchy rules below and the self-critique pass in anti-patterns.md; batch all fixes from one look into one round, then look again — at most three rounds. For new or changed motion, read the shared guidance and the matching section in [Motion rules](references/motion.md).
8. Run the matching checks in [Platform patterns](references/platforms.md) on the changed flow for Web, desktop, mobile, or interactive terminal. In an app with an HTML renderer, use Web checks for the rendered surface and the host platform's checks for affected native behavior.
9. When the user approves, record reusable design corrections as rules with their reasons in the project's DESIGN.md (create it if absent), so later sessions do not repeat the mistake. Do not write project files as a side effect of an unapproved task.

## Hierarchy rules

- One focal point per screen. Decide what the eye hits first, second, third; everything else recedes. If every card, button, and section claims equal weight, the design has no hierarchy — demote most of them.
- Create contrast with size and weight before color. On display and marketing surfaces, display text at least 2.5x body size — timid 1.2x steps read as accidental. Tools, native app screens, and terminals follow their own density instead: hierarchy from gray steps, weight, and the recipe's scale, not headline jumps.
- One accent color, used sparingly for the primary action and key status. Neutrals carry the interface. A second saturated color needs a semantic reason (error, success), not decoration.
- Group with whitespace and alignment; separate with a hairline border or a background step. Reach for shadows only on genuinely floating layers (popovers, dialogs, dragged items).
- Commit to one alignment grid and one spacing scale. Optical alignment beats mathematical centering for text next to icons.
- Spend boldness in exactly one place per screen — an oversized headline, a full-bleed image, an unusual layout move. Everywhere-bold equals nowhere-bold.
- Density is a style choice, not a virtue or a sin. Match it to the job: a comparison table used all day wants density; a first-run screen wants air.

## Verification

One rule: verify on the real rendered interface whenever it can run; when it cannot, report the gap honestly.

- Inspect the rendered result at representative sizes for the target (wide desktop, narrow laptop, phone width, narrow terminal) and with the relevant input methods.
- Verify one complete primary flow plus the empty, loading, and error states that were changed.
- If only code or a static preview could be inspected, state explicitly which visual and platform behaviors remain unverified. Never claim visual success from code review.

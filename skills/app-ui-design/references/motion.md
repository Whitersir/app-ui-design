# Motion rules

## Shared guidance

Use motion to show what changed or where an object moved. Keep frequent actions such as list selection and keyboard commands responsive. Respect the target platform's reduced-motion preference where available and keep content accessible when motion is reduced. Pause ongoing effects when their surface is off-screen or hidden.

## Web and HTML renderers

Treat the timing values as starting points and adapt them to the surface and interaction.

### Easing and duration

- Enter: ease-out, e.g. `cubic-bezier(0.16, 1, 0.3, 1)`. Never ease-in for an entrance — it reads as sluggish.
- Exit: ease-in, and faster than the enter (roughly 60–75% of its duration). Things leave quicker than they arrive.
- On-screen movement / layout change: ease-in-out or a spring; linear only for continuous loops, progress, and marquees.
- Durations: press/hover feedback 100–200ms; enter/exit 200–350ms; large layout or panel moves 300–500ms. Nothing the user triggered waits longer than 500ms.
- Stagger lists at 30–50ms per item, capped so the last item starts within ~300ms. Never stagger a list the user scans repeatedly.

### What may move

- Prefer `transform` and `opacity` for visual motion. Name the properties in each transition. When an expanding panel needs to reflow surrounding content, keep the layout animation local and check its performance.
- Elevation is a layered semi-transparent shadow (e.g. `0 1px 2px rgba(0,0,0,.06), 0 8px 24px rgba(0,0,0,.08)`), not a solid gray border pretending to be depth.
- Where hover is available, a background step or 1–2px lift can provide feedback. Keep keyboard focus visible immediately. Provide equivalent pressed feedback for touch.
- Drag and swipe track the finger 1:1 and carry release velocity; an in-flight animation can be caught and reversed mid-way.

### Choreography

- One orchestrated entrance per page (the hero), not a fade-and-slide-up on every section. Scattered section reveals are the generic AI default.
- Nothing moves because the page scrolled, except one deliberate scroll-driven moment the design is built around. No scroll-jacking, no parallax on text.
- Make animations that loop longer than 5s pausable. Use `prefers-reduced-motion` to apply the shared guidance to web content.

### Performance

- Keep layout reads outside animation frames. For WebGL or canvas scenes, cap concurrent contexts (4 max) and device pixel ratio (2 max).
- Reuse materials, geometry, and listeners. Use one `requestAnimationFrame` loop per scene and stop it when the scene is removed.

## Native desktop and mobile

- Use the platform or framework's transitions for navigation, dialogs, and expanding controls. On desktop, keep focus stable during a transition. On mobile, let drag and swipe follow the gesture and support interruption where the framework provides it.
- Follow the system's reduced-motion setting. Prefer immediate state feedback or a lightweight transition for controls used repeatedly.

## Interactive terminal

- Update focus, selection, and action results immediately. Use timed updates for meaningful work such as progress, and stop them when the work is finished or the view is dismissed. Keep status readable as text when animation is disabled.

# Anti-patterns: the default AI look

Apply the relevant checks to the rendered surface in scope. Use CSS, browser-unit, and landing-page examples for Web and HTML-rendered surfaces. For native apps, translate the visual intent into the project's type, components, and interaction conventions. For terminals, judge hierarchy through text, spacing, alignment, and selection cues in the cell grid.

**Calibration — defaults move.** These looks were fresh once and are now themselves AI tells: cream paper (`#F4F1EA`-ish) + high-contrast serif + terracotta accent (`#D97757`-ish); near-black + a single acid-green or vermilion accent; broadsheet hairline rules with zero radius everywhere; the SaaS-card kit. When a style recipe lands on one of these, derive the palette from the subject and change at least one structural decision — do not ship the recipe untouched.

## Color

- **Purple/indigo gradient backgrounds** (`#667eea → #764ba2` and relatives), gradient text on headlines. → Solid background from the chosen recipe; if a gradient is truly warranted, keep it within one hue family and barely perceptible.
- **The default AI palette**: white/slate background + Inter + one bright blue/violet accent. → Commit to the recipe's palette, including its neutrals (warm gray, cool gray, tinted off-white — pick deliberately).
- **Rainbow feature icons**: each card gets a different pastel icon chip (blue, green, orange, purple). → Monochrome icons; color only for semantic state.
- **Glassmorphism by default**: frosted cards, blurred translucent panels everywhere. → Opaque surfaces with a clear background step; glass only for genuine overlay chrome, once.
- **Pure `#000` on pure `#fff`** for long-form text surfaces. → Near-black on off-white, or the recipe's dark surface values.

## Typography

- **A generic type hierarchy on a custom-branded surface.** → Use type roles and weights deliberately. A distinctive display face can help when the project calls for custom typography. Use system fonts where the platform or design system expects them.
- **Timid scale**: everything between 14px and 24px. → Real contrast: display 40–72px (web) against 15–16px body, or the dense-tool scale done consistently.
- **Centered paragraphs of body text.** → Left-align (or rag-right) body; center only short headlines and deliberate moments.
- **ALL-CAPS labels without letter-spacing**, or letter-spacing on lowercase body. → Caps labels get +0.05–0.08em tracking; body gets none.
- **Emoji as icons** in buttons, headings, feature lists, empty states. → A real icon set (Lucide, Heroicons, SF Symbols, platform icons) at one consistent stroke weight, or no icon.

## Layout

- **The universal landing skeleton**: centered hero headline + subtext + two buttons, then a 3-column feature card grid, then testimonials, then CTA banner. → Choose a layout from the content: asymmetric hero, editorial split, product-screenshot-first, dense dashboard. Break the grid at least once, deliberately.
- **Every card identical**: same radius, same padding, same shadow, same weight, repeated in a grid. → Vary span and emphasis by importance; the primary item earns size, the rest stay quiet.
- **`rounded-2xl` + `shadow-md` on everything.** → One radius scale (e.g., 4/8/12 or 0 throughout); shadows only on floating layers. Flat with hairline borders is a valid, often better, choice.
- **Uniform generous padding everywhere** producing a sea of sameness. → Spacing encodes grouping: tight within a group, generous between groups.
- **Dead-center single column on a 1440px screen** for a tool/dashboard. → Use the width: panes, tables, side rails. Marketing pages may constrain measure (~65–75ch for prose), tools should not.

## Components & content

- **Lorem ipsum, "Feature One/Two/Three", "John Doe", perfectly round fake numbers.** → Real or realistic content with uneven lengths; design for the long label and the empty cell.
- **Buttons everywhere with equal fill**: three filled primary buttons in one view. → One filled primary per view; secondary = outline or quiet; tertiary = text.
- **Decorative stats bars** ("10k+ users, 99.9% uptime") invented to fill space. → Only real numbers; otherwise remove the section.
- **Stock-photo hero of smiling people at laptops.** → Real product UI, real photography relevant to the domain, or a confident typographic hero.
- **Spinner-only loading and "Oops! Something went wrong" errors.** → Skeletons matching the layout; errors that say what happened and what to do next.

## Copy

- **Slop words**: "Unlock", "Elevate", "Supercharge", "Seamless", "Empower", "Next-gen", "Revolutionize". → Say plainly what the thing does, in the product's own voice.
- **Vague CTAs**: "Submit", "Click here", "Learn more" as the only action. → Verb + object: "Save changes", "Download report". The action keeps its name through the flow (Publish → Published).
- **Decorative chrome text**: an ALL-CAPS tracked eyebrow above every heading, meta strings joined with middle dots ("A · B · C"), "WORD — fragment" labels, a "→" glued to every link. → Remove, or keep only where the content genuinely needs that structure. Numbered markers (01 / 02 / 03) only when the content really is a sequence.
- **Invented proof**: fake metrics, testimonials, customer logos, "trusted by" walls. → Absent proof stays absent; use real numbers or none.
- **Apologetic or vague errors** ("Oops! Something went wrong") and mood-only empty states. → State what happened and the next step; an empty screen is an invitation to act.

## Motion

- **Repeated entrance effects and ambient loops that compete with the task.** → Use motion to clarify an interaction or a state change. Follow the matching platform section in [Motion rules](motion.md).
- **Web transitions that animate unrelated properties or trigger repeated layout.** → Name the changing properties and prefer `transform` and `opacity` for visual movement.
- **Solid gray borders standing in for depth.** → Layered semi-transparent shadows on genuinely floating layers.

## Self-critique pass

After screenshotting, answer in order:
1. Where does the eye land first? Is that the intended focal point?
2. Which banned pattern above is present? Remove or justify it.
3. What can be deleted (a border, a shadow, an icon, a color, a whole section) without losing meaning? Delete it.
4. Does anything look like a template default — including the calibration looks? Replace it with a decision derived from the subject.
5. Would the longest name, an empty list, a 6-digit count, or a one-letter label break this layout? Fix what breaks.

For a polish or redesign pass, work in this order so earlier fixes are not undone by later ones: spacing → color → type → icons → copy → layout → details → visuals → motion.

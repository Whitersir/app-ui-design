# Style recipes

Pick ONE direction per product. Values are concrete starting points, not a house style: derive the actual palette from the subject's world (its industry, materials, content) and keep the recipe's structure and scale. Fonts listed are real and freely available (Google Fonts unless noted); ship the weights you use.

Use the CSS sizes, font pairings, and layout values as Web examples. For native apps, express the chosen hierarchy with the platform's text roles, controls, and spacing. In interactive terminals, use rows and columns, alignment, emphasis, and selection cues. An existing design system supplies the values for the surfaces it covers.

**These recipes can become slop too.** Editorial cream + serif + terracotta and technical near-black + acid green are current AI defaults (see the calibration note in anti-patterns.md). When a recipe lands there, shift the palette to the subject and change at least one structural decision. Mirror test before building: would a neighboring product in the same category get this exact combination? If yes, change one thing and say which.

## 1. Editorial / print

For: content products, publishing, portfolios, marketing sites with a voice, premium consumer brands.
Steal from: Stripe press pages, Read.cv, magazine layouts, NYT graphics.

- Display: a serif with personality — Fraunces, Newsreader, or Source Serif 4. Body: a quiet sans — Inter Tight, Public Sans, or IBM Plex Sans.
- Scale: display 48–72px (weight 500–600, tight leading 1.05–1.15), section titles 24–28px, body 16–17px / 1.6. Prose measure 65–75ch.
- Palette: paper off-white tinted by the subject (warm `#FAF7F2` is one option, not the default — a maritime product earns a cool tint), ink `#1C1917`, muted `#78716C`, one deep accent drawn from the subject's world (e.g., oxblood `#7F1D1D`, forest `#14532D`, marine `#1E3A5F`). No bright saturated colors; terracotta `#D97757`-ish is a known AI tell, avoid it unless the subject truly owns it.
- Structure: hairline rules (`1px #E7E5E4`) instead of cards and shadows. Radius 0–4px. Generous vertical rhythm (sections 96–160px apart on desktop). Asymmetric columns; let one element break the grid (pull quote, full-bleed image).
- Signature move: an oversized serif headline set against small, quiet metadata in mono or caps.

## 2. Dense tool

For: dashboards, admin panels, dev tools, finance, anything users operate for hours.
Steal from: Linear, Things 3, Height, Bloomberg-lite.

- One family, two weights max: Inter Tight, Geist, or IBM Plex Sans. Mono for numbers/IDs: Geist Mono, IBM Plex Mono, JetBrains Mono.
- Scale: body 13–14px / 1.45, labels 11–12px caps +0.06em (data labels in a tool only — never a decorative eyebrow on a marketing page), page titles 18–20px. Hierarchy comes from gray steps and weight, not size jumps.
- Palette (dark-first): bg `#0F1011`, raised `#17181A`, border `#26282B`, text `#E6E7E8`, muted `#8B8E93`, one accent used only for selection/primary (e.g., `#5E6AD2` Linear-style, or pick brand hue). Light variant: bg `#FCFCFD`, border `#E4E5E8`.
- Structure: radius 6px, no shadows except popovers/dialogs. Row heights 32–40px, cell padding 8–12px. Hairline borders; zebra striping only if rows exceed ~10 visible.
- Signature move: keyboard-first affordances — visible shortcuts, command palette, focus rings that are actually designed (2px accent, 2px offset).

## 3. Warm consumer

For: lifestyle apps, food, health, community, onboarding-heavy products.
Steal from: Duolingo's restraint (not its cartoon), Airbnb, Headspace.

- Display: a rounded or humanist face — Nunito Sans, Quicksand (headings only), or Sora. Body: Inter or DM Sans.
- Scale: display 32–44px, body 16px / 1.55. Friendly but not shouty.
- Palette: cream `#FFF8F0` or soft tint bg, ink `#292524`, one saturated accent (coral `#F0563C`, green `#3E9B4F`, or brand), secondary tints of the SAME hue for chips/backgrounds. Semantic colors stay standard.
- Structure: radius 12–16px on cards, full-round on buttons and chips. Soft shadow only on the primary card or floating action (`0 4px 16px rgba(0,0,0,0.08)`). Illustration or photography with a consistent treatment, never mixed stock styles.
- Signature move: one playful detail (a hand-drawn underline, a mascot moment in the empty state) — exactly one, not a theme park.

## 4. Technical / mono

For: CLI-adjacent tools, infra products, docs, data products, developer brands.
Steal from: Vercel, Fly.io, Charm, Warp.

- Mono for display and labels (JetBrains Mono, Geist Mono, IBM Plex Mono), clean sans for body (Geist, Inter Tight).
- Scale: display 28–40px mono, body 15px. Terminal-adjacent UI: respect the cell grid.
- Palette: near-black `#0A0A0A`, off-white `#EDEDED`, gray steps for structure, one signal color (terminal green `#4ADE80`, amber `#FBBF24`, or brand) used like a status LED — tiny doses.
- Structure: radius 0–6px, 1px borders, visible grid/section numbering (`01 /`, `[config]`) only where the content really is a sequence or labeled config, ASCII-adjacent dividers. Dark default, light optional. The acid-green-on-near-black combo is a current AI tell — pick the signal color from the subject (a payment tool's amber, an audio tool's waveform hue).
- Signature move: real terminal output or code as the hero visual, syntax-highlighted with a coherent 4–5 color scheme.

## 5. Bold brand

For: launches, campaigns, products whose brand IS the product.
Steal from: Arc, Teenage Engineering, x.ai, Figma marketing.

- One expressive display face (Clash Display, Space Grotesk, Archivo Expanded — or the brand face) + neutral body.
- Scale: display 64–120px web, tight tracking (-0.02em), leading 0.95–1.05. Body stays 16px and quiet — the contrast IS the design.
- Palette: either full-bleed single hue with black/white type, or stark white with one electric accent. Commit fully; half-bold reads as a mistake.
- Structure: oversized type as layout element, deliberate asymmetry, one huge image or product render. Everything else minimal.
- Signature move: a single scroll or hover moment with real motion (200–400ms, ease-out, respects reduced-motion). No ambient animation loops.

## Choosing

- Users operate it daily → Dense tool. Users read it → Editorial. Users feel it → Warm consumer. Users build with it → Technical. Users are being sold to → Editorial or Bold brand, depending on voice.
- Existing brand assets override recipe palettes; keep the recipe's structure and scale.
- When the user asks for alternatives, produce 2 directions from this list, not 3 shades of the same one.

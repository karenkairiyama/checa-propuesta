# Karen Kairiyama — Design System

> Estrategia de contenido y posicionamiento de marca
> para estudios de arquitectura y real estate en Argentina.

Karen Kairiyama is a one-person consultancy: she helps **architecture studios** and **real-estate developers in Argentina** find their voice, position their work, and write the content that surrounds the buildings they make. The brand expression sits between a quiet architecture monograph and a fashion-magazine masthead — minimalist, editorial, intentional.

This design system encodes that expression so every artefact — pitch decks, the marketing site, social grids, client proposals — comes out looking like it belongs to the same studio.

---

## Sources

We were given:

- **Brand spec (chat)** — palette, type, accent rules. Verbatim from the brief:
  > Paleta de dos colores: `#0D0D0B` (negro profundo) y `#F5F0D0` (crema amarillento). Tipografía principal: Outfit (Black for títulos, Light for subtítulos, Regular for body). Tipografía emocional: Cormorant Garamond Light Italic. Acento puntual: `#C4956A` (terracota) solo para highlights y CTAs. Estilo: minimalista, editorial, oscuro. Secciones alternan entre fondo negro y fondo crema. Sin grises ni colores intermedios. Sin border-radius grandes.
- **Palette revision (chat, follow-up)** — accent swapped from terracota `#C4956A` to **dark chocolate `#8B4A2E`**. The chocolate version is what every token, asset, and component in this system reflects.
- **`uploads/Outfit_Complete.zip`** — full Outfit family (Thin → Black) in OTF/TTF/WOFF/WOFF2. Extracted into `fonts/` (web formats only).

We were **not** given Cormorant Garamond font files. They are loaded from Google Fonts (`Cormorant+Garamond` 300 / 300 italic / 400 italic). **Flag for Karen**: if you have a self-hosted copy of Cormorant Garamond Light Italic, drop the file(s) into `fonts/` and we'll switch the `@font-face` block.

We were not given any existing screens, decks, logo files, or photography. Logos, slide templates, and the marketing-site UI kit in this project are **proposed expressions** of the spec, built to be edited.

---

## Index

```
.
├── README.md                  — this file
├── SKILL.md                   — entrypoint for Claude Skills / Code
├── colors_and_type.css        — single source of truth for tokens
├── fonts/                     — Outfit web fonts + OFL license
├── assets/                    — logos, marks, favicon
├── preview/                   — Design-System-tab cards (one concept each)
└── ui_kits/
    └── site/                  — marketing-site UI kit + index.html
```

Browse cards via the **Design System** tab, or open any file in `preview/` directly.

---

## CONTENT FUNDAMENTALS

Karen sells **experiencia de marca**. Her own copy is the demo: it has to feel like the writing she'd hand a client.

These notes are extracted from her actual writing samples (bio, captions, prospect emails). Match her patterns; don't invent a new tone.

### Language
- **Spanish, neutral rioplatense.** Doesn't push voseo. Uses neutral "tu" forms — "te interesa", "tu marca". "Estuve revisando", "Hola Juan!" — friendly but not slangy.
- **English** is allowed as a single technical word inside Spanish ("branding", "IA"). Never a whole English phrase, never marketing jargon ("engagement", "storytelling" as nouns).

### Voice
- **First person singular.** "Me interesa…", "Estuve revisando…", "Actualmente trabajo…", "Creo que…". She is the studio. No "nosotros", no "el equipo".
- **Two-step pattern: observation → personal stance.** Open with a general statement about brands or the market, then drop into "Me interesa…" / "Creo que…":
  > *Las marcas ya no compiten solo por atención. Compiten por percepción, experiencia y conexión emocional. Me interesa construir universos digitales que se sientan coherentes, humanos y visualmente sólidos.*
- **Frames opportunities, not problems.** "Hay oportunidades muy interesantes para ordenar X" — never "tu marca está mal". The diagnosis arrives as a list of openings.
- **Confident but warm.** "Creo que" — opinion-as-conversation, not assertion. Strategic without being corporate.
- **Greetings can carry `!`** ("Hola Juan!"). The "no exclamation" rule is about not shouting (`¡increíble!`, `¡bienvenidos!`) — not about banning the character.

### Sentences
- **Short. Declarative.** Often a denial + redirection: *"X ya no Y. X Z."*
- **Comma and period.** No em-dashes, no ellipses, no semicolons. (This is a real tonal marker — she does not reach for `—`.)
- **Lists with simple hyphens** (`- punto`) when enumerating opportunities or deliverables.

### Casing
- **Display headlines** in the visual system are UPPERCASE Outfit Black via CSS — when writing the headline as copy, type it sentence-case and let the layout uppercase it.
- **Body, captions, emails: sentence case.** Never Title Case In Spanish.
- **Eyebrows / labels:** uppercase letter-spaced (`0.22em`). Used for section numerals and category tags.

### Recurring vocabulary (her words — prefer these)
- **experiencia de marca · presencia digital · comunicación digital**
- **percepción · conexión emocional · universos digitales**
- **mirada estética y estratégica**
- **coherente · humano · sólido · aspiracional**
- **ordenar** (preferred verb for "improve / clean up")
- **construir** (preferred verb for what she does)

### Three formulae (templates from her own writing)

**BIO** — third-person role, first-person interest, present-tense practice:
```
Creativa digital enfocada en [X].
Me interesa la intersección entre [A], [B], [C].
Actualmente trabajo desarrollando [Y] para marcas con [Z].
```

**CAPTION** — general observation → personal stance → no CTA:
```
Las marcas ya no compiten solo por [X].
Compiten por [A], [B] y [C].

Me interesa construir [Y] que se sientan [adj1], [adj2] y [adj3].
```

**EMAIL / DM** — warm greeting, "estuve revisando", a bullet list of opportunities, framing line:
```
Hola [nombre]!
Estuve revisando [contexto] y creo que hay oportunidades muy interesantes
para ordenar [área].

Por ejemplo:
- [punto 1]
- [punto 2]
- [punto 3]

La idea es que [marca] no solo [acción básica],
sino también [valor mayor].
```

### Emoji
- **Never.** Not even on social. The brand is built on the absence of decoration. A single cream dot beats any emoji.

### Vibe (with examples — adapted from her real writing)
| Off-brand | On-brand |
|---|---|
| "¡Posicioná tu marca con nosotros 🚀!" | "Me interesa construir universos digitales que se sientan coherentes, humanos y visualmente sólidos." |
| "Servicios de branding 360°" | "Trabajo desarrollando identidades y presencia digital para marcas con mirada estética y estratégica." |
| "Tu marca al siguiente nivel ✨" | "La idea es que tu marca no solo comunique proyectos, sino también percepción, estilo y experiencia de marca." |
| "Vamos a mejorar tu Instagram" | "Hay oportunidades muy interesantes para ordenar la experiencia de marca y la comunicación digital." |

### What we never say
- **"Soluciones a medida"** / **"360°"** / **"Engagement"** / **"Storytelling"** (as a noun).
- **"Equipo apasionado / multidisciplinario."** Karen is the studio.
- **"Tu marca al siguiente nivel."** Never.
- **"Click acá / Hacé click."** Use a verb of action: "Conversemos.", "Veamos juntos.", "Te escribo."
- Adjective stacks like "increíble, fantástico, asombroso." She uses precise adjectives — *sólido, aspiracional, coherente, humano*.

---

## VISUAL FOUNDATIONS

The system is **two colours + two utility neutrals + one type family**, with a theme switcher that flips the whole site between dark and light. Editorial luxury minimalism — fashion-tech, contemporary-architecture vibe. Impact comes from size, air and motion, never from weight.

### Colour
- **`#0D0D0B` Ink** and **`#F5F0D0` Cream** are the two anchors. They swap roles between dark mode (bg=ink, fg=cream) and light mode (bg=cream, fg=ink). The site is single-theme at a time — no longer alternating section by section; the user picks one via the theme toggle.
- **Utility neutrals** for muted text and subtle borders — same tonal family, not chromatic accents:
  - `#A89B70` **Recess (dark)** — beige cálido, used for secondary copy and italic accents on ink.
  - `#7A6F4A` **Recess (light)** — beige oscuro, the equivalent on cream.
  - `#2A2724` **Smoke (dark)** — hairline divider on ink (or use `rgba(245,240,208,0.10)`).
  - `#D9D2B0` **Smoke (light)** — hairline divider on cream (or use `rgba(13,13,11,0.10)`).
- **No third chromatic colour.** Emphasis lives in contrast (cream-on-ink, ink-on-cream), italic Cormorant accents, and the recess tones.
- **No gradients.** Exception: an extremely subtle radial **glow** (`--kk-glow` at 5–10% opacity) behind the hero — barely a halo, never a colour wash.
- **Imagery:** warm, slightly desaturated, with visible grain. B&W always acceptable. Aspect ratios `4:5` portrait or `16:9` cinematic. No square. No bright saturation.

### Typography — *impact from size, not weight*
- **Outfit Regular (400)** for all headlines, displays, and body. This is the system's strongest tonal choice.
- **Outfit Light (300)** for body-large, subheads, longer captions.
- **Outfit Medium / Bold / Black** are available but **rarely used.** Reach for them only when a UI element genuinely demands more weight (e.g. a number badge); never for headlines.
- **Sentence case for titles.** No `TEXT-TRANSFORM: UPPERCASE` on headlines, hero, services, work cards, footer mark. Uppercase stays only on **eyebrows** (small tracked labels — "01 — Servicios") and remains valid for SVG wordmark variants when chosen.
- **No Cormorant Garamond italic in the live system.** It's still available in the CSS for legacy use, but the design now prefers tonal contrast (text in `var(--kk-recess)` for accent words) over font-style or family changes. Italic feels too decorative for the contemporary editorial direction the brand wants.
- **Tracking:** display `-0.025em`, headings `-0.022em`, eyebrows `+0.22em` (wide, uppercase). Body at `0`.
- **Line-height:** `0.95–1.05` for display, `1.1` for headings, `1.55–1.6` for body.
- **Buttons** are sentence case with subtle tracking (`0.02em`) — no uppercase pills.
- **Headlines feel premium because they're big, calm, and well-spaced — not because they're heavy or shouted.**


### Theme switcher
- A single source of truth: `<html data-theme="dark|light">`. Every colour token rebinds.
- Default is **dark**; preference persists in `localStorage('kk-theme')`.
- Theme transition: `500ms cubic-bezier(0.22, 1, 0.36, 1)` across background, color, border, fill, stroke. The whole site fades together — no flicker.
- The toggle itself: `56×28px` pill with a moving dot. Subtle glow on hover. Lives in the top-right of the top bar, paired with the wordmark on the left.

### Layout
- **Generous outer margins.** Desktop gutters `clamp(24px, 5vw, 128px)`. Whitespace is the brand.
- **Vertical rhythm:** sections pad `clamp(80px, 14vw, 180px)` top/bottom for full breathing.
- **Hero is full `100vh`**, with content distributed `space-between` — eyebrow at top, headline mid, sub + CTA at bottom.
- **Asymmetric placement is encouraged.** Hero glow offset, italic accent at end of headline, lone CTA pill in bottom-right.
- **Fixed elements:** only the top bar (transparent, gains a soft cream/ink overlay after the first `40px` of scroll).

### Corners & borders
- **Radius is `0`.** Cards, images, inputs, modals — all square.
- **One exception:** the CTA pill (`border-radius: 999px`). The contrast tone of the surface, full-bleed, white-space:nowrap.
- Borders are **`1px` hairlines** in the smoke tone or as `rgba(fg, 0.10)`.

### Shadows & elevation
- **No drop shadows.** Elevation = tone contrast + whitespace.
- **Glow** is allowed as an ambient halo behind the hero — never a button glow, never on cards.
- No glassmorphism, no inner shadows, no transparency stacks beyond the rule-opacity tones.

### Hover & press
- **Links and text:** hover drops to `72%` opacity. Press drops to `48%`. A `1px` underline animates in on hover for `.link-quiet`.
- **CTA pill:** hover drops to `86%` opacity + a radial bg shimmer follows the cursor. Press scales to `0.985`.
- **Service rows:** hover translates the row name `+12px`, fades in the description, slides the arrow `+8px`. All over `320ms`.
- **Cards (featured work):** hover scales the inner image `1.04` over `1.2s` with a subtle brightness drop. Outer card never moves.
- **No hover lifts** on text content. The cursor change is the affordance.

### Motion
- **Easing:** `cubic-bezier(0.22, 1, 0.36, 1)` ("ease-out-expo"). Slow, confident, no bounce.
- **Durations:** `180ms / 320ms / 640ms / 1000ms` (curtain). Theme transition `500ms`.
- **Scroll reveals:** every section uses a fade-up of `28px` over `1000ms`, triggered by `IntersectionObserver` once it crosses the viewport. Above-the-fold elements stay visible from first paint — no hidden hero.
- **Parallax:** subtle. Hero glow drifts at `0.3x` scroll speed; portrait images at `0.08x`. No carousel-style parallax — just background drift.
- **Cursor halo (desktop only, `pointer: fine`):** a 32px ring follows the mouse with smoothed easing; grows to 64px filled circle over interactive targets. Uses `mix-blend-mode: difference` so it inverts cleanly on both themes.
- **No flips, no spins, no scale bounces.**

### Cards
- A "card" is a content block, not a Material Design rectangle. **0 radius, 0 shadow.**
- Featured-work cards use full-bleed image with a soft bottom gradient overlay (`rgba(13,13,11,0.65)` to transparent) so the meta text reads on any image.
- Upcoming-project cards use just the smoke→bg-2 gradient and a centred "+ EN DESARROLLO" label.

### Buttons (summary — full coverage in the UI kit)
- **Primary CTA pill:** `background: var(--kk-fg)`, `color: var(--kk-bg)` — automatically inverts with the theme. Outfit Regular, uppercase, `0.20em` tracking. Often paired with an arrow SVG that translates `+4px` on hover.
- **Secondary (link-quiet):** text link with a hairline underline that scales in from left over `320ms`.
- **Tertiary:** uppercase eyebrow — no fill, no underline, often paired with a numeral.
- No outline buttons, no ghost buttons.

### What we never do
- Glassmorphism. Neumorphism. Aurora gradients. Emoji decoration.
- Drop shadows on cards or buttons.
- Rounded cards.
- Outfit Black or Bold in headlines.
- A third chromatic accent colour.
- Stock-photo "team smiling at laptop".

---

## ICONOGRAPHY

The brand is **almost icon-free by design.** A typographic system this tight doesn't need decoration; icons compete with the headlines for attention.

When iconography is unavoidable (a UI menu, a social row, a "next" affordance), we follow these rules:

- **System:** [Lucide](https://lucide.dev) — `1.5px` stroke, square caps, `24×24` viewbox. Loaded from CDN (`https://unpkg.com/lucide-static`) so we don't bundle a font. Lucide's quiet, editorial line weight matches the system; Heroicons-outline is an acceptable substitute.
- **Colour:** ink on cream, cream on ink. There is no third colour to forget. The only icon-shaped use of the contrast tone is a `6px` filled circle used as a bullet / status dot.
- **Size:** `16px`, `20px`, or `24px`. Nothing larger; if you want a big graphic, use a photograph.
- **Stroke + fill rule:** stroke-only icons. No two-tone, no fills.
- **Emoji:** never. Not even in informal posts.
- **Unicode glyphs:** the em-dash ( — ), the middle-dot ( · ), and the arrow ( → ) are explicitly part of the type system — used in eyebrows, footers, and inline rhythm. They are not icons but they do icon work.
- **Logo / wordmark:** the brand's primary mark is the wordmark `KAREN KAIRIYAMA` set in Outfit Black, tracked tight, optionally underlined by a 1px contrast-tone rule. A compact monogram `KK` (Outfit Black, the two K's kerned to touch) is the favicon / avatar. Both are in `assets/`.

We were not given a logo file. The wordmark in `assets/logo-wordmark.svg` and monogram in `assets/logo-monogram.svg` are **proposals**; treat them as Karen's-pending-approval and swap out if she shares finals.

---

## Caveats / things to confirm with Karen

- **Cormorant Garamond** is loaded from Google Fonts — confirm if she has a licensed file to self-host.
- The **logo wordmark + monogram** are proposals built from the spec. They are not derived from an existing file.
- **Photography**: no real assets shipped. Slide and UI-kit imagery use neutral architectural placeholders from Unsplash, sized + treated per the Imagery rules. Replace with her clients' work.
- **Iconography**: Lucide is a substitute choice. If she has a preferred set, swap the CDN URL and re-confirm stroke weight.
- **Voice examples** in CONTENT FUNDAMENTALS were written for this doc; they're directionally correct but should be reviewed by Karen for tone fidelity.

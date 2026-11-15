# Version 02 — design specification written before implementation

**Approach:** the student wrote this specification first; the AI agent implemented it. Layout,
hierarchy, palette, type, components and interactions were decided here, not by the agent.

---

## 1. Concept

This is not a marketing landing page. It should read like an engineering dossier: precise, quiet,
a little editorial — the visual equivalent of a lab notebook that has been tidied up. The claim the
page has to support is "I care about results that can be measured", so every section should prefer
evidence (numbers, dates, roles, tools) over adjectives. No stock photography, no decorative
illustration beyond one technical figure.

## 2. Layout

- Fixed left rail, 248 px wide, full viewport height, on screens wider than 1080 px.
  Contents: "ZG" monogram + name + "EEE · UNNC", numbered navigation (01 Profile … 05 Contact),
  and pinned to the bottom: availability status, email address, copy-email button, theme toggle.
- Main column starts at the rail edge with a comfortable page gutter; content max-width ~1140 px.
- On ≤1080 px the rail disappears and becomes a sticky top bar (name left, theme and menu right)
  plus a full-screen drawer for navigation.
- Generous vertical rhythm: each section separated by a full-width hairline and 96 px of padding.

## 3. Typography

- Display: **Space Grotesk** — tight tracking for the name and section headings.
- Body: **Inter** at 15–17 px, 1.6 line-height, comfortable measure (~60 characters).
- Labels and metadata: **IBM Plex Mono**, uppercase, letter-spacing .16em, 10–12 px.
- Hero name: very large (up to 6.5 rem), two lines, with an amber full stop as the only flourish.
- Numbers are the hierarchy: dates, metrics and section numbers use mono so they align.

## 4. Colour

Light (default)

| Token | Value | Use |
| --- | --- | --- |
| paper | `#f6f2ea` | page background |
| card | `#fbf8f2` | cards |
| ink | `#17181c` | primary text, rules of emphasis |
| ink-2 | `#3d3f45` | body copy |
| ink-3 | `#6b6f79` | metadata |
| rule | `#d8d0c1` | hairlines |
| accent | `#b45309` | section numbers, metrics, links |
| teal | `#0f766e` | roles and one secondary signal |

Dark variant: `#141311` background, `#1b1915` cards, beige `#ece6da` text, `#f0a54a` accent,
`#6fb3a8` teal. The toggle must persist in `localStorage` and respect the system preference on
first visit.

## 5. Sections

1. **Hero** — eyebrow "PORTFOLIO — 2026 / 07"; the name; a three-line statement of what I do;
   two buttons ("Download CV", "Selected work"); a four-cell spec sheet (based in, degree, GPA,
   currently). Beside it, one figure: an inline SVG of an AIS encounter — two vessel tracks, own
   ship, a dashed prediction cone, a CPA marker and the minADE/minFDE numbers. Caption "FIG. 01 —
   TRAJECTORY PREDICTION". The figure must be drawn, not an image file.
2. **01 Profile** — a short manifesto heading ("I build systems that have to work outside the
   lab."), three paragraphs and three numbered working principles; sticky quote card on the right.
3. **02 Selected work** — six cards in two columns. Each card: index (W.01…), date range, title,
   role in teal, one-line summary, metric chips in mono, a collapsible "technical detail" block,
   tool tags. Filter chips above the cards: All / Research / Hardware / Software, with counts.
4. **03 Education** — rows, not cards: dates in the left column, the qualification in the middle,
   metadata on the right, module chips under the degree.
5. **04 Toolkit** — four columns of skills, each skill a row of five squares (filled = proficiency),
   with a legend explaining the scale. Groups numbered 01–04.
6. **05 Contact** — a large question, a short paragraph, two buttons, and a definition list of
   email / phone / GitHub / location / availability. Footer: © line, "Designed & built by hand",
   links back to the AI-generated version and the repository.

## 6. Interaction and behaviour

- Scroll reveal: content fades and rises 16 px once; disabled under `prefers-reduced-motion`.
- Scrollspy: the active rail item is marked with the accent colour.
- A 2 px progress bar at the very top of the page.
- Work filters must compute their counts from the cards themselves, not hard-code them.
- Copy-email button writes to the clipboard and shows a small toast.
- Print stylesheet: hide the rail and controls, force work details open, black text on white.
- Keyboard: visible focus rings, skip link to content, `aria-expanded` on the mobile menu.

## 7. Constraints

- One self-contained HTML file; no framework, no build step, no external CSS or JS files.
- Google Fonts only; the page must still be readable if fonts fail.
- No layout shift when the theme changes; no horizontal scroll at 320–1920 px.
- Content must stay truthful to the CV: six projects (three research, three design builds),
  GPA 3.86/4.00, graduating 2027.

## 8. Review checklist used after implementation

Compare the result against this document at 1440, 1024 and 390 px; check both themes; check
keyboard navigation; check the print preview; confirm every metric on the page appears in the CV.

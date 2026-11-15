# Version 01 — brief given to the AI agent

**Approach:** general instructions only. The brief below was handed to the coding agent; the layout,
visual style, component structure and interactions were left to its judgement.

---

Build me a personal portfolio webpage for an Electrical and Electronic Engineering student at the
University of Nottingham Ningbo China. I'm applying for research opportunities and internships, so
it should look modern and professional, and work well on a phone as well as a laptop.

Use my CV content: education, research experience, projects, skills, and a few extracurricular
activities. I'll paste the CV text after this.

Requirements:

- one HTML file with the CSS and JavaScript inline;
- a dark theme is fine if it looks good — you decide;
- a navigation bar, a hero section, sections for about, research, projects, skills and contact;
- links to my email, phone and GitHub, plus a button to download my CV;
- responsive on mobile.

You choose the fonts, colours, spacing and any animations. Keep it clean and easy to read.

---

## What the agent produced, and what was corrected afterwards

The agent returned a single-file dark portfolio with a purple-to-cyan gradient, glass cards, a
centred hero, stat cards, a timeline, three research cards, three project cards, percentage skill
bars and an animated reveal on scroll.

Human review then fixed:

- emoji used as icons (they render differently per platform; the envelope even failed to draw) —
  replaced with a consistent inline SVG icon set;
- the hero heading stayed at desktop size on a 390 px screen and broke into five ragged lines —
  added a mobile size clamp;
- a "scroll" hint positioned absolutely at the bottom of the hero was clipped below the fold —
  removed;
- project and study counts that disagreed with each other — corrected to six engineering projects.

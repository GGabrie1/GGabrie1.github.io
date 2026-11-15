# Coursework Part I — Personal Webpage

**Module:** EEEE3134 Modern Programming · **Student:** Zhichen Gao · **Year:** 2026

Two versions of the same personal webpage, built with different levels of human direction and
published side by side for comparison.

| Version | Page | Approach |
| --- | --- | --- |
| 01 — AI-generated | [ai-generated-page.html](https://ggabrie1.github.io/ai-generated-page.html) | Short, general prompt. The agent chose the layout, palette, typography and interactions. |
| 02 — AI-guided | [me-designed-page.html](https://ggabrie1.github.io/me-designed-page.html) | Detailed specification written by hand: rail layout, editorial type system, filterable work index, dark mode. |

Landing page: [ggabrie1.github.io](https://ggabrie1.github.io/)

## Repository contents

```
index.html               landing page linking both versions
ai-generated-page.html   version 01 (single file: inline CSS + JS)
me-designed-page.html    version 02 (single file: inline CSS + JS)
assets/                  CV used by the download buttons
prompts/                 the brief (v1) and the design specification (v2)
```

Both pages are self-contained HTML files. The only external dependencies are Google Fonts and the
CV PDF in `assets/`.

## Process in one paragraph

Version 01 was produced from a short brief ([prompts/ai-generated-brief.md](prompts/ai-generated-brief.md)):
the agent decided the overall visual language (dark gradient, glass cards, centred hero), and the
human review then corrected a handful of issues — emoji icons that rendered inconsistently, an
oversized mobile heading, and a scroll hint clipped by the hero. Version 02 was specified in detail
before any code was written ([prompts/ai-guided-spec.md](prompts/ai-guided-spec.md)): a fixed
editorial side rail, numbered sections, warm paper palette, a hand-drawn SVG trajectory figure,
filterable work cards with technical disclosures, print styles and a persisted dark mode. The
agent implemented that specification, and the same review loop refined spacing, contrast and
responsive behaviour.

## Running locally

```bash
python -m http.server 8765
```

Then open <http://127.0.0.1:8765/>.

## Note on AI use

AI tools were used for coding, debugging and visual iteration, as permitted by the coursework
brief. The accompanying report's personal reflection and conclusions are written by the student.

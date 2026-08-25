# SETU GenAI Programme — Course 2: AI Competency

A self-paced, ~1-hour web course on working effectively and responsibly with AI.
Aimed at all SETU staff who have completed **Course 1 — AI Literacy**. Built on the
same template as Course 1, so the two courses read as one continuous programme.

## What it is

A **standalone static website** — plain HTML, CSS and JavaScript with **no build step
and no dependencies**. It runs by opening a file in a browser and can be hosted anywhere
(GitHub Pages, the SETU web server, an intranet folder, or an LMS as an embedded/uploaded
package).

## Two ways to distribute — one source

The same `index.html` + `assets/` power **both**:

1. **Standalone website** — host the folder anywhere (GitHub Pages, the SETU web
   server, an intranet). Nothing to build.
2. **SCORM package for your LMS** — run `python3 scorm/build_scorm.py` to produce
   `dist/setu-ai-competency-scorm-1.2.zip`, then upload it to Moodle/Brightspace/etc.
   The LMS tracks progress, resume position and completion. See **`scorm/README.md`**.

The SCORM adapter (`assets/js/scorm.js`) is inert without an LMS, so the website version
is unaffected and the two never diverge.

```
index.html             The whole course (cover + 10 sections + completion)
assets/css/styles.css   Design system (SETU brand tokens at the top — shared with Course 1)
assets/js/course.js     Navigation, progress, activities, flip cards, ratings, reflection
assets/js/scorm.js      SCORM 1.2 adapter (no-op outside an LMS)
assets/js/certificate.js Learner-generated certificate of completion
assets/fonts/           Self-hosted DM Sans + Inter (brand fonts) + fonts.css
scorm/                  Build script + packaging docs
dist/                   Built SCORM .zip (regenerate with the build script)
assets/img/             SETU logo assets (light/dark) + favicon — course images are still
                        placeholders, see docs/CONTENT-TODO.md
docs/CONTENT-TODO.md    Checklist of images and SETU-specific content still to insert
```

## Branding

Built to the **SETU Brand Guidelines (v1, May 2022)**, matching Course 1:
- **Colour** — Slate Grey `#435465` primary with the secondary accent palette
  (Sea Green, Barrow Blue, Sunset Red, Sunrise Yellow) for interactive and semantic
  states. All tokens live at the top of `assets/css/styles.css`.
- **Typography** — DM Sans (headings) and Inter (body), self-hosted in `assets/fonts/`
  so the course is fully self-contained and works offline.
- **Logo** — master logo in the top bar (with a white variant that swaps in for dark
  mode) and on the cover; the crest symbol as the favicon.

## Sections

Course Introduction · Choosing AI Well · Context Changes Everything · Collaborating,
Not Prompting · Evaluating AI Outputs · AI for Everyday Work · AI in Your Practice ·
From Individual Tasks to Workflows · Knowing the Boundaries · The Competency Challenge ·
Reflection — plus a cover and a completion screen. Content is drawn from the detailed
course script, *AI Competency: Working Effectively and Responsibly with AI*.

## Features

- **Progress bar** that remembers the furthest point reached (saved in the browser).
- **Contents panel** for jumping between sections; collapses to a drawer on mobile.
- **Interactive activities**, each drawn from the script:
  - **Confidence self-rating** — 1–5 scale on five statements, taken at the start and
    repeated at the end, with an inline "started at X · now Y" comparison.
  - "AI, AI-assisted or Human?" task spectrum with discussion notes.
  - "What's missing?" and progressive-reveal activities.
  - A one-shot-versus-conversation demonstration, revealed step by step.
  - "Be the reviewer" — click the flags in an AI-generated briefing (a factual error,
    a fabricated reference, an unsupported claim, an audience assumption — plus one
    important omission that can't be clicked, because it isn't there).
  - Flip cards for the five categories of everyday AI use (Create, Transform, Analyse,
    Challenge, Prepare).
  - Role **pathway** tabs (Teaching, Assessment, Research, Professional Services,
    Leadership) with case studies and reveal-a-model-answer questions.
  - A workflow-mapping activity (worked example + your own process).
  - A boundaries scenario with progressively revealed considerations.
- **Reflection notes** — spread across the course, autosaved locally, downloadable as
  a single text file at the end.
- **Certificate of completion** — the learner enters their name and downloads a branded
  certificate (print / save as PDF); the LMS also records completion via SCORM.
- Accessible (keyboard nav, skip link, focus states, reduced-motion support),
  responsive, light/dark aware, and printable to PDF.

## Run it locally

Just open `index.html` in a browser. Or serve the folder:

```bash
python3 -m http.server 8000    # then visit http://localhost:8000
```

## Before it goes live — SETU to complete

The narrated content is in place from the script. **Every image in this course is
still a placeholder** (a dashed box), because no photography or illustrations have
been supplied yet. See **`docs/CONTENT-TODO.md`** for the full list and suggested
sizes. In short:

1. **Images:** every section has a placeholder slot — see the checklist for what each
   one should show.
2. **Completion screen:** the name and enrolment link for Course 3 (AI Fluency).
3. **Case studies:** the names used in the role-pathway case studies (Sections 6) are
   illustrative — replace with real (anonymised) or approved fictional examples if
   preferred.

## Branding tokens

All colours live as CSS variables at the top of `assets/css/styles.css`
(`--brand` = Slate Grey, `--accent` = Sea Green, secondary palette, tints, etc.) —
identical to Course 1, so changing them there updates both courses' look consistently
if applied to each repo. Fonts are defined in `assets/fonts/fonts.css`.

## Notes

- In the **website** version, progress, ratings and reflections are stored in the
  visitor's own browser (`localStorage`) — nothing personal leaves the device.
- In the **SCORM/LMS** version, completion, progress and resume position are reported to
  the LMS for record-keeping (notes still stay on the device). Rebuild the package with
  `python3 scorm/build_scorm.py` after any content edit.
- This course reuses the interactive components built for Course 1 (AI Literacy) —
  spectrum activities, click-the-flag reviews, pathway tabs, flip cards, reveal
  buttons — so the two courses feel like one continuous programme.

# Content to insert before go-live — SETU checklist

The course content and interactions are in place, built from the *AI Competency:
Working Effectively and Responsibly with AI* script. The items below are what's still
needed before go-live. Search the codebase for `figure__slot` to find every image slot,
and `[SETU to confirm]` for the one open text item.

## 1. Images (you are supplying these)

Every slot is a `<figure class="figure">` with a dashed placeholder — none of this
course's images exist yet. To fill one, replace the inner
`<div class="figure__slot">…</div>` with `<img class="figure__img" src="assets/img/your-file.jpg"
alt="…">` (plus an optional `<figcaption>`). Recommended: SETU photography style
(shallow depth of field, natural light, authentic, inclusive), matching Course 1.
Suggested sizes below (all can be larger; keep the aspect ratio).

| Section | Where | Suggested size / ratio |
|---|---|---|
| Course Introduction | Banner under the hero | 1600×540 (3:1) |
| 1. Choosing AI Well | Header illustration | 1200×675 (16:9) |
| 2. Context Changes Everything | Header illustration | 1200×675 (16:9) |
| 3. Collaborating, Not Prompting | Header illustration | 1200×675 (16:9) |
| 4. Evaluating AI Outputs | Header illustration | 1200×675 (16:9) |
| 5. AI for Everyday Work | Header illustration | 1200×675 (16:9) |
| 6. AI in Your Practice | Header illustration | 1200×675 (16:9) |
| 7. From Individual Tasks to Workflows | Header illustration | 1200×675 (16:9) |
| 8. Knowing the Boundaries | Header illustration | 1200×675 (16:9) |
| 9. The Competency Challenge | Header illustration | 1200×675 (16:9) |
| 10. Reflection | Reflective image | 1200×675 (16:9) |

## 2. Completion / certificate

- [ ] **Course 3 (AI Fluency)** — add the name and enrolment link in the "Where next"
  box (currently `[SETU to confirm: name and enrolment link for Course 3.]` in
  `index.html`, in the final section).
- [ ] **Certificate wording** (optional) — the certificate reads "SETU GenAI Programme /
  Course 2 — AI Competency". If you want a signatory line (e.g. a name/title) or a QR/verify
  note, say so and it can be added. The learner types their own name; the LMS also records
  completion via SCORM.

## 3. Case studies (Section 6 — AI in Your Practice)

The role-pathway case studies (Sarah/programme leader-style academic, a researcher, a
registry staff member, a manager) are illustrative, written to match the shape of the
source script. Replace with real (anonymised, with consent) or SETU-approved fictional
examples if preferred, and confirm names are appropriate.

## 4. Branding (done — confirm)

- [x] Built on the same template, tokens and terminology as Course 1 (AI Literacy):
  **courses + sections** (no "module"/"stage"/"hub" as structural terms).
- [x] SETU logo, Slate Grey + secondary palette, DM Sans/Inter fonts (copied from
  Course 1's `assets/`).
- [ ] Optional: replace the extracted PNG logos with official **SVG/EPS** vector files
  (same optional item as Course 1).

## 5. Optional / general

- [ ] AI working group to review all sections for accuracy and SETU tone.
- [ ] Accessibility sign-off against SETU's WCAG target.
- [ ] After any edit, rebuild the SCORM package: `python3 scorm/build_scorm.py`.

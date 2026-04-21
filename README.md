
# AP Calculus BC — Practice Assessment

An interactive, self-scoring practice assessment for AP Calculus BC, hosted on GitHub Pages. Built for students preparing for the May 2026 AP exam, covering BC-only topics beyond the AB curriculum.

---

## What's Included

### Section I — Multiple Choice (45 pts)
- 15 original AP-style questions across all BC-only topics
- Auto-scores on submit with full explanations for every question
- Highlights correct answers and shows which topics to review
- Questions 1–10: no calculator | Questions 11–15: calculator permitted

### Section II — Free Response (40 pts)
Four original AP-style FRQ questions:

| # | Topic | Points |
|---|-------|--------|
| FRQ 1 | Integration by Parts & Improper Integrals — `f(x) = xe⁻ˣ` | 10 |
| FRQ 2 | Polar Curves — Area enclosed by `r = 2 + cosθ` | 10 |
| FRQ 3 | Parametric Equations — Full analysis of `x(t) = t²−4`, `y(t) = t³−3t` | 10 |
| FRQ 4 | Vector-Valued Functions & Particle Motion | 10 |

Each FRQ card includes:
- Full question text with typeset math (rendered via MathJax)
- A parts-at-a-glance table with skills tested and point values
- Photo upload (choose file or use webcam)
- Typed answer text area

---

## Topics Covered

- Integration by Parts (including tabular method)
- Partial Fraction Decomposition (linear and irreducible quadratic factors)
- Improper Integrals (infinite bounds and interior discontinuities)
- Euler's Method
- Parametric Equations (dy/dx, d²y/dx², arc length, speed, tangent lines)
- Polar Curves (area, slope dy/dx)
- Vector-Valued Functions (differentiation, integration, position/velocity/acceleration)

---

## How to Use

### For the student
1. Open the live site link shared by your teacher
2. Enter your **full name** in the field at the top — this is required for submission
3. Work through **Section I** (MCQ) — select your answers and click **Score MCQ** when done
4. Open the **Section II** FRQ questions, do your work on paper, then either:
   - Click **Choose file** to upload a photo from your device, or
   - Click **Use camera** to take a photo using your webcam (laptop) or camera (phone/tablet)
   - Type your work directly in the text box
5. Click **Submit to Teacher** — your results and photos are sent automatically

### For the teacher
- MCQ results (score, accuracy, missed topics) arrive in your inbox at **rkchina79@gmail.com**
- FRQ typed answers and uploaded photos are included in the same email
- Score FRQ manually using the answer key shown in the results panel on the page

---

## Submission Flow

```
Student completes assessment
        ↓
Clicks "Submit to Teacher"
        ↓
EmailJS sends email to rkchina79@gmail.com containing:
  • Student name
  • MCQ score and missed topics
  • FRQ typed answers
  • FRQ photos (compressed and embedded inline)
```

Photos are automatically compressed to fit within EmailJS's size limits before sending.

---

## Tech Stack

| Component | Technology |
|-----------|------------|
| Hosting | GitHub Pages (static) |
| Math rendering | MathJax 3 (CDN) |
| Email delivery | EmailJS (free tier, 200 emails/month) |
| Polar graph | Inline SVG (generated mathematically) |
| Webcam capture | Browser `getUserMedia` API |
| No backend | Pure HTML + JavaScript |

---

## File Structure

```
/
└── index.html      ← entire assessment (single self-contained file)
└── README.md       ← this file
```

---

## Updating the Assessment

Everything lives in `index.html`. To make changes:

- **Edit MCQ questions** — find the `const MCQ = [...]` array in the `<script>` section
- **Edit FRQ questions** — find the `const FRQ = [...]` array in the `<script>` section
- **Change the teacher email** — search for `rkchina79@gmail.com` and replace (appears in the EmailJS send call and the error message)
- **Update EmailJS credentials** — search for `service_r1x1rx6`, `template_z4re6dm`, and `b2cv_ErRDEPUuA0SO`

After any edit, commit and push to `main` — GitHub Pages updates within ~60 seconds.

---

## EmailJS Setup (for reference)

This project uses [EmailJS](https://emailjs.com) to send submissions without a backend.

| Setting | Value |
|---------|-------|
| Service ID | `service_r1x1rx6` |
| Template ID | `template_z4re6dm` |
| Public Key | `b2cv_ErRDEPUuA0SO` |
| Free tier limit | 200 emails/month |

The EmailJS template uses these variables:

| Variable | Contents |
|----------|----------|
| `{{subject}}` | Email subject line |
| `{{from_name}}` | Student's name |
| `{{mcq_score}}` | Score string e.g. `12/15 (80%) — 36/45 pts` |
| `{{mcq_missed}}` | Comma-separated list of missed topics |
| `{{message}}` | FRQ written answers (plain text) |
| `{{{photo_html}}}` | FRQ photos as inline HTML images (triple braces) |

> ⚠️ Use **triple braces** `{{{photo_html}}}` in the EmailJS template body — double braces will render the HTML as plain text instead of displaying the images.

---

## Exam Details

- **Exam date:** Monday, May 11, 2026 at 8:00 AM local time
- **Format:** Hybrid digital — MCQ in Bluebook app, FRQ handwritten in paper booklet
- **MCQ:** 45 questions, 1 hr 45 min, 50% of score
- **FRQ:** 6 questions, 1 hr 30 min, 50% of score

---

## Answer Key (FRQ — for teacher use)

**FRQ 1** — (a) `−e⁻ˣ(x+1) + C` (b) Converges to `1` (c) `2`

**FRQ 2** — (a) `9π/2` (b) slope `= 1/2` at θ = π/2 (c) `9π/4` (symmetric about polar axis)

**FRQ 3** — (a) Horizontal tangents at t = ±1 → `(−3, −2)` and `(−3, 2)`; vertical at t = 0 → `(−4, 0)` (b) `d²y/dx² = 15/32 > 0` at t = 2, concave up (c) Arc length = `∫₀² √(9t⁴−14t²+9) dt`; speed at t = 1 `= 2`

**FRQ 4** — (a) `r(t) = ⟨t²−t+2, t³−1⟩` (b) speed at t = 2 `= 3√17`; speeding up (v·a = 150 > 0) (c) distance `≈ 8.52`

---

*Built with Claude — Anthropic*

# Noy & Zhang (2023) — Experimental Evidence on the Productivity Effects of Generative AI

**Citation.** Noy, S. & Zhang, W. (2023). "Experimental evidence on the productivity effects of generative artificial intelligence." *Science*, 381, 187--192. DOI: 10.1126/science.adh2586. (Audited PDF is the 108-page Supplementary Materials; main-paper results are cross-referenced therein.)

**Preregistration.** AEA RCT Registry AEARCTR-0010882 (minor deviations listed in SI §A.3).

---

## 1. Identification Strategy: Preregistered Online RCT With 1:1 Treatment/Control Randomization

- **Design.** Randomized controlled trial conducted on Prolific. College-educated, fulltime-employed US workers in 5 occupations are recruited and randomized into a ChatGPT-access **treatment** arm or an Overleaf-signup **control** arm (SI p.2, Fig. S.1 p.5).
- **Outcomes measured as change scores** (post-treatment Task 2 minus pre-treatment Task 1). Participants first complete Task 1 without ChatGPT, then sign up for ChatGPT (T) or Overleaf (C), then complete Task 2 (SI §A.1, pp.2--3).
- **Cross-randomization into 3 incentive arms** (linear 40%, convex 40%, exact-time 20%) to test robustness; main paper figures use linear+convex only (SI p.3).
- **Main ITT regression (non-grade outcomes),** Eq. S.1 (SI p.7):
  Δy_i = β_0 + β_1 D_i + θ_occ(i) × α_first(i) + π_inc(i) + ε_i — occupation × first-task-seen FE, incentive-arm FE, robust SE.
- **Grade regression,** Eq. S.2 (SI p.7), observation = participant × evaluator: adds evaluator FE γ_j; SE clustered at participant level.
- **Treatment-on-Treated (IV/2SLS),** Eq. S.4 (SI p.82): ChatGPT-usage dummy instrumented with assignment dummy (Table S.1--S.2). Control compliance ≈10--20%, treatment compliance ≈80% (SI p.82).
- **Inequality analysis,** Eq. S.3 (SI p.8): grade_{ij} = β_0 + β_1 x_{ij} + β_2 D_i + β_3 (D_i × x_{ij}) + γ_j + ν_{ij}; β_1 is the "control slope," β_3 is "difference in slopes."

**The "shock"** is the randomly-assigned option (and nudge) to use ChatGPT on a realistic 20--30 minute occupational writing task, against an otherwise-identical Overleaf-placebo control that holds constant the experience of signing up for an external tool mid-survey.

---

## 2. Data & Sample: 450 Prolific Workers in 5 White-Collar Occupations, 1,135 Essay-Grader Observations

- **Population.** Prolific workers screened on self-reported occupation; prioritized college degree + fulltime employment (SI p.2).
- **Data collection window.** Main survey fielded **27 January -- 21 February 2023**, mostly 5pm--12am EST (so ChatGPT signups succeeded; 92% signup rate) (SI p.2).
- **Five occupations with two tasks each** (SI p.3, §B.6):
  - Marketers — press release
  - Grantwriters — grant cover letter
  - Managers / HR professionals — sensitive company-wide email
  - Data analysts — analysis plan in notebook format
  - Consultants — short report from 3 sources
  Each task designed for 20--30 min and ~400 words. 85% rated tasks "realistic/very realistic"; 68% had done a similar task on the job (SI p.3).
- **Final sample sizes** (SI p.8, Tables S.1--S.2):
  - **Participants (task data): N = 450** preregistered at 600; adjusted down when screening/grading budget was exhausted (SI p.8).
  - **Participant-level non-grade regressions: N = 449** (Table S.2, job satisfaction & self-efficacy).
  - **Time outcome: N = 346** (linear+convex arms only, main figure sample; Table S.1).
  - **Grade outcome: N = 1,135 participant-evaluator observations** (Table S.1).
- **Evaluators/graders.** 148 graders recruited on Prolific with stricter screening (≥1-year recent experience with similar task); **23 dropped for inter-grader correlation < 0.1**, leaving 125 graders used in main specifications (SI p.7). Graders: mean 14.5 years occupational tenure (IQR [5, 21]); each grades both essays per participant for up to 7 participants on a 1--7 scale (SI p.6). Two examples per prompt provided for calibration.
- **Pure ChatGPT benchmark.** Researchers themselves submitted raw ChatGPT outputs to graders: 67 unique essays, 408 grades, mean grade 4.88 (SD 1.53), 122 unique graders (Table S.3, SI p.108).

---

## 3. Main Findings: Time --0.8 SD and Grades +0.4 SD (ITT); Effects Roughly Double Under IV-TOT

All coefficients below come from the Supplementary Materials Tables S.1--S.2 (SI pp.107--108). "OLS" = intent-to-treat on assignment; "IV" = 2SLS treatment-on-treated, using assignment as an instrument for ChatGPT usage.

### Table S.1 — Time and Grades (SI p.107)

| Outcome | OLS (ITT) | IV (TOT) | N |
|---|---|---|---|
| **Time on task (minutes, Δ)** | **−10.842*** (1.382)** | **−16.507*** (1.986)** | 346 |
| **Grade (1--7 scale, Δ)** | **+0.651*** (0.145)** | **+0.949*** (0.185)** | 1,135 |

(Parentheses = SE; *** p<0.01. SE clustered at participant level for grade regressions.)

### Table S.2 — Job Satisfaction and Self-Efficacy (SI p.108)

| Outcome | OLS (ITT) | IV (TOT) | N |
|---|---|---|---|
| **Job satisfaction (1--10 Likert, Δ)** | **+1.164*** (0.211)** | **+1.928*** (0.297)** | 449 |
| **Self-efficacy (1--10 Likert, Δ)** | **+0.409** (0.204)** | **+0.805*** (0.280)** | 449 |

Reported in standardized units in the main paper / SI text (SI p.83):
- **Job satisfaction +0.50 SD (p < 0.001).**
- **Self-efficacy +0.20 SD (p = 0.05)** — author notes this is "mildly and imprecisely" identified and **not robust** in alternate specs.

### Task Structure (SI p.82)
- Pre-treatment time allocation: ~25% brainstorm, ~50% rough draft, ~25% edit.
- Post-treatment (treated group): rough-draft share **falls by more than half**, editing share **more than doubles**.

### Inequality / Skill Complementarity
- **Willingness to pay for ChatGPT is flat across terciles of writing skill** (self-reported and evaluator-measured); treatment respondents willing to pay ~0.5% of monthly salary (SI p.83).
- **Grade gains roughly flat across writing-skill terciles** — weaker writers do not experience unusually large gains. Authors caveat the WTP and grade-delta outcomes are noisy and underpowered (SI p.83).

### Pure ChatGPT vs Human-Using-ChatGPT (Table S.3, SI p.108)
Pure ChatGPT essays score **slightly higher** than human-with-ChatGPT essays on average (4.88 vs 4.76), driven by worse performance among data-analyst / grant-writer / marketer humans who modified ChatGPT output (often introducing typos or flow problems — SI p.87).

### Usage / Compliance
- **~80% of treated participants use ChatGPT on Task 2; 10--20% of control do** (SI p.82; "big pasting event" objective proxy shows 20% control upper bound).
- Among ChatGPT users: 58 submitted output unedited, 92 edited, 23 used for brainstorming (SI p.84).
- Levenshtein edit distance among editors: ~30% of final word count.

### Robustness (SI §C.7, Figs. S.15--S.21)
Main time and grade effects are robust to: controlling for imbalanced attrition characteristics and Lee bounds (Fig. S.15); not dropping "bad graders" (Fig. S.16--S.17); restricting to experienced taskers (Fig. S.18); excluding managers (Fig. S.19); excluding data analysts (Fig. S.20); and using objective "time active" measure (Fig. S.21). **Self-efficacy is explicitly flagged as non-robust.**

---

## 4. Limitations (As Noted by the Authors)

- **Sample size reduced from preregistered 600 to 450** due to screening + grading cost overruns (SI p.8).
- **Compliance is imperfect** (10--20% control contamination; 80% treatment uptake) — ITT vs IV diverge by ~50% (Tables S.1--S.2).
- **Randomization procedure changed mid-study** (Qualtrics random-integer generator was non-uniform; switched to "randomly present element" at obs 189); adding before/after FE does not move results (SI p.8).
- **Exact-time arm (N≈90) shows pre-treatment imbalance** because of small-sample draw; authors rely on DiD-identifying assumption for that arm (SI p.88).
- **Copywriters (2% of sample) mis-routed to grant-writing task**; robust to dropping them (SI p.9).
- **Tasks are short (20--30 min) artificial writing prompts** done by Prolific workers, not full on-the-job workflows.
- **Self-efficacy Likert measure is "pretty limited"** relative to the self-efficacy literature (SI p.83).
- **WTP & skill-complementarity analyses are underpowered** and the two writing-skill measures are uncorrelated with each other (SI p.83).
- Two **working-paper coding errors** (time-taken histogram binning, ChatGPT-usage category mapping) were caught pre-publication (SI p.9--10).

---

## 5. Key Implications for the Broader Research Agenda

- **Magnitudes.** On a writing task that mirrors real occupational content, ChatGPT access cuts time-to-completion by ~0.8 SD (~37% relative time reduction; −10.8 min of ~30) **and simultaneously raises output quality by ~0.4 SD on a 1--7 grader scale** — a rare joint productivity + quality effect in a tightly controlled RCT.
- **Inequality-reducing on observed grades.** ChatGPT narrows cross-person grade dispersion (main paper Fig. 2 / SI Fig. S.14): initially-lower performers close more of the gap, though authors find **no clear heterogeneity by self-reported or measured writing skill rank**.
- **Substitution, not augmentation.** Task restructuring (halving rough-draft time, doubling editing time) plus high rates of "submit-without-editing" (~58/173 users) suggest ChatGPT is functioning as a **direct output substitute**, not primarily as an ideation aid — the productivity gain is driven by replacing the drafting step.
- **Grader-calibration subtlety.** Pure ChatGPT output beats human-with-ChatGPT on average in 3/5 occupations, implying some humans actively degrade LLM output — a caveat for policies that assume human-in-the-loop always improves quality.
- **First credible causal estimate** in the post-ChatGPT literature of short-run productivity effects on mid-skill professional writing tasks; heavily cited as a benchmark for subsequent worker-level RCTs (e.g. Dell'Acqua et al. 2023 / BCG, Brynjolfsson--Li--Raymond 2023 / call-center).

---

## Audit Checklist

- [x] **Identification strategy:** preregistered individual-level RCT on Prolific (ChatGPT access vs Overleaf placebo), occupation × first-task FE, incentive-arm FE; plus 2SLS TOT instrumenting usage with assignment; plus cross-randomized incentive arms for robustness.
- [x] **Data & sample:** Prolific panel, Jan 27--Feb 21 2023, N=450 participants across 5 white-collar occupations; 1,135 participant-evaluator obs for grades; 125 evaluators retained after bad-grader drop.
- [x] **Main findings:** Time −10.842 min (SE 1.382) ITT / −16.507 (1.986) TOT; Grade +0.651 (0.145) ITT / +0.949 (0.185) TOT; Job satisfaction +1.164 (0.211) ITT / +1.928 (0.297) TOT; Self-efficacy +0.409 (0.204) ITT / +0.805 (0.280) TOT. Summary SDs: time −0.8, grade +0.4, satisfaction +0.50, efficacy +0.20.
- [x] **Limitations:** imperfect compliance, short artificial tasks, one non-robust efficacy estimate, sample-size cut, mid-study randomization change.
- [x] **Implications:** short-run LLM productivity gains are large and quality-enhancing on mid-skill writing; effects operate via drafting-step substitution and narrow grade inequality.

---

## Sections Skipped (Per Audit Protocol)

- SI §B (full survey questionnaires — pp.10--80) — reproduces instrument text without new empirical results; only the high-level task descriptions in §B.6 were used.
- SI §D.1--D.3 — supplementary figures and robustness plots were read as captions only (Figs. S.2--S.21); main coefficients were extracted from Tables S.1--S.3 and text in §C.1--C.3.
- Final MDAR checklist (not present in text body).

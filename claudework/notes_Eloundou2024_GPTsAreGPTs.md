# Eloundou, Manning, Mishkin & Rock (2024): ~80% of US Workers Have ≥10% of Tasks LLM-Exposed and ~19% Have ≥50% Exposed at the E1+0.5·E2 Level; Higher-Wage / Higher-Education Occupations Are More Exposed

**Citation:** Eloundou, T., Manning, S., Mishkin, P., & Rock, D. (2024). "GPTs are GPTs: Labor market impact potential of LLMs." *Science*, 384, 1306. DOI: 10.1126/science.adj0998. (Attached PDF is the 71-page Supplementary Materials file.)

**File:** `papers/Eloundou2024_GPTsAreGPTs.pdf` (71 pages — Supplementary Materials; main-text headline results reproduced inside)

---

## Identification Strategy Is a Rubric-Based Task-Exposure Audit of O*NET, Not a Causal Design (Descriptive / Measurement Paper)

- **Method:** Descriptive construct. **No causal identification** (no DiD, IV, RDD, RCT). The paper builds a *task-exposure measure* by applying two human- and GPT-4-administered scoring rubrics to the universe of O*NET task/activity descriptions, then aggregates to occupation, industry, and workforce shares using BLS employment weights.
- **Primary rubric — "E" (overall exposure) at the task level (pp. 10–13):**
  - **E0 (no exposure):** LLM cannot cut task time ≥50% at equivalent quality, or reduces quality.
  - **E1 (direct exposure):** direct access to an LLM (ChatGPT / Playground) alone cuts time ≥50%.
  - **E2 (LLM-powered software exposure):** LLM alone is insufficient, but plausible software built on top of the LLM would cut time ≥50%.
  - **E3 (image-capability exposure):** combined with E2 for all analyses.
  - Headline aggregate: $\text{E1} + 0.5 \cdot \text{E2}$ (and sensitivities $\text{E1}$ and $\text{E1} + \text{E2}$).
- **Secondary rubric — "T" (automation exposure) (pp. 12–14):** GPT-4 only. Five-point scale T0–T4: 0 = no automation exposure, 1 = low, 2 = moderate, 3 = high (90–100% automatable with oversight), 4 = full (all aspects automatable without oversight). Mapped to numeric {0, 0.25, 0.50, 0.75, 1}.
- **Labeling procedures:**
  - Six human annotators familiar with LLM capabilities labeled tasks with the E rubric.
  - GPT-4 labeled all tasks with both the E and T rubrics.
  - Human–GPT-4 agreement at the task level: **66%** (p. 19).
  - Occupation-level human-vs-GPT-4 agreement "high" (Figure 4).
- **Validation sources:** ChatGPT user survey, alternative weightings, network modularity of occupations (Louvain, modularity = 0.709), industry aggregation, GitHub-forks analysis of complementary software development.

## Data & Sample Are 19,265 O*NET Tasks × 1,016 Occupations Aggregated to the US Workforce Using BLS Employment Data

- **Task dataset (O*NET 27.2, p. 24):**
  - **19,265 tasks** (task description + associated occupation).
  - **2,087 Detailed Work Activities (DWAs).**
  - **1,016 occupations** (SOC6-level).
- **Workforce / wage data:** Bureau of Labor Statistics Occupational Employment Series 2020, 2021, 2022 (pp. 25–27). Uses BLS → O*NET crosswalk.
- **Industry data:** 3-digit NAICS aggregation using employment weights at SOC6 within NAICS3.
- **Productivity data:** BEA KLEMS integrated industry-level production account (2012 → 2020).
- **Education / training strata:** BLS "Typical Education Needed for Entry" and "On-the-Job Training Required," with 3,504,000 workers excluded for missing data.
- **Missing from PDF:** the attached PDF is the **Supplementary Materials**, not the main Science article; headline numbers are reported inside (Fig. 2, Tables 5–7) but the main-article prose is not included.

## Main Findings Are (1) ~80% of Workers Have ≥10% of Tasks Exposed and ~19% Have ≥50% Exposed, (2) Exposure Rises with Wages/Education, (3) Only 1.86% of Tasks Are Fully Automatable

### Headline Workforce-Level Exposure (Figure 2, p. 12)

At the $E1 + 0.5 \cdot E2$ level:
- **~80% of US workers** have ≥10% of their tasks exposed.
- **18.5% of workers** have >50% of their tasks exposed.

### Automation Distribution Across 19,265 Tasks (Table 1, p. 17)

| Automation label | Tasks | Share |
|---|---|---|
| T0 No automation exposure | 5,528 | 28.69% |
| T1 Low | 2,937 | 15.25% |
| T2 Moderate | 7,796 | 40.47% |
| T3 High | 2,646 | 13.73% |
| **T4 Full automation** | **358** | **1.86%** |
| Total | 19,265 | 100% |

### Exposure–Automation Correlation (Table 2, p. 17)

Regression of GPT-4 E-rubric score ($E1 + 0.5 \cdot E2$) on GPT-4 Automation score, N = 19,265:

| | Coef. | SE |
|---|---|---|
| Automation score | **0.936** | 0.00609 |
| Constant | 0.045 | 0.00201 |
| $R^2$ | **0.556** | — |

All coefficients significant at $p<0.01$. Univariate $R^2$ of 55.6% indicates that where automation is high, augmentation/exposure is also high.

### Exposure Rises Monotonically with Job Zone (Table 5, p. 32)

Job Zones 1→5 require increasing education/training. Median income rises from $30,230 (JZ1) to $81,980 (JZ5). Mean $E1 + 0.5 \cdot E2$ exposure:

| Job Zone | Median income | Employment (000s) | $H_{E1+0.5 E2}$ | $M_{E1+0.5 E2}$ |
|---|---|---|---|---|
| 1 (none/little prep) | $30,230 | 13,100 | 0.06 | 0.06 |
| 2 | $38,215 | 73,962 | 0.16 | 0.20 |
| 3 | $54,815 | 37,881 | 0.26 | 0.32 |
| **4 (bachelor's)** | $77,345 | 56,833 | **0.47** | **0.51** |
| 5 (master's+) | $81,980 | 21,221 | 0.43 | 0.45 |

Share of workers with >50% exposure at $E1+0.5 E2$: 0.00% (JZ1), 6.11%, 10.57%, **34.5%**, 26.45% (JZ5).

### Exposure by Education (Table 6, p. 33)

Mean $H_{E1+0.5 E2}$ by typical education needed for entry:

| Education | Median income | Employment (000s) | $H_{E1+0.5 E2}$ |
|---|---|---|---|
| No formal credential | $31,900 | 36,187 | 0.10 |
| High school | $45,470 | 67,033 | 0.20 |
| Postsecondary non-degree | $48,315 | 9,636 | 0.19 |
| Some college | $40,970 | 2,898 | 0.39 |
| Associate's | $60,360 | 3,537 | 0.31 |
| **Bachelor's** | **$78,375** | 71,698 | **0.47** |
| Master's | $79,605 | 3,216 | 0.46 |
| Doctoral / professional | $82,420 | 5,290 | 0.41 |

### Most-Exposed and Zero-Exposure Occupations (Tables 8–9, pp. 40–41)

- **34 occupations have zero exposed tasks** (human-labeled): all physical/manual, e.g., Agricultural Equipment Operators, Dishwashers, Stonemasons, Roofers, Tire Repairers, Slaughterers, Pile Driver Operators.
- **Top human-labeled $E1$ exposure:** Interpreters and Translators (76.5%), Survey Researchers (75.0%), Poets/Lyricists/Creative Writers (68.8%), Animal Scientists (66.7%), Public Relations Specialists (66.7%).
- **Fully exposed at $E1+E2$ (100%):** Mathematicians, Tax Preparers, Financial Quantitative Analysts, Writers and Authors, Web and Digital Interface Designers (human), plus 10 more; GPT-4 labeled 86 occupations as fully exposed (including Accountants, Journalists, Legal Secretaries, Clinical Data Managers, Climate Change Policy Analysts).

### Industry and Productivity Patterns (pp. 35–38)

- Highest exposure: data processing, information, hospitals (per both human and GPT-4 ratings, Fig. 9–10).
- **Little correlation between 2012→2020 TFP or labor-productivity growth and exposure** (Fig. 11–12) — suggests LLMs represent a new general-purpose technology channel not captured by recent measured productivity.

### Task-Type Robustness (pp. 28 and network analysis p. 42)

- **Writing and programming skills** have strongest *positive* association with exposure.
- **Science and critical-thinking-heavy tasks** have negative association.
- Louvain modularity of occupation network (DWA-shared edges) = **0.709**, indicating 11 coherent community clusters.

## Limitations as Noted by the Authors (§3.3, pp. 18–23)

- **Subjective human labels:** 6 annotators from OpenAI, not occupationally diverse; not experts on most O*NET jobs.
- **GPT-4 sensitivity:** GPT-4 ratings are sensitive to prompt wording, rubric order, and examples; the human and GPT-4 rubrics are deliberately slightly different.
- **Task-based framework validity:** unclear whether occupations can be fully decomposed into tasks; tacit skills may be omitted.
- **Forward-looking:** predictions depend on current LLM trajectory and are liable to change.
- **Augmentation bias in rubric design:** the E rubric asks about *time reduction at equivalent quality*, which tilts toward augmentation; a separate T (automation) rubric was introduced but labeled only by GPT-4, not humans.
- **Software as arbitrary co-invention:** E2 requires annotators to imagine unbuilt software; inherently imprecise.
- **No physical tasks:** LLM-controlled robotics excluded.
- **No adoption dynamics / general equilibrium:** exposure ≠ adoption ≠ wage impact; price/income elasticities of supply and demand determine who is displaced vs complemented (p. 16, citing 73).
- **Automation scores only from GPT-4:** should be interpreted with caution.

## Key Implications for the Research Agenda

- **LLMs satisfy general-purpose technology (GPT) criteria empirically:** pervasive task exposure across industries and occupations, continuous capability improvement, and dependence on complementary software/co-invention.
- **Regressive-vs-progressive exposure gradient is counter-intuitive:** exposure rises monotonically with wages and education through Job Zone 4, *opposite* the "routine-biased technological change" pattern of prior automation waves (Autor, Katz, Krueger 1998; Acemoglu & Restrepo 2018–20). This reverses the standard skill-biased/routine-biased framing.
- **Provides the canonical exposure measure now used downstream:** Acemoglu (2025) calibrates macroeconomics of AI using these exposure shares; Humlum & Vestergaard (2025), Liu (2025), Demirci et al. (2025), Larsen & Proserpio (2025), etc., all cite this task-level measure as the treatment-intensity proxy.
- **Validates GPT-4 as a scalable research annotator** for rubric-based task labeling — methodological contribution — while highlighting prompt-sensitivity caveats.
- **Policy:** high exposure does not equal immediate displacement (only 1.86% of tasks at T4); realization depends on co-invention, worker training, regulation, and trust.

---

## Audit Checklist

- [x] **Identification Strategy:** Descriptive task-exposure audit (E and T rubrics applied by humans + GPT-4 to 19,265 O*NET tasks). No causal design.
- [x] **Data & Sample:** O*NET 27.2 (1,016 occupations, 19,265 tasks, 2,087 DWAs); BLS OES 2020–2022 employment & wages; BEA KLEMS productivity; 3-digit NAICS.
- [x] **Main Findings:** ~80% of workers have ≥10% of tasks exposed at $E1+0.5 E2$; ~19% have ≥50%; 1.86% of tasks fully automatable (T4); exposure rises monotonically with wages/education through Job Zone 4; 34 occupations have zero exposed tasks (manual). Exposure–automation $R^2 = 0.556$.
- [x] **Limitations:** annotator bias; GPT-4 prompt sensitivity; forward-looking rubric; E tilts toward augmentation; software co-invention imprecise; no physical tasks; no adoption dynamics.
- [x] **Key Implications:** LLMs meet GPT criteria; exposure gradient is progressive (high-wage, college-educated), reversing the routine-bias pattern; provides the canonical exposure measure used in many downstream empirical and calibration papers.

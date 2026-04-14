# Liu (2025) — Labor Demand and Age in the Age of Generative AI

> Liu, X. (2025). "Labor Demand and Age in the Age of Generative AI." Working Paper.

---

## GenAI Disproportionately Reduces Demand for Entry-Level Positions, Intensifying Over Three Years

**Identification Strategy:** Difference-in-Differences exploiting ChatGPT's November 2022 release as an exogenous shock. The design compares occupations with high vs. low AI-substitution scores, conditional on similar GenAI exposure levels (using decile x quarter fixed effects to absorb the level effect of exposure). This two-dimensional framework separates substitution from complementarity. Pre-trend Wald test: F = 0.83, p = 0.66, confirming parallel trends.

**Shock/Variation:** ChatGPT's public release (November 30, 2022). Cross-sectional variation comes from occupation-level AI substitution scores.

---

## 285 Million Lightcast Job Postings Aggregated to 6.75 Million State-Industry-Occupation-Quarter Cells

**Data Source:** Lightcast (formerly Burning Glass Technologies) online job postings.

**Sample:**
- 285 million job postings
- Aggregated to **N = 6,753,930** state-industry-occupation-quarter cells
- 51 states, 20 industries, ~400 occupations
- **Time period:** 2018Q1 -- 2025Q2

**Unit of observation:** State-industry-occupation-quarter.

---

## Average Treatment Effect of -0.122 on Job Posting Volume, Reaching -0.182 by Year 3

**Preferred specification (Table 1, Column 3):**
- Average post-treatment effect: **-0.122*** (SE = 0.036)
- Dynamic effects:
  - Year 1 (2023): **-0.064*** (SE ~ 0.036, p < 0.10)
  - Year 2 (2024): **-0.135** (SE ~ 0.036, p < 0.05)
  - Year 3 (2025): **-0.182*** (SE ~ 0.036, p < 0.01)

**By experience level:**
- Entry-level positions: **-19%** long-term decline (largest effect)
- Effects attenuate with seniority

**By industry:**
- Administrative support: **~-40%** (largest sectoral effect)
- Professional services: **~-30%**

---

## Limitations

- **Demand only:** Measures job postings (labor demand), not actual employment or hours worked.
- **Arsinh transformation:** Inverse hyperbolic sine used for the dependent variable, with known interpretation caveats for large changes.
- **Cannot capture new job creation:** The framework identifies displacement in existing occupation categories but cannot detect entirely new roles created by GenAI.
- **U.S.-only:** Results may not generalize to other labor markets.
- **No wage data:** Cannot assess wage effects alongside quantity effects.
- **Substitution score not GenAI-specific:** The AI substitution scores were developed for broader AI, not specifically for generative AI capabilities.

---

## GenAI Displaces Labor Demand at Unprecedented Speed, Threatening the Entry-Level Pipeline

- Speed of displacement is historically unprecedented compared to robotics and prior AI waves.
- Entry-level pipeline is most at risk — the traditional pathway for young workers to gain experience and advance is being compressed.
- Administrative and professional service roles face the steepest declines.
- Urgent implications for workforce retraining programs and social protection policies targeted at early-career workers.

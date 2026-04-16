# Audit Notes: Acemoglu (2025) — The Simple Macroeconomics of AI

**Citation:** Acemoglu, D. (2025). "The simple macroeconomics of AI." *Economic Policy*, 40(121), 13–58. https://doi.org/10.1093/epolic/eiae042

**File:** `papers/Acemoglu2025_SimpleMacroeconomicsAI.pdf` (46 pages)

**Audit date:** 2026-04-16

---

## Identification strategy is analytical/calibration, not causal

This is a **theoretical + back-of-the-envelope calibration** paper, not a causal empirical study. There is no quasi-experimental shock, DiD, IV, or RDD. The identification logic is:

1. **Task-based production model** (building on Acemoglu and Autor 2011; Acemoglu and Restrepo 2018, 2019b, 2022). Final good produced from a continuum of tasks with measure $N$, CES aggregator with elasticity $\sigma$ between tasks. Each task can be allocated to capital or labour; automation is the expansion of the capital-assigned task set $I$ (pp. 21–22, eqs. 1–2).
2. **Hulten's theorem** (Hulten 1978) delivers the master equation (eq. 14, p. 28):
   $$d\ln \text{TFP} = \bar\pi \times (\text{GDP share of tasks impacted by AI})$$
   where $\bar\pi$ is average overall (not labour) cost savings. A refinement (eq. 15, p. 31) splits exposed tasks into easy-to-learn vs hard-to-learn:
   $$d\ln \text{TFP} = \mu_E \bar\pi_E + (1-\mu_E)\bar\pi_H \times (\text{GDP share impacted}).$$
3. **Calibration** of the master equation is done with external estimates of (i) the GDP share of exposed tasks (Eloundou et al. 2024; Svanberg et al. 2024) and (ii) average cost savings $\bar\pi$ (Peng et al. 2023; Noy and Zhang 2023; Brynjolfsson et al. 2023).
4. **Wage and inequality effects** are derived by adapting the general-equilibrium "propagation matrix" estimates of Acemoglu and Restrepo (2022, Table 8, col. 2, 1980–2016) to the AI exposure vector constructed here.

The "shock" is the rollout of generative AI and computer vision over a 10-year horizon; the paper does not exploit any real-world variation in AI adoption to identify an effect. It is a **disciplined forecasting exercise**, and the author repeatedly flags the speculative nature of parameter choices (pp. 18, 36–37).

## Data sources are proof-of-concept RCTs plus task-level exposure measures

- **Task exposure to AI:** Eloundou et al. (2024) GPT-4-coded automation index over **19,265 O*NET tasks** and **2,087 Detailed Work Activities (DWAs)** (p. 37). Acemoglu uses their β (indirect-exposure) automation index and defines "AI-exposed tasks" as those with >50% of activities flagged.
- **Feasibility filter:** Svanberg et al. (2024) estimate that **23%** of computer-vision-exposed tasks are cost-effectively automatable within 10 years (p. 38). Extrapolated to the full Eloundou set.
- **Cost savings:** Three experimental studies —
  - Peng et al. (2023): GitHub Copilot, freelance programmers, **55.8%** faster task completion (p. 39).
  - Noy and Zhang (2023): ChatGPT-3.5 for white-collar writing, **40%** faster, **18%** quality gain (p. 39).
  - Brynjolfsson, Li, and Raymond (2023): generative AI for customer service, **14%** faster, statistically insignificant quality decline (p. 39).
- **Wage-bill weights:** BLS National Occupational Employment and Wage Estimates pooled **2019–22** (p. 38).
- **Industry labour shares:** BEA NIPA, **14 aggregated industries**, years **2018–22** (footnote 24, p. 41).
- **Demographic groups:** **500 groups** by education × age × gender × ethnicity × native/foreign-born, from ACS 5-year sample 2018–22 (p. 48–49). Propagation matrix from Acemoglu and Restrepo (2022) based on 1980–2016.
- **Bad-task calibration:** Bursztyn et al. (2023) willingness-to-pay estimates for TikTok/Instagram; 2022 10-K revenues for Meta ($130B), Alphabet ($307B), Snapchat ($4.6B), X ($2.5B), TikTok ($16B) (pp. 46–47). IT security spend $78B (Statista).

**No new primary data collection.** Sample sizes $N$ are defined at the task level (19,265 O*NET tasks; 4,089 exposed tasks after filtering, p. 43) and at the demographic-group level ($N=500$ groups for the wage/inequality exercise).

## Main findings: 10-year TFP gain is bounded below 0.66%, GDP gain below 1.56%

### TFP and GDP (Sections 3.2–3.4)

- **20%** wage-bill-weighted share of US occupations exposed to AI (p. 38).
- Combined with Svanberg 23% feasibility filter, **GDP share of AI-impacted tasks = 0.23 × 0.20 = 4.6%** (p. 38, eq. applied p. 41).
- Average **labour** cost savings = **27%** (average of Noy-Zhang 40% and Brynjolfsson et al. 14%, p. 40).
- Average (exposure-weighted) labour share = **0.535**, so average **overall** cost savings $\bar\pi \approx 0.27 \times 0.535 = 0.144$ (14.4%, p. 41).
- **Baseline TFP gain, 10 years = 0.046 × 0.144 ≈ 0.66%** — i.e. ~0.064 percentage points per year (p. 41, eq. on p. 41).
- Including Peng et al.'s 55.8% → labour savings 0.36, overall 0.193 → TFP gain **≈ 0.89%** over 10 years (p. 42).
- **Easy/hard refinement (Section 3.3, p. 45):** 72.6% of wage-bill-weighted exposed tasks classified as easy-to-learn. Easy tasks = 3.3% of GDP, hard tasks = 1.3% of GDP. Easy cost savings 0.144, hard cost savings 0.037 (7% labour × 0.535). Result:
  $$d\ln \text{TFP} = 0.033 \times 0.144 + (0.046-0.033) \times 0.037 \approx 0.0053 = 0.53\%$$
  over 10 years (p. 45).
- **GDP translation (Section 3.4, p. 46):** Using capital share 0.43 and proportional capital-stock response, GDP gain = TFP gain × 1.75, giving **0.93%–1.16%** over 10 years. With the fuller Acemoglu–Restrepo (2022) investment response, upper bound rises to **1.4%–1.56%** (Table 1, row 7; p. 50–51). The 1.4% number is from column 7 (easy/hard-adjusted), the 1.56% from column 3 (baseline).

### Wage and inequality effects (Section 3.6, Table 1, p. 51)

Table 1 reports AI exposure and wage effects across five education groups, an average worker, and GDP, using the Acemoglu–Restrepo (2022) propagation matrix. Selected values (all over a 10-year horizon):

| Group | Baseline AI exposure (col. 1) | Direct effect (col. 2) | Total wage effect (col. 3) | Easy-exposure (col. 4) | Hard-exposure (col. 5) | Direct easy+hard (col. 6) | Total easy+hard (col. 7) |
|---|---|---|---|---|---|---|---|
| < HS | 0.0318 | −0.0323 | **+0.0157** | 0.0235 | 0.0083 | −0.0356 | **+0.0132** |
| HS grad | 0.0464 | −0.0617 | +0.0106 | 0.0337 | 0.0128 | −0.0649 | +0.0079 |
| Some college | 0.0494 | −0.0676 | +0.0139 | 0.0357 | 0.0138 | −0.0709 | +0.0112 |
| BA | 0.0523 | −0.0733 | +0.0060 | 0.0382 | 0.0140 | −0.0765 | +0.0040 |
| Post-grad | 0.0405 | −0.0498 | +0.0098 | 0.0299 | 0.0106 | −0.0530 | +0.0081 |
| Average worker | 0.0462 | −0.0612 | +0.0101 | 0.0336 | 0.0126 | −0.0644 | +0.0077 |
| GDP | — | — | **+0.0156** | — | — | — | **+0.0140** |

- **Direct wage impacts are negative** for every education group (col. 2: −3.2% to −7.3%), but equilibrium **total** wage effects are positive and small (col. 3: +0.6% to +1.6%; col. 7: +0.4% to +1.3%) once productivity and ripple effects are included (pp. 50–51).
- **No standard errors or confidence intervals are reported** — this is a calibration, not an estimation, so the reported numbers are point values conditional on the input parameters.
- Compare col. 8 (direct displacement 1980–2016 from Acemoglu–Restrepo 2022): less-than-HS = 0.2690, HS = 0.2706 — i.e., pre-AI automation was far more skewed against low-education groups. AI exposure is **much more evenly distributed** (p. 50).
- Between-group SD of log wages (employment-weighted) rises slightly from **0.35 to 0.36** (p. 51).
- **Capital share rises by ~0.31 percentage points** (p. 51) — inequality between capital and labour widens.
- Figure 3 (p. 53) shows **low-education women, especially white native-born low-education women**, experience real-wage declines.

### New bad tasks (Section 3.5, pp. 46–47)

- Bursztyn et al. (2023): TikTok/Instagram willingness to pay ≈ **$53/user-month** to use, but WTP ≈ **$19/user-month** for others to stop → ratio of negative to positive effect = **−19/53 ≈ −0.36**.
- Revenue proxy for AI-enabled "bad tasks": ≈ **2% of US GDP** (social media + digital ads $460B / 1.64% + IT security $78B / 0.28% + ~1/3 of that for malicious spend, p. 47).
- Apparent GDP boost = **+2.0%**, welfare impact = 0.02 × (−0.36) ≈ **−0.72%** of GDP in consumption-equivalent units (p. 47, restated p. 55).

## Key parameter choices and assumptions

- Elasticity of substitution between tasks $\sigma = 0.5$ (Humlum 2021; also used in Acemoglu–Restrepo 2022), p. 21.
- Elasticity of substitution between sectors in consumption $\eta = 0.2$ (Buera et al. 2022), p. 49.
- Capital share $s_K = 0.43$ (private business sector), p. 46.
- Hard-task cost savings set to **7% labour / 3.7% overall** — "half of Brynjolfsson et al.'s 14%"; explicitly speculative (p. 45).
- 50%-activity-impacted threshold in the Eloundou β-automation index used to define "exposed" (p. 37).

## Limitations (flagged by the author)

1. Only **1.5%** of US firms invested in AI by 2019 (Acemoglu et al. 2022) — adoption lag may further shrink realized gains (p. 42).
2. **J-curve** delays from digital-technology literature suggest the flat part can last ≥20 years (Greenwood–Yorukoglu 1997; Brynjolfsson–Rock–Syverson 2021), so 10-year cost reductions likely overstated (p. 42).
3. Extrapolating Svanberg et al.'s computer-vision feasibility to all Eloundou-exposed tasks is "not innocuous" (footnote 21, p. 38).
4. Propagation matrix is estimated on 1980–2016 robotics/software displacement, not AI — context-specificity caveat (p. 48).
5. New-good-task productivity gains are **excluded** from estimates because existing exposure measures do not cover them and because Acemoglu judges the industry is not currently oriented toward them (pp. 55–56).
6. Easy/hard classification uses a GPT-4-trained gradient-boosted tree calibrated on 500 manually-coded tasks (p. 45); author acknowledges specific misclassifications (e.g., "writing reports on climate studies" flagged 0.67 easy — likely too easy, footnote 27).
7. Only **US** economy; impact on developing economies unaddressed (footnote 2, p. 16).

## Key implications

- **Forecasts of 7% GDP gain (Goldman Sachs) or 1.5–3.4 pp annual growth (McKinsey) are not reconcilable** with the task-based Hulten accounting using existing microeconomic estimates. Acemoglu's upper bound for 10-year GDP gain is ~1.56%.
- TFP gain is modest: **0.53%–0.66% over 10 years** (≈ 0.05–0.07 pp/year), an order of magnitude below Goldman/McKinsey forecasts.
- **AI is unlikely to reduce wage inequality**: direct displacement is more evenly distributed than for prior automation, but (i) capital-labour gap widens by ~0.31 pp, (ii) low-education women (especially white, native-born) may see real-wage declines, (iii) between-group log-wage SD rises from 0.35 to 0.36.
- **New bad tasks can make GDP a misleading welfare proxy**: calibration suggests a +2% GDP effect can coexist with −0.72% welfare in consumption-equivalent units.
- Policy conclusion: bigger AI gains require re-orienting the technology toward **new pro-worker tasks** (expertise provision for electricians, nurses, teachers, clerical workers) rather than human-like conversational models.

## Appendix

- **Supplementary Appendix** (referenced throughout, p. 20 and elsewhere): contains the full list of verbs classified easy/hard, the 14-industry NIPA mapping, and the gradient-boosted-tree training details. Not read in this audit (classified by the prompt as technical appendix without new results).
- **References (pp. 56–58):** bibliography only; not audited.

---

**Audit completed by:** Claude (Opus 4)
**Protocol:** Lossless Research Audit per `Prompt.md`
**Method:** Full-text extraction via PyPDF2 (no page-range splitting needed for 46 pages at 1.6 MB).

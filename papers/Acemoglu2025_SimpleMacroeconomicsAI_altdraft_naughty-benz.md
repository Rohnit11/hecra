# AI's Macroeconomic Gains Are Modest: At Most 0.66% TFP Over 10 Years

**Citation:** Acemoglu, D. (2025). "The Simple Macroeconomics of AI." *Economic Policy*, 40(121), 13–58. DOI: 10.1093/epolic/eiae042

---

## Identification Strategy: Calibrated Task-Based Model + Hulten's Theorem

This is a **theoretical and calibration paper**, not a causal empirical study. There is no shock-based identification (no DiD, IV, or RDD). The strategy is:

1. **Theoretical framework**: Task-based general equilibrium model from Acemoglu & Restrepo (2018, 2019b, 2022). Final output requires a continuum of tasks [0, N]; tasks are assigned to capital (z ≤ I) or labour (z > I) based on comparative advantage. Elasticity of substitution between tasks σ ≈ 0.5 (Humlum 2021).

2. **Hulten's Theorem as the discipline**: For competitive economies with constant returns to scale, aggregate TFP change equals the GDP-share-weighted sum of task-level productivity improvements:
   - `d ln TFP = π̄ × (GDP share of tasks impacted by AI)` [Equation 14]
   - Refined: `d ln TFP = (μᴱπ̄ᴱ + (1−μᴱ)π̄ᴴ) × GDP share` [Equation 15]

3. **Calibration inputs** (all from external studies, plugged into the theorem):
   - Task exposure: Eloundou et al. (2024) GPT-4-coded O\*NET automation index
   - Feasibility/profitability of automation within 10 years: Svanberg et al. (2024)
   - Labour cost savings: Noy & Zhang (2023) and Brynjolfsson et al. (2023)
   - Wage/inequality effects: Acemoglu & Restrepo (2022) propagation matrix

4. **Easy vs. hard task classification** (novel contribution): 4-step ML pipeline on 4,089 exposed O\*NET tasks — (1) manual verb coding, (2) manual IWA coding, (3) LDA topic modelling (100 clusters, all 19,281 tasks), (4) gradient-boosted tree trained on 500 manually labelled tasks to assign easy/hard probabilities.

**Key assumption scrutinised:** Svanberg et al.'s computer vision feasibility rate (23%) is extrapolated to ALL AI-exposed tasks — a non-innocuous step the author flags explicitly.

---

## Data & Sample

| Source | Purpose | Coverage |
|--------|---------|----------|
| Eloundou et al. (2024) | Task AI exposure | 19,265 O\*NET tasks, 2,087 DWAs, GPT-4 coded (β automation index) |
| US BLS Occupational Employment & Wage Estimates | Wage bill weights | Pooled 2019–22, all US occupations |
| Svanberg et al. (2024) | Feasibility of automation within 10 years | Computer vision tasks subset |
| Noy & Zhang (2023) | Labour cost savings (writing tasks) | RCT, white-collar workers, ChatGPT-3.5 |
| Brynjolfsson et al. (2023) | Labour cost savings (customer service) | RCT, real business, generative AI tool |
| Peng et al. (2023) | Labour cost savings (programming) | RCT, GitHub Copilot, JavaScript tasks |
| US BEA NIPA (2018–22) | Industry labour shares | 14 aggregated NIPA industries |
| 5-year American Community Survey (2018–22) | Demographic wage effects | 500 demographic groups (education × age × gender × ethnicity × nativity) |
| Acemoglu & Restrepo (2022) propagation matrix | Ripple effects across groups | 49 BEA industries, 1980–2016 baseline |
| Bursztyn et al. (2023) | Social media welfare estimates | TikTok + Instagram, college students |

**No single N** — this is a calibration/theory paper. The task classification uses 4,089 exposed tasks, of which 500 are manually labelled as the training sample.

---

## Main Findings

### TFP Estimates (10-Year Horizon)

| Scenario | TFP Gain (10 yr) | Annual TFP Boost |
|----------|-----------------|-----------------|
| Baseline (no easy/hard distinction) | **0.66%** | ~0.064% |
| Adjusted for hard tasks | **0.53%** | ~0.053% |
| With Peng et al. (higher cost savings) | ~0.89% | ~0.089% |
| With rapid GPU cost decline (speculative) | ~0.90% | ~0.090% |

**Calculation (baseline, pp. 41):**
- GDP share impacted = 0.23 × 0.20 = **4.6%**
- Average overall cost savings = 0.27 × 0.535 = **14.4%**
- TFP = 0.046 × 0.144 = **0.0066**

**Calculation (hard-task adjusted, p. 45):**
- Easy tasks = 72.6% of exposed → 3.3% of GDP; cost savings 14.4%
- Hard tasks = 27.4% of exposed → 1.3% of GDP; cost savings 3.7%
- TFP = 0.033 × 0.144 + 0.013 × 0.037 = **0.0053**

### GDP Estimates (10-Year Horizon)

| Scenario | GDP Gain (10 yr) |
|----------|-----------------|
| Baseline TFP, modest investment (capital ∝ TFP) | **0.93–1.16%** |
| Baseline TFP, large investment boom (Acemoglu-Restrepo 2022 framework) | **1.40–1.56%** |
| Hard-task adjusted TFP, modest investment | **0.90%** |
| Hard-task adjusted TFP, large investment | **1.40%** |

GDP = TFP / (1 − capital share) = TFP / 0.57 ≈ TFP × 1.75 (benchmark); capital share = 0.43 (private business sector).

### Wage & Inequality Findings (Table 1, col. 7 — easy/hard exposure)

| Group | Total Wage Effect (10 yr) |
|-------|--------------------------|
| Workers < high school | +1.32% |
| Workers with high school | +0.79% |
| Workers with some college | +1.12% |
| Workers with Bachelor's | +0.40% |
| Workers with postgraduate | +0.81% |
| **Average worker** | **+0.77%** |
| **GDP** | **+1.40%** |

- Between-group SD of log wages rises slightly: **0.35 → 0.36**
- Capital share rises by ~**0.31 percentage points**
- **Low-education women** (especially native-born white) face **small real wage declines**
- AI exposure is MORE equally distributed across demographic groups than pre-AI automation (robotics/software)

### "Bad Tasks" Welfare Decomposition (pp. 46–47, speculative)

- Revenues from social media + digital ads + IT security arms race ≈ **2% of US GDP** (2022)
- Welfare damage ratio from Bursztyn et al.: −$19 / $53 = **−0.36** per dollar of revenue
- Implied welfare loss: 0.02 × 0.36 = **−0.072% of GDP** (consumption equivalent)
- Scenario: AI may appear to raise GDP by 2% while reducing welfare by **−0.72%**

---

## Limitations (As Noted by Author)

1. **Easy-task bias in existing evidence** — all RCT productivity estimates (Noy & Zhang, Brynjolfsson et al., Peng et al.) come from easy-to-learn tasks; hard-task gains are speculative (author assumes 7% vs. 27% labour savings)
2. **Low AI adoption** — <1.5% of US businesses had any AI investment in 2019; small/medium enterprises are underrepresented
3. **J-curve adjustment costs** — Greenwood & Yorukoglu (1997) find a flat 20-year J-curve for digital technologies; full gains may materialise beyond 10 years
4. **Svanberg et al. extrapolation** — computer vision feasibility rate applied to all AI-exposed tasks (including LLM/generative AI tasks), which is acknowledged as non-innocuous
5. **New good tasks excluded** — the paper does not model positive productivity effects from AI-generated new tasks (electricians, educators, healthcare), because current industry focus is on automation and monetisation, not worker-augmenting tools
6. **Propagation matrix is historical** — uses Acemoglu & Restrepo (2022) 1980–2016 ripple effects; may not apply to generative AI's specific displacement patterns
7. **"Bad tasks" estimates highly speculative** — Bursztyn et al. numbers pertain to college students; social media welfare damage proxied by willingness-to-pay experiments

---

## Key Implications

- **Challenges large forecasts**: Goldman Sachs (+7% global GDP) and McKinsey ($17–26 trillion) are implausible under Hulten's theorem applied to realistic task-level cost savings
- **Hulten's theorem as discipline**: The key insight is that macro gains are bounded by micro cost savings × exposed GDP share; no combination of plausible assumptions reaches 1% annual TFP growth
- **Capital-labour inequality will widen** regardless of whether AI improves productivity via automation OR task complementarities (when σ < sK ≈ 0.4)
- **"Blue-collar bonanza" not supported**: AI is more equally distributed across skill groups than robotics, but does not reduce inequality; low-education women face small losses
- **New task creation is the key**: Larger benefits require reorienting AI toward worker-complementary new tasks (plumbers, nurses, educators needing real-time context-specific information), not general-purpose LLMs
- **Welfare ≠ GDP**: Bad-task creation may cause GDP and welfare to diverge substantially

---

## Replication Feasibility

- **Data availability**: Eloundou et al. (2024) data shared by Pamela Mishkin and Daniel Rock (acknowledged). BLS/BEA/ACS data are public. Acemoglu & Restrepo (2022) propagation matrix is in that paper's replication package.
- **Code**: Supplementary Appendix available at *Economic Policy* online (lists 14 NIPA industries, task-to-occupation-to-industry crosswalks, easy/hard task classification details)
- **Classification training data**: 500 manually labelled tasks used to train gradient-boosted tree; full easy/hard task list in Supplementary Appendix
- **No replication archive** explicitly mentioned, but the methodology is fully described and relies on publicly available inputs

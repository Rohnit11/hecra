# Audit Notes: Goldberg & Lam (2026) -- Generative AI & Creative Goods: Market Expansion, Crowd-Out, and Copyright

**Paper:** Goldberg, Samuel G. and H. Tai Lam. "Generative AI & Creative Goods: Market Expansion, Crowd-Out, and Copyright." March 9, 2026.
**Affiliations:** Stanford GSB; UCLA Anderson School of Management.
**Previously circulated as:** "Generative AI in Equilibrium: Evidence From a Creative Goods Marketplace."
**JEL Codes:** L1, L15, L81, O14, O33, O34, Z11

---

## 1. Identification Strategy

**Method:** Difference-in-differences (DiD) with a single treatment date and cross-sectional variation in treatment exposure.

**Shock/Variation:** In December 2022, a large stock images platform (identified as Adobe Stock in Appendix A.4, p.56) announced it would allow GenAI-produced images starting July 2023. Two key policy conditions create identification:

1. **GenAI labeling requirement:** All GenAI images must be disclosed and labeled; enforced via algorithmic detection, human review, and account suspension for violations.
2. **Editorial image ban for GenAI:** GenAI is prohibited in editorial/branded image markets (images depicting real-world brands, newsworthy events). This creates the cross-sectional variation.

**Treatment group:** Non-branded keyword markets (1,335 markets) -- where GenAI entry is allowed.
**Control group:** Branded keyword markets (384 markets) -- where GenAI remains prohibited (editorial content).

**Specification (Equation 1, p.25):**

Y_mt = beta_1 * Post(1-6 mth)_t * Treated_m + beta_2 * Post(7+ mth)_t * Treated_m + FE_m + FE_t + epsilon_mt

- Post period split into announcement (months 1-6) and implementation (months 7+).
- Market FE and month FE included.
- Standard errors clustered at the market (keyword) level.
- Count outcomes estimated via Poisson; bounded fraction outcomes via fractional logit.
- Average Percentage Effects (APE) reported via delta method (pp.25-26).
- Event study specification also estimated (Equation 4, p.26).

**Parallel trends:** Pre-treatment trends are visually parallel (Figures 5, 6, 8). Formal tests following Roth (2022) fail to reject null of parallel pre-trends across all outcomes (Appendix D.3, p.27).

**Robustness checks (Appendix D):**
- Propensity score matching on pre-treatment observables (D.5)
- Embedding dissimilarity-weighted control group to address SUTVA/spillovers (D.4)
- Continuous treatment based on pre-treatment editorial image share (D.6)
- Pre-treatment linear trend tests (D.3)

---

## 2. Data & Sample

**Data source:** Large stock images platform (Adobe Stock), using official APIs and web scraping validation.

**Time period:** October 2021 to May 2024 (balanced monthly panel).

**Unit of observation:** Market (keyword) x month.

**Sample construction:**
- Markets defined by keyword searches on the platform.
- Keywords derived from platform category hierarchy, keyword suggestion chains, and public brand name lists.
- Filtered to narrow keywords (<10,000 images) with >75 images in pre-treatment period.
- Overlap exclusion algorithm applied to ensure distinct markets (95.19% of images appear in only one keyword market).

**Final sample:**
- **N = 55,008 market-month observations** (1,719 keywords x 32 months)
- **1,719 unique keyword-defined markets:** 384 branded (control), 1,335 non-branded (treated)
- **~3,001,183 unique images**
- **62,124 unique artists**
- Only 4.8% of images appear in multiple keywords.

**Key variables observed per image:** Artist profile, image ID, title, resolution, format, sold status (binary: ever sold vs. not), tags (up to 50), quality rank, GenAI flag (is_gentech), editorial flag, and 1,408-dimension embedding (Google Vertex AI multimodalembedding@001).

**Pricing:** Uniform $3 per image; artists receive 33% of net price. No price variation between GenAI and non-GenAI.

**Date imputation:** Publication dates estimated from sequential image IDs using truncated third-order polynomial fitted on ~100,000 images with explicit dates in titles (p.55).

**Summary statistics (Table 1, p.19, pre-GenAI period):**

| Outcome | Branded (N=384) Mean | Non-branded (N=1,335) Mean |
|---|---|---|
| Active Artists/month | 4.45 | 3.59 |
| Publications/month | 44.93 | 40.37 |
| Sales/month | 16.03 | 8.63 |
| Sold Rate | 0.40 | 0.24 |
| Predicted Sales Prob | 0.52 | 0.38 |

---

## 3. Main Findings

### 3A. Supply Side (Table 2, p.30; Figure 5, p.29)

**Image Production (Poisson, APE for Post 7+ mth x Treated):**
- All images: **+135.9%** (coeff 0.858, SE 0.040, p<0.01)
- Non-GenAI images: **-14.7%** (coeff -0.158, SE 0.037, p<0.01)

**Active Artists (Poisson, APE for Post 7+ mth x Treated):**
- All artists: **+47.1%** (coeff 0.386, SE 0.028, p<0.01)
- Non-GenAI artists: **-29.0%** (coeff -0.342, SE 0.021, p<0.01)

**Embedding Quality (Fractional Logit, APE for Post 7+ mth x Treated):**
- All images: **+9.6%** increase in predicted sale probability (coeff 0.389, SE 0.009, p<0.01)
- Non-GenAI images: **+1.8%** (coeff 0.071, SE 0.008, p<0.01) -- suggests low-quality non-GenAI artists exit.

**Announcement effect (Post 1-6 mth x Treated):** Immediate ~8-10% decline in non-GenAI production and active artists, driven entirely by non-GenAI artists leaving before GenAI even enters.

### 3B. Demand Side (Table 3, p.33; Figure 6, p.32)

**Sales (Poisson, APE for Post 7+ mth x Treated):**
- All sales: **+82.0%** (coeff 0.599, SE 0.036, p<0.01)
- Non-GenAI sales: **-28.2%** (coeff -0.331, SE 0.034, p<0.01)

**Sales Rate (Fractional Logit, APE for Post 7+ mth x Treated):**
- All: **-2.2%** (coeff -0.087, SE 0.025, p<0.01)
- Non-GenAI: **-4.8%** (coeff -0.192, SE 0.026, p<0.01)

**Sold Embedding Quality (Fractional Logit, APE for Post 7+ mth x Treated):**
- All: **+8.6%** (coeff 0.347, SE 0.010, p<0.01)
- Non-GenAI: **+1.2%** (coeff 0.049, SE 0.009, p<0.01)

### 3C. Product Characteristics & Market Composition (Table 4, p.38; Figure 8, p.37)

All estimated via OLS with keyword and month FE. Post 7+ mth x Treated coefficients:

| Measure | All | Non-GenAI |
|---|---|---|
| Volume | +1.153*** (0.141) | +0.132 (0.131) n.s. |
| Trace (variety) | -0.034*** (0.003) | +0.014*** (0.003) |
| Gini (concentration) | +0.046*** (0.003) | -0.009*** (0.003) |

**Interpretation:** GenAI expands market boundaries (volume increases) but production is concentrated in embedding space (Gini rises, trace falls). Non-GenAI responds by *differentiating* -- spreading out in embedding space (trace increases, Gini falls for non-GenAI). Overall pattern consistent with Figure 7b: new GenAI images enter in dense clusters outside the ex-ante convex hull.

### 3D. Heterogeneity Analysis (Section 5, pp.40-47)

**Content type -- Human vs. Non-Human images (Tables 5-6, pp.42-44):**
- Human markets see *more* total production increase (+20.6% additional, p<0.05) but *less* crowd-out of non-GenAI artists (+22.5% smaller decline, p<0.01).
- Model release requirements serve as a differentiation mechanism shielding non-GenAI artists in human-image markets.
- Non-GenAI sales rate decline is significantly smaller in human markets (Table 6, Col 4: +0.093*, p<0.10).

**Market size -- Large vs. Small (Tables 7-8, pp.46-47):**
- Niche (small) markets face greater disruption but also larger quality gains (embedding quality APE: -1.1% for large vs. small, p<0.05).
- Large markets show stickier non-GenAI demand: non-GenAI sales decline is +23.1% weaker in large markets (p<0.01, Table 8 Col 2).
- Large markets show weaker non-GenAI sales rate decline (+3.4%, p<0.05, Table 8 Col 4).

---

## 4. Limitations (as noted by authors, pp.49)

1. **DiD estimates ATEs only** -- effect heterogeneity across markets and timing heterogeneity in adoption may obscure important variation.
2. **Endogenous platform adjustments** -- platform may have changed moderation standards or search algorithms alongside policy change; cannot fully rule out subtle changes.
3. **Profiles vs. workers** -- observe artist profiles, not individual workers; cannot distinguish artists who exit entirely vs. reduce production vs. adopt GenAI themselves.
4. **GenAI labeling accuracy** -- identification relies on accurate labeling; mislabeling would attenuate treatment effects (estimates are conservative).
5. **Early adoption period** -- analysis captures relatively early period of GenAI adoption (through May 2024); dynamics may shift as models train on GenAI-generated content.
6. **Cannot fully bound welfare effects** -- lack data on artist-level production costs, outside options, and adoption decisions.
7. **Uniform pricing** -- $3 uniform price may amplify substitution effects vs. settings where price differentiation absorbs competitive pressure.
8. **Date imputation** -- publication dates approximated from sequential image IDs, introducing classical measurement error (mitigated by monthly aggregation and broad post-treatment indicators).
9. **Single platform** -- results may not generalize to platforms with weaker enforcement, no disclosure, or price flexibility.
10. **Sold measure is binary** (ever sold vs. not) -- 82% of images never sold, so binary is a close proxy, but not the same as observing detailed sales data.

---

## 5. Key Implications for Research Agenda

1. **Market expansion AND crowd-out coexist:** GenAI leads to simultaneous market expansion (+82% sales, +136% production) and substantial displacement of non-GenAI content (-28% sales, -29% active artists). These are not mutually exclusive.

2. **Copyright/fair use relevance:** Results speak directly to the fourth factor of fair use doctrine ("effect on the market for the original"). Evidence of substantial substitution and "market depletion" weakens fair use defenses. GenAI production is concentrated in embedding space rather than uniformly expanding creative possibilities, raising substantiality concerns under the third factor.

3. **Legal frictions as differentiation:** Model release requirements for human images moderate crowd-out, suggesting that copyright protections and regulatory frictions can serve as natural differentiation mechanisms for human creators.

4. **Quality selection effects:** Low-quality non-GenAI artists exit; remaining non-GenAI production is higher quality and more diverse. This is consistent with Schumpeterian creative destruction patterns.

5. **Non-GenAI strategic response:** Human artists differentiate into niches -- spreading out in embedding space where GenAI is not producing. This suggests human creators retain comparative advantage in less-populated regions of the product space.

6. **Long-run training data sustainability:** If non-GenAI production continues to decline, the original creative works needed for training future GenAI models may become increasingly scarce -- a potential negative feedback loop.

7. **Methodological contribution:** Novel use of image embeddings as high-dimensional product characteristics to measure market composition (volume, trace/variety, Gini/concentration). Embedding-based quality measure using pre-policy sales prediction model.

8. **Platform design matters:** Mandatory GenAI labeling + uniform pricing created transparent competition on quality. Platforms with opaque GenAI integration or price flexibility may see different dynamics.

---

## Appendix Structure (pp.50-120)

- **Appendix A (pp.50-65):** Data details -- API infrastructure, market definition strategy, variable construction, final sample, entry/exit decomposition, panel validation.
- **Appendix B (pp.65+):** Embedding measures construction details, quality measure validation (including lab experiment in B.2.6).
- **Appendix C:** Descriptive evidence on GenAI adoption driven by new artist portfolios (not incumbents switching).
- **Appendix D:** Robustness -- pre-trend tests (D.3), SUTVA/spillover tests (D.4), propensity score matching (D.5), continuous treatment (D.6), search algorithm analysis (D.7).
- **Appendix E:** Theoretical model of consumer search and firm technology choice.
- **Appendix F:** Anecdotal evidence on platform moderation and enforcement.

---

*Audit completed: 2026-04-13. All findings reported directly from paper text and tables. No data hallucinated.*

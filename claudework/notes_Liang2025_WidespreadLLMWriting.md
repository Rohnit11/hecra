# Liang et al. (2025) — Widespread LLM-Assisted Writing Across Society

> Liang, W. et al. (2025). "Widespread LLM-Assisted Writing Across Society." *Patterns*, Elsevier/Cell Press.

---

## A Distributional Framework Detects Population-Level LLM Writing Without Individual Classification

**Identification Strategy:** Descriptive / statistical — **not causal**. The paper develops a distributional framework to estimate the population-level share of LLM-assisted writing using token frequency mixture modeling (Maximum Likelihood Estimation). The method compares pre-ChatGPT and post-ChatGPT token probability distributions, identifying "excess mass" in high-probability tokens as a signature of LLM involvement. Prediction error < 3.3% in validation. Results are explicitly framed as a **lower bound** on true LLM adoption (cannot detect heavily edited LLM output).

**No shock or variation exploited for causal identification.** The temporal comparison (pre vs. post ChatGPT) is used for descriptive trend estimation, not causal inference.

---

## Four Large Corpora Spanning Consumer, Corporate, Labor, and International Domains

**Data Sources and Sample Sizes:**

| Corpus | Source | N | Period |
|--------|--------|---|--------|
| Consumer complaints | CFPB (Consumer Financial Protection Bureau) | 687,241 | Jan 2019 -- Sep 2024 |
| Job postings | Revelio Labs (LinkedIn) | 304.3M total; 1.44M small firms | varies |
| Corporate press releases | NewsAPI (Newswire) | 537,413 | varies |
| UN press releases | United Nations | 15,919 | varies |

**Unit of observation:** Individual document (complaint, posting, press release).

---

## ~18% of Consumer Complaints and ~24% of Corporate Press Releases Are LLM-Assisted by Late 2024

**Main Findings:**

- **Consumer complaints (CFPB):** ~18% LLM-assisted by late 2024
- **Corporate press releases (Newswire):** ~24% LLM-assisted by late 2024
- **Small-firm job postings:** ~10--15% LLM-assisted
- **UN press releases:** ~14% LLM-assisted

**Heterogeneity:**
- Younger/smaller firms show markedly higher LLM adoption
- Areas with lower educational attainment show modestly higher adoption (p < 0.001)
- Urban-rural divide: 18.2% vs. 10.9% LLM-assisted writing

**Validation:** Prediction error < 3.3% against known ground-truth mixtures.

---

## Limitations

- **Lower bound:** Cannot detect heavily edited LLM output — estimates are conservative.
- **English-only:** All corpora are in English; cross-language generalizability unknown.
- **ChatGPT-family focus:** Detection calibrated on ChatGPT-era models; may miss output from other LLM families.
- **No individual-level classification:** The framework estimates population shares, not whether a specific document was LLM-assisted.

---

## LLM Writing Adoption Is Rapid and Widespread, With Firm Age/Size as the Strongest Predictors

- LLM-assisted writing has diffused rapidly across consumer, corporate, labor market, and international institutions.
- Firm age and size are the strongest predictors of adoption — younger and smaller organizations adopt faster.
- Potential for content homogenization as LLM-assisted writing increases across domains.
- Raises trust and authenticity concerns for consumer complaints, job postings, and official communications.

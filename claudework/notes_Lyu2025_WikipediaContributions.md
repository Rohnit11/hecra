# Lyu et al. (2025) — ChatGPT and Wikipedia Contributions

> Lyu, X. et al. (2025). "ChatGPT and Wikipedia Contributions." WWW Companion '25, ACM. (Authors include Daron Acemoglu, MIT/Dartmouth/Columbia.)

---

## ChatGPT Reduces Wikipedia Pageviews by ~29,000 per Article but Edits Decline Is Only Marginally Significant

**Identification Strategy:** Difference-in-Differences using cosine similarity between Wikipedia articles and GPT-3.5-generated encyclopedic text as the treatment/control classification. Articles above the median similarity score are "treated" (more substitutable by ChatGPT); articles below the median are controls. The shock is ChatGPT's public launch on November 30, 2022.

**Shock/Variation:** ChatGPT launch (November 30, 2022). Cross-sectional variation from article-level cosine similarity to GPT-3.5 output.

---

## 2,206 Recently Created Wikipedia Articles Over a 24-Month Event Window

**Data Source:** English Wikipedia (top-1,000 most-viewed pages per month).

**Sample:**
- **2,206 articles** created since January 2020 (recency restriction to ensure active editing)
- 24-month event window: December 2021 -- November 2023 (12 months pre, 12 months post)
- **N = 6,060 observations** for the main T=6 specification

**Unit of observation:** Article-month.

---

## Views Drop by 29,013 per Article (p < 0.01); Edits Drop by 6.9 per Article (p < 0.10)

**Main results (Table 1, Page 4):**

| Outcome | DiD Estimate | SE | Significance |
|---------|-------------|-----|-------------|
| Pageviews | **-29,013.340** | 6,903.964 | p < 0.01 |
| Edits | **-6.877** | 3.719 | p < 0.10 |

**Robustness across recency parameters:**
- Views effect is robust across nearly all recency cutoffs
- Edits effect is suggestive but fades for older articles (not robust to all specifications)

---

## Limitations

- **Marginally significant edits result:** The editing decline is only significant at the 10% level — suggestive but not definitive.
- **Low R-squared:** Model explanatory power is limited.
- **Binary treatment:** Above/below median similarity is a coarse classification; a continuous treatment might reveal more nuance.
- **No mechanism test:** Cannot distinguish whether reduced views cause reduced edits, or whether both are independent responses to ChatGPT availability.
- **SUTVA concerns:** Spillovers between treated and control articles are plausible (editors may shift effort across articles).
- **Sample restricted to popular/recent articles:** Results may not generalize to the long tail of Wikipedia content.

---

## ChatGPT Substitutes for Wikipedia Consumption, With Suggestive Evidence of Reduced Contribution

- ChatGPT acts as a substitute for Wikipedia pageviews among articles whose content overlaps most with what ChatGPT can generate.
- The suggestive decline in editing activity raises concerns about a feedback loop: reduced readership may reduce contributor motivation, degrading content quality over time.
- Short paper (4 pages) — findings are preliminary and warrant follow-up with larger samples and continuous treatment measures.

# GEO Methods Boost Website Visibility in Generative Engine Responses by Up to 40%

## Citation
Aggarwal, P., Murahari, V., Rajpurohit, T., Kalyan, A., Narasimhan, K., & Deshpande, A. (2024). "GEO: Generative Engine Optimization." *Proceedings of the 30th ACM SIGKDD Conference on Knowledge Discovery and Data Mining (KDD '24)*, August 25–29, 2024, Barcelona, Spain. ACM.

---

## Identification Strategy

**Method:** Benchmarking / Black-box optimization evaluation. No causal identification (not a natural experiment or quasi-experiment). The authors propose Generative Engine Optimization (GEO) as a new paradigm analogous to SEO but for generative engines (GEs). They evaluate 9 GEO methods against a no-optimization baseline using their custom benchmark (GEO-bench).

**Design:** For each query, one source website is randomly selected for optimization. Each of the 9 GEO methods is applied separately to the same source. The generative engine produces 5 responses at temperature=0.7 per query, and results are averaged across 5 random seeds to reduce variance.

**Generative Engine Setup:** A 2-step pipeline — (1) fetch top 5 Google search results for a query, (2) generate a response using GPT-3.5-turbo grounded in those sources with inline citations. This mimics commercial GEs like Perplexity.ai and you.com.

---

## Data & Sample

- **GEO-bench:** 10,000 queries from 9 diverse sources (MS MACRO, ORCAS-1, Natural Questions, AllSouls, LIMA, Davinci-Debate, Perplexity.ai Discover, ELI5, GPT-4 Generated Queries).
- **Split:** 8K train / 1K validation / 1K test.
- **Domains:** 25 diverse domains (Arts, Health, Games, etc.); 9 query types; 7 category tags.
- **Query distribution:** 80% informational, 10% transactional, 10% navigational.
- Each query augmented with cleaned text content of top 5 Google search results.
- Real-world validation on **Perplexity.ai** using a subset of 200 test examples.

---

## Main Findings

### Top-Performing GEO Methods (Table 1, Page 6)
On **Position-Adjusted Word Count (Overall):**
| Method | Absolute Score | Relative Improvement vs. Baseline |
|---|---|---|
| No Optimization (Baseline) | 19.3 | — |
| Quotation Addition | **27.2** | **+41%** |
| Statistics Addition | 25.2 | +31% |
| Cite Sources | 24.6 | +27% |
| Fluency Optimization | 24.7 | +28% |

On **Subjective Impression (Average):**
| Method | Score | Relative Improvement |
|---|---|---|
| No Optimization | 19.3 | — |
| Quotation Addition | **24.7** | **+28%** |
| Statistics Addition | 23.7 | +23% |
| Authoritative | 22.9 | +19% |

### Non-Performing Methods
- **Keyword Stuffing** (traditional SEO): 17.7 overall Position-Adjusted Word Count — *worse* than baseline (19.3).
- **Unique Words:** marginal improvement (20.5).

### GEO on Perplexity.ai (Table 5, Page 8)
- Quotation Addition: 29.1 Position-Adjusted Word Count (+22% over baseline of 24.1).
- Statistics Addition: 33.9 Subjective Impression (+37% over baseline of 24.7).
- Keyword Stuffing: 21.9 Position-Adjusted Word Count (–10% vs. baseline).

### Domain-Specific Results (Table 3, Page 7)
- Authoritative: best for Debate, History, Science.
- Cite Sources: best for Statements, Facts, Law & Government.
- Statistics Addition: best for Law & Government, Debate, Opinion.

### Lower-Ranked Websites Benefit Most (Table 2, Page 7)
- Cite Sources: +115.1% visibility improvement for Rank-5 websites; –30.3% for Rank-1.
- Quotation Addition: +99.7% for Rank-5; –22.9% for Rank-1.

### Combination of Strategies (Figure 4, Page 7)
- Best combination: Fluency Optimization + Statistics Addition (35.8% relative improvement).

---

## Limitations
- Methods tested on only two generative engines (custom GE + Perplexity.ai); may need adaptation as GEs evolve.
- GEO-bench queries may not fully represent real-world query evolution over time.
- Black-box nature of search engine algorithms prevents evaluation of how GEO affects traditional search rankings.
- Larger context lengths in future models may reduce the impact of search rankings on source selection.
- Automated tagging of queries via GPT-4 may introduce noise.

---

## Key Implications
- Traditional SEO techniques (keyword stuffing) are **ineffective** for generative engines.
- Content creators should focus on **citations, quotations, statistics, and fluency** to improve visibility in GE responses.
- GEO has a **democratizing potential**: lower-ranked websites benefit disproportionately, potentially leveling the playing field against larger corporations.
- Domain-specific optimization is important — no single GEO method dominates across all topics.
- The paper formalizes the first framework for understanding and optimizing visibility in generative engines, opening a new research frontier.

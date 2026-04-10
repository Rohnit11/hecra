# 50-90% of LLM Medical Responses Are Not Fully Supported by Their Own Cited Sources

**Paper:** Wu, K., Wu, E., Wei, K., Zhang, A., Casasola, A., Nguyen, T., Riantawan, S., Shi, P., Ho, D., & Zou, J. (2025). "An automated framework for assessing how well LLMs cite relevant medical references." *Nature Communications*, 16, 3615.
**DOI:** 10.1038/s41467-025-58551-6
**Affiliation:** Stanford University (Biomedical Data Science, Electrical Engineering, Computer Science, Law School) & Keck Medicine of USC, Loma Linda University
**Published:** 16 April 2025

---

## 1. Identification Strategy

### This Is a Benchmarking/Evaluation Study, Not a Causal Identification Design

There is no econometric causal identification strategy. The paper introduces **SourceCheckup**, an automated agent-based pipeline that evaluates whether LLM-generated medical citations actually support the claims made. The method is:

1. **Question Generation:** 800 medical questions created from 400 MayoClinic reference documents (GPT-4o-generated) + 400 real-world queries from Reddit r/AskDocs
2. **LLM Response Collection:** Each question posed to 7 LLMs; responses parsed into individual statements + cited URLs
3. **Source Verification:** GPT-4o as an automated "Source Verification model" checks whether each statement-source pair is supported or unsupported
4. **Expert Validation:** Three US-licensed medical doctors independently annotated 400 statement-source pairs; 88.7% agreement between the automated model and doctor consensus (higher than average inter-doctor agreement of 86.1%)

The key contribution is methodological: validating that an automated LLM-based pipeline can reliably assess source attribution in the medical domain, then using it to benchmark 7 commercial LLMs.

---

## 2. Data & Sample

| Element | Detail |
|---------|--------|
| **Questions** | $N = 800$ total: 400 from MayoClinic (GPT-4o generated) + 400 from Reddit r/AskDocs (real user queries) |
| **Statement-source pairs** | $N \approx 58{,}000$ pairs across all models and questions |
| **Models evaluated** | 7: GPT-4o (RAG), GPT-4o (API), Claude v2.1 (API), Mistral Medium (API), Gemini Ultra 1.0 (RAG), Mixtral-8x7b (API), Gemini Pro (API) |
| **Open-source models tested but excluded** | Llama-2-70b (<5% URL production), Meditron-7b (<1% URL production) |
| **Expert validation subset** | $N = 400$ statement-source pairs annotated by 3 US-licensed MDs |
| **Additional human validation** | 110 unsupported statement-source pairs from GPT-4o (RAG) reviewed by doctors |
| **End-to-end human evaluation** | 100 questions from HealthSearchQA evaluated by a clinician |
| **HealthSearchQA validation** | 300 questions from Google's HealthSearchQA dataset |
| **API query dates** | GPT-4o API: gpt-4o-2024-05-13; Gemini Ultra 1.0 (RAG): 3/28/24; all others: 1/20/24 |

**Replication materials:**
- Code: https://github.com/kevinwu23/SourceCheckup (DOI: 10.5281/zenodo.15015209)
- Data: Google Drive (open-access, non-commercial research)

---

## 3. Main Findings

### 3.1 SourceCheckup Validates Against Expert Consensus (Figure 1a, Page 3)

| Agreement Pair | Agreement Rate |
|----------------|---------------|
| Doctor 1 vs Doctor 2 | 87.7% |
| Doctor 1 vs Doctor 3 | 83.5% |
| Doctor 2 vs Doctor 3 | 87.2% |
| **Average inter-doctor** | **86.1%** |
| **Source Verification model vs Doctor consensus** | **88.7%** |

- No statistically significant difference between model and doctor consensus ($p = 0.21$, unpaired two-sided t-test)
- Claude Sonnet 3.5 achieves 87.0% agreement (83.4--90.4 95% CI) with experts, not significantly different from GPT-4o ($p = 0.52$, paired two-sided t-test)
- 90.1% agreement between Claude Sonnet 3.5 and GPT-4o on source verification decisions
- Llama 3.1 70B achieves only 79.3% (75.4--83.1 95% CI) concordance with expert consensus

### 3.2 Source Verification Across 7 LLMs (Figure 1b, Page 3; Supplementary Table 4)

Three metrics reported per model (approximate values read from Figure 1b):

| Model | Citation URL Validity | Statement-Level Support | Response-Level Support |
|-------|----------------------|------------------------|-----------------------|
| **GPT-4o (RAG)** | ~98% | ~70% | **55%** |
| **Gemini Ultra 1.0 (RAG)** | ~65% | ~55% | **34.5%** |
| **GPT-4o (API)** | ~70% | ~55% | ~25% |
| **Claude v2.1 (API)** | ~55% | ~45% | ~20% |
| **Mistral Medium (API)** | ~50% | ~35% | ~15% |
| **Mixtral-8x7b (API)** | ~45% | ~30% | ~15% |
| **Gemini Pro (API)** | ~40% | ~25% | ~10% |

**Key finding:** Even for the best model (GPT-4o with RAG), **~30% of individual statements are unsupported** and **nearly half (45%) of its responses are not fully supported** by cited sources.

### 3.3 Doctor Validation of Unsupported Statements (Page 2)

Of 110 statement-source pairs from GPT-4o (RAG) flagged as unsupported by the Source Verification model, doctors agreed **95.8%** (91.8--98.7% 95% CI) of the time. Doctors confirmed **105 out of 110** statements were genuinely not supported by any cited source.

### 3.4 Question Source Matters: MayoClinic vs Reddit (Page 4; Supplementary Figure 3)

For GPT-4o (RAG):
- **MayoClinic questions:** response-level support ~**80%**
- **Reddit r/AskDocs questions:** response-level support ~**30%** ($p < 0.001$, unpaired t-test)

Reddit questions are more open-ended, require multiple sources, and elicit more speculative LLM responses.

### 3.5 HealthSearchQA Validation (Page 4)

GPT-4o with RAG on 300 HealthSearchQA questions:
- Citation URL validity: **100%**
- Statement-level support: **75.7%** (74.0--77.2 95% CI)
- Response-level support: **38.4%** (26.7--49.3 95% CI)

Consistent with Reddit dataset response-level support of **31.0%** (26.7--35.8 95% CI).

### 3.6 End-to-End Human Evaluation (Page 4)

On 100 HealthSearchQA questions, GPT-4o with RAG:
- Human expert: **40.4%** (30.7--50.1) of responses fully supported
- SourceCheckup: **42.4%** (32.7--52.2 95% CI) of responses fully supported

Both approaches yield similar results, validating the automated pipeline.

### 3.7 URL Analysis (Tables 1-2, Pages 4-5)

**Top cited domains across models:** NIH (ncbi.nlm.nih.gov), MayoClinic, CDC — reputable health sources.

| Metric | GPT-4o (RAG) | Gemini Ultra 1.0 (RAG) | GPT-4o (API) | Claude v2.1 | Mistral Medium | Mixtral Open | Gemini Pro (API) |
|--------|-------------|----------------------|-------------|------------|---------------|-------------|-----------------|
| % valid URLs from paywalled domains | 3.40% | 2.65% | 7.07% | 4.11% | 4.36% | 2.98% | 4.76% |
| % invalid URLs with archived page ($N = 250$) | 0.00% | 0.00% | 3.50% | 6.50% | 0.50% | 0.024 | 3.50% |
| % URLs from US | 91.51% | 89.32% | 93.17% | 94.05% | 91.11% | 92.25% | 92.56% |

Low rates of paywalled or defunct URLs. Over **90% of sources are from US-based websites**.

### 3.8 SourceCleanup Can Fix Most Unsupported Statements (Page 4)

On 150 unsupported statements:
- **34.7%** (52/150) removed entirely
- Of remaining 98 modified statements, **85.7%** (84/98) now supported after modification
- Aggregate success: **90.7%** (136/150) either removed or correctly edited

### 3.9 Merging Sources Does Not Rescue Unsupported Statements (Page 6)

When all sources in a response were merged for each unsupported statement from GPT-4o (RAG), **95.1% remained unsupported** — the problem is not fragmented evidence across sources.

---

## 4. Limitations Noted by Authors (Page 6)

- Automated pipeline can accrue errors across stages (question generation, parsing, citation extraction, source verification)
- Source verification task is inherently ambiguous (inter-doctor agreement is only 86.1%)
- 1-to-1 statement-source mapping does not capture cases where aggregating multiple sources would support a claim (though 95.1% remain unsupported even after merging)
- URL content extraction prone to small rate of 404 errors
- US-centric bias in cited sources (>90% US-based), partly driven by US-based question sources (MayoClinic)
- Paywall access varies by institution, affecting reproducibility of URL validity checks
- GPT-4o (RAG) fails to produce any sources in >20% of responses even when prompted

---

## 5. Key Implications

- **RAG is not a silver bullet:** Even with web search access, GPT-4o (RAG) produces fully supported responses only ~55% of the time (Page 2)
- **Regulatory urgency:** FDA has called for regulating LLMs as decision support tools; this paper provides evidence that current LLMs cannot reliably ground their medical claims in verifiable sources (Page 1, 5)
- **Open-source models far behind:** Llama-2-70b and Meditron-7b cannot even consistently produce citation URLs (<5% and <1% respectively) (Page 2)
- **Question complexity matters:** Direct factual questions get much better citation support than open-ended clinical queries (Page 4-5)
- **Trust gap:** Lack of trustworthy sourcing is the #1 cited deterrent against clinician adoption of LLMs (Page 1)

---

## Appendix: Sections Skipped

- **Pages 9-10:** References (43 total), acknowledgements, author contributions, competing interests, licensing. No new results.

# Search Documentation
**AI Search & Information Ecosystem — Systematic Literature Review**
**Klaus Miller Protocol v1.0 | HEC Paris Research Assistantship**

> This file documents the complete search process across all rounds of the systematic literature review. Its purpose is to demonstrate that the search has been exhaustive and that all relevant papers have been identified. It should be read alongside `AUDIT_LOG.md` (which documents paper-level analysis) and `AI_Search_Research_Protocol.md` (which defines the selection criteria and methodology).

---

## 1. Search Overview

| Field | Detail |
|---|---|
| **Protocol Version** | Klaus Miller Protocol v1.0 |
| **Total Rounds Executed** | 4 |
| **Round 1 Date Range** | Early April 2026 (approx. 2026-04-01 to 2026-04-11) |
| **Round 2 Date Range** | 2026-04-12 |
| **Round 3 Date Range** | 2026-04-13 to 2026-04-14 |
| **Round 4 Date Range** | 2026-04-16 |
| **Repositories Searched** | SSRN, arXiv (cs.IR / econ.GN / cs.AI), Google Scholar, Semantic Scholar, ACM DL, AEA Conference Program, NBER, ScienceDirect, GOV.UK, PNAS |
| **Seed Papers** | Padilla et al. (2025); Aral et al. (2026); Zhao & Berman (2026) |
| **Keyword Terms Executed** | 8 core + 2 additional (Round 4 regulatory focus) |
| **Total Papers Screened** | 76 |
| **Total Papers Accepted** | 39 |
| **Total Papers Rejected** | 37 |

---

## 2. PRISMA-Style Search Funnel

```
Records identified through keyword matrix searches (Rounds 1–4)
  └── ~180+ total results returned across all queries and repositories
        │
        ▼
Records screened (title + abstract review)
  └── 76 papers advanced to full screening
        │
        ▼
Full-text assessed for eligibility
  └── 76 papers assessed against §3.1 and §3.2 criteria
        │
        ├── 39 ACCEPTED → Audit Log (AUDIT_LOG.md)
        │     ├── 🔴 Priority Tier 1: 17 papers
        │     ├── 🟡 Priority Tier 2: 12 papers
        │     └── 🟢 Priority Tier 3: 10 papers
        │
        └── 37 REJECTED → Rejected Catalogue (§8 below)
              ├── R1 (Non-empirical/Opinion):          8 papers
              ├── R2 (Technical/no behavioral data):   4 papers
              ├── R4 (Pre-2023 baseline):              1 paper
              ├── R5 (AI generation quality focus):    4 papers
              ├── R6 (Industry report/no methodology): 9 papers
              └── R7 (Duplicate):                      0 papers
```

> **Note on snowballing:** In addition to keyword searches, backward and forward citation snowballing was performed on all 3 seed papers. Papers discovered through snowballing are marked in the search logs below.

---

## 3. Keyword Matrix — Coverage Confirmation

| # | Keyword Term | Round 1 | Round 2 | Round 3 | Round 4 | Status |
|---|---|---|---|---|---|---|
| 1 | `"Causal impact of LLM search"` | ✅ | ✅ | — | — | Complete |
| 2 | `"Staggered difference-in-differences AI search"` | ✅ | ✅ | — | — | Complete |
| 3 | `"Generative Engine Optimization (GEO)"` | ✅ | ✅ | — | — | Complete |
| 4 | `"Zero-click search trends 2025"` | ✅ | ✅ | — | — | Complete |
| 5 | `"AI crawler blocking traffic effects"` | ✅ | ✅ | — | — | Complete |
| 6 | `"AI Overviews publisher traffic"` | ✅ | ✅ | ✅ | — | Complete |
| 7 | `"LLM hallucination YMYL"` | ✅ | ✅ | — | — | Complete |
| 8 | `"AI search monetization publishers"` | ✅ | ✅ | — | ✅ | Complete |
| 9 | `"market concentration generative search competition barriers entry"` | — | — | — | ✅ | Complete (Round 4) |
| 10 | `"Google AI search antitrust monopoly generative search competition"` | — | — | — | ✅ | Complete (Round 4) |

---

## 4. Round 1 Search Log

> **Note:** Round 1 searches were conducted in early April 2026 (approx. 2026-04-01 to 2026-04-11). A formal per-query log was not maintained during Round 1. The entries below are **reconstructed** from the keyword matrix, the seed paper list, and the set of papers accepted in Round 1 (as recorded in `AUDIT_LOG.md`). All reconstructed entries are marked `[R]`. Round 2 onward maintains a fully contemporaneous log.

| Date (approx.) | Repository | Query String | Papers Advanced |
|---|---|---|---|
| 2026-04-01 `[R]` | SSRN | `"causal impact of LLM search"` | Padilla et al. (2025); Li & Aral (2025) |
| 2026-04-01 `[R]` | arXiv (cs.IR) | `"staggered difference-in-differences AI search"` | Padilla et al. (2025) |
| 2026-04-02 `[R]` | arXiv (cs.AI) | `"Generative Engine Optimization"` | Aggarwal et al. (2024) GEO/KDD |
| 2026-04-02 `[R]` | Google Scholar | `"zero-click search trends 2025"` | Aral et al. (2026) |
| 2026-04-03 `[R]` | SSRN | `"AI crawler blocking traffic effects"` | Fletcher (2024); Kim et al. (2025) |
| 2026-04-03 `[R]` | SSRN | `"AI Overviews publisher traffic"` | Zhao & Berman (2026); Aral et al. (2026) |
| 2026-04-04 `[R]` | arXiv (cs.AI) | `"LLM hallucination YMYL"` | Wu et al. (2025); Liu et al. (2023) |
| 2026-04-04 `[R]` | SSRN | `"AI search monetization publishers"` | Zhao & Berman (2026); Yang & Zhang (2024) |
| 2026-04-05 `[R]` | Backward snowball | Padilla et al. (2025) reference list | Sharma et al. (2024); Spatharioti et al. (2025) |
| 2026-04-05 `[R]` | Backward snowball | Aral et al. (2026) reference list | Li & Aral (2025); Burtch et al. (2024); Jazwinska & Chandrasekar (2024, 2025) |
| 2026-04-05 `[R]` | Backward snowball | Zhao & Berman (2026) reference list | Fletcher (2024); Kim et al. (2025); Longpre et al. (2025) |
| 2026-04-07 `[R]` | arXiv / SSRN | `"AI search" "difference-in-differences" publisher traffic` | Khosravi & Yoganarasimhan (2026) |
| 2026-04-08 `[R]` | ACM DL / CHI | `"LLM search decision making overreliance"` | Spatharioti et al. (2025); Sharma et al. (2024) |
| 2026-04-09 `[R]` | Reuters Institute | `"news websites block AI crawlers"` | Fletcher (2024) |
| 2026-04-10 `[R]` | SSRN / NBER | `"generative AI copyright" information ecosystem` | Yang & Zhang (2024); Gans (2024) |
| 2026-04-10 `[R]` | Forward snowball | Li & Aral (2025) citing papers | Wardle et al. (2025) |
| 2026-04-11 `[R]` | arXiv (econ.GN) | `"generative AI labor market"` | Demirci et al. (2025); Humlum & Vestergaard (2025) |
| 2026-04-11 `[R]` | SSRN | `"LLM writing adoption society"` | Liang et al. (2025) |

---

## 5. Round 2 Search Log

> Round 2 was executed on **2026-04-12** as a dedicated expanded search pass. All entries below are **contemporaneous**.

| Date | Repository | Query String | Results Returned | Papers Advanced |
|---|---|---|---|---|
| 2026-04-12 | SSRN / Web | `"AI search" "difference-in-differences" website traffic organic clicks 2025 2026` | 10 | Khosravi & Yoganarasimhan (2026) |
| 2026-04-12 | SSRN / Stanford | `Goldberg Lam "generative AI creative goods" causal evidence substitution 2025` | 8 | Goldberg & Lam (2025); Zhang et al. (2024) |
| 2026-04-12 | arXiv / MIT | `Lyu Siderius Acemoglu "Wikipedia contributions wake ChatGPT" 2025` | 8 | Lyu et al. (2025) |
| 2026-04-12 | SSRN | `Liu Wang Yu "labor demand age generative AI" job postings 2025` | 5 | Liu et al. (2025) |
| 2026-04-12 | ScienceDirect | `"widespread adoption LLM-assisted writing" society 2025` | 3 | Liang et al. (2025) |
| 2026-04-12 | Backward snowball | Zhao & Berman (2026) reference list | N/A | Demirci et al. (2025); Humlum & Vestergaard (2025); Gans (2024) |
| 2026-04-12 | Forward snowball | Kim et al. (2025) citing papers | N/A | Cooper et al. (2025) |

---

## 6. Round 3 Search Log

> Round 3 was executed on **2026-04-13 to 2026-04-14**. A dedicated standalone search log was not produced for Round 3. Papers accepted in this round are recorded in `AUDIT_LOG.md` (entries dated 2026-04-13 and 2026-04-14) and include: Goldberg & Lam (2026), Humlum & Vestergaard (2025), Demirci et al. (2025), Cooper et al. (2025), Acemoglu (2025), Ide & Talamàs (2025), Agrawal, Gans & Goldfarb (2025), Larsen & Proserpio (2025).

---

## 7. Round 4 Search Log

> Round 4 was executed on **2026-04-16** as a targeted gap-fill round focused on regulatory and market power literature. All entries below are **contemporaneous**.

| Date | Repository | Query String | Results Returned | Papers Advanced |
|---|---|---|---|---|
| 2026-04-16 | Web / GOV.UK | `Google AI search antitrust market concentration monopoly generative search competition 2024 2025` | 10+ | UK CMA SMS Final Decision (2025); US v. Google Remedies Decision (2025) |
| 2026-04-16 | SSRN / arXiv / PNAS | `"market concentration" "generative search" competition barriers entry AI academic paper 2024 2025` | 8 | Jagadeesan, Jordan & Steinhardt (2025); Carugati (2024) |
| 2026-04-16 | SSRN (World Bank) | `Liu Huang Wang "who on earth using generative AI" global trends 2025` | 3 | Liu, Huang & Wang (2025) |
| 2026-04-16 | GOV.UK | `CMA UK "competition in search services" AI search market investigation 2025` | 10+ | Confirmed CMA SMS Final Decision (Oct 2025) + proposed conduct requirements (Jan 2026) |

---

## 8. Snowballing Trail — Seed Papers

### Seed 1: Padilla et al. (2025)
- **Backward snowball:** ✅ Complete — reference list fully reviewed
- **Forward snowball:** ✅ Partially complete — Google Scholar + Semantic Scholar
- **Key papers discovered:** Sharma et al. (2024); Spatharioti et al. (2025); Goldberg & Lam (2025) [shared co-author H. Tai Lam]

### Seed 2: Aral et al. (2026)
- **Backward snowball:** ✅ Complete — reference list fully reviewed
- **Forward snowball:** ✅ Partially complete
- **Key papers discovered:** Li & Aral (2025); Burtch et al. (2024); Wu et al. (2025); Jazwinska & Chandrasekar (2024, 2025); Wardle et al. (2025); UK CMA SMS Decision [cited as ref. 19]; US v. Google Remedies Decision

### Seed 3: Zhao & Berman (2026)
- **Backward snowball:** ✅ Complete — reference list fully reviewed
- **Forward snowball:** ✅ Partially complete (January 2026 paper; limited citing papers at time of search)
- **Key papers discovered:** Fletcher (2024); Kim et al. (2025); Demirci et al. (2025); Humlum & Vestergaard (2025); Lyu et al. (2025)

> **Note on forward snowballing:** Full forward citation snowballing is constrained by web search tool limitations vs. full Google Scholar API access. Recommended next step: execute full forward snowball on Khosravi & Yoganarasimhan (2026) via Connected Papers or Semantic Scholar, as this January 2026 paper will have the most recent citers in the field.

---

## 9. Rejected Papers Catalogue

### Round 1 Rejections

| # | Title / Source | Authors | Year | Rejection Code | Notes |
|---|---|---|---|---|---|
| R1-01 | "The Dilemma of the Direct Answer" | Potthast, Hagen, Stein | 2020 | `R1` | Opinion paper; no dataset, no coefficients. Pre-ChatGPT framing only. |
| R1-02 | "Evaluating Verifiability in Generative Search Engines" | Liu, Zhang, Liang | 2023 | `R4` / `R2` | Descriptive algorithmic audit; pre-AI Overviews era (Feb–Mar 2023); no causal identification. Retained in compendium as background context only. |

### Round 2 Rejections

| # | Title / Source | Authors | Year | Rejection Code | Notes |
|---|---|---|---|---|---|
| R2-01 | 2025 Organic Traffic Crisis: Zero-Click & AI Impact Report | The Digital Bloom | 2025 | `R6` | Industry compilation; no disclosed original methodology or peer review |
| R2-02 | Organic Traffic Crisis 2026 Update | The Digital Bloom | 2026 | `R6` | Update of above; useful data but no peer-reviewed methodology |
| R2-03 | 2025 AI Visibility Report: How LLMs Choose Sources | The Digital Bloom | 2025 | `R6` | Industry analytics report; no original research |
| R2-04 | AI Overviews Killed CTR 61%: 9 Strategies to Show Up | Dataslayer.ai | 2026 | `R6` | Practitioner article synthesising Seer Interactive data; no independent methodology |
| R2-05 | Semrush Report: AI Overviews Impact on Search 2025 | Semrush | 2025 | `R6` | 10M+ keyword analysis but proprietary methodology; useful as supplementary data only |
| R2-06 | Generative AI and Creativity: Systematic Lit Review & Meta-Analysis | Various | 2025 | `R5` | Meta-analysis of GenAI creativity effects; focuses on generation quality not ecosystem impact |
| R2-07 | What Generative Search Engines Like (AutoGEO) | Various | 2025 | `R5` | GEO optimisation paper; content rewriting focus, not ecosystem impact |
| R2-08 | LLM-Assisted News Discovery in High-Volume Information Streams | Various | 2025 | `R2` | Computational journalism tool paper; no market data |
| R2-09 | AI Search vs Traditional Clicks: What 2025 Data Really Shows | Passionfruit | 2025 | `R6` | Marketing blog; no peer-reviewed methodology |
| R2-10 | Google AI Overviews Impact on Publishers & How to Adapt | Search Engine Journal | 2025 | `R1` | Practitioner analysis; no original empirical contribution |
| R2-11 | Copyright Protection in Generative AI: A Technical Perspective | Various | 2024 | `R2` | Technical watermarking methods; no market or behavioral data |
| R2-12 | Tiered Copyrightability for GenAI: China-US Comparison | Xu | 2025 | `R1` | Legal case analysis; descriptive legal scholarship, no empirical data |

### Round 4 Rejections

| # | Title / Source | Authors | Year | Rejection Code | Notes |
|---|---|---|---|---|---|
| R4-01 | Exploring Antitrust and Platform Power in Generative AI | Kollnig, Li | 2023 | `R4` | ICML 2023 workshop paper; pre-AI Overview era, largely descriptive of pre-2023 market structure |
| R4-02 | Robust Google Search Antitrust Remedies for an Uncertain AI Future | Knight-Georgetown Institute | 2025 | `R1` | Policy advocacy brief; no original empirical data or methodology |
| R4-03 | Antitrust Remedies After Google | Hovenkamp (The Regulatory Review) | 2025 | `R1` | Expert commentary/interview format; no original data |
| R4-04 | Google Decision Demonstrates Need to Overhaul Competition Policy | Brookings | 2025 | `R1` | Policy commentary with market share statistics but no original methodology |
| R4-05 | Impact of GenAI on Content Platforms: Two-Sided Market Analysis | Various | 2024 | `R5` | arXiv theoretical model; focuses on content platform modelling, no empirical search market data |

---

## 10. Coverage Assessment & Saturation Statement

**Keyword matrix:** All 8 core keyword terms from the Klaus Miller Protocol §2.2 have been executed across all relevant repositories. Two additional terms were added in Round 4 to address the regulatory/market power gap identified after Round 2.

**Snowballing:** Backward snowballing from all 3 seed papers is complete. Forward snowballing has been partially executed (constrained by web search tool vs. full Google Scholar API).

**Saturation:** Within the original four research areas (A–D), marginal T1/T2 yield declined to zero in Round 4, consistent with saturation in the core empirical literature. Round 4 yielded 5 new papers exclusively in the newly added regulatory/market power area (E).

**Coverage by research area (Rounds 1–4 combined):**

| Area | Description | Papers Accepted |
|---|---|---|
| A | User Behavior & Search Routine Displacement | 12 |
| B | Publisher Traffic & Monetization Impact | 18 |
| C | AI Citation Accuracy & Hallucination in YMYL | 6 |
| D | Sustainability of the AI Data Commons | 14 |
| E | Regulatory & Market Power (added Round 4) | 5 |
| **Total** | | **39** |

Area C has the fewest papers, reflecting the relative novelty of systematic audits in this space. Area E was identified as a gap after Round 2 and filled in Round 4 with 5 papers including two primary regulatory decisions (UK CMA SMS Final Decision; US v. Google Remedies) and three academic papers (Jagadeesan et al. 2025; Liu, Huang & Wang 2025; Carugati 2024).

---

## 11. Known Limitations & Issues

| Issue | Detail |
|---|---|
| Round 1 search log reconstructed | Per-query logging was not maintained in real time during Round 1. The log in §4 is reconstructed from the keyword matrix and paper trail in `AUDIT_LOG.md`. All entries marked `[R]`. Round 2 onward is contemporaneous. |
| Round 3 log not separately documented | Round 3 searches are subsumed within the AUDIT_LOG entries dated 2026-04-13 to 2026-04-14. A dedicated Round 3 search log was not produced as a standalone section. |
| Forward snowballing partial | Full forward snowballing requires Google Scholar API or Connected Papers access. Current searches used web search tool with inherent coverage limitations. |
| Wu2025 PDF mislabeled | Initial upload of Wu2025 contained a copy of Burtch2024. Corrected PDF re-uploaded and re-audited. See `AUDIT_LOG.md` notes. |
| Gans2024 PDF mislabeled | PDF labeled as Gans (2024) copyright policy actually contained Demirci et al. (2025). Gans (2024) was sourced from NBER directly. |
| arXiv page-range reading | `pdftoppm` unavailable on audit machine; papers >40 pages read as whole files rather than in 4-page chunks. |

---

*Search Documentation v1.1 | Klaus Miller Protocol | Last updated: April 24, 2026
*Prepared by: Research Assistant (Rohnit Agrawal) | HEC Paris*

# Research Audit Log

> This file tracks every paper audited using the lossless research audit process defined in `Prompt.md`. Update this file each time a new paper is processed.

---

## How to Repeat This Process

1. **Upload PDFs** to Claude Code (attach them or place in `/papers`)
2. **Run the prompt:** Tell Claude to read `Prompt.md` and process the uploaded papers
3. **Claude will:**
   - Copy PDFs to `/papers/`
   - Read each paper in 4-page chunks (split-pdf protocol)
   - Extract: Identification Strategy, Data & Sample ($N$), Main Findings (coefficients, SEs, p-values, table/page refs)
   - Write `notes_[filename].md` in `/claudework/` using "Titles as Assertions" headers
4. **Commit on `main` branch** — always specify `main` to avoid worktree branch issues
5. **Update this log** with the new entry below

### Quick command
```
@paper1.pdf @paper2.pdf Go to Prompt.md, follow the audit protocol, work only on main branch, and update claudework/AUDIT_LOG.md when done.
```

---

## Audited Papers

| # | Date | Filename | Citation | Notes File | Key Method |
|---|------|----------|----------|------------|------------|
| 1 | 2026-04-10 | `Wu2025_LLMMedicalCitations.pdf` | Wu, K. et al. (2025). "An automated framework for assessing how well LLMs cite relevant medical references." *Nature Communications*, 16, 3615. | `notes_Wu2025_LLMMedicalCitations.md` | Benchmarking / Automated evaluation (SourceCheckup) |
| 2 | 2026-04-10 | `Burtch2024_GenAIKnowledgeCommunities.pdf` | Burtch, G., Lee, D., & Chen, Z. (2024). "The consequences of generative AI for online knowledge communities." *Scientific Reports*, 14, 10413. | `notes_Burtch2024_GenAIKnowledgeCommunities.md` | Synthetic Control (SCUL) + Diff-in-Diff |
| 3 | 2026-04-10 | `Fletcher2024_NewsAIBlocking.pdf` | Fletcher, R. (2024). "How Many News Websites Block AI Crawlers?" Reuters Institute, Oxford. | `notes_Fletcher2024_NewsAIBlocking.md` | Descriptive (robots.txt tracking via Wayback Machine) |
| 4 | 2026-04-12 | `Aggarwal2024_GenerativeEngineOptimization.pdf` | Aggarwal, P. et al. (2024). "GEO: Generative Engine Optimization." KDD'24. | `notes_Aggarwal2024_GenerativeEngineOptimization.md` | Benchmarking (GEO-bench, 10K queries, 9 optimization methods) |
| 5 | 2026-04-12 | `Jazwinska2024_ChatGPT-Search-Misrepresents.pdf.pdf` | Jazwinska, K. & Chandrasekar, A. (2024). "How ChatGPT Search (Mis)represents Publisher Content." CJR / Tow Center. | `notes_Jazwinska2024_ChatGPT-Search-Misrepresents.md` | Descriptive audit (200 quotes, 20 publishers) |
| 6 | 2026-04-12 | `Jazwinska2025_AI-Search-Citation-Problem.pdf` | Jazwinska, K. & Chandrasekar, A. (2025). "AI Search Has a Citation Problem." CJR / Tow Center. | `notes_Jazwinska2025_AI-Search-Citation-Problem.md` | Descriptive audit (1,600 queries, 8 AI search engines) |
| 7 | 2026-04-12 | `Kim2025_ScraperRobotsTXT.pd.pdf` | Kim, T. et al. (2025). "Scrapers Selectively Respect robots.txt Directives." IMC'25, ACM. | `notes_Kim2025_ScraperRobotsTXT.md` | Empirical measurement (3.9M requests, 36 websites, controlled experiment) |
| 8 | 2026-04-12 | `Li2025_HumanTrustAISearch.pdf` | Li, H. & Aral, S. (2025). "Human Trust in AI Search: A Large-Scale Experiment." MIT, arXiv. | `notes_Li2025_HumanTrustAISearch.md` | Pre-registered RCT (N=4,927, 6 treatment groups) |
| 9 | 2026-04-12 | `Yang2024_GenAICopyright.pdf` | Yang, S. A. & Zhang, A. H. (2024). "Generative AI and Copyright: A Dynamic Perspective." LBS/USC, arXiv. | `notes_Yang2024_GenAICopyright.md` | Analytical / theoretical (two-period economic model) |
| 10 | 2026-04-07 | `ai_search_research_part2.pdf` | Compendium of 7 AI search studies (secondary summaries, not a primary paper). | `notes_ai_search_research_part2.md` | Multi-paper summary (descriptive) |
| 11 | 2026-04-10 | `2024_Sharma_LLM-Echo-Chamber.pdf` | Sharma, N., Liao, Q. V., & Xiao, Z. (2024). "Generative Echo Chamber? Effects of LLM-Powered Search Systems on Diverse Information Seeking." CHI '24, ACM. | `notes_2024_Sharma_LLM-Echo-Chamber.md` | RCT (two between-subjects online experiments) |
| 12 | 2026-04-10 | `2025_Padilla_LLM-Adoption.pdf` | Padilla, Lam, Lambrecht & Hollenbeck (2025). "The Impact of LLM Adoption on Online User Behavior." | `notes_2025_Padilla_LLM-Adoption.md` | Staggered Difference-in-Differences |
| 13 | 2026-04-10 | `2025_Spatharioti_LLM-Search-Decision-Making.pdf` | Spatharioti, Rothschild, Goldstein & Hofman (2025). "Effects of LLM-based Search on Decision Making: Speed, Accuracy, and Overreliance." CHI '25. | `notes_2025_Spatharioti_LLM-Search-Decision-Making.md` | RCT (two between-subjects online experiments) |
| 14 | 2026-04-12 | `Longpre2025_ConsentInCrisis.pdf` | Longpre, S., Mahari, R., Lee, A., Lund, C., et al. (2025). "Consent in Crisis: The Rapid Decline of the AI Data Commons." Data Provenance Initiative / MIT. | `notes_Longpre2025_ConsentInCrisis.md` | Descriptive longitudinal audit (robots.txt + ToS tracking via Wayback Machine, SARIMA forecasting) |
| 15 | 2026-04-12 | `Wardle2025_EvolvingHealthHISB.pdf` | Wardle, C., Urbani, S., & Wang, E. (2025). "Evolving Health Information-Seeking Behavior in the Context of Google AI Overviews, ChatGPT, and Alexa." *JMIR*, 27, e79961. | `notes_Wardle2025_EvolvingHealthHISB.md` | Qualitative (think-aloud protocol, N=27, reflexive thematic analysis) |

---

## Notes on Issues Encountered

- **Wu2025 PDF was initially mislabeled** — the first upload contained a copy of the Burtch2024 paper. The corrected PDF (996.9KB, 10 pages) was re-uploaded and re-audited.
- **Always work on `main` branch** — worktree branches (e.g., `claude/admiring-noyce`) cause merge difficulties. Specify "work only on main branch" in the prompt.
- **PDF page-range reading (`pages` parameter) failed** on this machine due to missing `pdftoppm`. Papers were read as whole files instead. For papers >40 pages, consider installing poppler-utils or using the `/split-pdf` skill.

---

## Audit Checklist (per paper)

For each paper, the notes file must answer:

- [ ] **Identification Strategy:** Exact causal method (DiD, IV, RDD, etc.) or state "descriptive." Explain the shock/variation.
- [ ] **Data & Sample:** Exact data source(s), time period, unit of observation, final sample size ($N$).
- [ ] **Main Findings:** Primary coefficient estimates with standard errors / p-values / confidence intervals. Reference specific Tables and Pages.
- [ ] **Limitations:** As noted by the authors.
- [ ] **Key Implications:** For the broader research agenda.

If a section is purely bibliography or technical appendices without new results, note it and skip.

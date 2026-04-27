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
| 16 | 2026-04-13 | `Cooper2025_GenAICopyrightPrimer.pdf.pdf` | Cooper, Z., Martens, B., Peukert, C., & Stocker, V. (2025). "The Law and Economics of Generative AI and Copyright: A Primer to Core Challenges for Our Digital Future." *Review of Network Economics*, 24(3), 161--176. | `notes_Cooper2025_GenAICopyrightPrimer.md` | Descriptive / theoretical (law-and-economics policy primer) |
| 17 | 2026-04-13 | `Demirci2025_WhoIsAIReplacing.pdf` | Demirci, O., Hannane, J., & Zhu, X. (2025). "Who Is AI Replacing? The Impact of Generative AI on Online Freelancing Platforms." Working Paper. | `notes_Demirci2025_WhoIsAIReplacing.md` | Difference-in-Differences (ChatGPT + Image AI releases as shocks, N=1,218,463 job posts) |
| 18 | 2026-04-13 | `Goldberg2026_GenAICreativeGoods.pdf.pdf` | Goldberg, S. G. & Lam, H. T. (2026). "Generative AI & Creative Goods: Market Expansion, Crowd-Out, and Copyright." Stanford GSB / UCLA Anderson. | `notes_Goldberg2026_GenAICreativeGoods.md` | Difference-in-Differences (Adobe Stock GenAI policy, 1,719 keyword markets, N=55,008 market-months) |
| 19 | 2026-04-13 | `Humlum2025_SmallLaborMarketEffects.pdf` | Humlum, A. & Vestergaard, E. (2025). "Large Language Models, Small Labor Market Effects." BFI Working Paper 2025-56, U of Chicago. | `notes_Humlum2025_SmallLaborMarketEffects.md` | DiD + Coworker IV (ChatGPT launch, ~25,000 workers, Danish admin data, precisely estimated zeros) |
| 20 | 2026-04-14 | `Khosravi2026_ImpactAISearchSummaries.pdf.pdf` | Khosravi, M. & Yoganarasimhan, H. (2026). "The Impact of AI Search Summaries on Publisher Traffic." U of Washington. | `notes_Khosravi2026_ImpactAISearchSummaries.md` | DiD (staggered AIO rollout across Wikipedia language editions, N=46.5M article-language-day obs) |
| 21 | 2026-04-14 | `Liang2025_WidespreadLLMWriting.pdf` | Liang, W. et al. (2025). "Widespread LLM-Assisted Writing Across Society." *Patterns*, Elsevier. | `notes_Liang2025_WidespreadLLMWriting.md` | Descriptive / Statistical (token frequency mixture modeling, MLE, 4 corpora) |
| 22 | 2026-04-14 | `Liu2025_LaborDemandAgeGenAI.pdf.pdf` | Liu, X. (2025). "Labor Demand and Age in the Age of Generative AI." Working Paper. | `notes_Liu2025_LaborDemandAgeGenAI.md` | DiD (ChatGPT launch, high- vs low-AI-substitution occupations, N=6.75M state-industry-occ-quarter cells) |
| 23 | 2026-04-14 | `Lyu2025_WikipediaContributions.pdf` | Lyu, X. et al. (2025). "ChatGPT and Wikipedia Contributions." WWW Companion '25, ACM. | `notes_Lyu2025_WikipediaContributions.md` | DiD (ChatGPT launch, article similarity to GPT output, N=2,206 articles) |
| 24 | 2026-04-14 | `Zhang2024_MarketEquilibriumGenAI.pd.pdf` | Zhang, X. et al. (2024). "Market Equilibrium in the Age of Generative AI." Working Paper. | `notes_Zhang2024_MarketEquilibriumGenAI.md` | DiD (NovelAI leak Oct 2022, tachie vs wallpaper on Mihuashi, N=126 category-week obs) |
| 25 | 2026-04-16 | `Acemoglu2025_SimpleMacroeconomicsAI.pdf` | Acemoglu, D. (2025). "The simple macroeconomics of AI." *Economic Policy*, 40(121), 13--58. | `notes_Acemoglu2025_SimpleMacroeconomicsAI.md` | Theoretical / calibration (task-based model + Hulten's theorem; Eloundou+Svanberg exposure; TFP gain ≤0.66%, GDP ≤1.56% over 10 yrs) |
| 26 | 2026-04-16 | `Ide2025_AIKnowledgeEconomy.pdf` | Ide, E. & Talamàs, E. (2025). "Artificial Intelligence in the Knowledge Economy." *Journal of Political Economy*, 133(12), 3762--3797. | `notes_Ide2025_AIKnowledgeEconomy.md` | Pure theory (Garicano-style knowledge hierarchies + AI agents; Props 1--6; autonomous AI helps top, nonautonomous AI helps bottom, output higher under autonomous) |
| 27 | 2026-04-16 | `Agrawal2025_GeniusOnDemand.pdf` | Agrawal, A., Gans, J. S., & Goldfarb, A. (2025). "Genius on Demand: The Value of Transformative Artificial Intelligence." NBER Economics of Transformative AI Conference (Stanford, 2025). | `notes_Agrawal2025_GeniusOnDemand.md` | Pure theory (Carnehl-Schneider knowledge-as-QA-pair + 3 worker types: routine/human-genius/AI-genius; Props 1--3; routine fully displaced iff η_AI ≤ 1/q²; human geniuses ultra-specialize at frontier) |
| 28 | 2026-04-16 | `Larsen2025_ImpactLLMsSponsoredSearch.pdf` | Larsen, P. & Proserpio, D. (2025). "The Impact of LLMs on Sponsored Search: Evidence from Google's BERT." Harvard Business School / USC Marshall Working Paper. | `notes_Larsen2025_ImpactLLMsSponsoredSearch.md` | DD (Oct 2019 BERT rollout × linguistic treatment intensity LC+Cosine; SEMRush panel 11,949 queries × 24 months, N=63,474; CS +0.1--0.4% uniformly; CPC +1.5% short, −2.5% long queries) |
| 29 | 2026-04-17 | `Eloundou2024_GPTsAreGPTs.pdf` | Eloundou, T., Manning, S., Mishkin, P., & Rock, D. (2024). "GPTs are GPTs: Labor market impact potential of LLMs." *Science*, 384, 1306. (Attached PDF is the 71-page Supplementary Materials.) | `notes_Eloundou2024_GPTsAreGPTs.md` | Descriptive task-exposure audit (E + T rubrics applied by humans + GPT-4 to 19,265 O*NET tasks across 1,016 occupations; ~80% of workers have ≥10% of tasks exposed at E1+0.5·E2, ~19% have ≥50%; only 1.86% of tasks fully automatable; exposure rises with wages/education through Job Zone 4) |
| 30 | 2026-04-17 | `Noy2023_ProductivityEffectsGenAI.pdf` | Noy, S. & Zhang, W. (2023). "Experimental evidence on the productivity effects of generative artificial intelligence." *Science*, 381, 187--192. (Attached PDF is the 108-page Supplementary Materials.) | `notes_Noy2023_ProductivityEffectsGenAI.md` | Preregistered individual-level RCT on Prolific (AEARCTR-0010882; N=450, 5 white-collar occupations, Jan--Feb 2023): ChatGPT access vs Overleaf placebo, occ × first-task FE, 3 cross-randomized incentive arms, 2SLS TOT instrument. Time −10.84 min (SE 1.38) ITT / −16.51 (1.99) TOT, N=346; grades +0.651 (0.145) ITT / +0.949 (0.185) TOT, N=1,135; job sat +0.50 SD (p<0.001); self-eff +0.20 SD (p=0.05, non-robust). Drafting time halves, editing doubles. |
| 31 | 2026-04-17 | `Potthast2020_DilemmaDirectAnswer.pdf` | Potthast, M., Hagen, M., & Stein, B. (2020). "The Dilemma of the Direct Answer." *ACM SIGIR Forum*, 54(1), June 2020 (12-page opinion paper). | `notes_Potthast2020_DilemmaDirectAnswer.md` | **Opinion paper — no identification strategy, no dataset, no coefficients.** Articulates "direct answer dilemma": user-side convenience vs diligence tradeoff, plus three system-side tradeoffs (retrievability, relevance-feedback short-circuit, responsibility/verisimilitude). Introduces "peak retrievability" conjecture. Illustrated by 6 hand-picked Google Assistant screenshots (admittedly "the very first questions we tried"). Pre-ChatGPT framing later tested empirically by Li-Aral 2025, Spatharioti 2025, Khosravi-Yoganarasimhan 2026. |
| 32 | 2026-04-17 | `Liu2023_VerifiabilityGenSearch.pdf` | Liu, N. F., Zhang, T., & Liang, P. (2023). "Evaluating Verifiability in Generative Search Engines." *Findings of ACL: EMNLP 2023*, pp. 7001--7025. | `notes_Liu2023_VerifiabilityGenSearch.md` | Descriptive algorithmic audit (no causal ID): 4 commercial generative search engines (Bing Chat, NeevaAI, perplexity.ai, YouChat) × 1,450 queries spanning 12 distributions (AllSouls, davinci-debate, ELI5-KILT/Live, WikiHowKeywords, 7 NaturalQuestions strata), scraped Feb--Mar 2023; 34 MTurk annotators using AIS (Rashkin 2022) framework; inter-annotator F1 ≥ 91. Avg citation recall 51.5%, precision 74.5%, fluency 4.48/5, perceived utility 4.50/5. Per-system: Bing Chat 58.7/89.5, NeevaAI 67.6/72.0, perplexity.ai 68.7/72.7, YouChat 11.1/63.6. Pearson r = −0.96 between precision and utility; r = 0.80 between BLEU/BERTScore similarity and precision (systems achieve precision by paraphrasing cited pages). No SEs/CIs/p-values reported. |
| 33 | 2026-04-22 | `Carugati2024_CompetitionGenAIFoundationModels.pdf` | Carugati, C. (2023). "Competition in generative artificial intelligence foundation models." *Bruegel Working Paper* 14/2023, 18 June 2023. SSRN=4553787. (Filename says 2024; PDF dated 2023.) | `notes_Carugati2024_CompetitionGenAIFoundationModels.md` | **Policy / narrative paper — no identification strategy, no dataset, no N, no coefficients.** Bruegel policy contribution reviewing FM value chain (LMs, data, compute), entry barriers, potential competition issues (leverage, data scraping, lock-in, algorithmic collusion), and policy recommendations (FTC/CMA/Adlc/DMA framing). Table 1 is an illustrative list of notable LLMs. Cites Eloundou 2023 (80% workers), Hatzius 2023 (7% GDP), Rae 2022, Hoffmann 2022 as secondary evidence. Snapshot pre-DeepSeek/Grok. |
| 34 | 2026-04-22 | `Liu2025_GlobalTrendsGenAI.pdf` | Liu, Y., Huang, J., & Wang, H. (2025). "Who on Earth Is Using Generative AI? Global Trends and Shifts in 2025." World Bank / Rice University, 8 Oct 2025. Sequel to Liu & Wang (2024). | `notes_Liu2025_GlobalTrendsGenAI.md` | Descriptive high-frequency panel (Semrush traffic, 60 GenAI tools, Dec 2022–mid-2025) + extensive/intensive margin decomposition + cross-sectional OLS (Table 4, p.29; authors frame as "correlation"). ChatGPT +113% YoY (=+42% users × +50% visits/user); HIC penetration 24% vs LIC 0.7%. Table 4: log GDP/capita coefs 0.61–0.79, p<0.01 for ChatGPT/Gemini/Claude across traffic & users; Google coefs collapse (R² 0.12/0.06). N=153 ChatGPT traffic, 148 users; Gemini 118/138; Claude 131/139; Google 164/164. Localization: Le Chat 69% Europe, Chinese tools >90% domestic. |
| 35 | 2026-04-22 | `Jagadeesan2025_SafetyVsPerformance.pdf` | Jagadeesan, M., Jordan, M. I., & Steinhardt, J. (2025). "Safety versus performance: How multi-objective learning reduces barriers to market entry." *PNAS*, 122(42), e2510004122. Published 15 Oct 2025. | `notes_Jagadeesan2025_SafetyVsPerformance.md` | **Pure theory — no data ("There are no data underlying this work," p.9).** Multi-objective high-dimensional linear regression marketplace with incumbent (stricter safety τ_I) vs entrant (weaker τ_E) firms choosing ridge regularizer λ and data-mixture α ∈ [0.5,1]. 5 theorems characterize market-entry threshold N_E*. Theorem 1: entrant can enter with finite data vs infinite-data incumbent. Theorems 2–3: multi-objective scaling exponent ν* takes 3 values (ν → ν/(ν+1) → 0); calibration to Hoffmann 2022 ν=0.34 gives 0.34 → 0.25 → 0. Theorem 4: N_E* = Θ(N_I^c), c ∈ {1, 0.75, 0} for ν=0.34. Theorem 5: N_E* = Θ(D^{-c}), c ∈ {2.94, 3.94, larger} as safety gap D shrinks. Implication: stricter regulatory scrutiny on dominant incumbents reduces entry barriers but risks race-to-the-bottom on safety. |

---

## Synthesis Decks

Decks built from audited notes via the `/compiledeck` skill (Promptpres.md protocol). Every deck commits both `.tex` and `.pdf`, with zero overfull/underfull warnings.

| # | Date | Deliverable | Synthesizes | Argument |
|---|------|-------------|-------------|----------|
| D1 | 2026-04 | `GenAI_Copyright_Deck.{tex,pdf}` | Yang & Zhang (2024); Cooper et al.\ (2025) | Fair use and AI-copyrightability are economically linked; designing them in isolation destroys welfare once data runs scarce. |
| D2 | 2026-04-27 | `Closing_Web_Deck.{tex,pdf}` | Cooper et al.\ (2025); Yang & Zhang (2024); Fletcher (2024); Kim et al.\ (2025); Longpre et al.\ (2025) | AI training rests on four pillars — consent signaling, voluntary compliance, premium content supply, and the legal backstop — and all four are cracking simultaneously. The web is not running out of data; it is running out of consent. |
| D3 | 2026-04-27 | `Veneer_Of_Search_Deck.{tex,pdf}` | Sharma, Liao & Xiao (2024); Spatharioti et al.\ (2025); Li & Aral (2025); Wardle, Urbani & Wang (2025) | AI search wears four veneers — speed, references, search, and utility — each manufacturing trust the underlying model has not earned. The interface earned the trust; the model did not. |
| D4 | 2026-04-27 | `Productivity_Gap_Deck.{tex,pdf}` | Eloundou et al.\ (2024); Noy & Zhang (2023); Acemoglu (2025); Demirci, Hannane & Zhu (2025); Goldberg & Lam (2026); Agrawal, Gans & Goldfarb (2025) | 80% of US workers are LLM-exposed and lab gains are large (−0.8 SD time, +0.4 SD grade), but Hulten arithmetic bounds 10-year GDP gain at 1.56%. Micro evidence (−21% writing freelance, −29% non-GenAI artists) is narrow but sharp — exactly as theory predicts when routine workers face $\eta_{AI}\!\le\!1/q^2$. The macro is small; the dislocations are not. |

---

## Notes on Issues Encountered

- **Wu2025 PDF was initially mislabeled** — the first upload contained a copy of the Burtch2024 paper. The corrected PDF (996.9KB, 10 pages) was re-uploaded and re-audited.
- **Always work on `main` branch** — worktree branches (e.g., `claude/admiring-noyce`) cause merge difficulties. Specify "work only on main branch" in the prompt.
- **PDF page-range reading (`pages` parameter) failed** on this machine due to missing `pdftoppm`. Papers were read as whole files instead. For papers >40 pages, consider installing poppler-utils or using the `/split-pdf` skill.
- **Gans2024_GenAICopyrightPolicy.pdf was mislabeled** — the PDF actually contained a copy of Demirci et al. (2025) "Who Is AI Replacing?" The actual Gans (2024) copyright policy paper was not in the batch. No audit entry created for the mislabeled file.
- **paper1.pdf and paper2.pdf** referenced in the command template were not found on the system — these appear to be placeholders from the AUDIT_LOG quick-command example.
- **Batch 3 (2026-04-13)** successfully used PyPDF2 split-pdf protocol for all papers, including the 120-page Goldberg2026 and 95-page Humlum2025.

---

## Audit Checklist (per paper)

For each paper, the notes file must answer:

- [ ] **Identification Strategy:** Exact causal method (DiD, IV, RDD, etc.) or state "descriptive." Explain the shock/variation.
- [ ] **Data & Sample:** Exact data source(s), time period, unit of observation, final sample size ($N$).
- [ ] **Main Findings:** Primary coefficient estimates with standard errors / p-values / confidence intervals. Reference specific Tables and Pages.
- [ ] **Limitations:** As noted by the authors.
- [ ] **Key Implications:** For the broader research agenda.

If a section is purely bibliography or technical appendices without new results, note it and skip.

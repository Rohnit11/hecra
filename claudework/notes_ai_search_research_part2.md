# Audit: AI Search Research Compendium Part II

**Source document:** `ai_search_research_part2.pdf` (12 pages, 3 chunks)
**Document type:** Collection of summaries of 7 research papers/studies plus supplementary data tables. This is NOT a primary research paper -- it is a curated compendium prepared for research assistant work. The summaries are secondary descriptions; coefficient estimates, standard errors, and regression tables are generally not reproduced here.

---

## 1. Wu et al. (2025) -- 50-90% of LLM Medical Citations Are Not Fully Supported by Their Sources

**Full title:** "An Automated Framework for Assessing How Well LLMs Cite Relevant Medical References"
**Venue:** Nature Communications, 16, 3615 (2025) -- Peer-reviewed
**DOI:** https://doi.org/10.1038/s41467-025-58551-6

### Identification strategy is automated source-verification pipeline, not causal inference
This is a measurement/evaluation study, not a causal study. The authors built "SourceCheckup," an automated agent-based pipeline that checks whether LLM-cited sources actually support the medical claims made. There is no quasi-experimental shock or causal identification strategy (no DiD, IV, or RDD). The method is systematic accuracy auditing with physician validation.

### Data: 800 medical questions yielding 58,000 statement-source pairs across 7 LLMs
- 800 medical questions
- 58,000 statement-source pairs
- 7 LLMs evaluated
- Independent validation by licensed medical doctors
- Open data available via Google Drive (pp. 1-2)

### GPT-4o with Web Search still had ~30% unsupported statements and ~50% not-fully-supported responses
- 50-90% of LLM responses are "not fully supported" by their cited sources (p. 2)
- Best-performing model (GPT-4o with Web Search): ~30% of individual statements lacked support; nearly half of all responses not fully supported (p. 2)
- Some cited sources actually contradicted the model's claims (p. 2)
- GPT-4 achieves 88% agreement with physician panels in validating source relevance (p. 2)
- Standard errors, p-values, and regression coefficients: not reported in text extraction. This is a descriptive accuracy study; consult the Nature Communications paper directly for confidence intervals.

---

## 2. Tow Center/CJR (Nov 2024) -- ChatGPT Search Was Confidently Wrong in 73% of Source-Identification Tests

**Full title:** "How ChatGPT Search (Mis)represents Publisher Content"
**Venue:** Columbia Journalism Review, November 2024

### Identification strategy is systematic accuracy testing, not causal inference
No causal identification. Researchers selected direct block quotes from news articles and asked ChatGPT Search to identify the source. The benchmark was whether Google/Bing returned the correct source in the top 3 results for the same quote.

### Data: 200 quote-identification tests across 20 publishers
- 20 publishers (mix of OpenAI partners, litigants, unaffiliated outlets)
- 10 block quotes per publisher = 200 test queries
- Repeated queries for consistency testing (pp. 2-3)

### ChatGPT fabricated sources in 146 of 200 cases; licensing deals did not help
- 146/200 cases (73%) confidently wrong (p. 3)
- Hedging language used in only 15 of 134 wrong answers (Part II supplementary data, p. 6)
- Even OpenAI-partnered publishers received inaccurate citations (p. 3)
- When crawlers were blocked by robots.txt, ChatGPT sometimes cited plagiarized versions from content mills (p. 3)
- Different answers each time same query was repeated (p. 3)
- Standard errors / p-values: not applicable (descriptive audit, not statistical inference)

---

## 3. Tow Center/CJR (Mar 2025) -- AI Search Engines Collectively Cited Incorrect Sources Over 60% of the Time

**Full title:** "AI Search Has a Citation Problem"
**Venue:** Columbia Journalism Review, March 2025

### Identification strategy is the same systematic accuracy testing extended to 8 platforms
Same quote-identification methodology as the Nov 2024 study, scaled to 8 AI search tools: ChatGPT Search, Perplexity, Perplexity Pro, Gemini, DeepSeek Search, Grok-2 Search, Grok-3 Search, and Copilot.

### Data: 1,600 queries (200 per platform) across 8 AI search tools
- 1,600 queries total
- 200 queries per platform (pp. 3-4)

### Error rates ranged from 37% (Perplexity) to 94% (Grok-3); premium chatbots often performed worse
- Collective error rate: over 60% (p. 4)
- Perplexity: 37% errors (most accurate) (p. 4)
- ChatGPT Search: 67% errors (p. 4)
- Grok-3: 94% error rate (p. 4)
- Premium (paid) chatbots often more confidently incorrect than free versions (p. 4)
- 5 of 8 chatbots appeared to bypass publishers' Robot Exclusion Protocol preferences (p. 4)
- Gemini and Grok-3 fabricated more URLs than they produced correct ones (p. 4)
- San Francisco Chronicle (OpenAI partner) had only 1/10 correct identifications (Part II supplementary data, p. 7)
- Standard errors / p-values: not applicable (descriptive audit)

---

## 4. Fletcher (2024) -- 48% of Top News Websites Blocked OpenAI Crawlers by End of 2023

**Full title:** "How Many News Websites Block AI Crawlers?"
**Venue:** Reuters Institute Factsheet, February 2024

### Identification strategy is descriptive cross-country robots.txt analysis, not causal inference
No causal identification method. This is a systematic descriptive study using archived robots.txt files from the Internet Archive's Wayback Machine. Monthly snapshots throughout 2023 document staggered adoption of AI crawler blocking.

### Data: 150 news websites (15 per country) across 10 countries
- 15 most widely used news websites in each of 10 countries (Brazil, Denmark, Germany, India, Mexico, Poland, Spain, UK, USA, and one additional)
- N = 150 websites
- Monthly snapshots throughout 2023 (pp. 5-6)

### Blocking varied enormously: 79% of U.S. sites vs. 20% in Mexico/Poland blocked OpenAI
- 48% of top news websites blocked OpenAI crawlers by end of 2023 (p. 5)
- 24% blocked Google's AI crawler (p. 5)
- U.S.: 79% blocked OpenAI (p. 5)
- Mexico and Poland: only 20% blocked OpenAI (p. 5)
- Google AI blocking: 60% in Germany to 7% in Spain (p. 5)
- Legacy print publishers most likely to block (57%); digital-born outlets least likely (p. 5)
- 97% of sites that blocked Google AI also blocked OpenAI, but not vice versa (p. 5)
- Standard errors / p-values: not applicable (descriptive statistics)

---

## 5. Longpre et al. (2025) -- The AI Data Commons Is Shrinking Rapidly as Websites Restrict Access

**Full title:** "Consent in Crisis: The Rapid Decline of the AI Data Commons"
**Venue:** NeurIPS 2025

### Identification strategy is longitudinal descriptive analysis of robots.txt restrictions
No causal identification method described in this summary. The study documents the timeline of robots.txt adoption for AI-specific crawlers and the growing asymmetry between content accessibility and AI demand.

### Data: Large-scale longitudinal analysis of robots.txt restrictions across the web
- Specific sample size: not reported in text extraction. The compendium describes it only as "large-scale longitudinal analysis" (p. 6).

### The freely available web content that AI relies on for training is eroding
- Dramatic increase in robots.txt restrictions following the rise of generative AI around 2022 (p. 6)
- Specific quantitative findings (coefficients, percentages, sample sizes): not reported in text extraction. Consult the NeurIPS 2025 paper directly.

---

## 6. Burtch, Lee & Chen (2024) -- ChatGPT's Launch Caused Significant Declines in Stack Overflow Questions and Answers

**Full title:** "The Consequences of Generative AI for Online Knowledge Communities"
**Venue:** Scientific Reports, 14(1), 10413 (2024) -- Peer-reviewed
**DOI:** https://doi.org/10.1038/s41598-024-61221-0

### Identification strategy is difference-in-differences around ChatGPT's launch
This is the only study in the compendium with an explicit causal identification method. The authors use a **difference-in-differences** design exploiting ChatGPT's launch as the treatment shock. Topics/question types where LLMs performed well serve as the treatment group (higher exposure to substitution), compared to topics where LLMs performed less well.

### Data: Stack Overflow posting data
- Specific N, time period, and unit of observation: not reported in text extraction. The compendium states only "Stack Overflow posting data, difference-in-differences around ChatGPT launch" (p. 7).

### Effects were heterogeneous: topics where LLMs performed well saw larger declines
- Significant reductions in both question volume and answer volume on Stack Overflow post-ChatGPT (p. 7)
- Larger declines for topics/question types where LLMs performed well (p. 7)
- Specific coefficient estimates, standard errors, and p-values: not reported in text extraction. Consult the Scientific Reports paper directly for Tables and regression output.

---

## 7. Wang et al. (2025) -- Users Integrated AI Tools into Search Routines Despite Trust Concerns

**Full title:** "Evolving Health Information-Seeking Behavior in the Context of Google AI Overviews, ChatGPT, and Alexa"
**Venue:** JMIR (Journal of Medical Internet Research) -- Peer-reviewed

### Identification strategy: qualitative think-aloud protocol, not causal inference
This is a qualitative study. No causal identification method. Researchers used a think-aloud protocol with reflexive thematic analysis.

### Data: 27 participants (ages 19-80) across 3 search platforms
- N = 27 participants
- Age range: 19-80
- 3 platforms tested: Google (including AI Overviews), ChatGPT, Alexa (pp. 7-8)

### Trust and utility did not align: users relied on ChatGPT despite sourcing concerns
- Participants integrated AI tools into broader search routines rather than using them in isolation (p. 8)
- ChatGPT valued for clarity, speed, and keyword generation even by skeptical users (p. 8)
- Older adults and those with lower digital literacy particularly vulnerable to accepting AI health information without verification (p. 8)
- AI Overviews appeared unexpectedly during data collection (coinciding with Google's Gemini rollout), reshaping the search experience mid-study (p. 8)
- Quantitative coefficients / p-values: not applicable (qualitative study)

---

## Part II Supplementary Data -- Cross-Study Statistics Are Consistent but Sourced from Primary Papers

Pages 8-11 compile statistics from the above studies plus Aral et al. (2026), Zhao & Berman (2026), and Kim et al. (2025). Key additional data points not covered above:

- AI Overview trigger rate for medical YMYL queries: 44.1%, vs. 20.5% baseline across all categories (Ahrefs analysis of 146M SERPs, 2025) (p. 10)
- Nearly 60% of Americans find AI-generated health info "somewhat or very reliable" (Annenberg, April 2025) (p. 10)
- 91.9% of cases: AI ordered unnecessary lab tests; 57.8% prescribed potentially inappropriate medications (Yale study on AI in chronic disease care) (p. 10)
- 22% of AI-generated medical Q&A responses contained severe errors (Stanford research) (p. 10)
- Top 30 U.S. newspaper publishers: ~80% blocked an OpenAI-related crawler at some point during 2023 (Zhao & Berman 2026) (p. 8)
- Blocking associated with ~10% decline in total traffic within 12 weeks post-blocking for large publishers (Zhao & Berman 2026) (p. 9)

## Part II Section D -- Data Sources and Repositories (Reference Only)

Pages 11-12 list open datasets and repositories. No new empirical results. Noted and skipped per audit constraints.

---

## Overall Assessment

This compendium is a secondary source that summarizes 7 studies. Only one (Burtch, Lee & Chen 2024) uses a formal causal identification strategy (DiD). The remaining six are descriptive accuracy audits, cross-country snapshots, qualitative studies, or longitudinal descriptive analyses. The compendium reliably reports top-line statistics from each study but does not reproduce regression tables, standard errors, or p-values. For any study where coefficient-level detail is needed, the primary papers must be consulted directly.

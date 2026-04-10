# Audit: Sharma, Liao & Xiao (2024) "Generative Echo Chamber? Effects of LLM-Powered Search Systems on Diverse Information Seeking"

**Citation:** Sharma, N., Liao, Q. V., & Xiao, Z. (2024). CHI '24, May 11-16, Honolulu, HI, USA. ACM. https://doi.org/10.1145/3613904.3642459

---

## Two Online Between-Subject Experiments, Not Observational Causal Identification

This paper uses a **randomized controlled experiment (RCT)** design across two studies. There is no quasi-experimental identification strategy (no DiD, IV, or RDD).

### Study 1: Three-Arm Between-Subjects RCT Comparing Search Modalities

- **Design:** Online between-subjects experiment. Participants were randomly assigned to one of three conditions:
  1. **WebSearch** -- conventional web search interface (keyword query, list of article links)
  2. **ConvSearch** -- LLM-powered conversational search (RAG-based, no source references)
  3. **ConvSearchRef** -- LLM-powered conversational search with inline source references
- **Randomization:** Random assignment to condition and to one of three controversial topics (Universal Health Care, Student Loan Debt, Sanctuary Cities). (pp. 3-4, Fig. 1)
- **Task:** Participants performed an information-seeking task (minimum 3 queries) then wrote a 50-100 word essay on the assigned topic. Pre- and post-task surveys measured attitudes, familiarity, and perceptions of consonant/dissonant articles. (pp. 3-4)
- **Key control:** All three systems searched from the same "closed-world" curated database of 47 documents (18 Supporting, 20 Opposing, 9 Neutral) to ensure neutral content exposure. Backbone model was GPT-4-32k (gpt-4-32k-0613). (pp. 5-6)
- **Analysis:** ANCOVA with search method as IV, each hypothesis measure as DV, controlling for age, gender, education, income, prior attitude toward conversational AI, usage frequency, assigned topic, and prior attitude on topic. Post-hoc pairwise comparisons via Tukey method. (p. 8)

### Study 2: 2x3 Fully Factorial Between-Subjects RCT on Opinionated LLMs

- **Design:** 2 (interface: ConvSearch vs. ConvSearchRef) x 3 (opinion bias: Consonant, Neutral, Dissonant) fully factorial between-subjects experiment. Since Study 1 found no significant difference between ConvSearch and ConvSearchRef, analysis aggregates across interface and focuses on the three bias conditions. (pp. 9-10)
- **Manipulation:** Opinion bias was created by (a) restricting the retrieval database to only documents aligned with the assigned bias + neutral documents, and (b) handcrafted prompts to generate biased responses. Bias assignment was personalized: if a participant held an opposing pre-existing attitude and was assigned to the Consonant condition, the system adopted an opposing bias. (pp. 9-10, Fig. 5)
- **Analysis:** ANCOVA with search system bias as IV, same controls as Study 1 plus search interface as additional control. (p. 10)

---

## Prolific Samples: N=115 (Study 1) and N=223 (Study 2), US English Speakers

### Study 1

- **Platform:** Prolific. Inclusion: fluent English speakers from the United States. Compensation: $15/hour. (p. 8)
- **Sample:** 124 started; **N = 115 completed and passed attention check** (WebSearch: N=40; ConvSearch: N=38; ConvSearchRef: N=37). (p. 8)
- **Demographics:** 48 women, 61 men, 5 non-binary/third gender. Median education: Bachelor's degree. Median household income: $50,000-$100,000. Median age: 25-34. (p. 8)

### Study 2

- **Platform:** Prolific. Same inclusion/compensation. Study 1 participants excluded. (p. 11)
- **Sample:** **N = 223** total (Consonant: 73; Neutral: 75; Dissonant: 75). Broken down by interface: ConvSearch=113, ConvSearchRef=110. (p. 11, Table 2)
  - Note: The 75 Neutral participants include the 75 from the ConvSearch and ConvSearchRef conditions of Study 1 (N=38+37=75), plus 148 newly recruited participants for the Consonant and Dissonant conditions. The text states "223 participants" total in Study 2. (pp. 10-11)
- **Demographics:** 112 women, 104 men, 7 non-binary/third gender. Median education: Bachelor's. Median income: $50,000-$100,000. Median age: 25-34. (p. 11)

### Data Coding

- 391 queries coded (Study 1) and an additional 265 queries (Study 2). Inter-rater reliability: Cohen's Kappa = 0.91 on 20% sample for queries. (pp. 6, 10)
- 794 sentences coded (Study 1) and an additional 1,000 sentences (Study 2). Cohen's Kappa = 0.95 on 20% sample for essay sentences. (p. 7)

---

## Conversational Search Increases Confirmatory Querying; Consonant LLMs Amplify Echo Chambers Across All Polarization Measures

### Study 1 Results (Table 1, pp. 8-9)

**H1 -- Conversational search induced more confirmatory querying (SUPPORTED):**
- Confirmatory Query: WebSearch M=1.46%, ConvSearch M=15.00%, ConvSearchRef M=16.15%
- ANCOVA: F(2,100) = 4.71, p = 0.01*
- Post-hoc: ConvSearch > WebSearch (p=0.03*, Cohen's D=0.76); ConvSearchRef > WebSearch (p=0.02*, Cohen's D=0.60)

**H2 -- Confirmatory attitude change (NOT SUPPORTED):**
- WebSearch M=0.03, ConvSearch M=0.08, ConvSearchRef M=-0.08
- ANCOVA: F(2,100) = 0.53, p = 0.60

**H3 -- Confirmatory arguments in essays (NOT SUPPORTED):**
- WebSearch M=35.39%, ConvSearch M=34.77%, ConvSearchRef M=34.83%
- ANCOVA: F(2,100) = 0.002, p = 0.998

**H4 -- Confirmatory agreement on post-task articles (SUPPORTED):**
- WebSearch M=0.80, ConvSearch M=1.79, ConvSearchRef M=1.89
- ANCOVA: F(2,100) = 6.61, p = 0.002**
- Post-hoc: ConvSearch > WebSearch (p=0.01**, Cohen's D=0.63); ConvSearchRef > WebSearch (p=0.005**, Cohen's D=0.78)

**H5 -- Confirmatory trust (PARTIALLY SUPPORTED):**
- WebSearch M=0.35, ConvSearch M=0.79, ConvSearchRef M=0.89
- ANCOVA: F(2,100) = 3.76, p = 0.03*
- Post-hoc: ConvSearchRef > WebSearch (p=0.04*, Cohen's D=0.65)

**H6 -- Confirmatory extremeness (NOT SUPPORTED):**
- WebSearch M=-0.53, ConvSearch M=-1.11, ConvSearchRef M=-1.08
- ANCOVA: F(2,100) = 1.57, p = 0.21

### Study 2 Results (Table 3, pp. 13-14)

**H1.a -- Consonant LLM increased confirmatory querying (SUPPORTED):**
- Consonant M=42.92%, Neutral M=15.57%, Dissonant M=12.33%
- ANCOVA: F(2,210) = 31.24, p < 0.001***
- Post-hoc: Consonant > Neutral (p<0.001***, Cohen's D=1.01); Consonant > Dissonant (p<0.001***, Cohen's D=1.19)
- H1.b (Dissonant reduces querying bias) NOT SUPPORTED.

**H2.a -- Consonant LLM increased confirmatory attitude change (PARTIALLY SUPPORTED):**
- Consonant M=0.27, Neutral M=0.00, Dissonant M=0.08
- ANCOVA: F(2,210) = 3.36, p = 0.04*
- Post-hoc: Consonant > Neutral (p=0.053, marginal, Cohen's D=0.39)
- H2.b NOT SUPPORTED.

**H3.a/H3.b -- Confirmatory arguments in essays (PARTIALLY SUPPORTED for both):**
- Consonant M=51.69%, Neutral M=34.79%, Dissonant M=15.58%
- ANCOVA: F(2,210) = 10.30, p < 0.001***
- Post-hoc: Consonant > Neutral (p=0.09, marginal, Cohen's D=0.70); Neutral > Dissonant (p=0.05, marginal, Cohen's D=0.36)

**H4.a -- Consonant LLM increased confirmatory agreement (SUPPORTED):**
- Consonant M=2.44, Neutral M=1.84, Dissonant M=1.51
- ANCOVA: F(2,210) = 7.43, p < 0.001***
- Post-hoc: Consonant > Dissonant (p<0.001***, Cohen's D=0.61); Consonant > Neutral (p=0.04*, Cohen's D=0.42)
- H4.b NOT SUPPORTED (Dissonant vs. Neutral p=0.38).

**H5.a -- Confirmatory trust (MARGINALLY SUPPORTED):**
- Consonant M=1.24, Neutral M=0.84, Dissonant M=0.93
- ANCOVA: F(2,210) = 2.91, p = 0.057 (marginal)
- Post-hoc: Consonant > Neutral (p=0.094, marginal, Cohen's D=0.41); Consonant > Dissonant (p=0.05, marginal, Cohen's D=0.27)
- H5.b NOT SUPPORTED.

**H6.a -- Confirmatory extremeness (PARTIALLY SUPPORTED):**
- Consonant M=-1.63, Neutral M=-1.09, Dissonant M=-1.03
- ANCOVA: F(2,210) = 3.30, p = 0.04*
- Post-hoc: Consonant < Dissonant (p=0.05, marginal, Cohen's D=-0.40); Consonant < Neutral (p=0.09, marginal, Cohen's D=-0.34)
- H6.b NOT SUPPORTED.

### Key Asymmetry Finding

Consonant (reinforcing) LLMs amplified selective exposure and opinion polarization across nearly all measures with medium-to-large effect sizes (Cohen's D up to 1.19). Dissonant (challenging) LLMs had little-to-no effect in reducing selective exposure -- the only partial exception was essay content (H3.b, p=0.05 marginal). This asymmetry is the paper's most striking result. (pp. 13-14)

### Additional Behavioral Measures (Discussion, pp. 14-15)

- In WebSearch, participants clicked 4.48 (SD=4.27) consonant article links vs. 3.28 (SD=3.11) dissonant links. (p. 14)
- In conversational search conditions, participants spent 116.6 seconds (SD=177.62) reading consonant outputs vs. 78.66 seconds (SD=111.90) on dissonant outputs. (p. 15)
- Participants clicked fewer than 1 reference per session on average (M=0.43, SD=1.13) in ConvSearchRef. (p. 15)

### Note on Standard Errors

Standard errors for the ANCOVA coefficient estimates are **not reported in the text extraction**. The paper reports means, standard deviations, F-statistics with degrees of freedom, p-values, and Cohen's D effect sizes, but not standard errors of the treatment effect estimates.

---

## Pages 17-18 Are Bibliography Only

Pages 17-18 contain only the reference list (references [10]-[72]). No new results or findings.

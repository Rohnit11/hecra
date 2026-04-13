# Audit Notes: Humlum & Vestergaard (2025) -- "Large Language Models, Small Labor Market Effects"

**Citation:** Humlum, Anders, and Emilie Vestergaard. 2025. "Large Language Models, Small Labor Market Effects." BFI Working Paper No. 2025-56, University of Chicago, April 2025.

**Auditor:** Claude (lossless research audit)
**Date of audit:** 2026-04-13
**Paper length:** 95 pages (30 pp main text + 12 pp figures/tables + 53 pp online appendix)

---

## 1. Identification Strategy

### Primary approach: Difference-in-Differences (DiD)
- Compares labor market outcomes (earnings, hours) of AI chatbot **adopters vs. non-adopters** before and after November 2022 (ChatGPT launch date).
- **Dynamic DiD** (Equation 2, p. 17): Monthly event-study coefficients beta_tau indexed to Nov 2022, with pre-determined controls (age, gender, experience, occupation FEs), month FEs for seasonality, and an adopter indicator.
- **Pooled DiD** (Equation 3, p. 18): Adds adopter-specific linear time trends to guard against spurious trends; estimates average post-treatment effect beta.

### Quasi-experimental variation: Employer encouragement policies
- Exploits that employer-wide policies to encourage AI chatbot use create variation in adoption among otherwise similar workers within the same occupation.
- **Reduced-form analysis** (Figure 9, p. 39): Replaces the adopter indicator A_i with an indicator for employer encouragement; first-stage effect on adoption = 0.363 (SE = 0.006) from Table B.1.

### Instrumental Variables: Coworker IV (Section 5.1, pp. 23-25)
- Instruments worker i's self-reported employer encouragement with the **leave-one-out average** encouragement rate among coworkers in the same occupation and workplace.
- First-stage coefficient approximately 1, F-statistic = 3,645 (Table E.1, p. 24).
- Empirical Bayes shrinkage procedure applied to reduce measurement error in leave-out means.
- IV estimates confirm OLS results: no labor market effects.

### Workplace-level analysis (Section 5.2, pp. 26-27)
- Shifts unit to workplace level, comparing high- vs. low-adoption workplaces on total employment and wage bills.
- Uses Empirical Bayes shrinkage for survey-based adoption rates to correct measurement error.

**Threats addressed:**
- Pre-trends examined visually and via dynamic DiD (Figure 7 shows flat pre-trends).
- Selection on observables controlled via Xi.
- Time-invariant unobservables differenced out.
- Unobserved confounding shocks addressed via employer policy quasi-experiment.
- Spillovers to non-users investigated via workplace-level analysis and direct survey question (99.6% of non-users report no earnings effect).

---

## 2. Data & Sample

### Data sources:
1. **Two large-scale adoption surveys** conducted via Statistics Denmark's digital mailbox infrastructure:
   - Round 1: November-December 2023
   - Round 2: November-December 2024 (primary focus of paper)
2. **Danish administrative registers:**
   - E-Income Register: monthly earnings, hours, occupation, industry for all job spells (2008 onward)
   - Employment Statistics of Employees (BFL) dataset (harmonized by Statistics Denmark)
   - Population Register (BEF): demographics
   - Personal Wealth Register (FORMPERS): wealth information
3. **Matched employer-employee data** through June 2024 (1.5 years post-ChatGPT launch)

### Sample construction (Table A.1, p. 46):
| Step | 2024 Survey | 2023 Main | 2023 Follow-Up |
|------|-------------|-----------|----------------|
| 1. Invitees | 115,000 | 100,000 | 15,000 |
| 2. Respondents | 30,411 (26.4%) | 29,067 (29.1%) | 4,094 (27.3%) |
| 3. In target occupation | 26,925 (23.4%) | 25,121 (25.1%) | 3,504 (23.4%) |
| 4. Complete responses | 25,241 (21.9%) | 18,109 (18.1%) | 2,561 (17.1%) |
| 5. Linked to registers | 24,796 (21.6%) | 17,907 (17.9%) | 2,559 (17.1%) |

### Unit of observation:
- Worker-month (for individual-level DiD)
- Workplace-month (for workplace-level analysis)

### 11 exposed occupations:
Accountants, customer support specialists, financial advisors, HR professionals, IT support specialists, journalists, legal professionals, marketing professionals, office clerks, software developers, teachers.

### Occupation selection criteria (p. 6):
(i) At least one O*NET task where AI chatbots can save time per Eloundou et al. (2024) "Direct Exposure (E1)" metric;
(ii) captured by well-defined ISCO codes;
(iii) sufficient workers for statistical analysis.

### Sampling design:
- Workplace-based: randomly draw workplaces, then sample all relevant workers within them.
- Maximizes statistical power for workplace-level analyses while maintaining representativeness.
- Three reminders per round (two email, one text).

### Representativeness checks (Appendix A.2.1):
- Balanced on observables (age, gender, experience, earnings, wealth).
- Randomized participation incentives show findings balanced on latent willingness to participate (following Dutz et al. 2025).
- Cross-checked survey responses against administrative register variables.

---

## 3. Main Findings

### A. Adoption and Employer Investments (Section 2, pp. 8-10)

**Employer initiatives are widespread (Figure 1, p. 31):**
- 43% of workers explicitly encouraged to use AI chatbots; 21% allowed; ~6% prohibited.
- 38% of firms deploy in-house AI chatbots (most customized versions).
- 30% of employees have participated in training courses on AI chatbot usage.

**Employer encouragement nearly doubles adoption (Figure 2, p. 32):**
- "Ever used" rises from 47% (baseline) to 83% (encouraged); all p < 0.01.
- Daily use rises from 8% to 21% when employers encourage.
- Gender gap in adoption shrinks from 11.9 pp to 5 pp with encouragement (Figure 3, p. 33).
- Training reduces gender gap further to 3.6 pp.

**OLS vs. IV estimates of encouragement effects (Table 2, p. 43):**
- OLS: Encouraged --> Ever Used = 0.363 (SE 0.007); IV = 0.725 (SE 0.022)
- OLS: Encouraged --> Daily = 0.137 (SE 0.005); IV = 0.228 (SE 0.017)
- IV estimates 1.5-2x larger than OLS, suggesting workplace-wide encouragement has stronger aggregate effect.

### B. Work Process Effects (Section 3, pp. 11-15)

**Time savings are modest (Table 1, p. 42):**
- Average time savings = **2.8% of total work hours** across all occupations and policies.
- Range: 6.8% (marketing, encouraged) to 0.6% (teachers, not encouraged).
- Average saving = 25 minutes per day of use (Figure 4b, p. 34).
- 64%-90% of users report time savings across occupations.

**Benefits are 10%-40% greater with employer encouragement (Figure 4, p. 34):**
- Time savings, quality improvements, creativity, task expansion, job satisfaction all significantly higher (p < 0.01).

**Task creation (Figure 5, p. 35; Figure 6, p. 36):**
- AI chatbots created new job tasks for **17% of users** (4.4 pp more same tasks, 10.9 pp new tasks, 1.7 pp both).
- **5% of non-users** also report new workloads from AI chatbots.
- New workloads 20-50% more pronounced in encouraging workplaces.
- Most common new task: AI integration into workplace (15%-40% of new tasks).

**Time allocation (Figure 4c, p. 34):**
- 80% reallocate saved time to other job tasks.
- <10% use for breaks or leisure.
- 25% spend more time on same tasks they saved time on.

### C. Labor Market Outcomes -- THE KEY RESULT (Section 4, pp. 16-22)

**Precisely estimated zeros on earnings and hours (Figure 7, p. 37):**
- Dynamic DiD: No significant impact on log earnings or log hours for adopters vs. non-adopters, 1.5 years post-launch.
- **CIs rule out average effects larger than 2%** in dynamic specification.
- No differential trend post-ChatGPT launch; flat pre-trends.
- No differential impact for adopters whose employers encourage use.
- No differential impact on extensive-margin employment (Figure D.2).

**Pooled DiD -- occupation-level effects (Figure 8a, p. 38):**
- **"All" pooled estimate rules out effects on earnings larger than 1%.**
- Occupation-specific estimates all close to zero, **generally ruling out effects larger than 6%.**
- No significant effects in ANY of the 11 occupations.

**No heterogeneous effects detected (Figure 8b, p. 38):**
- No differential effects by gender, age, experience, earnings level.
- No differential effects for workers reporting large time savings or daily use.
- No differential effects for workers reporting enhanced quality, creativity, or new workloads.
- No differential effects for early adopters (adopted within first year of ChatGPT).

**Reduced-form employer encouragement effects (Figure 9, p. 39):**
- Across all 11 occupations, workers encouraged to use AI chatbots have NOT fared differently in the labor market.
- First-stage effect on adoption: 0.363 (SE 0.006).

**Perceived earnings impact (Figure 10, p. 40):**
- Average perceived earnings impact: **0.04% (baseline) to 0.23% (encouraged).**
- ~97% of workers report NO change in earnings due to AI chatbots.
- Only 3-7% of time savings translate into earnings (pass-through rate).
- Pass-through ~3x higher when employers encourage use (7% vs. ~3%).
- These perceived effects collected November 2024, extending beyond June 2024 admin data window.

**Workplace-level effects (Figure 11, p. 41):**
- High-adoption workplaces have NOT fared differently in total employment or wage bills.
- Standardized effects larger than 1% can be ruled out.
- 99.6% of non-users report AI chatbots have not affected their earnings (Figure E.3).

### D. Coworker IV Results (Section 5.1, pp. 23-26)

**IV confirms OLS (Table 2, Figure E.2):**
- First-stage F-stat = 3,645; coefficient ~1.
- IV pass-through: 2%-6%, roughly 3x higher with encouragement (Table E.2).
- Conditional balance test: coworker characteristics do not predict own encouragement once coworker encouragement rate is controlled for.

---

## 4. Limitations (as noted by authors)

1. **Short time horizon**: Admin data through June 2024 (1.5 years post-ChatGPT). Authors note effects could emerge over longer horizons, though dynamic DiD shows no trend and Nov 2024 survey data confirms continued zero effects.

2. **Productivity J-curve**: Firms may be in the trough of a J-curve where current investments in AI integration are consuming resources before delivering productivity gains (Brynjolfsson, Rock and Syverson 2021). Evidence: the most common new task is "AI integration" itself (15%-40% of new tasks).

3. **Self-reported time savings**: May overstate or understate actual savings (Edelman, Ngwe and Peng 2023). Authors argue three factors lend credibility: estimates are below RCT benchmarks, perceived earnings effects match DiD estimates, and implied pass-through rates fall within standard literature range.

4. **Denmark-specific setting**: While Denmark's flexible labor market (low hiring/firing costs, decentralized wage bargaining) resembles the US, generalizability to other institutional contexts is uncertain. Authors argue Denmark is actually a favorable setting for detecting effects due to this flexibility.

5. **Occupational scope**: 11 exposed occupations selected by construction -- does not cover less-exposed occupations where effects could differ.

6. **Survey response rate**: ~22% response rate. Authors conduct representativeness checks and randomized incentive experiments to address potential nonresponse bias.

7. **Measurement error in workplace adoption rates**: Addressed via Empirical Bayes shrinkage; results robust to raw rates.

---

## 5. Key Implications for Broader Research Agenda

1. **Caution in extrapolating RCT findings**: Productivity gains of 15-50% from controlled experiments do not translate to comparable labor market effects in the broader economy. Two mechanisms explain the gap: (a) effect heterogeneity across occupations (RCTs concentrate on highest-gain occupations), and (b) lack of firm-based complementary investments in real-world settings.

2. **Weak productivity-to-wage pass-through**: Only 3-7% of productivity gains translate to earnings, at the low end of existing estimates (Card et al. 2018 estimate 5-15%). This is a structural channel limiting labor market transformation even if productivity gains grow.

3. **Firm-led investments matter for adoption equity**: Employer encouragement nearly doubles adoption, narrows gender gap from 11.9 pp to 5 pp, and training further reduces it to 3.6 pp. Policy implication: firm-level interventions (not just individual access) are key to equitable diffusion.

4. **Task creation is real but not yet economically significant**: 8.4% of workers have new tasks from AI chatbots, including non-users, consistent with Acemoglu and Restrepo (2019) on labor demand reinstatement. But these have not yet translated to measurable earnings/hours changes.

5. **"Solow Paradox" redux for Generative AI**: Authors explicitly invoke Solow (1987): "You can see the computer age everywhere but in the productivity statistics." Two years after the fastest technology adoption in history, labor market outcomes remain untouched at both individual and firm levels.

6. **Online freelance platforms are not representative**: Teutloff et al. (2025) find 20-50% demand declines on freelance platforms; this paper finds zero effects in standard employment. Freelance work has faster pass-through but does not reflect the broader labor market.

7. **Stock market anticipation vs. realized effects**: Eisfeldt et al. (2024) document stock price increases for AI-exposed firms, but this paper finds no corresponding employment or wage bill effects -- consistent with markets pricing in future (not yet realized) productivity gains.

---

## Key Figures and Tables Referenced

| Item | Page | Content |
|------|------|---------|
| Figure 1 | 31 | Prevalence of employer AI initiatives across 11 occupations |
| Figure 2 | 32 | Employer encouragement nearly doubles adoption (47% to 83%) |
| Figure 3 | 33 | Encouragement reduces gender gap from 11.9 to 5 pp |
| Figure 4 | 34 | Benefits of AI chatbots for adopters (time savings, quality, creativity) |
| Figure 5 | 35 | New workloads from AI chatbots (adopters and non-adopters) |
| Figure 6 | 36 | Composition of new AI tasks by occupation |
| Figure 7 | 37 | **MAIN RESULT**: Dynamic DiD -- precisely estimated zeros on earnings and hours |
| Figure 8 | 38 | Pooled DiD -- no effects by occupation or worker characteristics |
| Figure 9 | 39 | Reduced-form employer encouragement effects -- no labor market impact |
| Figure 10 | 40 | Perceived earnings vs. time savings; pass-through of 3-7% |
| Figure 11 | 41 | Workplace-level DiD -- no differential effects for high-adoption workplaces |
| Table 1 | 42 | Time savings decomposition by occupation and policy (average 2.8%) |
| Table 2 | 43 | OLS vs. IV estimates of encouragement effects on adoption and work |
| Table A.1 | 46 | Sample construction (~25,000 complete responses per round) |

---

## Remaining Pages (pp. 49-95): Appendix Content

Pages 44-95 contain the Online Appendix with:
- A: Data/sampling details, representativeness checks
- B: Additional adoption figures (employer initiatives at workplace level, ChatGPT product dominance, other employer initiatives, task-mix robustness)
- C: Benefits by occupation (Table C.1), task creation details, free-text classification
- D: Difference-in-means for earnings/hours, employment margin, perceived impact breakdown
- E: Coworker IV details (first stage, second stage, balance tests), workplace outcomes, Empirical Bayes shrinkage method
- F: Survey invitation letters (English and Danish)
- G: Full survey questionnaires (English and Danish)

No additional core results beyond those documented above.

# Audit: Padilla, Lam, Lambrecht & Hollenbeck (2025) "The Impact of LLM Adoption on Online User Behavior"

**Paper**: 69 pages. Main body ends at p.45 (References begin p.42). Web Appendices A-F span pp.46-69 (labeled App-1 through App-24).

---

## 1. Identification: Staggered Difference-in-Differences Using Variation in LLM Adoption Timing Across Users

### The design

The paper uses a **staggered difference-in-differences** (DiD) estimator following **Callaway and Sant'Anna (2021)** to estimate cohort- and time-specific average treatment effects on the treated (ATT_{g,t}). The "treatment" is individual-level adoption of LLMs (ChatGPT, Bing Chat/Copilot, Google Bard/Gemini), defined as the first of three consecutive weeks with at least one observed LLM URL visit (pp.10-11).

### The variation exploited

Users adopt LLMs at different points between December 5, 2022 and December 17, 2023. For each adoption cohort g, the **not-yet-treated** users serve as the control group. The paper explicitly avoids using never-treated units in the main specification (to avoid systematic differences between adopters and non-adopters) and restricts the sample to eventually-treated individuals only (p.17).

### Key identifying assumptions (pp.19-22)

1. **Conditional parallel trends**: Absent treatment, all cohorts would have experienced parallel outcome trends, conditional on control covariates (email, retail, news URL activity).
2. **No anticipation**: Users do not alter behavior before their adoption week.
3. The paper addresses calendar-time shocks (differenced out), level differences across cohorts (differenced out), heterogeneous treatment effects (non-parametric ATT_{g,t}), and declining activity over time (controlled via email/retail/news activity and Figure 1 showing stable ~5-5.7 active days/week).

### Activity controls as a validity check

URL calls to email, retail, and news websites are used as covariates to control for baseline internet activity. Table 3 (p.20) confirms these are unaffected by LLM adoption: ATT(weeks 20-47) = -777.9 (SE = 825.1), insignificant.

### This is NOT an RCT, IV, or RDD

There is no exogenous shock or instrument. Identification comes purely from staggered adoption timing under parallel trends. The paper acknowledges lower statistical power relative to TWFE due to non-parametric estimation across 2,448 individual ATT_{g,t} parameters (p.22-23).

---

## 2. Data: Comscore Desktop Clickstream Panel, N = 2,041 LLM Adopters Observed Weekly for 52 Weeks

### Source

**Comscore Web-Behavior Panel** for 2022-2023. Records URL-level desktop browsing for 1,179,088 panelists (p.9).

### Sample construction (pp.9-11)

1. Filter to users with at least 4 days of web traffic in every month from Nov 2022 to Oct 2023 --> 74,940 individuals.
2. Define adoption as 3 consecutive weeks with at least 1 LLM URL call --> **2,041 households** who adopted between Dec 5, 2022 and Dec 17, 2023.

### Final analysis sample

| Variable | Main | Education | Wikipedia | Stack Overflow | Reddit |
|---|---|---|---|---|---|
| Unique panelists | 2,041 | 1,886 | 1,634 | 287 | 1,488 |
| Weeks in data | 52 | 52 | 52 | 52 | 52 |
| Total observations | 106,132 | 98,072 | 84,968 | 14,924 | 77,376 |
| Pre-adoption obs | 64,543 | 59,706 | 51,120 | 8,246 | 46,245 |
| Post-adoption obs | 41,589 | 38,366 | 33,848 | 6,678 | 31,131 |

(Table 1, p.11)

### What is observed

- All URL calls and timestamps from desktop browsing
- Search queries on traditional search engines (content visible in URL; queries to LLMs are NOT observed)
- Ad impressions via URL calls to ad-service domains (adservice.google.com, imasdk.googleapis.com, ads.yieldmo.com)
- Comscore website categorizations (education, retail, email, news, social media)

### Key limitation

Desktop only -- no mobile browsing data. LLM query content is unobserved.

---

## 3. Main Findings

### LLM Adoption Reduces Traditional Online Search by 21.7% After 20 Weeks

**Table 4, p.25**: ATT(weeks 20-47) for all search = **-7.079** (SE = 3.517, p < 0.05), relative to a pre-adoption mean of 32.7 searches/week. This is a **21.7% decline**.

Without controls (Column 2): ATT = -9.735 (SE = 3.732, p < 0.01).

**Table 5, p.27** -- Breakdown by search type (all ATT for weeks 20-47):

| Search type | ATT | SE | Sig. | Pre-adoption mean | % change |
|---|---|---|---|---|---|
| All search | -7.079 | 3.517 | ** | 32.669 | -21.7% |
| Google only | -5.568 | 3.224 | * | 17.680 | -31.5% |
| Question searches | -1.256 | 0.469 | *** | 3.779 | -33.2% |
| Navigational only | -0.242 | 0.160 | n.s. | 0.800 | -- |
| Navig. + other | -0.407 | 0.170 | ** | 1.500 | -27.1% |
| Short (<=2 words) | -1.467 | 0.668 | ** | 5.030 | -29.2% |
| Long (>=6 words) | -2.466 | 0.795 | *** | 6.630 | -37.2% |

Key pattern: Informational searches decline sharply; pure navigational searches (e.g., typing "reddit") do NOT decline (p < 0.1 not met).

### Smaller Websites Lose 26% of Traffic; Large Websites Are Unaffected

**Table 6, p.30** (ATT weeks 20-47):

| Outcome | ATT | SE | Sig. | Pre-adoption mean |
|---|---|---|---|---|
| All websites | -17.752 | 561.734 | n.s. | 4,325.1 |
| Top 500 websites | 349.046 | 477.852 | n.s. | 2,928.0 |
| Non-top 500 websites | **-366.798** | 217.689 | * | 1,397.1 |
| Top 1,000 websites | 470.449 | 490.040 | n.s. | 3,219.9 |
| Non-top 1,000 websites | **-488.201** | 212.767 | ** | 1,105.2 |

**Table 7, p.31** -- By traffic quartile: Only the bottom 25% of websites (4,532,215 sites) shows a significant drop: ATT = **-482.310** (SE = 211.224, p < 0.05), a **41.8% decline** at the mean (1,154.3).

### Search-Referred Traffic to Small Websites Drops by 20.6%

**Table 8, p.32**: Referred traffic to bottom-25% websites: ATT = **-1.021** (SE = 0.566, p < 0.1), relative to pre-adoption mean of 4.947 = **20.6% drop**.

### Education Website Traffic Falls by 89.3% at the Mean

**Table 9, p.33** (N = 1,886 panelists, 98,072 obs):

| Outcome | ATT | SE | Sig. | Pre-adoption mean |
|---|---|---|---|---|
| All education | **-151.532** | 65.729 | ** | 169.688 |
| Variety of domains | **-0.520** | 0.166 | *** | 1.290 |
| Learning mgmt systems | **-23.124** | 14.049 | * | 62.199 |
| Online learning platforms | **-123.794** | 54.269 | ** | 55.785 |

The all-education decline of 151.5 relative to a mean of 169.7 represents an **89.3% drop** -- an enormous effect driven largely by online learning platforms.

### Stack Overflow Visits Decline by 68.8%; Wikipedia and Reddit Are Unaffected

**Table 10, p.35** (ATT weeks 20-47):

| Platform | ATT | SE | Sig. | Pre-adoption mean | N panelists |
|---|---|---|---|---|---|
| Wikipedia | -1.104 | 5.668 | n.s. | 13.878 | 1,634 |
| Stack Overflow | **-0.649** | 0.345 | * | 0.944 | 287 |
| Reddit | 12.736 | 12.172 | n.s. | 14.384 | 1,488 |

Stack Overflow's decline of 0.649 relative to a mean of 0.944 = **68.8% drop** (though only significant at p < 0.1 and based on only 287 panelists / 14,924 observations).

### Display Ad Exposures Fall by 72.9%; Search and Video Ads Are Unaffected

**Table 11, p.35** (ATT weeks 20-47):

| Ad type | ATT | SE | Sig. | Pre-adoption mean |
|---|---|---|---|---|
| All ads | **-154.213** | 73.299 | ** | 211.606 |
| Google display | **-122.217** | 73.479 | * | 161.092 |
| Google search | -1.914 | 1.978 | n.s. | 14.686 |
| Google video | -5.798 | 6.485 | n.s. | 3.952 |
| Yieldmo | -24.284 | 32.310 | n.s. | 31.876 |

### High-Retail-Activity Users Suffer the Largest Ad Exposure Decline

**Table 12, p.38**: Among users in the top tercile of retail activity, all ads ATT = **-561.285** (SE = 234.000, p < 0.05); Google display ATT = **-448.582** (SE = 243.936, p < 0.1). Low and mid terciles show no significant effects.

### Social Media Traffic Is Unaffected by LLM Adoption

**Table F.11, p.App-23**: No significant effects on any social media platform (Facebook, Instagram, X, Discord, LinkedIn, TikTok), individually or collectively.

---

## 4. Structure of the Paper and Appendices

| Section | Pages | Content |
|---|---|---|
| Main body | 1-41 | Introduction, literature review, data, identification, results, discussion, conclusion |
| References | 42-45 | Bibliography (no new results) |
| Web Appendix A | 46-47 (App-1 to App-2) | Sample criteria sensitivity |
| Web Appendix B | 48-49 (App-3 to App-4) | Additional descriptives; summary stats by adoption criterion; cohort heterogeneity in LLM usage |
| Web Appendix C | 50-54 (App-5 to App-9) | Comscore data processing details (foreground vs. background traffic, ad classification, video ad validation) |
| Web Appendix D | 55-61 (App-10 to App-16) | Robustness: anticipation, model specification (TWFE, Poisson), early adopter exclusion, placebo tests, retail classification |
| Web Appendix E | 62-63 (App-17 to App-18) | Cohort-level ATT heterogeneity (Tables E.4-E.7) |
| Web Appendix F | 64-69 (App-19 to App-24) | Education by monetization strategy; UGC platform event-study figures; social media analysis |

---

## 5. Key Methodological Notes

- **Inference**: Standard errors computed via influence-function linearization, clustered at the individual level (p.23).
- **Transformation**: Inverse hyperbolic sine (IHS) used for skewed control covariates (p.23).
- **Outcome measurement**: All outcomes are counts of URL calls (not time-on-site), aggregated to user-week level.
- **Effect timing**: All main effects emerge ~20 weeks post-adoption. The authors interpret this as a "learning period" during which users discover how to use LLMs effectively as substitutes (p.24-25). Effects at 35+ weeks post-adoption are noisy due to sparse data for early adopters.
- **Robustness**: Placebo randomization tests (Appendix D.4), alternative model specs (TWFE, Poisson -- Appendix D.2), exclusion of early adopters (Appendix D.3), and varying anticipation windows (Appendix D.1) all support main findings.

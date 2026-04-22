# Liu, Huang & Wang (2025) — Global GenAI Adoption Diverges by Income, Driven by GDP per Capita and Localization

**Citation:** Liu, Y., Huang, J., & Wang, H. (2025). "Who on Earth Is Using Generative AI? Global Trends and Shifts in 2025." World Bank / Rice University. October 8, 2025. Sequel to Liu & Wang (2024).

**Audit date:** 2026-04-22
**Pages audited:** 46 (12 chunks: p001-004 through p045-046)

---

## Identification Strategy Is Descriptive + Cross-Sectional OLS (Not Causal)

**No causal identification** — no DiD, IV, RDD, or experiment. The paper combines:

1. **Descriptive high-frequency panel** of website traffic across 60 consumer-facing GenAI tools, Dec 2022 – Jun/Jul 2025.
2. **Extensive/intensive margin decomposition** of ChatGPT traffic growth (Section 4.1–4.4).
3. **Cross-sectional OLS regression** (Section 4.2 / Table 4, pp. 28–29) relating country-level log per-capita traffic growth and user growth to three country characteristics: % population using internet, log GDP per capita (USD), fixed-broadband median download speed. **Authors explicitly frame results as "correlation," not causation** (Table 4 title and surrounding text, p. 29).

The authors state (p. 30): "These patterns are not yet definitive, they point to important gravity-model dynamics worth deeper investigation."

---

## Data and Sample

- **Primary source:** Semrush (digital-analytics provider) — monthly website traffic and unique-user estimates, collected daily across billions of URLs.
- **Coverage:** 60 most-visited consumer-facing GenAI tools as of June 2025, including chatbots (ChatGPT, Gemini, Claude, DeepSeek, Grok, Le Chat, Tencent Yuanbao, Doubao) and multi-modal tools (ElevenLabs, Suno, Sora, Runway, Midjourney).
- **Auxiliary sources:** ITU internet-user counts; World Bank income group classifications (HIC/UMC/LMC/LIC); GDP per capita 2024.
- **Period:** December 2022 – mid-2025 (various panels end April, May, or June 2025 depending on data availability).
- **Sample size for Table 4 regressions** (p. 29):
  - ChatGPT: **N = 153 countries** (traffic growth), **N = 148** (users growth)
  - Gemini: **N = 118** (traffic), **N = 138** (users)
  - Claude: **N = 131** (traffic), **N = 139** (users)
  - Google (benchmark): **N = 164**, **N = 164**
- **Known limitations (authors, p. 2):** misses backend API use, mobile-app usage, and enterprise deployments.

---

## Main Findings

### 1. Descriptive aggregate growth (Sections 3–4, pp. 3–20)

- **ChatGPT traffic +113% YoY** (Apr 2024 → Apr 2025), reaching 4.5 billion monthly visits.
- Decomposition: **+42% unique users × +50% visits/user** → 113% total.
- **ChatGPT share of top-60 GenAI traffic = 77%** in April 2025 (down from 89% in April 2023; chatbots collectively remain at 95% of GenAI traffic).
- **Average ChatGPT session duration roughly doubled** from 7 min to 15 min; similar acceleration for Gemini, DeepSeek.
- **Two of top-five April-2025 tools are new entrants** (DeepSeek, Grok); 9 of the top 60 are new to the sample.

### 2. Extensive vs. intensive margin by income group (Section 4, pp. 17–27)

| Income group | ChatGPT traffic Apr 2024 → Apr 2025 (M visits) | User growth | Visits/user growth | Session duration growth | Penetration (% of internet users using ChatGPT, Apr 2025) |
|---|---|---|---|---|---|
| HIC | 1,142 → 2,545 | +43% | +56% (5.2 → 8.0) | +133% | **24%** |
| UMC | 490 → 1,000 | +42% | +44% (5.5 → 7.8) | +94% | **5.8%** |
| LMC | 421.7 → 816.2 | +37% | +41% (5.8 → 8.2) | +90% | **4.7%** |
| LIC | 2.3 → ~10 | +n/a (small base) | +42% (>12 visits/user) | +162% | **0.7%** |

- HIC share of global traffic rose from **55% → 60%**; UMC 25% → 24%; LMC 20% → 19%; LIC 0.1% → 0.2%.
- **Key conclusion (p. 26):** "The widening divide across income groups is less about how intensively adopters use ChatGPT, and more about adoption itself: the extensive margin remains the primary driver of global disparities."
- Top-30 country contributions to the 113% growth: US 16%, India 6.8%, Brazil 5.1%, Germany 3.9%, Korea 3.5%, Japan 3.3%, France 3.1%, Viet Nam 3.2%, Indonesia 2.9% (Figure 10, p. 20).
- Highest penetration rates Apr 2025: **Singapore 80%**, Luxembourg/Lithuania/Netherlands/Denmark ~50% (Figure 15).

### 3. Cross-sectional OLS regression — Table 4 (p. 29)

**Dependent variable:** $\log[(\text{traffic}_{2025} - \text{traffic}_{2024})/\text{pop}]$, or equivalently for users (Google uses log ratio to avoid negative-growth sample loss).

| Predictor | ChatGPT Traffic (1) | ChatGPT Users (2) | Gemini Traffic (3) | Gemini Users (4) | Claude Traffic (5) | Claude Users (6) | Google Traffic (7) | Google Users (8) |
|---|---|---|---|---|---|---|---|---|
| % Population using internet | 0.031*** (0.008) | 0.028*** (0.008) | 0.017 (0.012) | 0.021** (0.009) | 0.019** (0.009) | 0.024*** (0.009) | **−0.012**\*\* (0.005) | **−0.010**\*\* (0.005) |
| log GDP per capita (USD) | **0.623**\*\*\* (0.129) | **0.611**\*\*\* (0.115) | **0.792**\*\*\* (0.211) | **0.783**\*\*\* (0.161) | **0.628**\*\*\* (0.138) | **0.635**\*\*\* (0.142) | 0.157\* (0.084) | 0.171\* (0.093) |
| Fixed-broadband median (Mbps) | 0.002 (0.004) | 0.004 (0.003) | −0.002 (0.005) | −0.000 (0.004) | 0.000 (0.003) | −0.000 (0.003) | −0.003** (0.001) | −0.003* (0.002) |
| Constant | −4.893 (0.822) | −7.299 (0.743) | −9.633 (1.220) | −10.460 (0.985) | −7.724 (0.862) | −9.962 (0.883) | −0.192 (0.425) | −0.562 (0.455) |
| N | 153 | 148 | 118 | 138 | 131 | 139 | 164 | 164 |
| R² | 0.67 | 0.67 | 0.55 | 0.65 | 0.61 | 0.63 | 0.12 | 0.06 |

Stars: \* p<0.1, \*\* p<0.05, \*\*\* p<0.01. Standard errors in parentheses.

**Key takeaways from Table 4 (p. 29):**
- log GDP per capita strongly and positively correlated with GenAI growth for ChatGPT, Gemini, Claude (all p<0.01, magnitudes 0.61–0.79).
- Internet penetration also positive & significant for ChatGPT and (mostly) Claude; marginal for Gemini.
- Fixed broadband is effectively **null** for GenAI tools once GDP & internet penetration are included.
- **Google is qualitatively different** — internet penetration coefficient flips *negative* and significant (−0.012\*\*, −0.010\*\*); R² collapses to 0.12 / 0.06, suggesting mature platforms have saturated the relationship.
- Authors explicitly frame this as "structural readiness continues to shape the pace and intensity of GenAI diffusion" (p. 29), **not causation**.

### 4. Localization / home-court advantage (Section 5, pp. 29–31)

- Le Chat (France): **69% of traffic from Europe**.
- Several Chinese tools (Doubao, Tencent Yuanbao) exceed **90% domestic usage** (Figure 17, p. 31).
- DeepSeek China share: 44% (Oct 2024) → 20% (Apr 2025); HICs now 44%, UMCs 40%, LMCs 16%.
- Interpretive framing (pp. 29–30) draws on Farrell–Gopnik–Shalizi–Evans (2025) "AI as cultural technology" literature, Bearson–Wright (2025), Krakowski et al. (2025), Choudhury (2022).

---

## Limitations (authors' own, pp. 2, 32)

- Web-traffic data misses backend/API, mobile apps, enterprise integrations (e.g., Copilot-inside-Office, ChatGPT embedded in third-party apps).
- Regression results are **correlational, not causal** (Section 4.2 / Table 4 caveats).
- ITU "internet user" definitions vary across countries.
- Panel is consumer-facing web tools only — cannot benchmark GenAI against on-device or API usage.
- Localization evidence is descriptive; "suggestive" per authors (p. 29).

## Key Implications

- **Structural digital divide is widening on the extensive margin,** not intensive — policy should focus on adoption/penetration, not just depth of engagement.
- Strong **GDP-per-capita gradient** suggests GenAI adoption tracks development with elasticity on the order of 0.6–0.8 (log-log).
- **Localization is a meaningful market-structure force** — non-US tools cluster in home regions. Relevant to competition-policy debates (cf. Carugati 2023 in this audit batch).
- Builds on Liu & Wang (2024); contrasts with survey-based adoption studies (e.g., Humlum 2025) by using real-time behavioral data.

## Structural Notes

- **Abstract & Intro (pp. 1–4):** Five-point summary of findings.
- **Section 2 (pp. 5–12):** Landscape of 60 tools, top-5 rankings, innovation patterns (multimodality, reasoning).
- **Section 3 (pp. 13–16):** ChatGPT dominance, chatbot segment dominance.
- **Section 4 (pp. 17–28):** **Main empirical content** — traffic decomposition, extensive vs intensive margin by income group, country rankings. **Table 3** (extensive/intensive decomposition) implicit in Section 4.1–4.2 narrative, formalized in country-ranking appendix tables.
- **Table 4 (p. 29):** Cross-sectional OLS regression (main quantitative result).
- **Section 5 (pp. 29–31):** Localization descriptive analysis, Figure 17.
- **Section 6 (p. 32):** Conclusion.
- **Pages 33–46:** References + Appendix tables (A1–A3: top-30 country rankings by traffic, penetration, and visits per user). Technical appendix — noted per protocol; country rankings contain data but no new causal estimates.

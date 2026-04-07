# Audit: Spatharioti et al. 2025 -- "Effects of LLM-based Search on Decision Making: Speed, Accuracy, and Overreliance"

**Citation:** Spatharioti, Rothschild, Goldstein, and Hofman. CHI '25, Yokohama, Japan. 15 pages.

---

## The Paper Uses Two Between-Subjects Randomized Online Experiments (RCTs), Not Quasi-Experimental Methods

There is no diff-in-diff, IV, or RDD. Both experiments are **randomized controlled trials** conducted online.

**Experiment 1:** Two-condition, between-subjects design. Participants were randomly assigned to complete consumer product research tasks (choosing between pairs of SUVs based on a cargo-space-to-length ratio) using either (a) a traditional search engine built on the Bing API, or (b) an LLM-based search tool built on GPT-3.5 (p. 4). The LLM tool was non-conversational (single-query-response, no dialogue memory) to keep the comparison tight against traditional search. Five tasks total: the first four used randomly generated popular SUV pairs ("easy" tasks where the LLM returns correct info); the fifth was deliberately selected so the LLM tends to err (confusing seats-up vs. seats-down cargo space for the 2020 Toyota 4Runner). The LLM ran at temperature=0 for determinism (p. 4).

**Experiment 2:** Three-condition, between-subjects design. All participants used the same LLM-based tool (GPT-3.0, needed for token probabilities). Conditions varied only the visual display of numeric measurements in responses (p. 8):
1. **Control (no highlighting):** Plain text, same as Experiment 1.
2. **High + low confidence:** Green highlights for high-confidence measurements, red for low-confidence (token generation probability <= 50%).
3. **Low confidence only:** Red highlights for low-confidence measurements only.

Three tasks: first two "easy," third deliberately "challenging" (same 4Runner error scenario). The first query of the third task was not pre-prompted with ground truth, so it would likely contain low-confidence errors (pp. 8-9).

---

## Experiment 1 Sample Is N=90 from MTurk; Experiment 2 Is N=120 from MTurk

**Experiment 1:** 90 U.S.-based participants recruited from Amazon Mechanical Turk. Qualifications: >= 2,500 HITs approved, >= 99% approval rate, plus Masters qualification. Paid $4. No demographic information collected (p. 4). Of these, 51 were assigned to the LLM-based condition and 39 to traditional search (implied from the reported breakdowns, e.g., "among the 51 participants in the LLM-based search condition" on p. 7; exact split for traditional search condition not reported in text but ~39 by subtraction).

**Experiment 2:** 120 U.S.-based participants from MTurk, from a vetted pool of high-effort workers. >= 2,500 HITs approved, >= 99% approval rate (no Masters requirement this time). Paid $5, no performance bonuses. No demographics collected (p. 9). Roughly 40 per condition (exact per-condition N not explicitly reported in text extraction).

---

## LLM-Based Search Cuts Task Time by Roughly 50% (1.6 vs. 3.4 Minutes) with Fewer but More Complex Queries

**Experiment 1 -- Efficiency (pp. 4-6, Figure 2):**

| Outcome | Traditional Search | LLM-Based Search | Estimate | SE | Test statistic | p-value |
|---|---|---|---|---|---|---|
| Log10(task duration) | 3.4 min (95% CI [2.8, 4.1]) | 1.6 min (95% CI [1.4, 1.9]) | -0.316 | 0.055 | t(78) = -5.70 | p < .001 |
| Number of queries | 2.5 (95% CI [2.1, 3.0]) | 1.9 (95% CI [1.7, 2.2]) | -0.26 | 0.12 | z = -2.244 | p = 0.02 |
| Query complexity (1-5 scale) | 1.8 (95% CI [1.6, 2.1]) | 3.4 (95% CI [3.1, 3.8]) | 0.65 | 0.09 | z = 7.38 | p < .001 |

All models are linear or generalized linear mixed models with random effects by participant, task number controls, and a fixed effect for condition (p. 5-6).

---

## Accuracy Is Comparable on Easy Tasks (~92-95%) but Drops to 47% for LLM Users on the Challenging Task vs. 93% for Traditional Search

**Experiment 1 -- Accuracy on Easy Tasks (pp. 6-7, Figure 3):**
- Traditional search: 92.3% correct (95% CI [83%, 97%])
- LLM-based search: 95.3% correct (95% CI [89%, 98%])
- No significant difference: z = 0.99, p = 0.33

**Experiment 1 -- Accuracy on Challenging Task (p. 7):**
- Traditional search: 93% correct (SE = 5%, 95% CI [76%, 98%])
- LLM-based search: 47% correct (SE = 7%, 95% CI [34%, 61%])
- Estimate = -2.72, SE = 0.79, z = -3.46, p < .001

Among 51 LLM-condition participants on the challenging task: 30 issued only one query; of these, 23 received incorrect LLM responses and chose wrong; 7 received correct responses and chose correctly. No participant attempted to re-query after encountering an incorrect response (p. 7).

---

## Confidence-Based Highlighting More Than Doubles Accuracy on the Challenging Task (from 26% to 53-58%)

**Experiment 2 -- Accuracy on Challenging Task (pp. 9-10, Figure 6):**
- Control (no highlighting): 26% correct
- High + low confidence highlighting: 58% correct (t(74.47) = -2.98, p < 0.01)
- Low confidence only highlighting: 53% correct (t(70.36) = -2.44, p = 0.02)

Accuracy on easy tasks was comparably high across all three conditions (Figure 6, p. 9).

The mechanism: participants in treatment conditions were more likely to issue follow-up queries when they saw low-confidence cues. On the challenging task, meaningful follow-up queries rose from 2/19 in control to 15/31 in treatment conditions (p. 10).

---

## Users Strongly Prefer LLM-Based Search (4.41 vs. 3.10) but Cannot Detect Its Errors

**Experiment 1 -- User Perceptions (p. 8, Figure 4):**
- Perceived reliability: No significant difference between conditions (t(62.03) = 0.11, p = 0.91). Both rated ~4-5 on a 5-point Likert scale, despite LLM users having been exposed to incorrect information.
- Overall search experience: LLM = 4.41, Traditional = 3.10 (t(58.00) = 8.38, p < .001).

**Experiment 2 -- User Perceptions (pp. 10-11, Figure 7):**
- Perceived reliability: No highlighting = 4.1, Low confidence only = 3.8, High + low confidence = 4.0. Neither treatment differs significantly from control (low conf vs. none: t(75.62) = 1.90, p = 0.06; high+low vs. none: t(77.70) = 0.81, p = 0.42).
- Search experience: No highlighting = 4.2, Low confidence only = 3.9, High + low confidence = 3.7. No significant differences (low conf vs. none: t(71.00) = 1.31, p = 0.19; high+low vs. none: t(75.75) = 1.92, p = 0.06).

---

## Experiment 2 Appendix: Treatment Groups Are Slightly Slower and Issue More Queries on the Challenging Task

**Experiment 2 -- Efficiency on Easy Tasks (pp. 14-15, Appendix C):**
- Task 1 average across conditions: 3.3 min (95% CI [2.9, 3.7]); Task 2: 1.8 min (95% CI [1.6, 2.0]).
- High + low confidence was slightly slower than control overall: t(113) = 2.09, p = 0.04. Low confidence only: t(113) = 0.63, p = 0.53.

**Experiment 2 -- Efficiency on Challenging Task (p. 15):**
- Time: Low conf vs. none: t(72.79) = -2.53, p = 0.01; High+low conf vs. none: t(72.63) = -3.70, p < 0.001.
- Queries on easy tasks: 2.3, 2.7, 2.7 per task (no highlighting, low conf, high+low conf). No systematic differences.
- Queries on challenging task: Low conf only = 3.0 vs. control = 2.2 (t(70.97) = -2.00, p = 0.05); High+low conf = 3.6 vs. control = 2.2 (t(73.21) = -3.29, p = 0.002).

---

## Pages 13-15 Are Primarily References and Appendix Figures

Pages 13-15 contain the bibliography (references [29]-[52]), Appendix A (Table 1 on traditional search query patterns from Bing data for top 25 SUVs in 2022), Appendix B (tutorial screenshots, speed-accuracy joint plot for Experiment 1), and Appendix C (efficiency results for Experiment 2). All quantitative results from the appendices are captured above. No new primary estimates beyond those already noted.

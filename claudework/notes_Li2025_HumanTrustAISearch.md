# Reference Links Increase Trust in GenAI Search Even When Hallucinated — A 4,927-Person Experiment

## Citation
Li, H. & Aral, S. (2025). "Human Trust in AI Search: A Large-Scale Experiment." *arXiv:2504.06435v1 [cs.CY]*, April 8, 2025. MIT Institute for Data, Systems, and Society / MIT Sloan School of Management.

---

## Identification Strategy

**Method:** Pre-registered, large-scale randomized controlled experiment (between-subjects and within-subjects design).

**Design:** Participants randomly assigned to one of 6 groups:
1. **GenAI** (control): Generative search responses labeled as AI-generated ($n=814$).
2. **Traditional search**: Identical information presented in Google featured snippet UI, labeled as not AI-generated ($n=842$).
3. **Reference links**: GenAI responses with clickable reference links; within-subjects randomization between valid vs. hallucinated/broken references ($n=785$).
4. **Uncertainty highlighting**: GenAI responses with color-coded confidence highlighting; within-subjects randomization between low-only vs. high+low certainty ($n=817$).
5. **Social feedback**: GenAI responses with "% of users who found this helpful"; within-subjects randomization between positive (65–95%) vs. negative (5–35%) feedback ($n=857$).
6. **Explanation**: GenAI responses with explanation of how AI Overviews work ($n=812$).

**Key design feature:** All groups saw **identical information** — only the presentation and labeling differed. This isolates the effect of GenAI design features from model quality.

**Trust measurement:** 5-item validated message credibility scale (accuracy, believability, bias, completeness, trustworthiness) on 7-point Likert scale (Cronbach's alpha >0.87 across all tasks). Plus willingness-to-share measure.

**9 search topics:** 5 policy debates (gun control, healthcare, immigration, civilian oversight, taxes) + 4 Pew "Top US Problems" (inflation, AI & jobs, vaccines, climate change).

---

## Data & Sample

- **$N = 4,927$ participants** (pre-registered target: 5,000), recruited via Prolific.
- **US-representative sample** matching adult population on age, gender, and ethnicity.
- **85% reported using GenAI**; 63% of GenAI users use it for information search (most popular use case).
- **67.83%** had used generative search engines before.
- **44,343 individual task-level observations** (4,927 participants x 9 search tasks).
- **Experiment period:** March 20 – April 2, 2024.
- **Global exposure study:** 11,372 queries x 7 countries = 79,604 real-time Google search results collected Oct–Nov 2024.

---

## Main Findings

### GenAI vs. Traditional Search (Figure 2A, Table S10, Page 10/53)
- GenAI **significantly reduces** trust ($\beta = -0.043$, $p < 0.05$ on 5-item trust; $\beta = -0.141$, $p < 0.001$ on willingness to share) compared to traditional search, when identical information is presented.
- This "trust gap" exists **purely because participants are told AI produced the results**.

### Reference Links Increase Trust — Even When Invalid (Figure 3A-B, Pages 10-11)
- **References significantly increase** trust ($\beta = 0.091$, $p < 0.001$) and willingness to share ($\beta = 0.121$, $p < 0.001$) compared to GenAI without references.
- **No significant difference** between valid and hallucinated/broken references on trust ($\beta = -0.021$, $p = 0.408$) or willingness to share ($\beta = -0.008$, $p = 0.820$).
- **Implication:** The mere **presence** of reference links creates trust regardless of their accuracy.

### Uncertainty Highlighting Reduces Trust (Figure 4A-B, Page 12)
- Uncertainty highlighting **significantly reduces** trust ($\beta = -0.157$, $p < 0.001$) and willingness to share ($\beta = -0.179$, $p < 0.001$).
- Low-certainty-only highlighting reduces trust **more** than mixed high+low highlighting ($\beta = -0.338$, $p < 0.001$ on trust within-subjects).

### Social Feedback (Figure 4C, Page 12)
- Negative social feedback **significantly reduces** trust ($\beta = -0.213$, $p < 0.001$) and willingness to share ($\beta = -0.286$, $p < 0.001$) compared to positive feedback (within-subjects).

### Explanations (Figure 4D-F, Page 12)
- Explanations of how GenAI works have **no significant average effect** on trust ($\beta = -0.011$, $p = 0.766$).
- BUT: Significantly increase trust for those with **no college degree** and those who have **never used GenAI**.

### Heterogeneity by Demographics (Figure 2B-G, Page 10)
- **Higher education** → more trust in GenAI.
- **Tech industry workers** → significantly more trust.
- **Frequent GenAI/search users** → significantly more trust.
- **Republicans** → trust GenAI significantly more than Democrats and neutrals.
- **Lower education, non-tech, less GenAI experience** → most vulnerable to trust induced by hallucinated references.

### Trust Predicts Behavior (Figure 6, Page 14)
- Higher trust → **more clicks** on GenAI results ($\beta = 0.107$, $p < 0.001$).
- Higher trust → **less time spent** evaluating content ($\beta = -1.139$ seconds, $p < 0.001$).
- Reference condition → more clicks and more time spent vs. GenAI baseline.
- Uncertainty highlighting → fewer clicks and less time spent.

### Global Exposure (Figure 1, Page 4)
- **42% of US Google searches** return AI Overview results.
- **56% of General Knowledge** and **51% of Health** queries return GenAI results.
- **Only 5% of Shopping** and **1% of Covid** queries return GenAI results.
- Query **style** is the strongest predictor: questions (49%), statements (16%), navigational (4%).

---

## Limitations
- Lab experiment; results may differ in real-world search behavior.
- Only search engines can conduct in-the-wild GenAI design experiments; unlikely to be reported publicly.
- Focused on consequential policy/public affairs topics; results may differ for mundane searches (product, DIY).
- US-only sample; trust in GenAI may vary across cultures.
- GenAI design is rapidly evolving; no experiment will be definitive.

---

## Key Implications
- **GenAI interface design can create trust independent of model trustworthiness** — the "veneer of rigor" (references, links) induces trust even when those references are fabricated.
- **AI interface design should be elevated to the same importance as foundation model reliability** in the AI trust debate.
- **Vulnerable populations** (lower education, less tech experience, Democrats for reference effects) are most susceptible to unwarranted trust from design features.
- **Uncertainty highlighting** effectively reduces trust but does so **regardless of whether confidence is high or low** — creating a paradox for designers.
- **Social feedback** significantly shapes trust, suggesting peer influence mechanisms can be leveraged (or manipulated) in GenAI contexts.
- Results support the need for **regulatory frameworks** addressing GenAI search design, not just model outputs.

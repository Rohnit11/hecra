# Generous Fair Use Can Harm AI Development When Training Data Is Scarce — A Dynamic Copyright Model

## Citation
Yang, S. A. & Zhang, A. H. (2024/2025). "Generative AI and Copyright: A Dynamic Perspective." London Business School / University of Southern California Gould School of Law. *arXiv:2402.17801v2 [econ.TH]*, first draft February 4, 2024; revised December 5, 2025.

---

## Identification Strategy

**Method:** Analytical / theoretical (two-period economic model). No empirical data or causal identification. The paper develops an equilibrium model to examine how two copyright policy levers — the **fair use standard** ($f$) and **AI-copyrightability** ($\phi$) — jointly influence AI development, creator income, consumer surplus, and social welfare.

**Model structure:**
- **Players:** A regulator, a generative AI company, and a continuum of content creators with heterogeneous skill levels ($x \in [0,1]$, uniformly distributed).
- **Two periods:** In Period 1, the regulator sets copyright policy; the AI company (endowed with model quality $X_1$) sets price; creators choose human creation, AI creation, or no creation. In Period 2, the AI company acquires training data, improves model quality to $X_2$, sets price; creators make new production decisions.
- **AI company objective:** Maximize value to AI creators subject to non-negative profit (competitive market assumption).
- **Training data:** Only high-quality human-generated content improves the model (motivated by model collapse concerns). Training data requirement function $q(X_2; X_1)$ is convex and increasing in target quality.
- **Scaling law specification:** $q(X_2; X_1) = \frac{1}{k} \log\left(\frac{1-X_1}{1-X_2}\right)$ (motivated by Kaplan et al. 2020).

---

## Data & Sample

**No empirical data.** The paper uses analytical proofs and numerical examples with the following baseline parameters: $c_H = 0.3$, $c_A = 0.05$, $\lambda = 0.6$, $\beta = 0.6$, $\phi = 0.6$, $M = 2$, $k = 5$, $X_1 = 0.4$.

Two data regimes analyzed:
1. **Data abundant:** $Q_0 \to +\infty$ (early-stage models, e.g., video generation).
2. **Data scarce:** $Q_0 = 0$ (mature models where historical data exhausted, e.g., LLMs).

---

## Main Findings

### Creator Behavior (Proposition 1)
- **Double-threshold policy:** Most skilled creators produce human content; intermediate-skill creators use AI; least skilled produce nothing.
- As model quality improves, AI creation expands at the expense of both human creation and non-creation.

### Data Abundant Regime (Section 5.1)

**Fair Use Standard (Proposition 7, Figure 2):**
- **Generous fair use ($f=0$) maximizes:** model quality ($X_2 = 1$), AI content quantity, creator income, and social welfare.
- Consumer surplus also maximized under generous fair use across all tested parameter values ($X_1$, $k$, $M$).

**AI-Copyrightability (Propositions 8-9, Figures 3-4):**
- Stronger AI-copyrightability **always increases** creator income (both periods).
- Impact on consumers is **ambiguous**: more content production (+) vs. larger creator share of value (–) vs. potential quality degradation when low-quality AI substitutes for human content (–).
- Stronger AI-copyrightability encourages AI model improvement through increased demand.

**Interaction (Corollary 2, Figure 5):**
- When $X_1$ is sufficiently large: optimal policy is **generous fair use ($f=0$) + full AI-copyrightability ($\phi=1$)**.
- Strong AI-copyrightability can **partially substitute** for generous fair use in model development.
- Connection is relatively weak; generous fair use dominates regardless of $\phi$.

### Data Scarce Regime (Section 5.2)

**Fair Use Standard (Propositions 10-11, Figure 7):**
- **Generous fair use can *harm* AI development** by reducing human content creation incentives — no training data available for model improvement (Proposition 10).
- **Overly strict fair use also harms** — when $f$ is too large, the AI company abandons model improvement entirely (Proposition 11).
- **A moderate fair use standard maximizes** AI development, social welfare, and consumer surplus.

**AI-Copyrightability (Proposition 12, Figure 8):**
- Under generous fair use, stronger AI-copyrightability **increases** AI content and creator income in Period 1 but **reduces** model quality in Period 2 (by shrinking human content supply for training).
- Under strict fair use, the negative effect is partially offset by increased AI company demand for training data.
- $X_2$ exhibits an **inverted-U** relationship with $\phi$.

**Interaction (Figure 9) — THE KEY NOVEL FINDING:**
- **When AI-copyrightability is weak:** generous fair use promotes AI development and welfare (because ample human content is created for training).
- **When AI-copyrightability is strong:** generous fair use *hinders* AI development and welfare (because too few creators produce human content for training).
- **The two policies must be considered jointly** when training data is scarce — treating them independently risks suboptimal policy.

### Optimal Policy (Figure 10)
- **Policy objectives are the primary driver** of optimal AI-copyrightability.
- Consumer surplus maximization → lowest $\phi$; social welfare/AI development → substantially higher $\phi$.
- **Fair use standard is more sensitive** to data availability, training efficiency ($k$), and market growth ($M$) than AI-copyrightability.
- A policymaker prioritizing AI development should set a **stricter** fair use standard than one focused on consumer surplus.

---

## Limitations
- Theoretical model with stylized assumptions (uniform skill distribution, competitive AI market, binary content quality).
- Does not model end consumers directly engaging with AI services.
- Assumes human and AI content are distinguishable (though acknowledges detection challenges).
- Treats human-generated content as the sole source of model improvement (excludes feedback/interaction data).
- Single regulatory body; does not model cross-border regulatory competition or forum shopping.
- Two-period model is a simplification of the continuous, evolving AI development process.

---

## Key Implications
- **No one-size-fits-all copyright doctrine** for generative AI — optimal policy depends on data availability, technological maturity, and regulatory objectives.
- **Dynamic perspective is essential:** A policy that works when training data is abundant (generous fair use) can backfire when data becomes scarce.
- **Fair use and AI-copyrightability are economically linked** through the bidirectional relationship between AI companies and content creators — analyzing them in isolation risks missing critical interactions.
- **Practical relevance:** As AI models mature and exhaust pre-existing training data, the data-scarce regime becomes increasingly relevant, making the paper's nuanced findings more applicable over time.
- **Regulatory divergence expected:** Different countries' policy priorities (US/China → AI growth; EU → consumer welfare) will likely drive variation in copyright regulation.
- Business leaders should anticipate **heterogeneous compliance environments** across jurisdictions.

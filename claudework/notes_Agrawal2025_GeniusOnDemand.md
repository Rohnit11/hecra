# Agrawal, Gans & Goldfarb (2025): Transformative AI Acts as an "On-Demand Genius" That Displaces Routine Workers and Pushes Human Geniuses to the Knowledge Frontier

**Citation:** Agrawal, A., Gans, J. S., & Goldfarb, A. (2025). "Genius on Demand: The Value of Transformative Artificial Intelligence." NBER Economics of Transformative AI Conference (Stanford, 2025). September 24, 2025. JEL: D24, J24, O33.

**File:** `papers/Agrawal2025_GeniusOnDemand.pdf` (20 pages, pure theoretical paper)

---

## Identification Strategy Is Pure Theory (No Empirical Causal Method)

- **Method:** Analytical / theoretical model. No data, no estimation, no causal identification.
- **Framework:** Extends Carnehl & Schneider (2025, *Econometrica*) knowledge-as-question-answer-pair model to incorporate AI as a distinct worker type with genius-like curvature properties.
- **Variation:** Comparative statics across three regimes (pre-AI, short-run AI introduction, long-run AI reorganization) and two curvature regimes (edge-first vs. interior-first optimal allocation).
- **Related literatures it positions against:**
  - Ide & Talamàs (2025, *JPE*): AI as hierarchical knowledge agent (autonomous vs. nonautonomous).
  - Acemoglu & Restrepo (2018, *AER*): AI as task-level substitute for labor.
  - Gans (2025a,b): complementary modeling of transformative AI.
  - This paper's contribution: AI modeled as an *autonomous genius substitute* whose error curvature differs from both routine and human-genius workers.

## Data & Sample Are Not Applicable (Theoretical Paper, N = 0)

- No dataset. No sample size. No empirical moments.
- Model primitives:
  - Knowledge space: $x \in [0,1] \subset \mathbb{R}$.
  - Single known question-answer pair: $F_t = \{(x_0, y(x_0))\}$, with $x_0 = 1/2$.
  - Conjecture distribution: $y(x) \sim \mathcal{N}(y(x_0), |x - x_0|)$ (Brownian motion in knowledge).
  - Quadratic loss with acceptance threshold $q$ (and abstention option).
  - Three worker types with value functions over position $x$:
    - **Routine** ($V_R$): linear decline, $V_R(x) = 1 - |x-x_0|/q$ if $|x-x_0| \le q$, else 0.
    - **Human genius** ($V_G$): quadratic cost, $V_G(x) = 1 - \eta (x-x_0)^2$.
    - **AI genius** ($V_{AI}$): quadratic cost, $V_{AI}(x) = 1 - \eta_{AI}(x-x_0)^2$, with $\eta_{AI} \ge \eta$.
  - Parameter restrictions: $1/2 > q$; $\eta \le 4$; routine supply $L_R \ge 2q$ (abundant); human genius supply $L_G < 1$ (scarce); AI supply unlimited.

## Main Findings Are Three Propositions on Optimal Allocation Before, During, and After AI Arrival

### Proposition 1: Pre-AI Optimal Allocation Has Two Regimes Depending on Human-Genius Curvature

*(pp. 9--11, eq. for absolute advantage $AA(x) = V_G(x) - V_R(x)$)*

- Rank positions by $AA(x) = V_G(x) - V_R(x)$ and assign the scarce human geniuses where their advantage is greatest.
- **Edge-first regime** ($\eta \le 1/(2q^2)$): $AA(x)$ peaks at the boundary $x = x_0 \pm q$ (edges of the region routine can cover). Human geniuses are allocated outward from these edges first.
- **Interior-first regime** ($\eta > 1/(2q^2)$): $AA(x)$ peaks at the interior points $x = x_0 \pm 1/(2\eta q)$. Human geniuses are allocated from these interior peaks outward.
- Three spatial regions emerge: $[0, 1/2-q]$, $[1/2-q, 1/2+q]$, $[1/2+q, 1]$; outside $[1/2-q, 1/2+q]$, routine workers cannot produce (unanswered region absent human/AI geniuses).

### Proposition 2: Short-Run AI Introduction Pushes Human Geniuses Outward and Fills Unanswered Regions

*(pp. 12--14)*

- Define human-vs-AI comparative advantage: $AA_{H/AI}(x) = V_G(x) - V_{AI}(x) = (\eta_{AI} - \eta)(x-x_0)^2$, which is **increasing in distance from** $x_0$.
- Therefore, conditional on both being productive, humans are allocated to the furthest positions (frontier), AI to closer positions.
- **AI replaces human geniuses at closer positions** (where AI's relative penalty is small).
- **AI fills previously unanswered regions** (positions where neither routine nor the scarce human geniuses were previously deployed).
- **Routine workers remain unchanged** in the short run because AI does not yet reach into the routine's comparative-advantage band.

### Proposition 3: Long-Run AI Displaces Routine Workers Entirely When η_AI ≤ 1/q² and Human Geniuses Ultra-Specialize at the Frontier

*(pp. 14--16, plus footnote 6 on knife-edge case)*

- **Displacement condition:** if $\eta_{AI} \le 1/q^2$, then $V_{AI}(d) \ge V_R(d)$ for all $d \in [0,q]$. AI weakly dominates routine throughout the routine region and fully displaces routine workers.
- In this regime, human geniuses retreat to the **frontier** $|x - x_0| \ge d^*$ (ultra-specialization at the furthest positions from the known answer).
- **Footnote 6 (knife-edge):** if $\eta_{AI} > 1/q^2$, routine survives only in a narrow edge band $1/(\eta_{AI} q) < |x-x_0| < q$ where routine's linear decline outpaces AI's quadratic decline.

### Summary Results Table (Verbal)

| Regime | Routine | Human genius | AI genius |
|--------|---------|--------------|-----------|
| Pre-AI | Interior $[x_0-q, x_0+q]$ | Scarce; deployed by $AA(x)$ peak (edge or interior) | Not available |
| Short-run AI | Unchanged | Pushed to furthest positions | Closer positions + previously unanswered region |
| Long-run AI, $\eta_{AI} \le 1/q^2$ | Fully displaced | Frontier only ($\ge d^*$) | Covers routine band and near-frontier |
| Long-run AI, $\eta_{AI} > 1/q^2$ | Survives only in narrow edge band $(1/(\eta_{AI} q), q)$ | Frontier | Interior |

## Limitations as Noted by the Authors

- AI modeled purely as **substitute** (autonomous genius); the paper does not model AI as a **tool or complement** that augments human workers (flagged as future research, referencing Agrawal et al. 2025 NBER WP 30434).
- Single known question-answer pair $(x_0, y(x_0))$; richer knowledge bases with multiple anchors are not modeled.
- Brownian motion over knowledge imposes a specific correlation structure on conjecture variance; alternative stochastic processes are not explored.
- Static framework: no investment in human capital, no dynamic response of genius supply to AI arrival.
- Parameters treated as exogenous; no market for AI services or pricing of genius labor.

## Key Implications for the Broader Research Agenda

- **Polarization through the knowledge-frontier channel:** transformative AI does not symmetrically substitute all labor. Routine workers face displacement when AI curvature $\eta_{AI} \le 1/q^2$; human geniuses are pushed outward to the frontier rather than displaced.
- **Complement to Ide & Talamàs (2025):** Ide-Talamàs have autonomous AI benefiting the most knowledgeable and nonautonomous AI benefiting the least knowledgeable; Agrawal et al. reach a parallel conclusion from a different modeling primitive (curvature of the value function rather than hierarchy of problem difficulty).
- **Departs from Acemoglu & Restrepo (2018):** rather than task-level substitution, AI's impact here is mediated by the geometry of value functions and the scarcity structure of human genius.
- **Policy / welfare:** total output rises with AI because previously unanswered regions are now covered, but the distributional effect on routine workers is unambiguously negative when $\eta_{AI} \le 1/q^2$.
- **Research frontier question:** empirical test of whether AI substitutes first for tasks closest to known answers (Proposition 2 prediction) rather than uniformly across tasks.

---

## Audit Checklist

- [x] **Identification Strategy:** Pure theory (comparative statics on worker-allocation model; no empirical identification).
- [x] **Data & Sample:** N/A — theoretical paper, no dataset.
- [x] **Main Findings:** Propositions 1--3 on pre-AI, short-run, and long-run AI allocation; displacement condition $\eta_{AI} \le 1/q^2$; two curvature regimes (edge-first vs. interior-first). Page references pp. 9--16.
- [x] **Limitations:** AI-as-substitute only; single knowledge anchor; Brownian conjecture; static; no AI market.
- [x] **Key Implications:** Polarization at the knowledge frontier; routine displacement conditional on AI curvature; parallels Ide-Talamàs via different primitives; departs from Acemoglu-Restrepo task substitution.

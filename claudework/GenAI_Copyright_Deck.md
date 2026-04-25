---
marp: true
theme: default
paginate: true
math: katex
style: |
  section { font-size: 26px; }
  h1 { font-size: 38px; }
  h2 { font-size: 32px; }
  table { font-size: 22px; }
  blockquote { border-left: 4px solid #888; color: #444; }
---

# GenAI Copyright Demands Dynamic, Jointly-Designed Policy

**Synthesis of two complementary audits**

- Yang & Zhang (2024). *Generative AI and Copyright: A Dynamic Perspective.* arXiv:2402.17801v2.
- Cooper, Martens, Peukert, & Stocker (2025). *The Law and Economics of Generative AI and Copyright.* *Review of Network Economics* 24(3): 161–176.

---

## GenAI Breaks Copyright at Both Input and Output Stages

| Stage | Core question | Status |
|---|---|---|
| **Input** | Can copyrighted works be scraped to train models? | Unsettled — fair use (US), TDM exceptions + opt-outs (EU) |
| **Output** | Are AI-assisted works copyrightable? | Disparate thresholds across US / EU / China |

> Cooper et al. (2025) frame the "AI copyright conundrum" as a two-sided problem along the AI value chain (pretraining → post-training → inference).

---

## Two-Thirds of AI Training Datasets Are Licensed Incorrectly or Not at All

- **~65%** of datasets on Hugging Face / PapersWithCode have missing, incorrect, or ambiguous license metadata (Longpre et al. 2024a, cited in Cooper 2025, p. 167).
- In **LAION-5B** (largest public image dataset): fewer than **1 in 1,000** data points carry license metadata (Shcherbakov et al. 2025).
- **10 website domains** account for **23%** of LAION's 2 billion images — supply is concentrated, not representative.
- Opt-out vs. licensed images depict **semantically different concepts** and differ in technical quality.

---

## Anthropic's $1.5B Settlement Is the Largest Copyright Recovery in History — and Doctrine Is Still Unsettled

- **Alsup (Anthropic):** initial downloading **infringing** → **$1.5B** recovery; subsequent *training* use ruled fair use.
- **Chhabria (Meta):** training fair use *only because* "these plaintiffs made the wrong arguments"; judge stated training on protected works "would generally be illegal" (Cooper 2025, p. 165).
- **USCO (2025b):** doubts fair use applies when AI outputs **compete in existing markets** for training works.
- **EU:** Hamburg LAION ruling suggests **terms-of-service opt-outs are enforceable**.

> Dozens of US suits remain pending; resolution is years away (Cooper 2025, pp. 171–172).

---

## When Training Data Is Abundant, Generous Fair Use Maximizes Every Welfare Metric

Yang & Zhang (2024), Proposition 7 (data-abundant regime, $Q_0 \to \infty$):

| Variable | Maximized by |
|---|---|
| Model quality $X_2$ | $f = 0$ (fully generous fair use) → $X_2 = 1$ |
| AI content quantity | $f = 0$ |
| Creator income | $f = 0$ |
| Consumer surplus | $f = 0$ (across all tested $X_1, k, M$) |
| Social welfare | $f = 0$ |

- Corollary 2: optimal joint policy is $\{f=0, \phi=1\}$ (generous fair use **plus** full AI-copyrightability).
- Baseline parameters: $c_H = 0.3$, $c_A = 0.05$, $\lambda = 0.6$, $\beta = 0.6$, $k = 5$, $X_1 = 0.4$.

---

## When Training Data Is Scarce, Generous Fair Use *Harms* AI Development

Yang & Zhang (2024), Propositions 10–11 (data-scarce regime, $Q_0 = 0$ — e.g., mature LLMs):

- **Generous fair use ($f \to 0$):** kills creator incentives → **no human content** for training → model improvement stalls (Prop. 10).
- **Strict fair use ($f$ too large):** AI company **abandons model improvement** entirely (Prop. 11).
- **A moderate $f$ maximizes** $X_2$, social welfare, and consumer surplus.

> The paper's central novel finding: a policy that is welfare-maximizing in 2020 can be welfare-destroying in 2026 once pre-existing data is exhausted.

---

## Strong AI-Copyrightability Flips Fair Use From Helpful to Harmful

Yang & Zhang (2024), Figure 9 — the **interaction effect** in the data-scarce regime:

| AI-copyrightability $\phi$ | Effect of generous fair use on AI development |
|---|---|
| **Weak** | **Promotes** development (creators still produce human content for training) |
| **Strong** | **Hinders** development (too few creators → training data dries up) |

- $X_2$ is **inverted-U** in $\phi$ when data is scarce (Proposition 12).
- Implication: $f$ and $\phi$ **cannot be designed independently**; analyzing them in isolation risks suboptimal policy.

---

## Courts on Three Continents Reach Three Different Verdicts on the Same Work

Cooper et al. (2025), Section 3.2:

| Jurisdiction | Ruling | Threshold |
|---|---|---|
| **China** (Li v. Liu, 2023) | **Copyrightable** | "Intellectual investment" + "personalized expression" via prompting |
| **US** (USCO, 2025a) | **Not copyrightable** | "All current-state prompting outputs" lack sufficient human control |
| **EU** (Czech Dall-E ruling) | **Not copyrightable** | "Plaintiff did not personally create the work" |

- Copyright is **separable per element** in the US — within one work, drums may be uncopyrightable while lyrics are protected.
- Any cross-border work has **divergent legal status** by default.

---

## Disclosure Cannot Enforce the AI / Non-AI Dichotomy — and Creates Perverse Incentives

- **The "Old Hard Drive Debacle"** (Cooper 2025): artists must log every GenAI use, *solely to strip themselves of rights* → strong incentive to **deny** AI use.
- **No robust detection tool** exists for whether — let alone *which elements* of — a work used GenAI (10+ sources on watermarking limits cited in Cooper 2025).
- **Convergence problem:** search-engine crawlers and AI training crawlers are technologically indistinguishable; blocking one blocks the other (Cooper 2025, p. 172).

---

## GenAI Produces Infringing Outputs Without Intent — Synthetic Data Is No Escape

- GenAI can output **near-identical copies** of protected works even with developer safeguards (Cooper & Grimmelmann 2025).
- US "Blurred Lines" precedent: **weak similarity thresholds** mean outputs need not be close replicas to infringe.
- **Copy-mining incentive** (Cooper 2025, Lemley 2024): mass-generate to claim maximum rights, mining out the latent space between existing works.
- **Synthetic data fails as a fix:** depends on real-data quality, cannot generate genuine novelty, and recursive training risks **model collapse** (Shumailov et al. 2024).

---

## Optimal Policy Depends on Objective and Data Regime — Divergence Is Rational

Yang & Zhang (2024), Figure 10:

| Regulator's objective | Optimal $\phi$ | Optimal $f$ |
|---|---|---|
| Consumer surplus | **Lowest** | More generous |
| Social welfare / AI development | **Substantially higher** | **Stricter** |

- Fair use is **more sensitive** than $\phi$ to data availability ($Q_0$), training efficiency ($k$), and market growth ($M$).
- Cooper et al. (2025): countries with **less restrictive** copyright regimes show better AI innovation outcomes (Peukert 2025a).
- Predicted alignment: **US / China** → AI growth; **EU** → consumer welfare → persistent jurisdictional divergence.

---

## The Path Forward Is Joint, Dynamic, and Hybrid

1. **Joint design of $f$ and $\phi$** — Yang & Zhang show treating them independently is welfare-destroying when data is scarce.
2. **Stock vs. flow** — Cooper: legal uncertainty restricts the *stock* of reusable data **and** chills the *flow* of new content. Both must be modeled.
3. **Hybrid remuneration** — royalties where authorship is attributable + collective fund for the remainder (Senftleben 2023, 2024; Cooper 2025, p. 171).
4. **Dynamic perspective** — as pre-existing training data exhausts, the data-scarce regime becomes the **default** case, not the edge case.

> Empirical gaps remain: how opt-outs reshape training-data representativeness, how copyright uncertainty changes creator behavior, and the actual prevalence of memorized infringing outputs across models.

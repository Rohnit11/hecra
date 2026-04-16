# Audit Notes: Ide & Talamàs (2025) — Artificial Intelligence in the Knowledge Economy

**Citation:** Ide, E. & Talamàs, E. (2025). "Artificial Intelligence in the Knowledge Economy." *Journal of Political Economy*, 133(12), 3762–3797. https://doi.org/10.1086/737233

**File:** `papers/Ide2025_AIKnowledgeEconomy.pdf` (39 pages)

**Audit date:** 2026-04-16

---

## Identification strategy is pure theory, not empirical causal inference

This is a **fully theoretical general-equilibrium paper** — no data, no regression, no shock, no DiD/IV/RDD/RCT. The "identification" is the comparison of two analytically characterized competitive equilibria (pre-AI vs post-AI) within a knowledge-hierarchy model. Specifically:

1. **Baseline model (pre-AI):** Extension of Garicano (2000), Garicano and Rossi-Hansberg (2004), Antràs–Garicano–Rossi-Hansberg (2006), and Fuchs–Garicano–Rayo (2015) knowledge hierarchies. Unit mass of humans with knowledge $z\in[0,1]$ drawn from CDF $G$, each endowed with 1 unit of time. Problems drawn uniformly from $[0,1]$. An individual with knowledge $z$ solves problems of difficulty $\le z$. Firms have at most 2 layers. Helping cost $h\in(0,1)$ (solver time consumed per question). Firms break even under perfect competition, complete information (pp. 3771–3776).
2. **AI model (post-AI):** Same primitives plus a continuous measure $m$ of "compute" (exogenous). AI technology converts 1 unit of compute → 1 "AI agent" of exogenous fixed knowledge $z_{AI}\in[0,1)$. Compute is **abundant relative to human time** (Assumption; sufficient condition given in footnote 14, p. 3776).
3. **Two AI regimes compared:**
   - **Autonomous AI** — agents serve as coworkers (pursue production) AND as copilots (advise) — §III–V.
   - **Nonautonomous AI** — agents serve only as copilots — §VI.
4. **Within autonomous AI, two sub-cases:**
   - **Basic AI:** $z_{AI}\in \text{int}\,W$ (knowledge of pre-AI workers).
   - **Advanced AI:** $z_{AI}\in \text{int}\,S$ (knowledge of pre-AI solvers).
5. **"Shock":** analytically comparing equilibrium objects (occupational partition $W,I,S$; matching function $m(z)$; wage schedule $w(z)$; rental rate $r$ of compute) with and without AI. No empirical shock or instrument.

The paper is an **equilibrium-theory contribution**: all claims are propositions (1–6) proved in the online appendix, illustrated with parametric simulations under the uniform distribution $G(z)=z$ and $h=1/2$.

## Data source: zero primary data; only stylized-fact citations

There is **no $N$, no regression sample, no panel**. The paper uses external facts/studies only to motivate assumptions and benchmark predictions:

- **Motivating statistics:** 100M+ US workers in knowledge/cognitive roles as of Dec 2024 (BLS via Dvorkin and Shell 2024), p. 3763.
- **Foundation-model adoption:** Andreessen Horowitz survey of ~100 Fortune 500 firms — 94% using existing foundation models, 6% building their own (Wang and Xu 2024), footnote 7, p. 3770.
- **Exposure estimates cited (not re-estimated):** Eloundou et al. (2024) — 46% of jobs have >½ tasks exposed to AI; Nathan et al. (2023) — two-thirds of US occupations at least partially exposed, ~25% amenable when employment-weighted (p. 3771).
- **Computational capacity:** Nordhaus (2007) exponential growth; Amodei (2024) — current AI models process outputs 10–100× faster than humans (p. 3766, 3776).
- **Corroborating micro studies cited (not audited):** Dell'Acqua et al. (2023), Noy and Zhang (2023), Peng et al. (2023), Wiles et al. (2023), Caplin et al. (2024), Brynjolfsson et al. (2025), Alekseeva et al. (2024), Berger et al. (2024) — used in the Discussion (§VII) to argue that the model reconciles apparently contradictory empirical findings.
- **Anecdotal industry evidence:** Klarna (700 customer-service agents automated via OpenAI), Harvey (legal research on OpenAI), Claude Sonnet at Lonely Planet and Bridgewater, Salesforce Agentforce, AllDay TA, GitHub Copilot, BrainTrust AIR (pp. 3770, 3777); Beane and Anthony (2024) investment banking; Litera (2022) M&A lawyer survey (p. 3787).

**Sample size $N$ is not applicable** — this is a model-theory paper. The only numerical object is the simulation: uniform $G(z)=z$, $h=1/2$ (so $h<h_0=3/4$), $z_{AI}=0.425$ (basic) or $z_{AI}=0.85$ (advanced), used only to render figures 3–9.

## Main findings: 6 numbered propositions + reconciliation of micro evidence

No regression coefficients, standard errors, or $p$-values (none exist). Findings are qualitative **propositions** (Props 1–6), each proved in the appendix:

### Proposition 1 (pre-AI equilibrium, p. 3780)
Unique, efficient equilibrium with:
- **Occupational stratification:** $W \preceq I \preceq S$ (workers ≤ independent producers ≤ solvers in knowledge).
- **Positive assortative matching** between workers and solvers ($m$ strictly increasing).
- $W\ne \emptyset$, $S\ne \emptyset$ always; $I\ne \emptyset$ iff helping cost $h > h_0\in(0,1)$.
- Wage function $w(z)$ continuous, strictly increasing, strictly convex on $W\cup S$; explicit piecewise form given.

### Proposition 2 (autonomous-AI equilibrium, p. 3782)
Unique and efficient equilibrium with:
- Post-AI stratification $W^*\preceq I^*\preceq S^*$; AI sits at $z_{AI}$: $W^*\preceq \{z_{AI}\}\preceq S^*$.
- **Rental rate of compute $r^*=z_{AI}$.**
- If $z_{AI}\in W$ → AI necessarily used as worker (possibly also solver).
- If $z_{AI}\in S$ → AI necessarily used as solver (possibly also worker).
- Explicit wage formulas for each occupational sub-class.

### Proposition 3 (occupational displacement, p. 3786)
- **Basic autonomous AI** ($z_{AI}\in \text{int}\,W$): displaces humans from routine work *to* specialized problem-solving — $W^*\subset W$, $S^*\supset S$.
- **Advanced autonomous AI** ($z_{AI}\in \text{int}\,S$): displaces humans from problem-solving *to* routine work — $W^*\supset W$, $S^*\subset S$.

### Proposition 4 (productivity and span of control, p. 3786)
- Basic AI: pre-AI workers who remain workers see **strictly lower productivity**; span of control of solver $z$ increases iff $e(z)<z_{AI}$, decreases iff $e(z)>z_{AI}$.
- Advanced AI: pre-AI workers who remain workers see **strictly higher productivity** if $z<e(z_{AI})$, lower if $z>e(z_{AI})$; span of control of remaining solvers strictly larger.

### Proposition 5 (winners at the extremes, p. 3788)
- $B=\{z\in[0,z_{AI}]: w^*(z)>w(z)\} = [0,z_b)$ — "winners at the bottom."
- $T=\{z\in[z_{AI},1]: w^*(z)>w(z)\} = (z_t,1]$ — "winners at the top."
- **Always $T\ne\emptyset$** (the most knowledgeable always gain under autonomous AI, given $h<h_0$ and $z_{AI}<1$).
- $B\ne\emptyset$ **iff** $z_{AI}>\bar z_{AI}$, where $\bar z_{AI}\in\text{int}\,W$. i.e., the least knowledgeable only gain if AI is sufficiently capable.
- The individual at exactly $z_{AI}$ **always loses**: $w^*(z_{AI})<w(z_{AI})$.

### Proposition 6 (nonautonomous AI, p. 3791)
- Equilibrium is unique and efficient; maximizes labor income.
- Rental rate $r^\dagger = 0$ (some compute idle).
- AI used iff sufficiently advanced: $z_{AI}>w(0)$. Otherwise $W^\dagger_a=\emptyset$ and outcomes = pre-AI.
- **Output ranking:** autonomous AI > nonautonomous AI > no AI (p. 3791, items 1–2).
- **Least knowledgeable (neighborhood of $z=0$):** $w^\dagger(z) \ge \max\{w(z), w^*(z)\}$ — strictly when $z_{AI}>w(0)$. Nonautonomous AI is **best** for them.
- **Most knowledgeable (neighborhood of $z=1$):** $w^\dagger(z)\le w^*(z)$ — strictly except at $z=1$. Autonomous AI is **best** for them.

### Reconciliation of empirical evidence (§VII, pp. 3793–3794)
The paper argues its theory reconciles two strands of existing micro-empirical evidence:
1. **Studies finding AI helps the lowest-skilled most** (Dell'Acqua 2023; Noy–Zhang 2023; Peng 2023; Wiles 2023; Caplin 2024; Brynjolfsson–Li–Raymond 2025) — these study **AI copilots** → map to the nonautonomous regime (or advanced autonomous AI as copilot).
2. **Studies finding AI substitutes for low-skilled and complements high-skilled** (Alekseeva 2024; Berger 2024 — including post-ChatGPT LinkUp job-posting decline for entry-level white-collar roles, rise for executive roles) — these reflect **AI as coworker** / basic autonomous AI.

## Key parameter choices in the illustrations

- Knowledge distribution: **$G(z)=z$** (uniform) for all figures.
- Helping cost: **$h=1/2$** (below threshold $h_0=3/4$ under uniform $G$) in figs. 3A, 4, 5, 6, 7, 9; $h=0.8125$ (>$h_0$) in fig. 3B only.
- Basic AI illustration: **$z_{AI}=0.425$**.
- Advanced AI illustration: **$z_{AI}=0.85$**.

These parameterize figures only; none of the propositions depend on the uniform distribution (proofs in appendix).

## Limitations (as flagged by the authors)

1. **Two-layer restriction** maintained throughout the main text for comparability between autonomous/nonautonomous regimes (§VI.B, p. 3793); the appendix generalizes to arbitrary layers and confirms that the core insights hold.
2. **Compute abundance** assumed: if compute is scarce relative to production opportunities → different conclusions (some humans less knowledgeable than AI become unemployed; discussed p. 3779 and in appendix).
3. **Single AI technology** assumed in the main text; appendix shows coexistence possible if smaller models require substantially less compute (pp. 3778–3779).
4. **$z_{AI}<1$** required for the main results. When $z_{AI}=1$ (superintelligent AI), the most knowledgeable humans **necessarily lose** (footnote 19, p. 3790).
5. **$h<h_0$** assumption made for the main text's tractability; extensions for $h\ge h_0$ in Ide and Talamàs (2024) earlier working paper (p. 3790).
6. **No training / data / compute-production costs modeled** — compute is taken as an exogenous endowment during the inference phase (§III.B "On compute," p. 3778).
7. **No uncertainty or asymmetric information** about AI knowledge $z_{AI}$; perfect observability assumed throughout.
8. **Welfare analysis focuses on labor income**; capital income accrues to compute owners (treated as separate from the human population) — distributional welfare across capital-holders vs. labor is not explored.
9. **Empirical quantification absent** — the authors explicitly call for future work to **quantify the output-inequality trade-off** in AI autonomy regulation (p. 3796).

## Key implications for the research agenda

- **Policy trade-off:** regulating AI autonomy (e.g., EU AI Act, 2024 O.J. L 2024/1689) trades **output against inequality**. Autonomous AI maximizes output but widens labor-income inequality vs. nonautonomous AI.
- **Anti-inequality benchmark (copilots):** Micro RCT evidence on AI disproportionately helping lower-skilled workers is consistent with the **nonautonomous / copilot regime**; predictions could differ sharply for autonomous AI coworkers (Klarna-style deployments).
- **AI ≠ offshoring or immigration**: key difference is **scalability + homogeneity** — AI introduces a large, homogeneous agent population, whereas large human populations are heterogeneous in tacit knowledge (p. 3795).
- **AI ≠ earlier ICT waves**: ICT (computers, email) had near-universal adoption; AI has **partial adoption** in equilibrium even when costless (nonautonomous AI useless to very knowledgeable firms), plus strictly positive opportunity cost under autonomous AI (p. 3795, citing Svanberg et al. 2024).
- **Advanced vs developing economies:** same AI may be "basic" in an advanced economy (higher solver threshold) and "advanced" in a developing economy, reversing the direction of occupational displacement (p. 3796).
- **Future empirical research:** disentangling effects of AI coworkers vs. AI copilots is the key open question the paper teases (p. 3794).

## Appendix

- **Online mathematical appendix** referenced throughout (p. 3769 and passim) contains all formal proofs of Propositions 1–6, the $h\ge h_0$ extension, the multi-layer generalization, the $z_{AI}=1$ case, the limited-compute case, the multiple-AI-technologies extension, and the distributions of firm size / productivity / decentralization. Per audit protocol, technical appendices without new empirical results are noted and skipped.
- **References (pp. 3796–3797):** bibliography only; not audited.

---

**Audit completed by:** Claude (Opus 4)
**Protocol:** Lossless Research Audit per `Prompt.md`
**Method:** Full-text extraction via PyPDF2 (39 PDF pages / 15 physical article pages at 1.4 MB).

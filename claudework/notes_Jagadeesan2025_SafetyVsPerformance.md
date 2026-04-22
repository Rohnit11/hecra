# Jagadeesan, Jordan & Steinhardt (2025) — Safety-Performance Tradeoffs Reduce LLM Market Entry Barriers

**Citation:** Jagadeesan, M., Jordan, M. I., & Steinhardt, J. (2025). "Safety versus performance: How multi-objective learning reduces barriers to market entry." *PNAS*, 122(42), e2510004122. Published October 15, 2025. DOI: 10.1073/pnas.2510004122.

**Audit date:** 2026-04-22
**Pages audited:** 11 (3 chunks: p001-004, p005-008, p009-011)

---

## Identification Strategy Is Pure Theory: Multi-Objective High-Dimensional Linear Regression

This is a **purely theoretical / mathematical** paper. **No causal identification.** No empirical shock, no DiD, IV, or RDD. The paper develops a stylized economic model of a marketplace with two firms fitting linear regression models.

### Framework

- **Input:** $x \in \mathbb{R}^P$.
- **Two objectives:** performance-optimal output $\langle\beta_1, x\rangle$ and safety-optimal output $\langle\beta_2, x\rangle$.
- **Firms:** Incumbent $I$ (with $N_I$ data points) and Entrant $E$ (with $N_E$ data points). Each picks mixture parameter $\alpha \in [0.5, 1]$ (share of data labeled with performance objective) and ridge regularizer $\lambda$, subject to safety constraint $\tau_C$.
- **Key assumption:** $\tau_E > \tau_I$ — incumbent faces stricter safety threshold (regulatory/reputational scrutiny is uneven by firm size).
- **Statistical assumptions (p. 5):** Power-law covariance decay $\lambda_i = i^{-1-\gamma}$; alignment coefficients $\mathbb{E}[\langle\beta_j, v_i\rangle^2] = i^{-\delta}$; correlation parameter $\rho \in [0,1)$ where $\mathbb{E}[\langle\beta_1, v_i\rangle\langle\beta_2, v_i\rangle] = \rho \cdot i^{-\delta}$.
- **Marcenko–Pastur (random matrix theory)** used to derive deterministic equivalent for loss.

### Object of interest

Market-entry threshold $N_E^*$ (Definition 1, p. 4): minimum entrant dataset size needed to match or beat incumbent's performance while respecting $\tau_E$.

---

## Data and Sample: No Empirical Data

**"Data, Materials, and Software Availability: There are no data underlying this work."** (p. 9, explicitly stated.)

Calibration to empirically observed LLM scaling exponent $\nu = 0.34$ is taken directly from Hoffmann et al. 2022 (Chinchilla paper, reference 9), not estimated here.

---

## Main Findings Are Five Theorems, Not Coefficients

All "findings" are theorem statements giving asymptotic scaling rates $\Theta(\cdot)$, not point estimates with standard errors. There are no confidence intervals or p-values in the paper.

### Theorem 1 (p. 5) — Warm-up: infinite-data incumbent, unconstrained entrant

With $N_I = \infty$ and $\tau_E = \infty$:
$$N_E^* = \Theta\left(\left(\sqrt{L^*(\rho)} - \sqrt{\min(\tau_I, L^*(\rho))}\right)^{-2/\nu}\right)$$
where $\nu = \min(2(1+\gamma), \delta+\gamma)$ and $L^*(\rho) = \Theta(1-\rho)$.

**Key result:** Entrant can enter with *finite* data even against an infinite-data incumbent, provided (1) incumbent's safety constraint binds and (2) $\rho < 1$. Threshold rises as $\tau_I$ weakens or $\rho$ strengthens.

### Theorem 2 (p. 6) — Multi-objective loss scaling law

Under optimal regularization, loss scales as $N^{-\nu^*}$ where $\nu^*$ takes **three values** depending on $N$:

| Regime | Range | Exponent $\nu^*$ |
|---|---|---|
| 1 | $N \leq (1-\alpha)^{-1/\nu}(1-\rho)^{-1/\nu}$ | $\nu$ |
| 2 | intermediate | $\nu/(\nu+1)$ |
| 3 | $N \geq (1-\alpha)^{-(2+\nu)/\nu}(1-\rho)^{-1/\nu}$ | $0$ |

**Calibration to LLMs** (p. 6): With empirical $\nu = 0.34$, scaling exponent drops $0.34 \to 0.25 \to 0$ as $N$ grows.

### Theorem 3 (p. 7) — Excess loss scaling law

Three regimes; third-regime exponent is $\nu'/(\nu'+1) > 0$ where $\nu' = \min(1+\gamma, \delta+\gamma)$, so the excess loss keeps improving even when the loss plateaus.

### Theorem 4 (p. 7) — Finite-data incumbent

$$N_E^* = \begin{cases}\Theta(N_I) & \text{small } N_I\\ \Theta(N_I^{1/(\nu+1)} \cdot (G_I(1-\rho))^{-1/(2(\nu+1))}) & \text{intermediate}\\ \Theta(G_I^{-1/\nu}) & \text{large } N_I\end{cases}$$

**Calibration (p. 7):** With $\nu = 0.34$, exponent $c$ in $N_E^* = \Theta(N_I^c)$ drops from **1 → 0.75 → 0** as $N_I$ grows. Entrant scales dataset at slower rate than incumbent.

### Theorem 5 (p. 8) — Entrant also faces safety constraint

$N_E^* = \Theta(D^{-c})$ where $D = G_I - G_E$ is the gap between infinite-data losses and $c$ increases from $1/\nu$ to $(\nu+1)/\nu$ to $(\nu'+1)/\nu'$ as $D$ shrinks.

**Calibration (p. 8):** With $\nu = 0.34$, $c$ ranges from **2.94 → 3.94 → even larger** as safety thresholds converge.

---

## Limitations (authors' own, p. 9-10)

- Only studies market *entry*, not long-run survival.
- Assumes homogeneous users who choose on performance alone (no price competition, no downstream developers).
- Linear regression may not fit all safety objectives (privacy, worst-case queries, multigroup criteria).
- Multi-objective scaling laws not yet empirically validated for LLMs.
- No empirical data — calibration borrowed from Hoffmann et al. 2022 exponent only.

## Key Implications

- **Pro-entry regulatory theory:** Stricter safety scrutiny on dominant incumbents can *reduce* barriers to entry — new firms trade off less safety for more performance-oriented data.
- **Scaling laws are worse with multiple objectives:** The exponent decreases with $N$, unlike the single-objective case. Incumbents with huge datasets hit diminishing returns that entrants can exploit.
- **Caveat — race to the bottom:** The same mechanism that lowers entry barriers may incentivize new firms to undershoot on safety. Regulators face a competitiveness vs. safety tradeoff.
- Results extend conceptually to social media / recommendation platforms (EU Digital Services Act's VLOP threshold of 45M users is an analog of $\tau_I < \tau_E$).

## Structural Notes

- Pages 5–9 contain Theorems 1–5 + proof sketches + Figures 1–4.
- Pages 10–11 are **bibliography only** (87 references); no new results. Skipped per protocol.
- SI Appendix (referenced but not in the main PDF) contains formal definitions of deterministic equivalents $L_1^{\text{det}}, L_2^{\text{det}}$ and full proofs.

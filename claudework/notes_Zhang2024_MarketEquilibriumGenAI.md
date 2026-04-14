# Zhang et al. (2024) — Market Equilibrium in the Age of Generative AI

> Zhang, X. et al. (2024). "Market Equilibrium in the Age of Generative AI." Working Paper.

---

## NovelAI Leak Cuts Anime Art Prices by 64% but Expands Volume by 121%, Increasing Total Revenue

**Identification Strategy:** Difference-in-Differences with two-way fixed effects (TWFE) using the NovelAI model leak on October 6, 2022 as a natural experiment. The leaked model specialized in anime-style character art ("tachie"), creating a sudden, exogenous increase in AI art generation capability for this specific style. Treatment group: tachie (anime character art) commissions. Control group: wallpaper commissions (not affected by the leak). The design compares the two categories before and after the leak.

**Shock/Variation:** NovelAI Stable Diffusion model leaked on October 6, 2022 (4chan). This was an unanticipated event that suddenly made high-quality anime art generation freely available to the public.

---

## ~197,000 Orders on Mihuashi Platform, 126 Category-Week Observations

**Data Source:** Mihuashi — China's leading art outsourcing/commission platform.

**Sample:**
- ~197,000 orders
- Aggregated to **N = 126 category-week observations** (2 categories x 63 weeks)
- **Time period:** January 2022 -- February 2023

**Unit of observation:** Category-week (tachie vs. wallpaper).

---

## Prices Fall 64%, Volume Rises 121%, Net Revenue Increases 56%

**Main results (Table 2, Page 11, all significant at 1%):**

| Outcome | DiD Estimate | Effect Size |
|---------|-------------|-------------|
| Average price | **-646.5 yuan** | -64% |
| Weekly volume | **+140.3 orders/week** | +121% |
| Weekly revenue | **+56,674 yuan/week** | +56% |

**Heterogeneity (Table 3):**
- Growth driven almost entirely by **low-end personal orders** (log volume: +2.95)
- Commercial orders barely affected (log volume: +0.39)
- Market expansion occurs at the low end, not displacement at the high end

**Supply-side effects (Table 4):**
- Incumbent artists (registered before the leak) won **97.41% of post-leak orders** and **97.96% of revenue**
- New AI-using entrants did **not** displace human creators
- Incumbents adapted by lowering prices and increasing volume

---

## Limitations

- **Single treated-control pair:** Only two art categories compared (tachie vs. wallpaper) — limited cross-sectional variation.
- **Single platform/country:** Results are specific to Mihuashi and the Chinese art commission market.
- **Short post-period:** Only ~5 months of post-leak data (October 2022 -- February 2023).
- **Quality unobserved:** Cannot measure whether art quality changed post-leak; price declines could partly reflect quality shifts.
- **Price proxy:** Prices based on a lower-bound proxy (platform-listed minimum prices), not exact transaction prices.

---

## GenAI Expands the Market for Creative Goods Rather Than Destroying It, but Compresses Prices

- The NovelAI leak dramatically expanded the market for anime art commissions — volume more than doubled.
- Price compression was severe (-64%), but the volume expansion more than compensated, yielding net revenue growth (+56%).
- Market expansion occurred at the low end (personal commissions from new buyers), suggesting AI lowered the cost threshold for commissioning art.
- Incumbent human artists retained nearly all market share — AI entrants did not displace them.
- Results contrast with narratives of wholesale creative job destruction, at least in the short run on this platform.

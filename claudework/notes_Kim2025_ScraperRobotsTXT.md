# Web Scrapers Selectively Comply with robots.txt — Compliance Drops as Directives Become Stricter

## Citation
Kim, T., Bock, K., Luo, C., Liswood, A., Poroslay, C., & Wenger, E. (2025). "Scrapers Selectively Respect robots.txt Directives: Evidence From a Large-Scale Empirical Study." *Proceedings of the 2025 ACM Internet Measurement Conference (IMC '25)*, October 28–31, 2025, Madison, WI, USA. ACM.

---

## Identification Strategy

**Method:** Large-scale empirical measurement study with controlled experiments. The authors conduct the **first controlled study of scraper compliance with robots.txt at scale**.

**Design:** Two complementary studies:
1. **Active experiment (single high-traffic site):** Deployed 4 versions of robots.txt files with increasingly strict directives over 8 weeks (2 weeks each):
   - **Base:** Standard permissions (allow all except /404, /dev-404-page, /secure/*).
   - **Version 1:** Same access + 30-second crawl delay.
   - **Version 2:** Most bots restricted to /page-data/* only; 8 SEO bots exempted.
   - **Version 3:** Most bots denied all access; same 8 SEO bots exempted.
   Each version validated via Google's robots.txt parser.
2. **Passive observation (36 sites):** Monitored bot behavior across 36 institution-controlled websites over 40 days to analyze robots.txt check frequency and general bot behavior.

**Compliance metrics:** Novel compliance ratios computed for each directive, compared against baseline behavior using paired z-tests for difference in proportions.

**Spoofing detection:** Heuristic based on ASN concentration (>90% of traffic from one ASN; minority ASN requests flagged as potentially spoofed).

---

## Data & Sample

- **3.9 million external web requests** to 36 websites managed by a large private US university.
- **Collection period:** February 12 – March 29, 2025 (40 days), plus January 2025 baseline.
- **231,859 unique IP addresses**, 19,250 unique user agents, 8,841 unique ASNs (Table 2, Page 4).
- **Known bots:** 11,291 unique IPs, 405 unique user agents, 179 unique ASNs.
- **130 self-declared bots** analyzed; 26 bots with $\geq 5$ accesses under each directive used for detailed analysis.
- **Top 20 bots account for >40% of all web traffic** (Table 3, Page 4): YisouSpider (15.95%), Applebot (15.52%), Baiduspider (1.99%), bingbot (1.69%), meta-externalagent (1.68%).

---

## Main Findings

### RQ1: Bots Comply Most with Crawl Delay, Least with Disallow All (Table 5, Page 7)
**Weighted average compliance ratios by directive:**
| Directive | Average Compliance |
|---|---|
| Crawl delay (30s) | **0.609** |
| Endpoint access restriction | 0.310 |
| Disallow all | 0.307 |

**Key insight:** Bots are **less likely to comply with stricter robots.txt directives**. Compliance nearly halves from crawl delay to disallow-all.

### RQ2: SEO Crawlers Most Compliant, Headless Browsers Least (Table 5, Page 7)
| Bot Category | Average Compliance |
|---|---|
| **SEO Crawlers** | **0.695** |
| AI Search Crawlers | 0.631 |
| AI Assistants | 0.616 |
| AI Data Scrapers | 0.559 |
| Search Engine Crawlers | 0.447 |
| Headless Browsers | 0.155 |

### RQ3: Individual Bot Behavior (Table 6, Figure 9, Pages 9-10)
Notable individual bots:
- **Amazonbot, ClaudeBot, GPTBot:** Made notable efforts to comply across all directives (compliance 1.000 on disallow-all for all three).
- **Applebot:** Promised to respect robots.txt but showed low compliance (0.043 on disallow-all).
- **Bytespider (ByteDance):** Does not promise to respect robots.txt; compliance 0.000 on endpoint and disallow.
- **PerplexityBot:** Explicitly states it will *not* respect robots.txt, yet showed 0.933 crawl-delay compliance and 0.897 endpoint compliance.
- **BrightEdge:** Claims to respect robots.txt but showed 0.000 disallow compliance.

### Frequency of robots.txt Checks (Figure 10, Page 11)
- **AI assistants and AI search crawlers check robots.txt the least** — fewer than 40% re-checked within a 168-hour window.
- Scrapers, archivers, and intelligence gatherers consistently re-check within 12 hours.
- 9/34 bots never checked robots.txt during crawl-delay experiment; 15/47 never checked during endpoint/disallow experiments.

### User Agent Spoofing (Table 8, Page 13)
- **18 bots flagged** for potential spoofing (minority ASN traffic).
- Notable: Baiduspider (381 potentially spoofed of 15,132 accesses), Googlebot (33 of 9,103), SkypeURIPreview (26 of 831).
- Spoofed requests account for <0.1% of all traffic (Table 9, Page 16).
- Spoofed bots show **little respect for robots.txt** compared to their legitimate counterparts (Figure 11, Page 16).

---

## Limitations
- Data from 36 websites owned by a single institution (large US university) — bots may behave differently on other types of sites.
- robots.txt experiment conducted on a single website.
- 45-day snapshot; bot behavior will evolve over time.
- Spoofing detection heuristic (90% ASN threshold) is somewhat arbitrary; cannot definitively prove spoofing.
- Institution's existing anti-spoofing tools may have filtered some bots before they appeared in the dataset.

---

## Key Implications
- **robots.txt is an unreliable mechanism** for preventing unwanted scraping, particularly for strict access restrictions.
- **AI-specific bots (assistants, search crawlers) rarely check robots.txt** — frequent updates to robots.txt may not effectively prevent AI scraping.
- The **non-legally-binding nature** of robots.txt means compliance requires scraper goodwill, which is inconsistent.
- **Spoofing** allows malicious bots to circumvent robots.txt by impersonating privileged bots (e.g., Googlebot).
- Results **highlight the need for stronger, enforceable alternatives** to robots.txt — such as legally binding standards, reverse proxies, proof-of-work mechanisms, or tarpits.
- Content hosts should not rely solely on robots.txt for content protection, especially against AI crawlers.

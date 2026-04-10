# 48% of Top News Websites Blocked OpenAI Crawlers by End of 2023, with Legacy Print Outlets Leading

**Paper:** Fletcher, R. (2024). "How Many News Websites Block AI Crawlers?" Reuters Institute for the Study of Journalism, University of Oxford. Factsheet, February 2024.
**DOI:** 10.60625/risj-xm9g-ws87
**Author:** Richard Fletcher, Director of Research, Reuters Institute for the Study of Journalism

---

## 1. Identification Strategy

### This Is a Descriptive Study, Not a Causal Identification Design

This paper is a **descriptive factsheet**, not a causal inference paper. There is no econometric identification strategy, no treatment effect estimation, no regression. The method is:

- **Automated longitudinal tracking** of `robots.txt` files from the Internet Archive's Wayback Machine
- Checking for the presence of directives blocking specific AI crawlers: `GPTBot`, `ChatGPT-User` (OpenAI), and `Google-Extended` (Google AI)
- Tracked for **every available day in 2023**
- Cross-sectional comparisons by country, outlet type, and reach

The "shock" events are the launches of OpenAI's crawlers (August 7, 2023) and Google's AI crawler (September 28, 2023), which gave publishers the technical ability to opt out.

---

## 2. Data & Sample

| Element | Detail |
|---------|--------|
| **Sample frame** | 15 most widely used online news sources per country, according to the 2023 Reuters Institute Digital News Report (Newman et al. 2023) |
| **Countries** | 10: Brazil, Denmark, Germany, India, Mexico, Norway, Poland, Spain, UK, USA |
| **Total websites** | $N = 150$ (15 per country x 10 countries) |
| **Data source** | Archived `robots.txt` files from the Internet Archive's Wayback Machine |
| **Time period** | Full year 2023 (every available day) |
| **Crawlers tracked** | OpenAI: `GPTBot`, `ChatGPT-User`; Google: `Google-Extended` |
| **Blocking definition** | A site is counted as blocking if it blocks the specific crawler OR blocks all crawlers via robots.txt |

**Notes on sample construction (Page 2, footnote 1):**
- Generic options like "Local or regional newspaper online" were excluded and replaced with next-highest-reach source
- Some lists include international/non-domestic sources (e.g., BBC in the US) and aggregators (e.g., Yahoo! News, MSN)
- India list is for English-speaking population only
- December 2023 data available for all websites except the Washington Post (USA)

---

## 3. Main Findings

### 3.1 Overall Blocking Rates (Page 3)

By end of 2023, across all 10 countries:
- **48%** of top news websites blocked **OpenAI's** crawlers
- **24%** blocked **Google's** AI crawler
- **97%** of sites blocking Google AI also blocked OpenAI

### 3.2 Blocking Rates by Country (Figure 1 & 2, Pages 3-4)

**OpenAI blocking (end of 2023):**

| Country | % Blocking OpenAI |
|---------|-------------------|
| USA | **79%** |
| Denmark | 67% |
| Germany | 60% |
| India | 60% |
| Norway | 60% |
| UK | 53% |
| Brazil | 33% |
| Spain | 27% |
| Mexico | 20% |
| Poland | 20% |

**Google AI blocking (end of 2023):**

| Country | % Blocking Google AI |
|---------|----------------------|
| Germany | **60%** |
| Denmark | 40% |
| USA | 36% |
| UK | 27% |
| Brazil | 20% |
| India | 20% |
| Mexico | 13% |
| Norway | 13% |
| Poland | 7% |
| Spain | 7% |

Global North outlets more likely to block than Global South.

### 3.3 No Reversals Observed (Page 4)

During 2023, **no website unblocked** either an OpenAI or Google AI crawler once the decision to block had been made. (Dips in Mexican trendlines are due to missing Wayback Machine data, not unblocking.)

### 3.4 Blocking by Publisher Reach (Figure 3, Page 5)

Among outlets with **weekly online news reach of 20%+**: 32% blocked Google AI by end of 2023.
Among outlets with **reach under 10%**: only 22% blocked Google AI.
Differences for OpenAI blocking are smaller across reach tiers.

### 3.5 Blocking by Outlet Type (Figure 4, Page 5)

**OpenAI blocking:**
| Outlet type | % Blocking |
|-------------|------------|
| Legacy print | **57%** |
| Broadcast | 48% |
| Digital-born | 31% |

**Google AI blocking:**
| Outlet type | % Blocking |
|-------------|------------|
| Legacy print | **32%** |
| Broadcast | 19% |
| Digital-born | 17% |

Legacy print outlets (newspapers, magazines) are consistently most likely to block.

### 3.6 News vs. Websites Generally

Comparing to Originality.ai's tracker of the world's 1,000 most popular websites (~1/3 block OpenAI) and Ben Welsh's tracker of 1,156 news publishers (~50% block OpenAI), **news publishers are more likely to block than popular websites overall** (Page 3).

---

## 4. Limitations and Caveats

- **Snapshot in time:** Situation is fast-moving; deals between publishers and AI companies (e.g., Axel Springer-OpenAI) may shift dynamics (Page 6)
- **robots.txt compliance is voluntary:** Blocking is an instruction, not enforcement. AI companies could ignore it.
- **Sample is top-15 outlets per country:** Does not capture long-tail publishers
- **Missing Wayback Machine data** creates gaps (especially Mexico)
- **Causation not claimed:** The paper cannot say *why* publishers block (IP concerns? revenue fears? precautionary principle?)
- **Google blocking may be suppressed** by publishers' fear of losing search prominence, even though search and AI crawlers are separate (Page 3)

---

## 5. Key Implications

- **Training data consequences:** If ~half of top news sites block AI crawlers, future LLMs will have less news content in training data, potentially degrading AI performance on news-related queries (Page 6)
- **Retrieval consequences:** Blocking also prevents real-time information retrieval by AI systems, limiting their ability to provide current news
- **Asymmetric blocking:** Legacy print publishers (who produce much of the premium journalism) are most likely to block, meaning the most valuable content is disproportionately excluded

---

## Appendix: Sections Skipped

- **Page 6:** References (10 total). No new results.
- **Page 7:** Acknowledgements and author bio. No new results.

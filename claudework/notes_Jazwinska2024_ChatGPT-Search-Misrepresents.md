# ChatGPT Search Misattributes Publisher Content in 153 of 200 Queries

## Citation
Jazwinska, K. & Chandrasekar, A. (2024). "How ChatGPT Search (Mis)represents Publisher Content." *Columbia Journalism Review / Tow Center for Digital Journalism*, November 27, 2024.

---

## Identification Strategy

**Method:** Descriptive audit study. No causal identification. The Tow Center conducted a systematic evaluation of ChatGPT Search's ability to correctly identify the source of block quotes from news articles.

**Design:** The researchers randomly selected 20 publishers (representing a mix of those with OpenAI licensing deals, those in lawsuits against the company, and unaffiliated publishers that either allowed or blocked ChatGPT's search crawler). They selected 10 different articles from each publication and chose block quotes that, if pasted into Google or Bing, would return the source article among the top three results. They then asked ChatGPT to identify the article that was the source of each quote, evaluating whether it correctly returned the publisher, date, and URL.

---

## Data & Sample

- **$N = 200$ quotes** from **20 publishers** (10 quotes per publisher).
- **Publishers sampled across affiliation types:** Licensing Deal (Financial Times, Wired, Politico, New Yorker, TIME, New York Post, The Atlantic), Unaffiliated (MIT Tech Review, Marshall Project, BuzzFeed News, Washington Post, Rest of World, Sahan Journal, Philadelphia Inquirer, Boston Globe, Baltimore Banner), Lawsuit (New York Times, Orlando Sentinel, Mother Jones), and Axios (Unaffiliated, blocked).
- **40 of the 200 quotes** were sourced from publishers who had blocked ChatGPT's search crawler.
- **Data collection period:** Around November 2024 (at launch of ChatGPT Search).

---

## Main Findings

### Overall Accuracy (Figure, Page 3)
Of 200 queries:
- **Confidently Answered:** ~193 (ChatGPT rarely declined)
  - **Correct:** 47
  - **Partially Correct:** 57 (identified some but not all of publisher name, date, URL)
  - **Wrong:** 89
- **Unsure/Declined:** Only 7 times

**ChatGPT returned partially or entirely incorrect responses on 153 of 200 occasions** (76.5%). It only acknowledged inability to answer accurately 7 times.

### Publisher-Level Results (Table, Page 8)
**Most accurately cited publishers:**
| Publisher | Affiliation | Crawler Enabled | Wrong | Partially Correct | Correct |
|---|---|---|---|---|---|
| Financial Times | Licensing Deal | Yes | 2 | 1 | **7** |
| MIT Tech Review | Unaffiliated | Yes | 2 | 1 | **7** |
| Wired | Licensing Deal | Yes | 2 | 2 | **6** |
| Politico | Licensing Deal | Yes | 4 | 0 | **6** |

**Least accurately cited (0 correct):**
- New York Times (Lawsuit, blocked), Axios (Unaffiliated, blocked), Orlando Sentinel (Lawsuit, blocked), Philadelphia Inquirer, Boston Globe, Baltimore Banner, Mother Jones.

### Key Behavioral Patterns
1. **Copycat sources:** When blocked from accessing original content (e.g., NYT), ChatGPT cited plagiarized or syndicated versions (e.g., DMS Retail copying a NYT whale article). (Page 5-6)
2. **Syndicated attribution:** Even for publishers that *allow* crawlers (e.g., MIT Tech Review), ChatGPT cited a syndicated version on Government Technology rather than the canonical source. (Page 6)
3. **Unpredictable inconsistency:** The same query asked multiple times returned different answers — sometimes correct, sometimes wrong — due to GPT-4o's temperature setting. (Page 6-7)
4. **No publisher spared:** No publisher — regardless of licensing deals, crawler permissions, or lawsuit status — was spared inaccurate representations. (Page 7)

### Crawler Access vs. Accuracy
- Enabling crawler access did **not** guarantee a publisher's visibility or accurate citation.
- Blocking crawlers did **not** entirely prevent content from being surfaced (NYT content still appeared despite blocking + active lawsuit).

---

## Limitations
- Small sample (200 quotes, 20 publishers); more rigorous experimentation needed to understand true error frequency.
- Variability in ChatGPT outputs means results from a single query are not fully reproducible.
- Does not account for ChatGPT's evolving capabilities (the tool was newly launched).
- The study did not test typical user behavior — it used a specific quote-identification task.

---

## Key Implications
- **OpenAI makes no explicit commitment** to ensuring citation accuracy, which is a notable omission for publishers expecting faithful representation.
- The **"illusion of control"** for publishers: robots.txt and licensing deals do not reliably control how content is surfaced or attributed.
- ChatGPT Search risks **reputational damage** to publishers through misattribution (e.g., attributing an Orlando Sentinel letter to a TIME article).
- The tool's tendency to cite **syndicated or plagiarized** copies rather than originals undermines the value proposition for original journalism.
- With an estimated 15 million US users already using AI search platforms, these citation failures have significant implications for publisher trust, traffic, and revenue.

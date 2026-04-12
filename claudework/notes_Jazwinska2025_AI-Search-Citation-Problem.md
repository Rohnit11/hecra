# Eight AI Search Engines Collectively Provide Incorrect Answers to Over 60% of Citation Queries

## Citation
Jazwinska, K. & Chandrasekar, A. (2025). "AI Search Has a Citation Problem." *Columbia Journalism Review / Tow Center for Digital Journalism*, March 6, 2025.

---

## Identification Strategy

**Method:** Descriptive audit study (extension of the authors' November 2024 ChatGPT study). No causal identification. The Tow Center systematically tested **eight generative search tools** on their ability to accurately retrieve and cite news content, and to behave appropriately when they cannot access content.

**Platforms tested:** OpenAI's ChatGPT Search, Perplexity, Perplexity Pro, DeepSeek Search, Microsoft's Copilot, xAI's Grok-2 and Grok-3 (beta), and Google's Gemini.

**Design:** 20 news publishers with varying stances on AI access (licensing deals, lawsuits, blocking crawlers, permitting crawlers). 10 articles randomly selected per publisher, with excerpts manually chosen that would return the original source within the first 3 Google results. Each chatbot was asked to identify the corresponding article's headline, original publisher, publication date, and URL. Responses evaluated on 3 attributes: (1) correct article, (2) correct publisher, (3) correct URL.

---

## Data & Sample

- **1,600 queries total** (20 publishers x 10 articles x 8 chatbots).
- **200 excerpts** from **20 publishers** tested across all 8 platforms.
- **Publishers span:** licensing deals (Financial Times, Wired, Politico, TIME, New York Post, The Atlantic, New Yorker, etc.), lawsuits (NYT, Orlando Sentinel, Mother Jones), unaffiliated with various crawler permissions.
- **Response categories:** Completely Correct, Correct but Incomplete, Partially Incorrect, Completely Incorrect, No Answer Provided, Crawler Blocked.
- **Data collection period:** Tests conducted in February 2025.

---

## Main Findings

### Overall Accuracy Across Platforms (Page 5-6)
**Collectively, chatbots provided incorrect answers to more than 60% of queries.** Inaccuracy rates varied:
- **Perplexity:** 37% incorrect (best performer)
- **Grok 3:** 94% incorrect (worst performer)

### Confident Wrongness (Page 6)
- Most tools presented inaccurate answers **with alarming confidence**, rarely using qualifying phrases like "it appears," "it's possible," or "I couldn't locate the exact article."
- **ChatGPT:** Incorrectly identified 134 articles but signaled lack of confidence only 15 times out of 200 responses. Never declined to provide an answer.
- **Copilot:** The exception — declined more questions than it answered. The only chatbot not blocked by any publishers in the dataset.

### Premium Models Are Worse (Page 7)
- **Perplexity Pro** and **Grok 3** (premium/paid tiers) answered more prompts correctly than their free counterparts BUT **paradoxically demonstrated higher error rates** because they provided definitive, wrong answers rather than declining.

### Robots.txt Violations (Page 8-10)
- **5 of 8 chatbots** (ChatGPT, Perplexity, Perplexity Pro, Copilot, Gemini) have publicly named crawlers.
- **DeepSeek, Grok 2, and Grok 3** do not disclose crawler names.
- On some occasions, chatbots **incorrectly answered or declined queries from publishers that permitted access**, while **correctly answering queries about publishers whose content they shouldn't have had access to**.
- **Perplexity Pro:** Correctly identified nearly a third of the 90 excerpts from articles it should not have had access to.
- **Perplexity (free):** Correctly identified all 10 excerpts from paywalled National Geographic articles despite the publisher blocking its crawlers.

### Wrong Article / Fabricated Links (Page 13-15)
- **DeepSeek:** Misattributed the source of excerpts 115 out of 200 times — content most often credited to the wrong source.
- **More than half of responses from Gemini and Grok 3 cited fabricated or broken URLs** leading to error pages (154 of 200 for Grok 3).
- Chatbots frequently directed users to **syndicated versions** (Yahoo News, AOL) or **unofficial copies** rather than original sources.

### Licensing Deals Don't Help (Page 16-19)
- Formal licensing deals (e.g., TIME with both OpenAI and Perplexity) did **not** translate to more accurate identification or attribution.
- The *San Francisco Chronicle* permits OpenAI's crawler and has a Hearst "strategic content partnership," but ChatGPT correctly identified only 1 of 10 excerpts.

---

## Limitations
- Research design does not reflect typical user behavior (specific quote-identification task).
- Each excerpt queried only once per platform — results would likely vary if re-run.
- Study focuses on observable factors (robots.txt permissions) and did not have visibility into publishers' use of alternative crawler control mechanisms (TollBit, ScalePost, Cloudflare blocking).
- Findings represent a diversity of AI company-publisher relationships but are not intended to be extrapolated to all models or news organizations.

---

## Key Implications
- **AI search tools have a systemic citation problem** that is not unique to any single platform — it recurs across all prominent generative search tools.
- **Publishers have limited options** for controlling whether and how their content is surfaced by chatbots, and those options appear to have limited effectiveness.
- The **authoritative conversational tone** of chatbots creates an **illusion of reliability** that makes it difficult for users to distinguish accurate from inaccurate information.
- **Licensing deals and crawler permissions provide no guarantee** of accurate attribution — undermining the economic logic of publisher-AI partnerships.
- The tendency to cite syndicated/plagiarized content rather than original sources **deprives publishers of proper attribution and referral traffic**.
- These findings support calls for **stronger accountability mechanisms** beyond voluntary compliance with robots.txt.

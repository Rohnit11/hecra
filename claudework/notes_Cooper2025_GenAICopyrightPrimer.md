# GenAI Challenges Copyright Law at Both the Input and Output Stages, Creating a Conundrum for Law and Policy

## Citation
Cooper, Z., Martens, B., Peukert, C., & Stocker, V. (2025). "The Law and Economics of Generative AI and Copyright: A Primer to Core Challenges for Our Digital Future." *Review of Network Economics*, 24(3), 161--176. https://doi.org/10.1515/rne-2025-0039. Received August 15, 2025; accepted September 9, 2025; published online November 6, 2025.

---

## Identification Strategy

**Method:** Descriptive / theoretical (law-and-economics policy primer). No empirical estimation, no causal identification strategy, no econometric models. The paper is a narrative synthesis of legal developments, economic reasoning, and policy considerations surrounding GenAI and copyright. It draws on case law, regulatory texts, and existing empirical literature to frame the "AI copyright conundrum" but does not generate new quantitative evidence.

**Analytical framework:** The paper structures its analysis around two dimensions:
1. **Input side** -- legal and economic issues around scraping copyrighted data for AI model training.
2. **Output side** -- copyrightability of AI-generated or AI-assisted works, including the question of human authorship thresholds and infringing outputs.

The paper contextualizes these within the AI value chain (pretraining, post-training, inference/deployment) and across jurisdictional comparisons (primarily US, EU, and China).

---

## Data & Sample

**No original data.** This is a law-and-economics primer. The paper cites empirical findings from other studies to support its arguments, including:

- **Longpre et al. (2024a):** Audit of AI data repositories (Hugging Face, PapersWithCode) finding ~65% of datasets had missing, incorrect, or ambiguous licensing information (p. 167 / p. 7).
- **Shcherbakov et al. (2025):** In LAION-5B (the largest publicly available image dataset), fewer than 1 in 1,000 data points contain license metadata. Ten website domains account for 23% of images in LAION's 2 billion images. Images with stated license information and images where rightsholders opted out depict semantically different concepts and differ in technical quality (pp. 167, 171 / pp. 7, 11).
- **Cooper et al. (2025a):** Study of memorization in open-weight models finding significant memorization but also significant variation between models and copyrighted works (p. 166 / p. 6).

---

## Main Findings

### Legal Uncertainty Surrounds Large-Scale Scraping of Copyrighted Data for Model Training (Section 3.1, pp. 164--168 / pp. 4--8)

- **US:** AI developers rely on fair use doctrine, but it is unsettled. The USCO expressed doubts about fair use applicability when AI outputs compete with training works in existing markets (USCO 2, 2025b). Dozens of lawsuits remain pending. Two recent federal rulings: (1) Judge Alsup found Anthropic's initial downloading of books to be copyright-infringing (resulting in a $1.5 billion recovery -- described as the largest copyright recovery of all time), while finding the subsequent training use to be fair use; (2) Judge Chhabria found Meta's book training to be fair use, but stated he believed training on protected works would generally be illegal, finding fair use only because "these plaintiffs made the wrong arguments" (p. 165 / p. 5).
- **EU:** Text and data mining (TDM) exceptions under Articles 3 and 4 of the Copyright in the Digital Single Market Directive. Article 4 allows rightsholders to opt out. The AI Act confirms applicability of these articles. The Code of Practice requires compliance with robots.txt. The Hamburg ruling on LAION suggested terms-of-service opt-outs would likely be enforceable (p. 166 / p. 6).
- **Global fragmentation:** No globally accepted legal framework. Countries with less restrictive copyright regimes tend to perform better in AI innovation (citing Peukert 2025a) (p. 166 / p. 6).

### Opt-Outs and Privatization Narrow the Pipeline of Available Training Data (Section 3.1, pp. 166--168 / pp. 6--8)

- The "stock" of existing high-quality online data (Wikipedia, Common Crawl, GitHub, etc.) is vast but not infinite and has largely been mined by leading developers.
- The "flow" of new digital content is slowing or becoming privatized: paywalls, restrictive terms of service, exclusive licensing deals with major AI labs.
- If contributors fear unauthorized reuse, they may stop creating altogether (citing Peukert et al. 2024).
- Exclusive licensing deals exacerbate concentration of data access, limit downstream innovation, and create non-representative training data that may conflict with AI Act requirements (Art. 10(3)) for representative, error-free data (p. 168 / p. 8).
- Existing data stock is skewed: English-dominant, Global South underrepresented, persistent culture/gender biases (citing Guilbeault et al. 2024).

### Synthetic Data Is Not a Panacea for Training Data Scarcity (Section 3.1, p. 168 / p. 8)

- Synthetic data depends on quality of real data from which it is generated.
- Cannot produce genuine novelty or social grounding.
- Recursive training on synthetic outputs risks drift, loss of relevance, and model collapse (citing Shumailov et al. 2024).
- May entrench existing biases and errors.

### Courts Worldwide Struggle to Define When AI-Assisted Works Qualify as "Human-Authored" (Section 3.2, pp. 168--170 / pp. 8--10)

- **China (Li v Liu, 2023):** Beijing Internet Court found extensive prompting and refinement reflected enough "intellectual investment" and "personalized expression" to meet originality threshold -- first jurisdiction to grant copyright to AI-assisted output.
- **US (USCO):** Dichotomizes between AI-assisted works (copyrightable) and "purely AI-generated material, or material where there is insufficient human control over the expressive elements" (not copyrightable). USCO asserts all current-state prompting outputs are uncopyrightable (USCO 1, 2025a).
- **EU:** Single Czech ruling denied copyright to Dall-E image with reasoning "[t]he plaintiff did not personally create the work; it was created by artificial intelligence."
- **Result:** Disparate authorship thresholds worldwide; any individual work partly made with AI potentially holds divergent copyright status across national frameworks (p. 169 / p. 9).
- Copyright is separable per element in many frameworks (e.g., US), meaning within a single work, non-GenAI elements may be protected while AI-generated elements (e.g., melodies, drums) may not be (p. 169 / p. 9).

### Disclosure and Detection Cannot Reliably Enforce the AI/Non-AI Copyright Dichotomy (Section 3.2, pp. 169--170 / pp. 9--10)

- Artists would need to maintain records of every instance of GenAI use, despite this record-keeping serving only to strip them of rights -- creating perverse incentives to deny AI use ("The Old Hard Drive Debacle," Cooper 2025).
- No robust technological tool can definitively detect whether any work has incorporated GenAI, let alone determine element-by-element GenAI use with enough granularity for copyright assessment (citing 10+ sources on watermarking/detection limitations).

### GenAI Tools Can Produce Copyright-Infringing Outputs Even Without Intent (Section 3.3, pp. 170--171 / pp. 10--11)

- GenAI can create near-identical copies of protected works (citing Cooper and Grimmelmann 2025).
- Liability is complicated by jurisdiction and circumstance -- even expressly infringing works can be created where users had no intent and developers attempted safeguards.
- Overly filtered models may disallow entirely legal forms of expression (fair use, private copying), undermining utility.
- Weak similarity thresholds (e.g., US "Blurred Lines" case) mean outputs need not be close replicas to infringe.
- Mass generation may mine out the latent space between existing works, making it chaotic to maintain derivative work regimes (p. 170 / p. 10).
- Low similarity thresholds + easy generative tools incentivize "copy-mining" -- creating as much content as possible to hold as many rights as possible (citing Cooper 2025, Lemley 2024) (p. 171 / p. 11).

---

## Limitations

As noted by the authors:

1. **No original empirical evidence.** The paper is a primer/synthesis, not an empirical study. All quantitative claims are drawn from cited literature.
2. **Rapidly evolving landscape.** The authors repeatedly note that legal cases are still pending (will take "years" to resolve), technology is continuously reshaping copyright-relevant practices, and policy responses are in flux (pp. 171--172 / pp. 11--12).
3. **Jurisdictional incompleteness.** The paper focuses primarily on US, EU, and (briefly) China. Other major jurisdictions are not examined in depth.
4. **No formal model.** Unlike Yang & Zhang (2024), the paper does not construct a formal economic model to derive welfare implications -- policy recommendations are qualitative.
5. **Transparency constraints.** The authors acknowledge that AI companies maintain confidentiality over data, compute, methods, and labor, making full analysis of copyright implications difficult (p. 164 / p. 4).

---

## Key Implications for the Broader Research Agenda

1. **Stock vs. flow problem:** Research should distinguish between the existing stock of training data and the ongoing flow of new content creation. Legal uncertainty threatens both, but through different mechanisms (reuse restrictions vs. chilling effects on production).
2. **Empirical measurement needed:** The paper identifies a gap for empirical work measuring (a) how opt-outs and licensing deals affect the representativeness and quality of available training data, (b) whether and how copyright uncertainty changes creator behavior, and (c) the actual prevalence of memorized/infringing outputs across models.
3. **Collective licensing and remuneration models:** The paper flags collective licensing and output-based remuneration (a la Senftleben 2023, 2024) as potential solutions but notes feasibility is a "huge question mark" -- transaction cost burden would shift to intermediaries. Hybrid systems (royalties where authorship is attributable, collective fund for remainder) are suggested (p. 171 / p. 11).
4. **Convergence of search engines and AI:** Attempts to block AI bots while permitting search engine crawling face technological convergence between search and AI answer engines. Fully unrestricted AI summarization may undermine publisher business models, but overly restricted access keeps user search/learning costs artificially high (p. 172 / p. 12).
5. **Secondary uses (distillation, agents):** Knowledge distillation (models learning from other models' outputs) and agentic real-time data retrieval extend copyright issues beyond static training datasets across the full AI lifecycle -- these remain underexplored in legal doctrine and policy (p. 172 / p. 12).
6. **Cross-jurisdictional incoherence:** The divergent authorship thresholds (China vs. US vs. EU) create practical chaos for any work with international distribution. Research on harmonization or mutual recognition frameworks is needed.

---

## Audit Metadata

- **Paper type:** Law-and-economics primer / policy synthesis
- **Pages read:** 1--16 (all); pp. 13--16 are acknowledgments and references
- **Tables/Figures:** None
- **Empirical results:** None (all cited from other sources)
- **Key cross-references in our corpus:** Yang & Zhang (2024), Longpre et al. (2024b), Shcherbakov et al. (2025), Kim et al. (2025)

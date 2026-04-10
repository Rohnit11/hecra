# Research Audit Log

> This file tracks every paper audited using the lossless research audit process defined in `Prompt.md`. Update this file each time a new paper is processed.

---

## How to Repeat This Process

1. **Upload PDFs** to Claude Code (attach them or place in `/papers`)
2. **Run the prompt:** Tell Claude to read `Prompt.md` and process the uploaded papers
3. **Claude will:**
   - Copy PDFs to `/papers/`
   - Read each paper in 4-page chunks (split-pdf protocol)
   - Extract: Identification Strategy, Data & Sample ($N$), Main Findings (coefficients, SEs, p-values, table/page refs)
   - Write `notes_[filename].md` in `/claudework/` using "Titles as Assertions" headers
4. **Commit on `main` branch** — always specify `main` to avoid worktree branch issues
5. **Update this log** with the new entry below

### Quick command
```
@paper1.pdf @paper2.pdf Go to Prompt.md, follow the audit protocol, work only on main branch, and update claudework/AUDIT_LOG.md when done.
```

---

## Audited Papers

| # | Date | Filename | Citation | Notes File | Key Method |
|---|------|----------|----------|------------|------------|
| 1 | 2026-04-10 | `Wu2025_LLMMedicalCitations.pdf` | Wu, K. et al. (2025). "An automated framework for assessing how well LLMs cite relevant medical references." *Nature Communications*, 16, 3615. | `notes_Wu2025_LLMMedicalCitations.md` | Benchmarking / Automated evaluation (SourceCheckup) |
| 2 | 2026-04-10 | `Burtch2024_GenAIKnowledgeCommunities.pdf` | Burtch, G., Lee, D., & Chen, Z. (2024). "The consequences of generative AI for online knowledge communities." *Scientific Reports*, 14, 10413. | `notes_Burtch2024_GenAIKnowledgeCommunities.md` | Synthetic Control (SCUL) + Diff-in-Diff |
| 3 | 2026-04-10 | `Fletcher2024_NewsAIBlocking.pdf` | Fletcher, R. (2024). "How Many News Websites Block AI Crawlers?" Reuters Institute, Oxford. | `notes_Fletcher2024_NewsAIBlocking.md` | Descriptive (robots.txt tracking via Wayback Machine) |

---

## Notes on Issues Encountered

- **Wu2025 PDF was initially mislabeled** — the first upload contained a copy of the Burtch2024 paper. The corrected PDF (996.9KB, 10 pages) was re-uploaded and re-audited.
- **Always work on `main` branch** — worktree branches (e.g., `claude/admiring-noyce`) cause merge difficulties. Specify "work only on main branch" in the prompt.
- **PDF page-range reading (`pages` parameter) failed** on this machine due to missing `pdftoppm`. Papers were read as whole files instead. For papers >40 pages, consider installing poppler-utils or using the `/split-pdf` skill.

---

## Audit Checklist (per paper)

For each paper, the notes file must answer:

- [ ] **Identification Strategy:** Exact causal method (DiD, IV, RDD, etc.) or state "descriptive." Explain the shock/variation.
- [ ] **Data & Sample:** Exact data source(s), time period, unit of observation, final sample size ($N$).
- [ ] **Main Findings:** Primary coefficient estimates with standard errors / p-values / confidence intervals. Reference specific Tables and Pages.
- [ ] **Limitations:** As noted by the authors.
- [ ] **Key Implications:** For the broader research agenda.

If a section is purely bibliography or technical appendices without new results, note it and skip.

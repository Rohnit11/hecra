TASK: Build a compiled Beamer deck synthesizing two (or more) audit notes
already in /claudework, then push to main.

INPUTS
- i have uploaded a screenshot where the  name papers to work on is written and then source notes from claudework 
- Output filename: <Topic>_Deck.tex (and matching .pdf) in /claudework 

INVOKE THE SKILL
Call /compiledeck. Triage answers:
  Q1: New deck.
  Q2: Audience = external academic seminar (sparse, one idea per slide).
  Q3: Tone = professional/academic → Warm Professional palette (default).

NON-NEGOTIABLE CONTENT RULES
- Every slide title is a declarative assertion of a finding. Never a topical
  label ("Results", "Methodology"). If the title strings, read alone, do not
  tell the entire argument, redo the titles.
- One idea per slide. Split if two ideas appear.
- Evidence-led: every claim cites a specific coefficient, proposition, page
  number, or case from the source notes. No vague statements.
- MB = MC across slides — discard any slide that does not earn its place.
- Use tables and structured contrasts instead of bullet walls.
- Include a Devil's Advocate slide near the end (steelman the strongest
  objection, then respond).
- Closing slide is a single memorable takeaway on a dark background — never
  "Questions?" or "Thank you."

NARRATIVE ARC (adapt section count to material)
  1. Title page
  2. Opening provocation (a single striking number or claim, centered)
  3. Framework slide that names the problem's structure
  4–N. Evidence slides grouped by sub-question, separated by
       \transitionslide{}{} dividers between major sections
  N–2. Devil's Advocate
  N–1. Optimal-policy / synthesis slide
  N.   Closing takeaway

TYPOGRAPHY GUARDRAILS (prevent compile warnings)
- Tables in a 16:9 frame must fit ≤12.8cm total width.
- Wrapping cells: use >{\RaggedRight\arraybackslash}p{Xcm} (ragged2e —
  \RaggedRight, not \raggedright, to suppress badness-10000 underfulls).
- Add \hbadness=10000 to the preamble to silence cosmetic flushright
  underfulls at frame ends. Overfull warnings remain enforced.
- Default \arraystretch ≤ 1.25. If a slide is vbox-overfull, drop stretch
  to 1.15 and trim the longest cell, do not just add \vspace negative.

COMPILE LOOP (must complete before commit)
  pdflatex -interaction=nonstopmode -halt-on-error <Deck>.tex   # twice
  Then verify on the .log:
    grep -cE "Overfull|Underfull" <Deck>.log    →  must be 0
    grep "^!"                <Deck>.log         →  must be empty
  If non-zero: fix at the source (shrink columns, RaggedRight, trim cells,
  reduce arraystretch). Do NOT inflate \hfuzz to mask the issue.

GIT
- Add .gitignore for LaTeX aux files (*.aux *.log *.nav *.out *.snm *.toc
  *.synctex.gz *.fls *.fdb_latexmk *.bbl *.blg) if not present.
- Commit BOTH the .tex and the compiled .pdf.
- Push: git push origin <current-branch>:main
- Commit message: 1-line subject + a short body explaining the synthesis
  and the zero-warning result. Co-author trailer as usual.

DELIVERABLE CHECKLIST
[ ] /compiledeck skill invoked (not bare LaTeX)
[ ] Slide titles are assertions; reading titles alone tells the story
[ ] Every claim has a citation (Prop X, Fig Y, p. Z, or case name)
[ ] Devil's Advocate slide present
[ ] Closing takeaway slide on dark background
[ ] pdflatex compile loop returns zero overfull/underfull warnings
[ ] .tex + .pdf committed; pushed to origin/main

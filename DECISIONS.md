# Decisions Log

Append-only record of project decisions. Agents: add an entry whenever a non-trivial decision is made during a session (structural changes, venue choices, theoretical commitments, scope changes, reviewer feedback acted on). Keep entries short.

Format: `## YYYY-MM-DD` then bullet points with **bold topic** and brief rationale.

---

## 2026-03-17

- **Anonymization approach**: Created `main-anonymous.tex` as a separate file (not modifying `main.tex`). Self-citations replaced with hardcoded "(Author, 2025)" / "(Author, 2026)" text rather than anonymous bib entries. Rationale: the bib entries themselves would reveal authorship.
- **First person retained in anonymous version**: "My dog" and "I" kept throughout. The CogSci guidelines "recommend" third person for anonymization, but first person doesn't reveal identity here; self-citations were the actual risk.
- **Submission as Regular Article**: 9,744 words (limit: 12,000). No need for Extended Article status.
- **Free Format submission**: Using existing LaTeX with APA-style BibLaTeX rather than converting to Wiley NJD template. Guidelines explicitly support this.
- **Keywords chosen**: conceptual metaphor, homeostatic property cluster, cross-domain extension, categorization, canine cognition, theory-constitutive metaphor, projectibility (7 keywords, guideline: 4-8).
- **Abstract expanded to 157 words**: Added bidirectional-contribution sentence ("Metaphor, in turn, reveals a capacity HPC hasn't theorized: cross-domain extension."). Satisfies 150-word minimum.
- **AI disclosure in Methods section**: Wiley AIGC policy requires disclosure "within the Methods section" with "clear description of the content that was created." Added Methods section with subsection specifying AI generated initial prose drafts for all sections, author substantially revised.
- **Submitted 2026-03-17** via Research Exchange.


## 2026-03-30

- **Retargeted to Metaphor and Symbol.** Desk rejected from Cognitive Science (Rick Dale, Mar 24). M&S is single-blind, format-free, no word limits. Submitted Mar 30 (ID 260828053).
- **Grady/Kövecses gap noted.** Readiness check flagged missing engagement with Grady (1997) primary metaphors and Kövecses (2020) cultural variation. Potential "straw Lakoff" objection from M&S reviewers. Deferred to revisions if requested.

## 2026-04-01

- **Cuaya et al. (2022) and Castro & Wasserman (2017) noted for revision.** Dog fMRI paper (cortical speech/language discrimination) relevant to §7; pigeon abstract categorization relevant to §8 phylogeny. Filed in STATUS.md literature section.

## 2026-04-06

- **M&S portal broken.** Verification emails not arriving at any address (Humber, UofT, Gmail). Exploring alternative venues: Mind & Language, Philosophical Psychology, Philosophy of Science, Cognitive Linguistics.
- **No named CMT formulas for dog sections.** Decided against `\metaphor{A LINE IS A TRAIL}` in §7. The paper deliberately avoids attributing named conceptual metaphors to the dog; the operation is cross-domain HPC extension, not a CMT mapping.
- **POWER IS UP kept as shorthand.** L&J's actual label is HIGH STATUS IS UP (p. 16), but POWER IS UP is standard in secondary literature and M&S readers will recognise it.

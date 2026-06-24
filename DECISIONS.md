# Decisions Log

Append-only record of project decisions. Agents: add an entry whenever a non-trivial decision is made during a session (structural changes, venue choices, theoretical commitments, scope changes, reviewer feedback acted on). Keep entries short.

Format: `## YYYY-MM-DD` then bullet points with **bold topic** and brief rationale.

---

## 2026-06-24

- **Desk-rejected by *Metaphor and Symbol*** (HMET-2026-0061; AE Stephen Flusberg, Ed. Herbert Colston). Not sent for external review. Three substantive charges: (1) insufficient novelty / no engagement with extended CMT (Kövecses), deliberate metaphor theory (Steen), discourse-and-cross-linguistic metaphor, cultural variation, conventionalization; (2) underspecified core terms (mechanism, mechanism support, projectibility, functional domain, cross-domain extension) and no engagement with formal/computational concept-learning; (3) "polished but generic" LLM-associated prose (broad claims, repeated argument skeletons, fast transitions). Letter and diagnosis in `notes/metaphor-symbol-desk-rejection-2026-06-24.md`.
- **Retarget to another metaphor-studies venue** (not back to *Cognitive Science*, already spent; not phil-of-cog-sci). Implies a theory-first restructure: positioning section moves up front, the dog demotes from spine to one case study, paper retitled to lead with the theory. Brett's call, 2026-06-24.
- **Positioning strategy = orthogonal-questions, not redescription.** Kövecses answers online contextual selection across schematicity levels (synchronic, production-side); Steen answers communicative status (deliberate vs not); HPC answers diachronic stability + projectibility. None reduces to another. Scaffold (grounded, claim-by-claim, with redescription-rebuttals and divergent predictions) in `notes/positioning-scaffold-2026-06-24.md`. Concept-learning anchor: Murphy & Medin 1985 (theory-theory of conceptual coherence), with HPC as its world-side completion.
- **Sourcing gap flagged.** No Kövecses (2020 ECMT; 2005 *Metaphor in Culture*), Steen (2015, 2017), or Murphy & Medin (1985) in library or central bib. Steen grounded for now via Flusberg et al. 2018 (the AE's own paper). Primary Kövecses text needed before final page-cited prose.
- **Sourcing gap CLOSED (same day).** Brett supplied primaries: Kövecses 2017 "Levels of metaphor" (Cog. Ling. 28(2):321–347), Kövecses 2020 "An extended view of CMT" (RoCL 18(1):112–130), Murphy & Medin 1985 (Psych. Review 92(3):289–316). §3.1 and §3.4 rewritten with primary grounding; all four direct-quote page cites verified against the PDFs via pdftotext (Kövecses 2017:326 for the LTM/WM quote; Kövecses 2020art:113 and :125; Murphy & Medin:289). Key payoff: extended CMT's offline/online axis is **long-term vs working memory**, not diachronic, and Kövecses concedes the processing model is "informal and hypothetical" (p.125) — so the mechanism/stability question is genuinely HPC's, not redescription. **Bib correction:** earlier `kovecses2015` entry was wrong (had "Reconnecting Cognition and Culture / MIT"); corrected to *Where Metaphors Come From: Reconsidering the Role of Context in Metaphor*, OUP, DOI 10.1093/acprof:oso/9780190224868.001.0001. Added Steen 2008 (the canonical 3-D-model DMT paper, itself in *Metaphor and Symbol* 23(4):213–241), plus Semino 2008 and Musolff 2006 as discourse anchors. All in `references-local.bib`. Draft: `notes/section3-situating-DRAFT.tex` (rev. 2).

---

## 2026-06-24 (cont.)

- **Framing shift: projectibility-first, not HPC-first.** Brett's steer. Projectibility (Goodman 1955: what observing some features licenses predicting about the rest) is now the lead construct and the paper's organizing question; mechanism support is the *underwriter* of projectibility, not the headline. Rationale: (a) matches Brett's research programme and the standing "don't drop projectibility" discipline; (b) sharper, more precisely-cited contribution than "mechanisms" (answers AE's "underspecified constructs" jab); (c) the criterion neither Kövecses (selection-in-context) nor Steen (communicative status) theorizes at all, so it makes the novelty legible.
- **New §3 "Situating the account" integrated into main.tex** (after §2 Source-domains, before Boyd §). Four subsections: Kövecses extended CMT, Steen DMT, cultural/cross-linguistic variation, concept structure (Murphy & Medin). Includes a 2×2 (deliberateness × projectibility) table. Primary-grounded, page-verified cites. Marked with BEGIN/END comments + mirrored in `notes/section3-situating-DRAFT.tex` (rev. 3). Prose still needs Brett's voice pass (AE charge #3).
- **Title changed** (provisional): "What Dogs Know About Trails…" → "The Projectibility of Metaphor: Mechanism Support and the Reliability of Cross-Domain Inference." Dog dropped from title (demoted to case study per metaphor-venue plan). pdftitle metadata updated to match.
- **Abstract + intro roadmap reframed** projectibility-first; Goodman 1955 now cited at first mention (was previously uncited despite house-style requirement). Keywords already include projectibility.
- **Build verified:** xelatex+biber+xelatex×2 all exit 0; no undefined refs/cites; all new keys resolve; PDF 23→25 pp.
- **STILL TODO (next pass):** projectibility-first reframe of the *body* (Consequences §, Conclusion §, and the intro's dog-first opening still read HPC-first); demote/trim the dog section ~35%; de-AI prose pass over existing sections (the repeated "X adds three things" enumerations, the "Lakoff was right/wrong" cadence). These are voice-sensitive — Brett's call on how much to delegate.
- **Cross-project dependency surfaced (Brett's pointer): `papers/Kinds_as_Projectibility_Profiles`.** Brett's mature synthesis: kinds = projectibility profiles; `homeostatic` conflates four achievements that should be graded apart — **order < stabilizer < maintainer < controller**, with strict `homeostatic` = the *controller* grade only (corrective, perturbation-sensitive feedback). "Homeostatic control is a subcase, not the default." Sibling: `reynolds2026notEveryStableCluster`. Consequence for THIS paper: it uses "homeostatic" as the master stabilizer throughout, which over-claims on the mature view (e.g. ARGUMENT IS WAR is stabilized by discursive norms = stabilizer/maintainer grade, not controller-grade homeostasis; the dog TRAIL feedback loop genuinely IS controller-grade). Added cite to `reynolds2026kindsProjectibilityProfiles` at §3 first mention of projectibility (imports the profile definition). **OPEN DECISION (awaiting Brett): depth of alignment** — light (keep HPC spine, cite + calibrate + fix loose "homeostatic") vs deep (recast gradient in order/stabilizer/maintainer/controller vocabulary, demote "homeostatic," possibly drop "HPC" from the paper's identity). Keys all in central bib.

## 2026-06-24 (deep alignment + relocation)

- **Deep alignment to the support-grade framework DONE** (Brett chose "Deep"). The paper's spine shifted from "metaphor = cross-domain HPC extension" to "metaphor = cross-domain *projectibility-profile* extension." Support is now graded — **order < stabilizer < maintainer < controller**, with strict `homeostatic` reserved for the controller grade — introduced in §"Projectibility, support, and theory-constitutive metaphor" with the valley/wound/body-temperature schema and cites to `reynolds2026kindsProjectibilityProfiles` + `reynolds2026notEveryStableCluster`. Changes: abstract, intro thesis + roadmap, the reframing section + its title, the typology (literary = weakest support; everyday = stabilized by norms/practice, explicitly *not* feedback; constitutive = highest grade), the Consequences sweep (HPC→profile/account throughout), the dog section (TRAIL = the clean **controller-grade / strict-homeostatic** case, its feedback loop named as such), and the conclusion. Section titles de-HPC'd. `homeostatic`/`HPC` now appear only where legitimate: Boyd's named theory, the reflexivity point (HPC-applied-to-grammar as TCM), literal biological homeostasis, and the controller grade. Builds clean, 26 pp, no undefined refs/cites.
- **Project RELOCATED mid-session** (not by me): `papers/metaphor-hpc-extension/` → `papers/preprints/metaphor-cross-domain-extension/`. Same git repo, all work intact. The move broke two relative symlinks (now one level too shallow): `references.bib` and `literature`. **Fixed** both to `../../../` depth. Flagged to Brett: confirm the move was intentional, and check whether `main-anonymous.tex`, `submission-bundle/`, and the PsyArXiv preprint metadata need updating for the new name.

## 2026-04-19

- **Kuleshova et al. (2026, *Cognitive Science*) ingested.** "Artifacts, Analogy, and Metaphor: Toward an Interdisciplinary Framework for Studying the Evolution of Analogy." Directly adjacent to this paper's remit (phylogeny of cross-domain extension + metaphor-as-proxy for complex analogy). Propose a two-pronged method integrating comparative psychology and cognitive archaeology, with a novel archaeological diagnostic — productional diversity in tool-making (Pointe aux Oies, Olduvai DK 1) as evidence for case-based reasoning in extinct hominins. Take an anti-Rubicon / graded-continuity position that lines up structurally with our HPC framing. Likely citations: the paper itself; Brand, Mesoudi & Smaldino (2021) on analogy-as-cultural-evolution catalyst; Meneganzin & Currie (2022) on Rubicon critique; Gentner (2025) for current authoritative definition of analogy. Full notes: `literature/kuleshova_et_al_2026_evolution_of_analogy.notes.md`.

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

## 2026-06-24

- **Metaphor and Symbol desk rejection recorded.** Decision from Herbert Colston with Stephen Flusberg as associate editor; decision-letter ID HMET-2026-0061. Not sent for external review. Rationale: novelty not sufficiently established within metaphor theory; adjacent frameworks under-engaged; key terms under-specified; prose read as polished but generic/LLM-like.
- **Next submission requires a lane choice.** Either do a major metaphor-theory rewrite around extended CMT, deliberate metaphor theory, discourse/cross-linguistic metaphor, analogy, and computational concept/category work, or retarget to a philosophy/cognitive-science venue and narrow the claim away from a broad CMT update.

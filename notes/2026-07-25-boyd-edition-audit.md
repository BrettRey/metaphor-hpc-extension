# Boyd citations point at the wrong edition
<!-- SUMMARY: all 19 page-bearing boyd1979 citations use 1993 second-edition pages under a first-edition key, so they don't resolve as printed; at least two pages are also wrong within 1993 · status: needs a per-citation pass before resubmission · updated: 2026-07-25 -->

Found 2026-07-25 while checking a Boyd citation in the HPC book. This paper is the worst-affected file in the portfolio.

## What's wrong

The central bib holds two entries for the same chapter:

| key | edition | pages |
|---|---|---|
| `boyd1979` | Ortony, *Metaphor and Thought*, 1st ed., 1979 | 356--408 |
| `boyd1993metaphor` | Ortony, 2nd ed., 1993, "substantially revised" | 481--532 |

`main.tex` cites `boyd1979` **19 times with a page number, and every page falls in 481--532** (481, 482 ×2, 483, 486--487, 487--488, 488--489, 488, 515, 526 ×2, 527 ×3, 529, 530, 532, plus `\textcite` forms). None of those pages exists in the 1979 chapter, which ends at 408.

So this isn't a cosmetic pagination slip. **As printed, "(Boyd 1979, p. 527)" directs a reader into a chapter that stops at p. 408, and the pointer fails.** The `boyd1979` entry even carries a note in the central bib warning against using revised-version pagination.

## Which text was actually used

The 1993 one. Four quotations spot-checked 2026-07-25, all present in the 1993 text:

- "important for scientific explanation or for the formulation of successful inductive inferences" -- cited 527, on **527**
- "will preserve the naturalness of the kind referred to" -- cited 527, on **526**
- "no adequate literal paraphrase is known" -- cited 482, on **486** (page header "486 RICHARD BOYD")
- "inductive open-endedness" -- cited 488, on **488**

So the content is 1993 content and the quotations are genuine. Two of four page numbers are also wrong *within* 1993.

## Root cause

`literature/boyd1993-metaphor-and-theory-change-2nd-ed.pdf` **is the 1993 text** despite its filename: printed folios run 482--532. Reading pages off that file and citing `boyd1979` reproduces this error exactly. Ten files reference that filename so it wasn't renamed; the companion `.md` now carries a warning header.

## The fix, and why it isn't purely mechanical

1. Repoint all page-bearing citations from `boyd1979` to `boyd1993metaphor`. The pages are then mostly correct, since they were read from that edition.
2. **But check each page individually**: two of the four sampled were off (482 -> 486, and one 527 -> 526). A full pass over all 19 is a small job and worth doing before resubmission.
3. **Decide the year question.** Repointing changes every rendered citation from 1979 to 1993, in a paper partly about the history of Boyd's account. The argument dates to 1979; the text quoted is the 1993 revision. Standard resolutions: cite the edition used and give the original date where priority matters (`Boyd 1993 [1979]`), or cite both entries where the paper is making a chronological claim. Check any prose that dates the account, and whether the paper positions Boyd relative to contemporaries by date.
4. Bare `\citep{boyd1979}` / `\textcite{boyd1979}` with no page and no quotation may stay as references to the 1979 argument, if that's what they mean.

Precedent: the same defect in HPC book ch. 5 was fixed 2026-07-25 (wrong key *and* off-by-one page); see that repo's DECISIONS.md. The book's other `boyd1979` cites are bare and legitimately reference the 1979 argument.

## Option: cite the 1979 edition instead

Better where it works, because it puts the year right in a paper partly about the history of Boyd's account. But it can't be assumed, and for the passages this paper leans on there's specific reason for doubt.

**What's established.** The 1993 chapter is substantially revised, not a reset of the same text: it cites work through 1992, so parts of it are demonstrably post-1979.

**What's open.** The immediate neighbourhood of the key quotations (folios 525--528) cites only 1970, so those particular sentences might well be original 1979 material. Internal evidence neither confirms nor refutes it. The wider stretch around them (folios ~522--532) does contain post-1979 citations, so that region was worked on.

**Why to check these passages first.** The quotations at 526--527 sit inside a numbered list of features of natural-kind terms with property-cluster definitions and irresolvable extensional vagueness. That is HPC apparatus, and Boyd's HPC formulations are normally placed in his later work (1988 onward). If the list is an addition, quoting 1979 for those sentences isn't available at all. Five minutes with the 1979 volume settles it.

**The rule to apply per citation.** Quote whichever edition was actually verified and cite that edition, with pages matching it. A mixed paper is normal: some citations to `boyd1979`, some to `boyd1993metaphor`. Where the paper makes a chronological claim and the wording exists only in 1993, cite 1993 and date the argument to 1979 in prose.

**Fastest way to settle it.** The Internet Archive has two scans of the 1979 first edition, both controlled-lending:

- <https://archive.org/details/metaphorthought00orto>
- <https://archive.org/details/metaphorthought00orto_585>

A free account borrows for an hour, which is enough to check four phrases. Tried and failed from here: IA advanced search, Open Library, and three search-inside endpoint forms (404, 404, 403), so this needs a browser.

Library fallback: title search `"Metaphor and thought" Ortony`, restricted to **1979** and the **first edition** (catalogues list both; 2nd ed. is 1993). Chapter locator: Boyd, "Metaphor and Theory Change: What Is 'Metaphor' a Metaphor For?", pp. 356--408. No DOI for the 1st edition; the 2nd-edition chapter is 10.1017/CBO9781139173865.023.

**Phrases to check, with their 1993 locations:**

| phrase | 1993 page |
|---|---|
| no adequate literal paraphrase is known | 486 |
| inductive open-endedness | 488 |
| not resolvable even given all the relevant facts and all the true theories | 526 |
| will preserve the naturalness of the kind referred to | 526 |
| important for scientific explanation or for the formulation of successful inductive inferences | 527 |

## RESOLVED 2026-07-25: Boyd says what's new, so the split is determinate

The chapter's acknowledgements note answers the whole question:

> The present essay is a revision of the original version which appeared in the 1979 edition of this collection. **Apart from minor revisions, the only new material is the material on homeostatic property cluster definitions** described in the Introduction and developed in the sections entitled "Metaphors, property homeostasis, and deference to nature" and "Homeostasis, reference, and precision." This material is also developed in Boyd (1988, 1989, 1991).

Section boundaries in the 1993 text:

| section | folios |
|---|---|
| Introduction | 481-- |
| (pre-HPC body, 1979 material) | 482--523 |
| Metaphors, property homeostasis, and deference to nature | 524--528 |
| Homeostasis, reference, and precision | 529--532 |

So folios **524--532 are 1993-only**, and **482--523 is the 1979 text with minor revisions**.

### Classification of this paper's citations

Corrected count: **20** page-bearing citations to `boyd1979` (an earlier entry in this note said 19), plus 3 bare ones.

- **8 fall in 1979 material** (482 ×2, 483, 486--487, 487--488, 488--489, 488, 515). These *can* move to `boyd1979`. Two things still needed: convert each page to the 1979 pagination (the chapter runs 356--408 there), and confirm the wording, since "minor revisions" may have touched it. This is the only remaining use for the 1979 volume, and it's now a bounded job over one page range.
- **11 fall in the 1993-only HPC sections** (526 ×2, 527 ×3, 529, 530, 532, and `\textcite` at 526--527, 527, 532). These **cannot** be cited to 1979: the material does not exist there. They must be `boyd1993metaphor`.
- **1 at 481** (Introduction) needs an individual look, since the HPC material is "described in the Introduction" while the rest of the Introduction is 1979 text.

### The priority point is recoverable another way

Boyd says the HPC material "is also developed in Boyd (1988, 1989, 1991)". So the earliest citable source for the property-cluster apparatus is **1988, not 1993**. Where this paper wants to date Boyd's cluster account, it should cite the 1988/1989/1991 work rather than reaching back to a 1979 chapter that doesn't contain it. `literature/boyd_1988_how_to_be_a_moral_realist_author_reprint.pdf` is already on disk.

That resolves the year tension without any misattribution: 1979 for the metaphor/epistemic-access argument, 1988 onward for the cluster apparatus, 1993 for wording that appears only in the revised chapter.

## DONE 2026-07-25: verified against both editions and repointed

Brett supplied the 1979 first edition (Anna's Archive, ISBN 9780521227278, good text layer). Now filed as `literature/ortony1979-metaphor-and-thought-1st-ed.pdf` with a `.md` beside it. Boyd's chapter sits at pdf pp. 368--420, i.e. folio = pdf page − 12.

Every citation was checked against both editions by locating its quoted string and reading the folio off the running head. Result: **8 citations moved to `boyd1979` with first-edition pages, 15 to `boyd1993metaphor`.** Both `main.tex` and `main-anonymous.tex` updated identically; `submission-bundle/main-anonymous.tex` deliberately left alone as a record of what was actually sent.

### Moved to the 1979 first edition (wording verbatim there)

| was | now | verified by |
|---|---|---|
| `[481]` | `[356--357]` | catachresis discussion (no quotation) |
| `[482]` | `[360]` | "an irreplaceable part of the linguistic machinery of a scientific theory", "no adequate literal paraphrase is known" |
| `[483]` | `[358]` | "introducing terminology, and modifying usage of existing terminology... causally and explanatorily significant features of the world" |
| `[487--488]` | `[361]` | "conceits", "not through one literary work, but through the work of a generation or more of scientists", "the property of the entire scientific community" |
| `[488]` | `[363--364]` | "inductive open-endedness", "invitations to future research" |
| `[515]` | `[396]` | jade / nephrite example (no quotation; note Boyd spells it "jadite" in both editions, the paper's "jadeite" is its own prose and correct) |

Plus the two bare `\textcite{boyd1979}` calls, which attribute the theory-constitutive-metaphor account and are right as they stand.

### Kept at the 1993 revision

The 11 HPC citations (folios 524--532), which cannot go to 1979 because the material isn't there, plus three whose wording doesn't match the 1979 text, plus the bare `\posscite` that attributed **HPC theory** to 1979 (a substantive misattribution: HPC is the added material). Two page numbers corrected in passing: "important for scientific explanation or for the formulation of successful inductive inferences" is on **526**, not 527 (two sites).

### Still open: four quotations that match neither edition

These need an authorial decision, so they were left alone. Each is inside `\enquote{}`, so each reads as a quotation.

1. **`\enquote{distinctive capacities and merits}`** (p. 482). Both editions read "distinctive capacities and **achievements**". Also this is **Black's** wording quoted by Boyd (Boyd gives "(p. 37)"), so it should be attributed to Black as quoted in Boyd, not to Boyd's own page.
2. **`\enquote{...the employment of terms in such metaphors may best be understood as contributing to features of the world...}`** (p. 489). Both editions read "the **metaphorical terms** in such metaphors may best be understood as **referring to** features of the world". "Referring to" and "contributing to" are different claims, and the paper's surrounding argument may lean on the version it printed, so restoring the source wording could change what the paragraph asserts. Worth a careful look.
3. **`\enquote{indexing,}` and `\enquote{storage,}`** (p. 486). The 1993 list reads "certain information is \enquote{encoded} or \enquote{indexed} in \enquote{memory store} by \enquote{labeling}, whereas other information is \enquote{stored} in \enquote{images}". So "indexing," and "storage," are paraphrases wearing quotation marks. "information processing," "computer," and "retrieval" are fine.
4. **`\enquote{favour the presence of some of the properties given the presence of the others}`** (p. 526). Source reads "**favor** the presence of the others". Two departures: anglicized spelling, and inserted material. Compare how `english-interjections` handles this legitimately, preserving Coulmas's British spelling inside the quotation with a `%` comment recording why.

### State

`main.tex` builds clean (27 pages, no citation warnings). Every remaining page number verifies against the edition named. The only outstanding items are the four quotations above.

## COMPLETE 2026-07-25: the four quotations fixed as well

No outstanding Boyd citation or quotation problems remain. Every quotation now verifies verbatim against the edition and page it cites.

| # | was | now | source |
|---|---|---|---|
| 1 | \enquote{distinctive capacities and merits} | metaphorical statement \enquote{has its own distinctive capacities and achievements}, attributed to Black as quoted by Boyd | both editions; Boyd is quoting Black at his "(p. 37)" |
| 2 | \enquote{the employment of terms\dots contributing to features of the world} | \enquote{the metaphorical terms\dots referring to features of the world} | both editions |
| 3 | \enquote{storage,} \enquote{indexing,} | information \enquote{encoded} or \enquote{indexed} in \enquote{memory store} by \enquote{labeling} | Boyd's numbered list, item 4 |
| 4 | \enquote{favour the presence of some of the properties given the presence of the others} | \enquote{there are underlying mechanisms or processes which tend to maintain the presence of the properties} | Boyd's clause 2, second disjunct |

Notes on the choices.

**(1)** The full quoted clause is now used rather than a fragment, and the attribution names Black, since Boyd is quoting him. No `black1962` entry was added: the paper hasn't consulted Black directly, so "as quoted by" is the honest form.

**(2)** Restoring the source wording strengthens the paragraph rather than weakening it. The point being supported is inductive open-endedness, and "referring to features of the world delineated in terms of those, perhaps as yet undiscovered, similarities" is a reference-fixing claim that fits that argument better than "contributing to" did.

**(3)** Boyd's list has no "storage" or "retrieval" item; those came from a different passage. The sentence now tracks item 4 of the list on the cited page.

**(4)** Boyd's clause 2 is a disjunction: either properties favour each other's presence, or underlying mechanisms maintain them, or both. The paper's argument at that point is about corrective feedback under perturbation, so the second disjunct is the one it needs, and that is now what it quotes. The British "favour" that triggered the mismatch survives only in the paper's own parenthetical gloss at the definition of homeostasis, which is paraphrase outside quotation marks and correct as it stands.

### Verification

Every `\citep`/`\textcite` to `boyd1979` or `boyd1993metaphor` carrying a quotation was checked programmatically against the correct scan, matching normalised text and reading folios off running heads: **11 verified, 0 failures.** (A twelfth reported a miss; it is the catachresis citation, which carries no quotation of its own, and the checker had picked up the preceding sentence's.) Build is clean at 27 pages with no citation warnings, and the 11 overfull boxes are pre-existing, identical before and after.

### Two things deliberately left

1. **`main-anonymous.tex` has diverged from `main.tex` by 186 lines** (347 vs 297 lines). Its Boyd citations and quotations are now fixed to match, but it is an older draft maintained by hand, and hand-syncing two versions of a paper is how quotation drift starts. It should be regenerated from `main.tex` at retarget rather than kept in parallel.
2. **`submission-bundle/main-anonymous.tex` untouched**, deliberately: it records what was actually sent to Metaphor and Symbol and should not be rewritten.

Unrelated, spotted in passing: the sentence at `main.tex` line ~127 uses "central to the present argument", which the house style rule against "the present" self-reference forbids. Not fixed, since it is outside this audit.

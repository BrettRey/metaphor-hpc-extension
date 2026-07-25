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

`literature/boyd1979-metaphor-and-theory-change.pdf` **is the 1993 text** despite its filename: printed folios run 482--532. Reading pages off that file and citing `boyd1979` reproduces this error exactly. Ten files reference that filename so it wasn't renamed; the companion `.md` now carries a warning header.

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

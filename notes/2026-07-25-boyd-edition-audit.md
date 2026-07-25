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

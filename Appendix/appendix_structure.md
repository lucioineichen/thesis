# Appendix structure

**Scope (fixed):** the appendix contains **only** the proof of the Komlós lemma. Everything else standard (Doob–Dynkin, regular conditional distributions, martingale-transform theorem, Hornik) is cited, not proved.

## A.1 The Komlós lemma

- Statement as used in §3.5: forward convex combinations of a sequence of nonnegative random variables converge a.s. to a $[0,\infty]$-valued limit; the limit is finite a.s.\ whenever the convex hull is $L^0$-bounded (Delbaen–Schachermayer, Lemma A1.1).
- Full proof, self-contained, in `appendix_v1.tex`.
- The statement in Chapter 3 (§3.5) cites this appendix; the proof lives here so Chapter 3 stays focused on the attainment argument.

## Artifacts in this folder

- `appendix_structure.md` — this file.
- `appendix_v1.tex` — standalone LaTeX (statement + proof); merge into the thesis in the very last step.
- `bib.md` — sources needed for this part (Delbaen–Schachermayer 1994).

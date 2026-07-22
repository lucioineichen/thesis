# Bibliography management

## Rules

1. **Every chapter/part folder keeps a `bib.md`** listing all sources needed for that part.
2. **For every work cited anywhere in the thesis, a PDF must be found and stored in this folder.** Naming convention: `author_year_shorttitle.pdf` (e.g. `buehler_2019_deep_hedging.pdf`).
3. The final thesis bibliography is assembled at the very end by merging the per-folder `bib.md` lists (deduplicated). The Chapter 4 drafts carry their own `thebibliography` environments — these get stripped and merged here.
4. Citation convention in the text: cite Bühler et al.'s results as "Bühler et al., Proposition 4.3" etc. (never by bare number), so their numbering never collides with the thesis's own.

## Master list (current state)

| Reference | Used for | PDF in this folder |
|---|---|---|
| Bühler, Gonon, Teichmann, Wood (2019), *Deep hedging*, Quantitative Finance 19(8) | framework (all chapters); §5 backtesting cited in §4.4 | to find (see `Sources/`) |
| Föllmer, Schied, *Stochastic Finance* (2nd revised and extended ed., 2004) | convex risk measures (Defs.\ 4.1, 4.4); martingale-transform / local supermartingale (Prop.\ 9.6); complete markets (Ch.\ 5) | to find (see `Sources/descrete_time_finance_math.pdf`) |
| Delbaen, Schachermayer (1994), *A general version of the fundamental theorem of asset pricing* | Komlós lemma (§3.5, Appendix) | to find (see `Sources/`) |
| Hornik (1991), *Approximation capabilities of multilayer feedforward networks* | universal approximation (§4.1) | to find (see `Sources/`) |
| Ben-Tal, Teboulle (2007), *An old-new concept of convex risk measures: the optimized certainty equivalent* | OCE (§2.6) | to find (see `Sources/`) |
| Markowitz (1952), *Portfolio Selection*, Journal of Finance 7(1) | variance as classical risk criterion (§2.4) | see `Sources/markowitz_source.md` |

Add new rows as sources appear in the per-folder `bib.md` files.

# Chapter 5 structure

**Title (working):** Conclusion

**Status:** to be written. Short chapter: summary of the thesis, then a brief outlook only.

**Scope decisions (fixed).**
- Summary and conclusion only — no new theorems.
- Outlook is short (one section, roughly ½–1 page): two directions only (see §5.2).
- Do not reopen Chapter~3/4 proofs; point back to the main results (attainment; Thm~4.8 / Cor~4.10).

---

## 5.1 Summary

Recap the arc of the thesis in a few paragraphs (not a full restatement of every lemma):

- **Setting (Chapters~1–2).** Deep hedging in discrete time with frictions, on a *general* probability space; convex risk measures / OCEs as the optimality criterion; the terminal P&L as the central object.
- **Attainment (Chapter~3).** On finite $\Omega$ the hedging infimum is attained by elementary arguments; on general $\Omega$ one needs (A1)–(A6). Under these hypotheses an optimal hedge exists (Komlós + Fatou-type continuity of $\rho$).
- **Approximation (Chapter~4).** Bühler et al.\ prove $\pi_M\to\pi$ on finite $\Omega$ (Prop.~4.3). Finiteness enters at (F1)–(F3); gains/costs passages do not need $|\Omega|<\infty$. On general $\Omega$ the result fails without extra structure (Prop.~4.7). Under (A1) and (A6) alone one restores $\pi_M\to\pi$ for OCEs (Thm~4.8). Combined with Chapter~3: under (A1)–(A6), neural-network strategies are $\varepsilon$-optimal for an *attained* optimum (Cor~4.10). Strategies themselves need not converge.
- **Algorithmic link.** The OCE structure yields a finite-dimensional training problem; Bühler et al.\ §5 report that the method works in backtests, with the caveat that networks are trained on historic data and past performance is not indicative of future results.
- **One-sentence takeaway.** Passing from finite to general $\Omega$ does not break the deep-hedging framework, but replaces automatic arguments by identifiable analytic hypotheses — attainment on the one hand, neural-network value approximation on the other.

---

## 5.2 Outlook (short)

Keep this section brief. Only the following two directions; no long research agenda.

1. **General convex risk measures.** The thesis stays with OCEs. Extending the approximation theory (and the continuity arguments behind (F3) / Lemma~4.4) to general convex risk measures via robust representation, as indicated in Bühler et al.\ §4.5, remains open — especially on general $\Omega$, where the same limit passages reappear in sharper form.
2. **Empirical validity of the assumptions.** Hypotheses such as (A1)–(A6) (bounded liabilities, gain-side admissibility, Fatou-type continuity, closedness of the gain cone, etc.) are mathematically sufficient. Whether they hold, approximately or after natural modelling constraints, in real markets is an empirical question left for future work: observe or test these structural assumptions on market data rather than take them as purely theoretical standing conditions.

Optional one-line pointers (only if space/need; not separate subsections): unbounded liabilities (European call, §3.7); model risk of the scenario generator used for training.

---

## End of Chapter 5

No further sections.

---

## Writing checklist

- [ ] §5.1 covers Chapters~1–4 at summary level; punchline Cor~4.10 appears
- [ ] §5.2 is short and limited to: general risk measures; empirical check of assumptions
- [ ] No new mathematics; no numerics
- [ ] Follow `styling.md`

# Chapter 4 structure

**Title (working):** Approximating hedging strategies by neural networks

**Status:** to be written from the drafts `extension_of_approximation_on_general.tex` (finite Ω, what breaks, counterexample) and `extension_with_A1_to_A6.tex` (repair under (A1),(A6)).

**Central question.** Bühler et al.\ prove on a finite probability space that neural-network strategies approximate the optimal hedge ($\pi_M\to\pi$). Does this survive on a general $\Omega$, and under which of the Chapter~3 hypotheses?

**Scope decisions (fixed).**
- OCE risk measures only
- Repair via (A1) and (A6); no sharpness counterexample for dropping (A1).
- No numerical experiments.
- Strategy non-convergence section: one example + one remark only (no entropic uniqueness / identification theory).

Provisional numbering below follows the artifact labels (Lemma~4.1 monotone, Prop.~4.3 finite, Lemma~4.4 usc, Lemma~4.6 truncation, Prop.~4.7 counterexample, Thm~4.8, Cor~4.10); these mirror the drafts for ctrl+F and do **not** reflect the final order below. Renumber cleanly when assembling; keep Cor~4.10 as the thesis punchline.

**Section order (fixed):** setup + monotone sandwich lemma $\to$ finite-$\Omega$ proposition (+ what breaks) $\to$ counterexample $\to$ repair tools (usc + truncation) + repaired theorem + corollary (thesis in one line) $\to$ algorithm $\to$ strategy non-convergence.

Reason: the finite-case proof already uses the monotone sandwich lemma, so that lemma must precede Prop.~4.3; the usc and truncation lemmas answer (F3) and (F1), so they belong after the diagnosis, inside the repair section.

---

## Chapter introduction

- Recall $\pi$ from Chapter~3 and the deep-hedging idea: replace the infinite-dimensional strategy class by neural networks.
- State the chapter plan: setup and the monotone sandwich $\to$ finite-$\Omega$ result of Bühler et al.\ and where finiteness is used $\to$ what fails on general $\Omega$ $\to$ repair under (A1),(A6) $\to$ algorithm $\to$ strategies need not converge.
- Scope: OCE only

---

## 4.1 Neural networks, market setup and $\pi_M$

- Feed-forward networks; families $\mathcal{NN}_{M,d_0,d_1}$; exhaustion / zero network / zero-weight embedding as in Bühler et al.
- Hornik: density in $L^p(\mu)$ for every finite measure $\mu$. Remark: Hornik is already a general-measure theorem; finiteness of $\Omega$ is used elsewhere.
- Semi-recurrent parametrization $\delta_k=F_{\theta_k}(I_0,\dots,I_k,\delta_{k-1})$; unconstrained rewriting via $H\circ\delta$ (Bühler et al., Lemma~4.2).
- Approximate problem $\pi_M(X):=\inf\{\rho(X+W(H\circ\delta)):\delta\in\mathcal{H}_M\}$.
- Standing market structure as in Bühler / Chapter~2, on general $(\Omega,\mathcal{F},\mathbb{P})$.

### Lemma 4.1 — monotone sandwich for $\pi_M$

- $\pi_M(X)\downarrow$ and $\pi_M(X)\ge\pi(X)$; hence $\pi_M\to\pi$ iff for every $\varepsilon>0$ some network class gets within $\varepsilon$ of $\pi$.
- Needs no finiteness and no (A1)/(A6); natural companion of the definition of $\pi_M$; **used already in the proof of Prop.~4.3**.

---

## 4.2 The finite-$\Omega$ approximation theorem and what breaks

### Proposition 4.3 (Bühler et al.)

- Statement and full proof: $\pi_M(X)\downarrow\pi(X)$ on finite $\Omega$. The proof opens by invoking the monotone sandwich (Lemma~4.1).
- After the proof (or interleaved carefully), a **visible** discussion of where finiteness enters — not buried only in the proof. Three failure points only:
  - **(F1)** boundedness of $\delta_k$ (hence integrability of the Doob–Dynkin maps $f_k$) is automatic on finite $\Omega$;
  - **(F2)** $L^1$-convergence upgrades to convergence at every $\omega$ (atoms of positive mass);
  - **(F3)** $\rho$ is a convex function on $\mathbb{R}^N$, hence continuous — the passage to the limit in the objective is free.
- Explicitly **not** an F: once $\delta^m\to\delta$ suitably, continuity of the maps $H_k$ and of the stochastic integral give $(H\circ\delta^m)\cdot S\to(H\circ\delta)\cdot S$, and upper semicontinuity of the $c_k$ give $\limsup_m C_T(H\circ\delta^m)\le C_T(H\circ\delta)$. This step needs no finiteness of $\Omega$.

### What breaks on general $\Omega$ (own subsection; essential)

- Point-by-point, matching the three F's only:
  - **(F1)** strategies need not be bounded, so integrability of $f_k$ must be assumed or restored (truncation);
  - **(F2)** $L^1$-convergence only gives a.s.\ convergence along a subsequence (harmless on general $\Omega$);
  - **(F3)** a convex risk measure on an infinite-dimensional space need not be continuous along the relevant a.s.\ convergent sequences — this is where the limit cannot be pulled inside $\rho$.
- Do not invent an (F4) for costs/constraints: those passages are already justified without finiteness (see above).
- Connect (F3) to Chapter~3: Fatou-type continuity, counterexample ideas for $\rho=-\mathbb{E}[\cdot]$.

### Proposition 4.7 (failure without extra assumptions)

- The companion-draft counterexample: on a general $\Omega$, the finite-space argument does not go through; exhibit a concrete market where $\pi_M\not\to\pi$ (or $\pi_M\equiv+\infty$ while $\pi$ is finite) when the needed envelope / integrability fails.
- Role: motivate the repair; do **not** follow with an A1-only sharpness construction.

---

## 4.3 Repair under the Chapter~3 hypotheses

Lead-in $\to$ two repair lemmas $\to$ theorem $\to$ punchline corollary.

### Lead-in

- Prop.~4.3 fails on general $\Omega$ (Prop.~4.7); the genuine gaps are (F1) and (F3) ((F2) is harmless).
- Chapter~3 already supplies (A1) and (A6): bounded liability gives a constant envelope, nonnegative gains survive truncation. Use these to restore $\pi_M\to\pi$ for OCEs.
- (A2)–(A5) are not needed for value convergence; they return only for attainment and Corollary~4.10.
- Announce the plan: the next two lemmas repair (F3) and (F1); Theorem~4.8 combines them with Lemma~4.1; Corollary~4.10 brings in Chapter~3 attainment.

### Lemma 4.4 — constant-envelope upper semicontinuity of OCEs

- If $Y_m\ge -B$ a.s.\ and $\liminf Y_m\ge Y$ a.s., then $\limsup\rho_\ell(Y_m)\le\rho_\ell(Y)$.
- Remark: this is upper semicontinuity; (A3) is lower semicontinuity — different directions. Repairs (F3).

### Lemma 4.6 — truncation / value-density of bounded strategies

- Under (A1) and (A6): for every $\delta\in\mathcal{H}^{\mathrm{u}}$ and $\varepsilon>0$ there is a bounded $\delta'$ with objective within $\varepsilon$.
- Connect explicitly to Chapter~3: (A1) gives the constant envelope $\|Z\|_\infty$; (A6) keeps truncated gains nonnegative so the envelope survives truncation. Repairs (F1).

### Theorem 4.8

- Under the standing Bühler market/network setting, $\rho=\rho_\ell$ an OCE, and hypotheses **(A1) and (A6)** only:
  \[
  \lim_{M\to\infty}\pi_M(-Z)=\pi(-Z)
  \]
  (monotone from above, in $[-\infty,\infty]$).
- Proof outline: near-optimal target $\to$ truncate (Lemma~4.6) $\to$ Hornik in $L^1$ $\to$ a.s.\ subsequence $\to$ continuity of $H_k$, usc of costs $\to$ Lemma~4.4; Lemma~4.1 reduces the claim to $\varepsilon$-approximation.
- Short remark: (A2)–(A5) unused for value convergence; optional pointer to (A1$'$) as a possible weakening (no counterexample required).

### Corollary 4.10 — the thesis in one line

- Assume in addition (A2)–(A5), so Chapter~3 gives attainment. Then there exists an optimal $\delta^*\in\mathcal{H}$, and for every $\varepsilon>0$ there exist $M$ and a network strategy $\delta^\varepsilon\in\mathcal{H}_M$ with
  \[
  \rho\bigl(-Z+W(H\circ\delta^\varepsilon)\bigr)
  \le
  \rho\bigl(-Z+W(\delta^*)\bigr)+\varepsilon.
  \]
- **Punchline sentence (use in the statement or immediately after):** under (A1)–(A6), neural-network strategies are $\varepsilon$-optimal for an *attained* optimum.

---

## 4.4 From theory to algorithm (brief; ~1 page)

- OCE objective $w+\mathbb{E}[\ell(-Y-w)]$ with $Y=-Z+W(H\circ\delta^\theta)$ makes the problem a finite-dimensional minimization over $(w,\theta)$.
- Joint minimization; minibatch estimation of the expectation; backpropagation through the semi-recurrent network.
- Entropic case: $w^*$ explicit, so one minimizes only over $\theta$.
- No numerics of our own: this thesis does not re-run experiments.
- **Cite Bühler et al., Section~5 (backtesting):** report their main empirical finding that the trained hedges work in out-of-sample / backtest evaluation (risk reduction vs.\ unhedged / classical benchmarks as they present it). Keep this to a short citation of their results, not a reproduction.
- **Important caveat (state explicitly):** the networks are trained exclusively on historic (or historically calibrated simulated) data; past backtest performance is not indicative of future results. This is a structural limitation of the method, not a footnote afterthought.
- Optional one-sentence outlook only: general convex risk measures via robust representation (Bühler et al., §4.5) lead to a minimax over two networks — not pursued.

---

## 4.5 Strategies need not converge (short)

- **One example:** e.g.\ constant $S$ (or two identical assets), zero costs — every strategy is optimal / gains coincide, so network near-minimizers need not converge.
- **One remark:** Theorem~4.8 and Corollary~4.10 are about *values* and $\varepsilon$-optimality, not about $\delta^M\to\delta^*$ in any topology; without strict convexity of $\ell$ and non-redundancy of $S$, strategy convergence is not to be expected.
- Do **not** include: Komlós recovery proposition, entropic P&L uniqueness, conditional non-degeneracy, identification lemmas.

---

## End of Chapter 4

No further sections. Chapter~5 (conclusion) picks up: summary of attainment + approximation, open problems (unbounded liabilities, general CRM, model risk).

---

## Writing checklist

- [ ] §4.1 ends with Lemma~4.1 (monotone sandwich), ready for Prop.~4.3
- [ ] Prop.~4.3 proved in full (invoking Lemma~4.1); finiteness discussion visible as its own block (F1)–(F3) only; gains/costs not an F
- [ ] Prop.~4.7 (counterexample / failure) present; **no** A1-sharpness proposition
- [ ] §4.3: lead-in $\to$ Lemma~4.4 (usc, repairs (F3)) $\to$ Lemma~4.6 (truncation, repairs (F1)) $\to$ Thm~4.8 $\to$ Cor~4.10
- [ ] Thm~4.8 under (A1),(A6); Cor~4.10 states the attained + $\varepsilon$-optimal punchline
- [ ] Algorithm subsection ~1 page: SGD sketch + cite Bühler §5 backtesting (hedges work) + historic-data / past≠future caveat; no own numerics
- [ ] Strategy subsection = one example + one remark only
- [ ] Cross-refs: (A1)–(A6) to Chapter~3; OCE to §2.6; market objects to Chapter~2
- [ ] Follow `styling.md`; number only equations that are referred to

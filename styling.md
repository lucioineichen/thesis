The instructions below and in the attachment should help you in writing a well-written and nicely formatted text. They are not complete, but hopefully cover a substantial number of points.

*************************************

General formatting:

0) Each new paragraph should be indented, except for the first paragraph in each chapter/section/subsection. No extra vertical space between successive paragraphs should be added.

1) Numbering: Please number your results/remarks/definitions/assumptions as well as your equations consecutively within each section. This means that in Section n, Definition n.1 will be followed by Lemma n.2, Theorem n.3 etc.

2) Numbering again: For your displayed equations, please number only those that you actually refer to in your paper. This avoids unnecessary equation numbers. Using \refcheck can help you identify unused equation numbers and labels.

3) When referring to an equation by number, please use \eqref{number} and not (\ref{number}). Using \eqref will automatically create the required brackets ().

4) Footnotes: Please avoid footnotes as far as possible; in particular, do not put into a footnote material that is meant as a remark or an explanation. Integrate all potential footnote material into the body of the paper.

5) Spelling: Many mistakes can easily be eliminated by using a spellchecker.

6) Capitals: Please use capitals very sparingly -- essentially only for personal names and for theorems, remarks etc. when these are followed by an identifying number.

Formulas:

7) Formulas in displays: Please make sure that your displayed formulas do not exceed the margins.
Note: Do NOT mess around with font sizes for this!

8) Formulas in text: Please make sure that formulas in text passages are not broken across lines. In some cases, this can be achieved by slightly rewording your sentences. In other cases, you may need to use a display for the equation.
Note: Do NOT use \linebreak or similar commands.

9) Multiline formulas: The best choice for alignments is to use \begin{align} ... \end{align}. Please make then also sensible alignments.
Note: Do NOT use \begin{array} ... \end{array} for multiline formulas.

10) There are many different ways to add extra space in formulas. One can use \; or \ or \> etc. NONE of them is needed, and you should remove ALL of them.
The only exception is the use of the small extra space \, in front of differentials d. If you decide to use that, please do it consistently everywhere.

11) For the set of all x having property A, please write {x : x has property A} with a colon :, not with a vertical dash | . This makes much better reading if the formula involves for instance absolute values.

12) If you have a formula with several cases, please use \begin{cases} ... \end{cases} and not a DIY construction like \left\{ ... \right.

Citing and references:

13) Citing: Please do not cite by numbers only. Giving credit to persons for their work usually involves citing by name(s) and number from the list of references. In some cases, e.g. when you merely cite a technical result or when you cite some work multiple times, it can make sense to use numbers only, perhaps after a certain point. Use reasonable judgement for such cases.

14) Citing textbooks: As a rule, citing an entire textbook is not useful for readers. Please give more precise references in such cases, e.g. to a chapter or a section or a theorem, etc. But do not refer to page numbers.

15) References: Please check and provide full and accurate details for all your references. Typical questions that come up are: Page numbers? Editor of a volume or a collection of papers? Is a paper quoted as preprint already published? For unpublished work: where can it be found (on which web page?) ?

Important: bracket choice and bracket sizes

16) Bracket types: Please use square brackets [ ] for all expectations, conditional expectations and probabilities. Please use curly brackets { } for sets. For all other purposes, please use round brackets ( ). (One obvious exception is [X,Y] for the square bracket process of X and Y.)

17) Bracket sizes, part I: All formulas within text, and all fractions, must not contain brackets other than the standard size. So for all these formulas, please remove all size commands.

18) Bracket sizes, part II: Displayed equations (and only these, see above) become much better readable if they do not contain several pairs of identical bracket types which have the same size. For instance,
$$ f(g(h(t))) = x$$
produces a badly readable formula. To correct this, please start with the normal size for the innermost pair, and then increase successively by using \big, then \Big and finally \bigg.
Note that when you have conditional expectations or conditional probabilities, the size of the vertical dash | should match the corresponding brackets.

19) Bracket sizes, part III: Please remove all \left ... \right commands because these regularly produce bad bracket sizes. Note also that the maximal bracket size you should use is \bigg, and that in displayed equations, this should always be used around integrals and sums. For max, sup etc., the size \Big is appropriate.

Other additions:

20) Commas: Do NOT apply the oxford comma: When listing items, there is no comma before the and. An example of desired listing is: apples, oranges and pears.

21) No titles for results: Do not give theorems, propositions, lemmas, corollaries, definitions, remarks or assumptions an optional title in the LaTeX environment (i.e. never write `\begin{proposition}[Some title]`). Use the bare environment `\begin{proposition}` (likewise for the others). Attributions and source pointers belong in the surrounding text, not in the result header, e.g. write "B\"uhler et al., Proposition~4.3, states that ..." in the prose before or after the statement, not as `\begin{proposition}[B\"uhler et al., Proposition~4.3]`.

22) No en-dashes or em-dashes: Do not use LaTeX `--` (en-dash) or `---` (em-dash) in the text. Prefer commas, parentheses or a single hyphen `-` as appropriate. Examples: write "(F1) to (F3)" or "(F1)-(F3)", not "(F1)--(F3)"; write "(in particular, ...)" or ", in particular, ...", not "--- in particular ---"; write "convergence, harmless" or "convergence (harmless)", not "convergence --- harmless".

23) Sequences indexed by natural numbers: Always write sequences with the index ranging over \(\mathbb{N}\) (or \(\N\)) explicitly. Write \((\pi_M(X))_{M\in\N}\), \((a_n)_{n\in\N}\), \((\delta^m)_{m\in\N}\), not \((\pi_M(X))_M\), \((a_n)_n\) or \((\delta^m)_m\). The same applies to subsequences and double-indexed families when the free index runs over \(\N\).

24) Closed compounds with "non": Write prefixes of the form "non-..." as a single word, without a hyphen. Examples: nonincreasing, nondecreasing, nonconstant, nonnegative, nonredundant, nonuniqueness; not non-increasing, non-decreasing, non-constant, etc.
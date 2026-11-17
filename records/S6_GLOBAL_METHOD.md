# Global polar exclusion for sixteen disks

This directory extends the global certificate mechanism of the fifteen-disk manuscript. A **complete global exclusion forest** has now been generated. Its validity for the sharp sixteen-disk radius also depends on the separately proved exact candidate construction and analytic local lemma in `../local/`.

## Geometric reduction

Let the desired center radius be a real number \(\rho>2\). A smaller packing of sixteen unit disks would, after dilation, give sixteen centers in the closed disk of radius \(\rho\), with every pair distance strictly greater than two. Choose a strict configuration with the maximum possible number of centers on its boundary. The same direct radial-replacement argument as in the fifteen-disk paper gives

\[
r_i=\rho\quad\text{or}\quad 0\le r_i<\rho-4/\rho.
\]

This part is independent of the number sixteen. At least one center lies on the boundary. For a center-radius parameter satisfying

\[
3.61542559487\le\rho\le3.61542559488,
\]

we conservatively use the rational boundary interval \([3.61542559487,3.61542559488]\) and interior interval \([0,D]\), where

\[
D=3.61542559488-\frac4{3.61542559488}=2.509055156593\ldots.
\]

The numerical interval is a **hypothesis** of these certificates. Its application to the exact conjectured optimum requires the candidate-radius enclosure to be proved separately.

Every pair of boundary centers has minor angular separation greater than \(0.56\). This is certified by the four-corner rational chord check described below. Since \(12(0.56)>2\pi\), there can be at most eleven boundary centers. Sorting the centers by polar angle and quotienting by cyclic shifts and reversal gives precisely 2,146 words. The numbers by boundary count 1 through 11 are

| Boundary centers | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Orders | 1 | 8 | 21 | 72 | 147 | 280 | 375 | 440 | 375 | 280 | 147 |

If the classical proved optimum for nine equal disks is admitted as an input theorem, a further simplification follows. Nine centers at pair distance at least two require center radius at least \(\csc(\pi/8)=\sqrt{4+2\sqrt2}>D\). Consequently the normalized sixteen-center configuration has at most eight interior centers, hence at least eight boundary centers. This removes all words with seven or fewer boundary centers, leaving 1,242 words. The saved computational exclusions do not rely on that input theorem.

## Exact certificate leaf

For nonnegative radial intervals \(I,J\), a rational \(0<t<\pi\) is an angular lower bound if

\[
r^2+s^2-2rs\,C_-(t)\le4
\]

at each of the four rectangle corners, where \(C_-(t)\le\cos t\). Separate convexity in \(r,s\) proves the inequality throughout the rectangle. Strict pair separation then forces its minor angle to exceed \(t\). An angle numerator equal to zero is accepted as the trivial nonnegative lower bound.

The searcher uses angles with denominator \(10^6\). It bounds cosine from below by the Taylor polynomial

\[
P_{42}(t)=\sum_{k=0}^{21}\frac{(-1)^kt^{2k}}{(2k)!}\le\cos t
\quad(0\le t\le\pi),
\]

rounding every positive summand downward and every negative summand downward on scale \(10^{30}\). The tail starts with a positive term and has decreasing magnitudes: its first successive ratio is at most \(\pi^2/(45\cdot46)<1\). Thus the alternating-series remainder proves the displayed inequality. The independent verifier computes \(P_{42}\) directly as a Fraction, without importing the searcher's rounded-integer routine.

For an ordered cycle of distinct center indices \(v_0,\ldots,v_{m-1}\), let \(w\) be the number of its descending edges under polar order. Its directed angular gaps sum to \(2\pi w\). A leaf with exact angle sum

\[
\sum_k t_k>2\pi_+w,
\qquad\pi_+=3.14159265358979323847>\pi,
\]

is therefore impossible. All arithmetic in this check is rational/integer arithmetic.

## Subdivision coverage

Strict separation implies \(r_i+r_j>2\), so an upper endpoint \(U_j\) gives the conservative propagated lower bound \(r_i\ge2-U_j\). Each subdivision splits a radial interval at its exact rational midpoint and retains both closed halves. A possible radius vector is consequently never lost. Empty intervals are impossible. An order is excluded only when every leaf of its complete binary tree is exactly excluded.

`polar_search.py` uses floating point solely to propose cycles. `verify_results.py` independently reconstructs every radial box, checks all saved leaves (including both children of partial trees), and independently enumerates the canonical words using combinations. The verifier explicitly reports unresolved leaves and unprocessed orders. The two scripts also verify rational upper and lower bounds for pi using independent alternating-series enclosures in Machin's identity.

## Current verified evidence

The first depth-eight scan completely excluded 1,230 orders. Refining the 916 remaining orders to depth sixteen excluded another 802. Refining the 114 remaining orders to depth twenty-four excluded another 113. These certificates and their separate independent audits are retained.

The only word requiring local analysis is `0001001001001001`: five interior centers with intervening boundary runs of lengths three, two, two, two, two. Its interior positions 3 and 15 have the candidate radius of type A, positions 6 and 12 have type B, and position 9 has type C (indices zero-based). The exact enclosures of these candidate radii are stored in `../local/candidate_radial_intervals.json`. Their approximate values are 1.6301742123, 1.7204880215, and 1.8115554464.

The separately verified analytic lemma excludes a strict configuration in this order whenever all five interior radii lie within 1/2000 of their identified candidate radii. To certify a whole radial interval `[L,U]` for a type whose exact candidate enclosure is `[a,b]`, the local leaf requires

\[
L\ge b-1/2000,\qquad U\le a+1/2000.
\]

The direction of these conservative inequalities is important: every point of the saved interval must lie in the neighborhood of every radius permitted by the enclosure. The actual eleven boundary radii must equal the **exact candidate radius**, even though the global root box relaxes them to a small rational interval. A local leaf is not a theorem for all boundary radii in that root interval.

Refining the target word with this local predicate gives a complete tree with 28,333 nodes, 14,029 angular-cycle leaves, and 138 local leaves. `merge_forests.py` selects a complete tree for every word from the saved searches and produces `complete_forest.json`. Its totals are

| Quantity | Count |
|---|---:|
| All canonical orders | 2,146 |
| Subdivision nodes | 155,291 |
| Exact angular-cycle leaves | 157,299 |
| Analytic local leaves | 138 |
| Total nodes | 312,728 |
| Unresolved leaves or orders | 0 |

The complete-forest SHA-256 is `8fc563c4fc46875d939d6a69157082bfaa20b4e1df6a053633bae581997bc3e9`. The independent audit receipt is `complete_forest_audit.json`; it must confirm all saved leaves checked and full global exclusion. The numeric counts satisfy the forest identity 312728 = 2(155291)+2146, but coverage relies on the full traversal and enumeration, not that identity.

Every angular leaf applies to arbitrary point placements within the stated radius hypothesis. The local leaves use the separately proved exact candidate theorem. No symmetry or contact graph is assumed of the counterexample. The construction's contact graph is used only to exclude the final small radial neighborhoods.

# Global polar exclusion for seventeen unit disks

This directory contains finite radial subdivision trees for the seventeen-disk candidate. The exact candidate and its local rigidity theorem are certified separately in `../geometry` and `../local`. A complete certificate requires a complete tree for every geometrically possible circular order, plus the independent replay of every saved leaf.

## Geometric normalization

A packing in a smaller circle, after dilation, gives seventeen centers inside the exact candidate center radius rho with every pair distance strictly greater than two. Among all such strict configurations choose one having the greatest integer number of boundary centers. The radial replacement argument of the fifteen-disk paper gives, for every center,

    r = rho  or  0 <= r < rho - 4/rho.

The enclosing rational interval used here is

    3.79203374830 <= rho <= 3.79203374832.

Thus boundary radii are relaxed to that interval, and interior radii to `[0,D]`, where `D = 3.79203374832 - 4/3.79203374832 < 2.738`.

Every boundary pair has angular separation strictly greater than 0.53 radians; the exact four-corner chord test below proves this. Since `12*0.53 > 2*pi`, there are at most eleven boundary centers.

The independently verified auxiliary ten-disk exclusion at center radius 2.738 proves that at most nine centers can be interior. Its normalized configurations have at most eight boundary centers, at most three interior centers, and hence seven or eight boundary centers. Its thirteen possible orders require just thirty-five nodes and twenty-four exact angular leaves. Consequently a normalized seventeen-center configuration has between eight and eleven boundary centers.

Up to cyclic shifts and reversal there are precisely 2,492 binary circular words: 750 with eight boundary centers, 750 with nine, 600 with ten, and 392 with eleven. The search and the independent verifier enumerate these words using different code.

Polar angles may coincide. Sorting is weak, with any order among equal angles. Directed gaps and descending-index winding counts remain valid in this situation. A center at the origin may be assigned an arbitrary angle; the radial inequalities still cover it.

## Exact angular leaves

For nonnegative intervals I,J and rational `0 < t < pi`, the condition

    r^2 + s^2 - 2*r*s*C_lower(t) <= 4

at all four endpoint pairs proves the same inequality throughout the radial rectangle by separate convexity. Here `C_lower(t) <= cos(t)`. Therefore pair separation strictly greater than two forces its minor angular separation to exceed t. A saved zero angle is accepted as the trivial nonnegative bound.

The search proposes angles with a positive integer denominator stored as each leaf's `angle_scale` (one million when that field is absent), then accepts them only by exact integer/rational arithmetic. Finer denominators are permitted when refining narrow unresolved boxes; every leaf retains its own exact denominator. Its cosine lower bound is the degree-forty-two Taylor polynomial ending in a negative term, with every summand rounded downward on scale `10^30`. The alternating remainder is positive on `[0,pi]`. The independent checker instead evaluates the whole polynomial directly with `Fraction`, then rounds that exact sum downward on scale `10^40` for faster corner arithmetic. It falls back to the unrounded direct polynomial if needed. Both bounds are below cosine, and it imports no searcher routines.

For a directed cycle of distinct indices in weak polar order, the directed angular gaps sum to `2*pi*w`, where w counts descending-index edges. If the saved angle lower bounds sum to more than `2*pi_upper*w`, the entire radial box is impossible. Both codes independently certify their rational pi bounds using Machin's identity and alternating arctangent sums.

## Tree coverage

Strict pair separation implies `r_i+r_j>2`. The search propagates conservative lower bounds `r_i>=2-U_j` among interior radii. It then bisects a chosen interval at its exact rational midpoint and retains both closed children. Empty boxes are impossible. A tree covers its root only if every leaf is certified; unresolved leaves never count as excluded.

The local analytic leaves require the actual boundary radii to equal the exact candidate rho, despite the small relaxed interval used by angular leaves. They apply only to the candidate canonical word `00100100100101101` and to whole radial boxes lying inside independently proved neighborhoods.

The candidate has seven interior indices `2,5,8,11,13,14,16` (zero based). Their types are B,A,B,C, and either T,D or D,T at indices thirteen and fourteen, followed by C. Types T and D correspond to the two centers sharing the positive vertical ray in the exact candidate, so both assignments are required. The local data store both modes and the exact radial enclosures. The baseline Cartesian proof uses radius `1/10000` in `../local/candidate_radial_intervals.json`. A stronger independently audited direct polar proof permits radius `1/550` in `../geometry/radial_flow/polar_dual_radial_intervals.json`; the final forest identifies the exact profile it uses.

For candidate radial enclosure `[a,b]` and epsilon, a whole interval `[L,U]` is accepted only if `L>=b-epsilon` and `U<=a+epsilon`. Thus all radii allowed by a leaf lie within epsilon of the exact candidate radius. No candidate symmetry or contact graph is assumed of the hypothetical competitor.

## Verification artifacts

`polar_search.py` builds trees, `merge_forests.py` selects a complete tree for each of the 2,492 orders, and `verify_results.py` independently reconstructs every box and audits every exact leaf. The final forest must contain no unresolved cases. The root proof bundle provides a second replay using an independently implemented sine upper bound.

Search data are partial until a full forest and successful independent audit exist. Concrete final counts and hashes belong in the generated receipts, rather than being inferred from search progress.

## Completed exact verification

The complete forest is now saved in `complete_forest.json`. Both complete global replays passed: the independent cosine checker in `verify_results.py`, and the separately implemented sine checker called by `../verify_complete_proof.py`. The latter also freshly checked the candidate construction, normalization, auxiliary ten-disk theorem, local positive-stress theorem, and the exact binding of the local profile to the forest.

| Quantity | Verified count |
|---|---:|
| Circular orders | 2,492 |
| All nodes | 8,529,090 |
| Subdivision nodes | 4,263,299 |
| Exact angular leaves | 4,257,671 |
| Analytic local leaves | 8,120 |
| Unresolved or unprocessed orders | 0 |

The final forest uses the strongest base dual profile with radial epsilon `1/550`. Its exact SHA-256 is `25e6927ba5bf7e6d5007f7defcb246930f1553559c5f15ab2b1e32350320a89a`. The independent cosine receipt is `complete_forest_audit.json`; its verifier source SHA-256 is `bce170f410b4e0c9883eb913521a5c812999bba29579c309f4b76ec8810d311d`. The end-to-end sine receipt is `../complete_verification.json`. Both verify all 2,492 orders, and both bind their results to the unchanged forest bytes.

The cosine checker hashes precisely the bytes it parses and rejects any change in either those bytes or its own source during replay. The end-to-end checker similarly guards its source files and the forest before and after verification. These receipts substantiate the computer-assisted proof; external mathematical review remains separate.

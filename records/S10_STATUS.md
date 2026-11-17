# Packing theorems for 16, 17, 18 and 20 circles, and a manuscript

This directory contains four complete Lean optimality proofs and their
manuscript draft. Final theorem audits, rather than individual components,
record completion of the proofs.

The requested completion gates are:

- Complete exact global and local exclusion certificates for 18 and 20 circles,
  independently replayed with no unresolved circular orders or boxes.
- Exact feasible constructions for the target cardinalities.
- Separate complete Lean files for 16, 17, 18, and 20, each proving the
  least containing radius with every analytic and finite-check hypothesis
  discharged. No admitted local optimality premise, `sorry`, or external
  Python verification oracle may replace a proof.
- A professional manuscript naming Jensen Kohlmeyer, Grant Huffman,
  Will Howe, and Liam Kruer, with the supplied emails and an AI acknowledgment.
  The manuscript covers only those four cardinalities.

## Current checkpoint

The four unconditional least-radius theorems are complete:
`SixteenCirclesInACircle.isLeast`, `SeventeenCirclesInACircle.isLeast`,
`EighteenCirclesInACircle.isLeast`, and `TwentyCirclesInACircle.isLeast`.
Each has its own source file and final source/binary and axiom audit under
`lean/certificates/{sixteen,seventeen,eighteen,twenty}_full_lean_verification.json`.
The proofs use the documented native-compilation trust boundary, with no
`sorryAx`, assumed optimality theorem, or external Python-success premise.

For 20 disks, all 19,796 canonical cases pass both exact arithmetic replays
and the Lean forest checks. The 54 disjoint forest blocks contain
199,234,854 nodes, 99,607,529 splits, 99,332,302 angular leaves and 295,023
local leaves (9,558 polar and 285,465 joint-cycle applications). The separate
dummy case and indexed-family coverage theorem discharge the entire root
case predicate. The final explicit unconditional type witness compiles.
Its audit binds 249 project modules and exactly 598 finite native acceptance
receipts in addition to `propext`, `Classical.choice`, and `Quot.sound`.

The complete 20-disk center-radius enclosure is
`[4.1223207369915283214476857922008406476319,
4.1223207369915283214476857922008406476320]`.
The containing radius for unit disks is one plus this value.

The current manuscript states all four results, gives their constructions
and proof method, records the computational trust boundary, names all four
requested authors with their supplied emails, and acknowledges AI assistance.
The existing editor file remains `circle-packings-16-19.tex`.
The downloadable 11-page PDF has compiled with the existing Tectonic 0.17.0
compiler and passed visual inspection of every page. All 25 fonts are embedded,
with no overfull boxes, missing-character reports or unresolved references.
The PDF is `../../output/pdf/circle-packings-16-17-18-20.pdf`, with source and
PDF hashes in `manuscript-pdf-verification.json`. The built-in editor compiler
still reports a platform-directory error; the existing editor stays open.
All four constructions are illustrated. The labeled 16- and 17-disk panels
appear on page 4 and are generated from the certified coordinate enclosures.
The manuscript remains a draft for author review.

`lean/build.ps1` rebuilds the four selected theorem closures and native runtimes
from source with explicit dependency/toolchain path parameters. The source
archive generator is `lean/package_proof_sources.py`; its output manifest and
archive verification receipt record the exact distributed files. The source
archive has not been independently rebuilt on a second machine.

The finished source supplement is `proof-sources-16-17-18-20.zip`:
376 source/documentation/audit files, including 366 Lean modules, totaling
7,446,343,992 uncompressed bytes and 1,298,180,402 archive bytes.
Every archived source was read back and matched to its SHA-256 manifest;
ZIP CRC checks also passed. The archive SHA-256 is
`564ef772741880206a52f4b0dd7f0e36d9f3c05abd0caf1149816f76e03ade5e`.
The verification receipt is `proof-source-archive-verification.json`.

The sections below are a historical audit trail; their partial counts and
pending-work descriptions are superseded by this checkpoint.

## Verified components and earlier audit trail

The existing 16- and 17-circle exact certificate projects remain in
`../circle16` and `../circle17`. Their full forests passed independent
replays and their recorded source hashes were freshly matched. These are
exact computational proofs. The full sixteen-circle Lean least-radius theorem
is now complete, as are the seventeen- and eighteen-circle final theorems.

The exact construction for 18 uses containing radius
`1 + sqrt(6) + sqrt(2)` and has also been checked in Lean. The 18-circle
local certificate acts on a rigid 17-center core because a boundary circle
can move. Its rational matrix/stress checks and radial bridge have independent
verification. Its full forest has passed both independent exact replays:
4,863 orders and 8,233,519 nodes, with no unresolved or unprocessed cases.
The forest SHA-256 is
`445f0d1543ab1bd1d8cd7d69aaa7b874aedcd4bc4a8393e0c4172d4a277e6743`.
Five additional stressed templates and the core family cover 41 words and
138 modes. The complete computational proof is in `../circle18`.

On October 7, 2026, the user changed the fourth cardinality to 20. The
twenty-circle extension is now in scope and has not yet been proved. The
existing manuscript is edited in place, retaining its original filename.

The Lean modules in `lean/CirclePacking` contain checked geometry,
polar exclusion-tree soundness, word symmetry, exact hexagonal constructions,
and auxiliary 10-, 11-, and 13-circle finite certificates. The full concrete
16-circle Cartesian rigidity, candidate minor-angle modules, and the full
`SixteenLocalExclusion.localBoxCheck_sound` theorem compile. Its audit contains
no `sorryAx`: the actual inverse, positive stress, contact geometry, radial
containments, argument lifts, angular corner bounds and paths are discharged.
The full 312,728-node global finite acceptance and the hypothesis-free
`SixteenCirclesInACircle.isLeast` theorem have also compiled. Their final
receipt is `lean/certificates/sixteen_full_lean_verification.json`: all 38
local project dependencies are bound to current source and binary hashes,
with a separate kernel equality audit for the restored global source.
The final axiom audit contains no `sorryAx` and only the standard three
axioms plus the explicitly recorded finite native acceptance receipts.
Generic soundness lemmas with
explicit application hypotheses are not complete main theorems.

The 20-circle primary coordinate file is recorded in
`../circle20/packomania-cci20.txt`. Its exact radical construction and root
bracket have now been independently checked with rational intervals, including
all 164 noncontacts. It has 12 wall contacts, 26 disk contacts, and one loose
circle at the origin; the candidate container radius is about 5.12232073699153.
The core stress and radial bridge have also passed independent audits.
The frozen v3 profile uses intersection-safe radius intervals so each accepted
box lies inside the exact tolerance. Its seven words and 14 modes cover all
origin insertions for this candidate family; coverage of every remaining
global configuration is not yet established. Its unused origin interval covers
the entire broader global box. Earlier v2 forest shards retain their original
provenance and are checked against the archived, narrower origin interval.

The auxiliary 13-circle forest and its complete geometric exclusion theorem
compile in Lean. `TwentyNormalization.exists_normalized_polar` then restricts
the 20-circle search to 8--12 boundary circles. Successful source/binary/axiom
receipts for these components and the 16-circle local theorem are recorded
in `certificates`. The generic anchor-cut geometry also compiles and preserves
strict separation under rotation, reflection, and relabeling. The exact
integer cosine Taylor checker is kernel-proved equal to the original rational
polynomial. All six 18-circle Cartesian local exclusions have compiled, and
the additional origin bound from the inner hexagon also compiles without
admitted steps. The complete 18-circle radial/mode local application now
also compiles, covering all 138 modes with no `sorryAx`; its global finite
acceptance and final optimality assembly are complete. The original 17-circle
polar inverse residual predicate has compiled using exact common-denominator
integer data, with all original rational entry identities checked in Lean.
The full seventeen-circle polar local theorem now compiles with every
matrix, Hessian, contact-domain and wrap premise discharged. Its transitive
source and binary receipt is `certificates/seventeen_local_lean_verification.json`.

The 20-circle depth-six search processed all 19,796 circular words. It closed
285 words and left 19,511 unresolved, with no accepted local leaves in this
initial pass. Both independent replays have checked the immutable closed
subset of 285 orders. Deeper exclusion work is in progress. This partial
forest does not prove 20-circle optimality. The exact candidate root and
feasible twenty-circle packing now compile in Lean, with all ten current
project dependencies hash-bound in
`certificates/twenty_construction_lean_verification.json`. The complete global
exclusion and final Lean optimality assembly remain unfinished.

The separate broader radial neighborhood at eta `1/625` and coordinate
epsilon `3/400` passed a fresh independent bridge and stress audit. Its
contraction is `2430729/2500000 < 1`; the original v3 inputs are preserved.
The separate Cartesian proof for this neighborhood remains unaccepted;
the neighborhood is also covered by the compiled polar proof below.
The seven-word depth-64 pilot
still has unresolved leaves after reaching its node budget, so it is not
an accepted complete exclusion forest.

The stronger direct polar certificate at eta `1/125` now has both an
independent exact audit and a compiled Lean proof. Its 26-contact matrix
uses seven radial and 18 angular variables. The common dual constant is 90,
and the effective contraction is
`720000000000000000000000009/1000000000000000000000000000 < 1`.
No initial angular proximity is assumed. The full application to all 14
physical modes, omitting the loose origin from the rigid core, compiles as
`TwentyCirclesInACircle.PolarLocalExclusion.localBoxCheck_sound`.
The receipt `../circle20/lean_polar_local_verification.json` binds 41
current source/binary dependency pairs and 44 explicit finite native receipts,
with no `sorryAx`; these hashes and the compiler log were independently
matched after receipt creation. The frozen profile SHA-256 is
`7ae0b1b09825de08adf5c7ac25899c0b816aeec27150b6d6e0c26117bdcff2ad`.
The independent forest replayer now accepts this separately audited profile.
This completes the candidate-family local proof; global optimality remains open.

The standalone `lean/TwentyCirclesInACircle.lean` candidate-packing theorem
also compiles, with 11 current dependencies bound in
`certificates/twenty_candidate_file_verification.json`. It supplies the
exact feasible upper bound; it contains no unproved least-radius assertion.

Complete circular-word coverage and global forest acceptance for 17 and 18
now compile in Lean, using a compiler-generated native
runtime that is kernel-proved equivalent to the original tree semantics.
The runtime audit records the pure Lean sources, generated C and DLL hashes,
compiler arguments, and equality/soundness proofs with only standard axioms.
Its current receipt is `lean/certificates/native_runtime_verification.json`.
These generic bindings connect to the separately accepted finite forest receipts.

The hypothesis-free `SeventeenCirclesInACircle.isLeast` and
`EighteenCirclesInACircle.isLeast` are complete. Their final receipts are
`lean/certificates/seventeen_full_lean_verification.json` and
`lean/certificates/eighteen_full_lean_verification.json`. They bind all 70
and 97 current transitive source/binary pairs, respectively, together with
the complete retained forests and native runtime provenance. The final
axiom audits have no `sorryAx` and only the standard three axioms plus
explicit finite native acceptance receipts. The independent root audit
`lean/certificates/completed_17_18_independent_hash_audit.json` matched all
340 receipt-listed source files, compiled files and compiler logs.

Complete 20-circle word coverage also compiles in Lean:
`TwentyCirclesInACircle.WordCoverage.all_words_covered` covers all 772,616
binary words in the proven boundary band and reduces them to 19,796
canonical orders. Its receipt
`../circle20/global/word_coverage_lean_verification.json` binds nine current
project source/binary pairs and the native runtime provenance. This is
the full discrete coverage theorem; exclusion of every saved order remains.

The first candidate-profile order for 20 is fully excluded in the immutable
`../circle20/global/pilot_polar160_first.json` forest (SHA-256
`3d3f3580c60eb390b409301be4e28529407d86cdb1ac4d2525c2ac9a0e4a3bcb`).
Both independent exact replays passed all 1,567,227 nodes: 783,613 splits,
780,538 angular leaves, and 3,076 polar local leaves, with zero unresolved.
Their receipts are `pilot_polar160_cosine_replay.json` and
`pilot_polar160_sine_replay.json` in the same directory. They bind the frozen
polar profile and verifier SHA-256
`26c8c10f524364cc6396bd1092c9288b90252abb09576ea32b7748f1a34f8357`.
This pilot represents one of 19,796 global circular orders.

A second candidate-profile order is completely excluded in
`../circle20/global/pilot_polar160_fresh_part2.json` (SHA-256
`f9af78f96de55520e97ab3604ed8eeeabec74f89a8835097c15adf7ab873fed9`).
Both independent exact replays accepted all 1,539,459 nodes: 769,729 splits,
768,669 angular leaves and 1,061 polar local leaves, with zero unresolved.
The matching cosine and sine receipts have the same filename stem with
`_cosine_replay.json` and `_sine_replay.json` suffixes. These partial results
are not a complete global exclusion theorem.

The generic shared-radius derivative and mean-value bound now compile in
`CirclePacking/JointAngleBounds.lean`, and the geometric cycle consequence
compiles in `CirclePacking/JointCycleBounds.lean`. Their axiom audits list
only the standard three axioms. The reusable `jointCycleCheck_sound` also
compiles with standard axioms, and `JointWitness20.box_exclusion` compiles
with its one explicit finite native receipt. Its receipt is
`certificates/joint_witness20_lean_verification.json`. The independent root
audit `../circle20/local/joint_lean_independent_binding_audit.json` matched
all fourteen transitive source/binary pairs, the compiler log, and every
box, cycle, midpoint-angle and shared-DAG entry against the independently
replayed fixture. Both cosine and sine replays accepted the 50- and
30-digit fixtures; the explicit box margin is greater than `0.00072999`.
Twelve malformed fixture variants were rejected by both methods. Joint
cycle leaves are not yet part of the accepted global forests.

Five partial twenty-circle finite forest blocks compile with labels
`Initial`, `Second`, `Third`, `Part1`, and `Parts023`; their receipts are
`lean/certificates/TwentyClosed{label}_verification.json`. Together they
cover 6,794 distinct canonical root indices, 9,410,210 nodes and 5,774
polar local leaves. The root audit
`../circle20/global/partial_lean_blocks_independent_audit.json` matches
the current source, binary and compiler-log hashes, the exact compiled
index arrays, all 66 transitive project modules per block, and the 26
native-runtime receipt files. The separate inventory audit
`../circle20/global/closed_union_independent_audit.json` matches these
indices to the same union of independently replayed cosine and sine
forests, confirming that the 100-order pilot is contained in the closed
depth-16 subsets and is not counted twice.

The four initial depth-16 search shards have finished. Their structurally
closed subsets contain 6,506 orders and 4,245,318 nodes; all four subsets
passed both independent exact replay methods. Adding the disjoint
285-order initial subset and three candidate-profile orders gives the
6,794 accepted canonical orders above. The exported tree theorems retain
the ordinary polar-leaf callback; the completed polar local library
supplies that callback in the final normalized geometric assembly.
The compiled `TwentyAcceptedFamilies` theorem now combines these five
blocks and the separately excluded dummy case. The independent audit
`../circle20/global/accepted_union_independent_audit.json` binds all 77
current project modules and checks that the axiom list is exactly the
standard three plus eleven explicit finite acceptance receipts. This
assembles 6,795 of the 19,797 indexed cases; it does not assert full coverage.
There are still 13,002 canonical orders without accepted complete
exclusion certificates at this checkpoint. The deeper search and the
joint-cycle candidate continuation are separate ongoing computations;
they do not yet supply a complete global theorem.

The first joint-cycle continuation has now saved a structurally complete
candidate-order proposal as
`../circle20/global/pilot_joint192_active_part1.json`, SHA-256
`3252f38beff7ff515ffc907144b2720733292acc72434f98c06c538ccf6a1c07`.
It contains 2,351,985 nodes, including 17,119 joint-box leaves and 1,101
ordinary polar leaves, with zero unresolved leaves. Its 431-entry sidecar
has SHA-256
`02b34a262c82a6fac72bc98c9d4d6902c00e25c5c143850f002cd190f763e6a3`.
Both independent replays have now passed the entire tree and all 431
sidecar certificates, with zero unresolved leaves. The receipts are
`pilot_joint192_active_part1_cosine_replay.json` and
`pilot_joint192_active_part1_sine_replay.json` in the same directory.
Lean acceptance remains pending, so this order is not included in the
Lean-accepted total above. All 54 generated Lean table batches, including
every box, cycle, DAG node, witness root and midpoint angle, match the
independently checked sidecar; the audit also checks aggregate box order
and owner indices. This data-binding audit is
`../circle20/global/joint_pilot_lean_data_binding.json`. All 431 individual
table certificates and the aggregate table exclusion theorem have now
compiled. The independent audit
`../circle20/global/joint_table_compilation_independent_audit.json` matches
all 55 completed module records, 78 transitive project dependencies and
the exact finite native axiom lists. Finite forest acceptance is still
pending; the table alone does not exclude the entire canonical root.

Four immutable depth-24 checkpoint snapshots are saved as
`../circle20/global/depth24_part{0,1,2,3}_closed_snapshot1.json`.
They contain respectively 1,542, 1,540, 1,538 and 1,577 structurally closed
orders, totaling 24,741,615 nodes. Each snapshot has a companion manifest
binding every included source checkpoint. The independent inventory check
`../circle20/global/checkpoint_snapshot_inventory.json` verifies that all
6,197 proposed orders are disjoint from each other and from the 6,794
accepted orders. All eight exact replays have now finished successfully.
The final binding audit is
`../circle20/global/checkpoint_snapshot_verified_coverage.json`; it checks
both replay receipts, exact source hashes and counts for all four files.
The 6,197 new cases bring the ordinary independently replayed union to
12,991 orders. Their Lean compilation remains pending, so they are not
included in the compiled total above.

For the next large exports, `lean/export_twenty_closed_streaming.py` reads
one forest result at a time. The old exporter is preserved. Full generated
Lean output agrees after namespace renaming on the 100-order pilot and
on a results-first fixture that removes 100 already accepted rows and
retains one new row. The comparison receipts are
`lean/certificates/streaming_twenty_exporter_comparison.json` and
`lean/certificates/streaming_twenty_exporter_late_comparison.json`.
This exporter comparison is a software check, not geometric acceptance;
every new Lean finite certificate still has to compile.

The separately staged `lean/export_twenty_closed_fast_streaming.py` uses a
faster frozen reader and passes the same complete-output comparisons.
The separate `../circle20/global/replay_forest_fast.py` preserves the
baseline cycle, local, domain and split checks. The independent audit
`../circle20/global/fast_replayer_independent_audit.json` binds its reader
and exact propagation probes and checks that its proof logic is unchanged
after those two substitutions and the added source-hash guards. It is
replayed a further disjoint batch of 435 depth-32 roots and four depth-40
roots by both trigonometric methods. All 7,079,911 nodes passed both
checks. The audit
`../circle20/global/depth32_40_part0_batch1_independent_audit.json` binds
the source hashes, both receipts, exact counts, disjoint case indices and
the generated `TwentyClosedDepth32Part0Batch1` Lean sources. Including
the independently checked joint-cycle pilot, the independent union now
covers 13,431 canonical orders. Lean acceptance of these new batches is
still pending. The baseline replayer remains frozen.

A second deeper batch has 488 closed depth-32 roots and four depth-40
roots. Its paired checks and `Depth32Part1Batch1` export have finished.
The closed depth-32 source has SHA-256
`a97fbf00362e508682634649c241e48c98453e44e38ba33bf00604425648b4f0`.
All 7,996,950 nodes passed both exact methods, and its 492 roots are
disjoint from the preceding 13,431-root independent union. Live search
ownership and next disjoint selections are recorded in
`../circle20/global/search_pending_work_circle18.json`.

## Build environment

- Lean: 4.33.1, Windows.
- FormalConjectures: `8432eac998110a563e03df65a28c117e97c8c142`.
- Mathlib: `0df444a360eaa60ab8c11dca51a86af692955474`.

The draft source is `circle-packings-16-19.tex`. The built-in LaTeX compiler
has repeatedly returned `Unable to find standard directories for platform`.
No successful PDF compilation or layout verification is claimed.

This checkpoint must be updated from actual final receipts before delivery.

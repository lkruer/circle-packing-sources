---
type: "result"
title: "Portfolio source: Sixteen, seventeen, eighteen, twenty circles"
problem: "other-circle-packing"
kind: "survey"
status: "informational"
review: "none"
scope: "supporting"
date: "2026-10-11"
authors: ["Will Howe", "Grant Huffman", "Jensen Kohlmeyer", "Liam Kruer"]
agents: ["Codex"]
origin: "JENW1N/jensen-portfolio@75e0415ab82aaa8aeb2c0a8c475a19eeb0e531f1; entry circle-packings"
tags: ["portfolio", "completed-source", "exact-target"]
novelty: "unassessed"
visibility: "private"
summary: "Source intake: The manuscript determines the least circular container radii for 16, 17, 18 and 20 congruent unit disks, allowing arbitrary asymmetric placements. Eighteen has the exact radius 1 + √2 + √6; the other three are specified by radical closure equations and forty-decimal enclosures."
---
# Portfolio source: Sixteen, seventeen, eighteen, twenty circles

## Claim

The portfolio reports the following completed result at its stated scope. This record files that claim and its sources; it does not provide a new proof verdict.

The manuscript determines the least circular container radii for 16, 17, 18 and 20 congruent unit disks, allowing arbitrary asymmetric placements. Eighteen has the exact radius 1 + √2 + √6; the other three are specified by radical closure equations and forty-decimal enclosures.

## Evidence

Strict dilation and maximal-boundary normalization reduce a hypothetical smaller packing to finitely many circular orders and radial boxes. Rational angular-cycle certificates exclude remote boxes; equilibrium stresses handle neighborhoods of the attaining arrangements. The twenty-disk proof additionally uses joint bounds on complete angular cycles. It covers 19,796 canonical circular orders and 199,234,854 tree nodes. Source: Theorems 1.1–1.3 and Sections 2–7. The explorer reconstructs only the feasible arrangements in Section 3.

## Limits

The October 8 manuscript is a working draft for author review. It reports four compiled least-radius theorems, exact certificate replays, source binding and axiom audits. The finite native_decide receipts add trust in compiled evaluation to the standard Lean axioms. The supplied four short Lean files are entry modules importing the larger CirclePacking project; that dependency and certificate bundle is not included here, so they cannot be replayed in isolation. This portfolio checks the displayed construction coordinates, separations and contacts at high numerical precision, not the global optimality proof. Classical candidate arrangements are credited to Goldberg, Reis and Pirl, with Packomania as a coordinate reference; no independent acceptance or discovery-priority claim is implied.

Historical verification, acceptance and axiom claims remain attributed to the portfolio or its manuscript. No Lean proof was replayed and no review level was promoted by this import.

## Files

| Portfolio path | Preserved bytes | SHA-256 |
| --- | ---: | --- |
| [README.md](<../../../../../archive/portfolio-collatz-261011/tree/portfolio/b64b1566f7b210b2/README.md>) | 33178 | `b64b1566f7b210b2504d48851ad92a34f4dbebbef21f9381c5323aa4621aceba` |
| [papers/EighteenCirclesInACircle.lean](<../../../../../archive/portfolio-collatz-261011/tree/portfolio/39f9e6ca0cd488aa/EighteenCirclesInACircle.lean>) | 1115 | `39f9e6ca0cd488aa6b2499a989c94931429f25b3e4335362faaab55755109fc9` |
| [papers/SeventeenCirclesInACircle.lean](<../../../../../archive/jk-pc-partials-20261008/tree/other-circle-packing/saved-files/dc657596561e23c4/SeventeenCirclesInACircle.lean>) | 1419 | `dc657596561e23c4dbc76506a32169376a48cd5b750ab137f773eec0de8d2c7c` |
| [papers/SixteenCirclesInACircle.lean](<../../../../../archive/jk-pc-partials-20261008/tree/other-circle-packing/saved-files/1959250541fd59c3/SixteenCirclesInACircle.lean>) | 1571 | `1959250541fd59c3c6e0b92c76d6a45565f8610f9d37ab7a1f61e12d61a522b6` |
| [papers/TwentyCirclesInACircle.lean](<../../../../../archive/jk-pc-partials-20261008/tree/other-circle-packing/saved-files/0ab8fa3af06bcd10/TwentyCirclesInACircle.lean>) | 1263 | `0ab8fa3af06bcd10c2019e5e81f42c0df9a5d855a8e94ebd2fbc7a59322a1d34` |
| [papers/circle-packings-16-17-18-20.pdf](<../../../../../archive/jk-pc-partials-20261008/tree/unclassified-writeups/saved-files/5aea449a1db6cd9a/circle-packings-16-17-18-20.pdf>) | 158812 | `5aea449a1db6cd9a513dbba5a03f2de138335b4a37ae3ec5556b8fa05da9eca1` |
| [papers/research-certificate.json](<../../../../../archive/portfolio-collatz-261011/tree/portfolio/b1210c1c08c68db8/research-certificate.json>) | 29483 | `b1210c1c08c68db8785e416be99eaa95836a90c6fb30dcd23201eac353e9b529` |
| [papers/selected-verification-records.json](<../../../../../archive/portfolio-collatz-261011/tree/portfolio/72ea69d7aac3d55d/selected-verification-records.json>) | 1561 | `72ea69d7aac3d55d145a0674098a651bdcca0e34b7eb724e19811772dc333748` |
| [papers/verify_research.py](<../../../../../archive/portfolio-collatz-261011/tree/portfolio/f9499204100a7a59/verify_research.py>) | 12177 | `f9499204100a7a592ba57b3eaf3f5eec5b0338fe3fb486c888d0cb83ee8d32d4` |

## How to check it

Verify the attached SHA-256 values and use the exact source toolchain, target and dependency revisions recorded in the manuscript and source. Finite example checkers verify only their recorded ranges. The complete portfolio inventory and reconstruction map are in [the intake index](<../../../../operations/jklaptop-import/portfolio-collatz-20261011/README.md>).

## Provenance

Jensen Kohlmeyer, Grant Huffman, Will Howe, and Liam Kruer. The working draft credits OpenAI Codex assistance with mathematical exploration, certificate generation and checking, manuscript preparation, and Lean development.

Repository: [JENW1N/jensen-portfolio](https://github.com/JENW1N/jensen-portfolio/tree/75e0415ab82aaa8aeb2c0a8c475a19eeb0e531f1), entry `circle-packings`. The extracted entry is saved in [portfolio-entry.json](<portfolio-entry.json>).

Source problem: "https://en.wikipedia.org/wiki/Circle_packing_in_a_circle".


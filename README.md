<!-- solve-problem:2cb6e54e-ae6c-4ed5-9085-ac00168d5acd -->
# Infinitude of the polynomial hierarchy

A [Tangle Solve problem](https://solve.tangle.tools/problems/2cb6e54e-ae6c-4ed5-9085-ac00168d5acd).

## What is the problem?

The polynomial hierarchy (PH) is defined via oracle relativization of NP: Σ₁ᵖ = NP, and Σ_{k+1}ᵖ = NP^{Σ_kᵖ}; equivalently Σ_kᵖ is the class of languages decidable by a polynomial-time alternating Turing machine with at most k alternations between existential and universal branches, starting existentially (Π_kᵖ is the dual, starting universally). The problem: determine whether the hierarchy is **proper**, i.e., whether Σ_kᵖ ⊊ Σ_{k+1}ᵖ for every fixed k ≥ 1, or whether it **collapses** to some finite level (Σ_kᵖ = Σ_{k+1}ᵖ for some k, which by standard padding/downward arguments implies PH = Σ_kᵖ).

Note the logic: even proving Σ₂ᵖ ≠ Σ₃ᵖ (a single separation at any level ≥ 2) is open. Proving Σ₁ᵖ ≠ Σ₂ᵖ would already imply P ≠ NP, which is itself open. The unconstrained problem "prove PH is infinite" subsumes P ≠ NP and is among the deepest structural complexity questions.

Standard equivalent characterizations: Σ_kᵖ via alternating machines; via quantified Boolean formulas with k−1 alternations decided by a polynomial-time predicate (e.g., QBF with k alternation blocks is Σ_kᵖ-complete); via oracle machines as above.

## Why does it matter?

If PH collapsed to some finite level, many results proved by "PH is infinite" assumptions (e.g., in circuit lower bounds, learning theory, cryptography, and proof complexity) would become vacuous; conversely, proving PH infinite would immediately yield P ≠ NP and much more. The collapse of PH is a key intermediate step in many conditional results: e.g., if the permanent has polynomial-size arithmetic circuits, then PH collapses to Σ₂ᵖ (Kannan/ZPP-type arguments; Toda's theorem shows PH ⊆ P^#P, so any separation of PH from counting classes would separate levels). It is the canonical test case for whether quantifier alternation genuinely adds power under polynomial time.

## What's already known?

- **Stockmeyer (1976)** defined PH and proved the complete-problem characterization (QBF with bounded alternations) and basic closure properties.
- **Baker–Gill–Solovay (1975)** showed there are oracles A with PH^A infinite and oracles B with PH^B collapsing to Σ₁ᵖ (even P^B = NP^B). Hence any proof of infinitude or collapse must use **non-relativizing** techniques.
- **Toda (1991)**: PH ⊆ P^#P — a surprising collapse of PH to counting, showing PH is "not too big."
- **Kannan (1982)**: for every k, there is a language in Σ₂ᵖ ∩ Π₂ᵖ (indeed within PH's second level) requiring circuits of size n^k; so some level of PH (Σ₂ᵖ or below vs. Σ_kᵖ) must be separated unconditionally by circuit size — but not the class-level separation asked here.
- **Sipser–Gács–Lautemann**: BPP ⊆ Σ₂ᵖ ∩ Π₂ᵖ, a rare nontrivial containment.
- Modern non-relativizing tools (arithmetization, algebrization barriers of Aaronson–Wigderson 2008) show even most algebrizing techniques cannot resolve PH-level questions; natural proofs (Razborov–Rudich) block standard circuit routes.

No unconditional separation Σ_kᵖ ≠ Σ_{k+1}ᵖ for any k ≥ 1 is known.

## What would count as solving it?

Any of the following would be major (in increasing strength):
1. **A separation at one level**: a proof that Σ_kᵖ ≠ Σ_{k+1}ᵖ for some explicit k ≥ 2 (k = 1 gives P ≠ NP). Referee criterion: an unrelativized, unconditional proof — no assumptions.
2. **Infinitude**: a proof that for every k, Σ_kᵖ ⊊ Σ_{k+1}ᵖ (e.g., via showing Σ_kᵖ-time hierarchies, diagonalization against relativization barriers).
3. **Collapse**: a proof that Σ_kᵖ = Σ_{k+1}ᵖ for some k — equally publishable and would be revolutionary (implying, e.g., unexpected consequences in counting classes via Toda).
Also acceptable as partial progress: any non-relativizing separation technique that provably evades the algebrization barrier for PH-level questions.

## How to start

1. Read Stockmeyer (1976) for the definitions and complete problems; then Arora–Barak, *Computational Complexity: A Modern Approach*, Chapters 5 (hierarchy theorems) and 17? (oracle barriers)—actually the relevant chapters are 3–5 and 9 (verify chapter numbers).
2. Internalize why time-hierarchy-style diagonalization fails: relativization (BGS) — the diagonalizing machine cannot be simulated relative to oracles it queries.
3. Study the successful non-relativizing results: IP = PSPACE (Shamir), Toda's theorem, and the algebrization framework (Aaronson–Wigderson 2008) to see exactly which technique space remains.
4. Natural first target: the "easy witness method" / Karp–Lipton-style collapse consequences (if NP ⊆ P/poly then PH ⊆ Σ₂ᵖ) — try to weaken or strengthen collapse conditions to locate a contradiction. Main obstacle: every known barrier (relativization, algebrization, natural proofs) applies to this problem.

## Key references

- L. Stockmeyer, "The polynomial-time hierarchy," *Theoretical Computer Science* 3(1):1–16, 1976. Defines PH, gives alternating-machine and quantifier characterizations, proves complete problems. DOI: 10.1016/0304-3975(76)90061-X
- T. Baker, J. Gill, R. Solovay, "Relativizations of the P =? NP question," *SIAM J. Comput.* 4(4):431–442, 1975. Constructs oracles relative to which P = NP and P ≠ NP; the same machinery gives collapsing and infinite PH oracles.
- S. Toda, "PP is as hard as the polynomial-time hierarchy," *SIAM J. Comput.* 20(5):865–877, 1991. Proves PH ⊆ P^#P via randomized reductions.
- R. Kannan, "Circuit-size lower bounds and non-reducibility to sparse sets," *Information and Control* 55:40–56, 1982. Shows Σ₂ᵖ ∩ Π₂ᵖ contains languages without n^k-size circuits.
- S. Aaronson, A. Wigderson, "Algebrization: a new barrier in complexity theory," *ACM TOCT* 1(1), 2009. arXiv:0806.1345. Shows arithmetization-based techniques also relativize/algebrize, blocking many approaches to PH separations.

## Warnings

- Do not attempt pure diagonalization or black-box simulation: Baker–Gill–Solovay oracles kill all relativizing proofs in both directions.
- The problem statement "prove Σ_kᵖ ≠ Σ_{k+1}ᵖ for every fixed k" is strictly harder than P ≠ NP; set intermediate milestones.
- Common error: conflating Σ_kᵖ ≠ Σ_{k+1}ᵖ with a time hierarchy for fixed k — the machines at level k+1 are *not* a syntactically larger class with more time, so the standard deterministic time hierarchy theorem does not apply.
- Algebrization (Aaronson–Wigderson) rules out most arithmetization-based proofs; any approach must be explicitly non-algebrizing.

---
*`ALGO-000027` · unverified*

## Acceptance guidance

Any of the following would be major (in increasing strength):
1. **A separation at one level**: a proof that Σ_kᵖ ≠ Σ_{k+1}ᵖ for some explicit k ≥ 2 (k = 1 gives P ≠ NP). Referee criterion: an unrelativized, unconditional proof — no assumptions.
2. **Infinitude**: a proof that for every k, Σ_kᵖ ⊊ Σ_{k+1}ᵖ (e.g., via showing Σ_kᵖ-time hierarchies, diagonalization against relativization barriers).
3. **Collapse**: a proof that Σ_kᵖ = Σ_{k+1}ᵖ for some k — equally publishable and would be revolutionary (implying, e.g., unexpected consequences in counting classes via Toda).
Also acceptable as partial progress: any non-relativizing separation technique that provably evades the algebrization barrier for PH-level questions.

## Contribute

Contributions, audits, and critiques from humans, agents, or both are welcome. Open a pull request with your work, then [publish the exact revision or artifacts on Solve](https://solve.tangle.tools/problems/2cb6e54e-ae6c-4ed5-9085-ac00168d5acd?contribute=1). Include reviewed agent traces when available. Contributions need not solve the entire problem.

Keep experiment code, reports, and trace artifacts in this repository. Publish only material you have reviewed for public sharing. Solve retains the contribution snapshot and its review history independently of whether a pull request is merged.

Source record: ALGO-000027.

- [Public source catalog](https://drewstone.github.io/problems/#/p/ALGO-000027)

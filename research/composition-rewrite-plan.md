# Composition and gluing rewrite

## Goal

Replace the current multi-stage proof with a short, rigorous explanation that composition of coherent chain-complex maps corresponds, under the Pontryagin--Thom construction, to gluing the relevant manifolds with corners.

The issue is not doubt about the result. The issue is that the current presentation is duplicated and routes through more one-categorical and spine-cube machinery than may be necessary.

## Current source assessment

- `ChModels.tex` is the active endpoint/coend proof, with the finite-cell weights and relative finite-dimensional representative lemma. `ChOfFlow.tex` supplies the indexing category and bounded collapse model.
- `DiffOfFlowCat.tex` is the active geometric proof: rounding, collapse/composition, relative realization, corner restoration, and the differential theorem. The coherent connecting-map comparison, including its sign, remains explicitly marked (see the follow-up review below).
- `archived-drafts/CompInTop.tex` is an incomplete earlier start. It introduces horn filling and rigidification and then stops during the definition of a spine cube. No completed result in it currently needs to be restored.
- Relevant exploratory notes include [`../Ignore/A note on models.md`](../Ignore/A%20note%20on%20models.md), [`../Ignore/Models - summary.md`](../Ignore/Models%20-%20summary.md), and [`../Ignore/why-move-to-longer-cubes.md`](../Ignore/why-move-to-longer-cubes.md).

## Source review and revision — 27 September 2026

The bounded endpoint/coend route is retained. Spine cubes are unnecessary for this particular composite; no claim about a general category of flow bimodules is needed. Keep the short model checks in the body for now. The finite-representative lemma is the natural item to move if an appendix later becomes useful.

Dependency chain: `prop:J_equivalence` → `prop:ChModels.derived` → cellular endpoint weights → `prop:ChModels.composition`; geometrically, rounding → collapse comparison, while `lem:ChModels.finite_representatives` → relative transversality → flow-module realization. Corner restoration then supplies the next extension.

| Former task | Assessment and revision |
| --- | --- |
| G1 | The collar thickening rounds the stated face colimit. Compare its double-overlap coordinate exchange with the fixed normal trivializations; use a family for bordism independence. |
| G2 | Relative embeddings and product tubular charts supply the collapse diagram. Rounding preserves its normal coordinate, hence its collapse map. **Still check the sign against the suspension/connecting-map conventions in `SSofCh.tex`.** |
| G3 | Added the finite free-cell argument: stable maps and relative homotopies descend to one suspension level. Relative transversality and homotopy extension then realize the specified morphism while retaining its top representative. This is an argument supplied here, not a theorem attributed wholesale to Genauer. |
| G4 | Attach the retained rounding collar to a framed null-bordism, reverse the attaching normal, then embed relative to the prescribed faces. |

Auxiliary choices need only produce the same framed bordism class. Stable relative embedding spaces admit parameter extensions; compatible collars are unique up to isotopy. Neither the space of framings nor the space of algebraic extensions is asserted to be contractible.

Sources checked at the relevant passages:

- [Genauer](https://arxiv.org/pdf/0810.0581), Proposition 2.8, Theorem 3.17, and §9: relative neat embeddings and corner Pontryagin–Thom/transversality. Interpret embedding uniqueness stably, allowing the ambient dimension to grow with the parameter family.
- [Porcelli–Smith, v3](https://arxiv.org/pdf/2401.11766v3), Lemmas 3.19, 4.9, 4.41–4.43: relative collars and the framed gluing construction. Their overlap calculation is relevant, not merely their confident use of gluing.
- [Côté–Kartal](https://arxiv.org/pdf/2309.15089), Proposition 2.24 and Appendix A: collapse naturality and compatible embeddings. Their Remark 2.15 does **not** establish the localization of J-modules used here; that comparison uses Schwede–Shipley and Lurie.
- [Blakey](https://arxiv.org/pdf/2410.11478), §4.1, Proposition 4.9, and Remark 4.10: a useful exposition model, citing the foundational flow-category theory and sketching the changed comparison. Contractible **operator-gluing** choices are not a citation for contractibility of our geometric choices.
- Schwede–Shipley, Theorem 7.2 and §§6–7; Lurie, *Higher Topos Theory*, Theorem 2.2.5.1 and Propositions 4.2.4.4, 5.3.3.3; Mandell–May–Schwede–Shipley: projective enriched diagrams, model comparisons, and finite stabilization.

The edits also specify the ordered Euclidean blocks in the bounded collapse construction, remove its duplicate point-set desuspension argument, and fill the missing zero-morphism cases in the definition of J. The older proposed **unbounded** space-level limit/colimit remains outside this proof and retains its TODO.

Verification: source and dimension checks, diff review, label/citation checks; no compilation, as requested. Do not regard the full rewrite as complete before the remaining sign check and a later build review.

## Proof-review follow-up — 27 September 2026

This review supersedes the earlier assessment that only a sign check remained. The sketches were checked at the level of their omitted constructions before the verified arguments were written as manuscript proofs. No compilation was performed, as requested.

- **Enriched localization:** checked the actual hypotheses of Schwede–Shipley Theorem 7.2 and Lurie HTT Proposition 4.2.4.4. Added the passage to a combinatorial simplicial spectrum model and the cellular reduction at the zero object.
- **Endpoint/coend calculation:** checked both weight filtrations, their attaching faces, the use of objectwise cofibrancy, cotensor fibrancy, and transport through replacements. Checked the single-degree case as well as all multiple-face intersections. The ordinary coend computes the required derived pairing for these weights.
- **Quotient truncation used by survival:** replaced the termwise calculation in `SSofCh.tex` by a comparison on filtered Yoneda generators and their transition maps, closing the existing coherence TODO on this dependency.
- **Finite representatives:** wrote the finite mapping-space pullback argument, including the homotopy fiber needed for prescribed partial data. This is an adaptation supplied in the manuscript, not a theorem attributed to the references.
- **G1 and geometric G2:** checked the local boundary-orthant model, the constant normal rank, the common ordered normal framing, and the product tubular collapse. Explained the cofibration condition behind the face homotopy colimits. Porcelli–Smith v3 Lemmas 3.19, 4.9, and 4.41–4.43 support the collar, framing, and bordism arguments; Côté–Kartal Proposition 2.24 supports the collapse naturality. The equality proved is between the geometric collapse and the coend composite.
- **G3:** replaced the unrestricted inverse-image argument with a descending relative construction. The previously realized products prescribe the actual boundary collapse. Its stable extension is realized after suspension in extra module coordinates, leaving the fixed flow blocks untouched. Relative transversality fixes those collars; homotopy extension retains the entire endpoint morphism. This addresses the missing product-boundary justification in the previous sketch. Genauer Theorem 3.17 and §9 provide the inverse-image construction; the relative adaptation is explained here, rather than quoted as an existing module-realization theorem.
- **G4:** checked that retaining the rounding collar restores precisely the specified face intersections. Framed boundary identification and relative stabilized embedding extend the prescribed normal framing. No contractibility of framing choices is needed.
- **Remaining G2 dependency:** the coend sphere must be compared with the coherent connecting morphism in `lem:Ch_diff`. That proof's passage from suspension to index shift does not identify the resulting coherent map; checking the one-degree product does not resolve this in every window. Lurie HA Construction 1.2.2.6 and Definition 1.2.2.9 (read in the supplied extract) define the filtered differential, but do not supply this model-specific comparison. No exact reference was found in the sources checked. The TODO distinguishes those related results from the missing identification, and the theorem's proof explicitly retains the dependency.

Blakey §4.2, Proposition 4.9 and Remark 4.10 were checked for the intended level of exposition. They do not give the missing endpoint comparison; operator-gluing contractibility is not used for our choices. Genauer's embedding argument is used after stabilization, allowing the ambient dimension to increase for a parameter family, not as a claim of weak contractibility in a fixed finite dimension.

The unbounded construction in `ChOfFlow.tex` remains outside this bounded argument. Existing unrelated suspension-typo and convergence TODOs are not certified by this review. No new hypotheses or strengthened claims were added; the substantive change is the relative proof of realization and the more accurate status of the algebraic comparison.

Verification: mathematical dependency review, source locators, dimensions and boundary cases, LaTeX environment/label/citation checks, and diff review. Compilation deliberately omitted. No completion boxes checked.

## Historical audit of `ChModels_old.tex`

The old file is not the active source, but it preserves the most explicit version of the original permutohedron/spine-cube argument. It should remain available because it records the motivation and several possible lemmas that may be useful in the rewrite.

Its main mathematical ingredients are:

1. In the rigidified simplicial model of the cube, mapping simplicial sets are described by ordered partitions and geometrically realized by permutohedra.
2. The boundary decomposition of a permutohedron into products of smaller permutohedra models composition through an intermediate object.
3. Spine cubes are obtained by collapsing or localizing off-spine objects, giving a cubical presentation of coherent chain complexes.
4. The half-cube, half-permutohedron, and diagonal isolate the pieces relevant to composing two maps.
5. Contractibility of mapping spaces through off-spine objects explains why only the corner contributes nontrivially.
6. A horn filling produces the comparison between the corner contribution (composition through the middle object) and the diagonal contribution (the desired composite).

The old draft is not ready to use verbatim. It contains TODOs, inconsistent indexing and notation, informal claims about contractibility, and a long geometric route without a single sharply stated comparison theorem. The active `ChModels.tex` already reorganizes some of this material around flow modules and flattening.

Use `ChModels_old.tex` for three purposes:

- recover a precise lemma if the active draft deleted an important explanation;
- test whether the enriched/coend proposal genuinely captures the higher coherence encoded by the permutohedra;
- explain, if necessary, why a small spine-cube or permutohedron comparison lemma remains in the final proof.

Do not maintain both versions as parallel manuscript sections. The default source hierarchy is:

\[
\text{`ChModels.tex\'} \quad\longrightarrow\quad
\text{`Ignore/ChModels_old.tex\'} \quad\longrightarrow\quad
\text{`research/archived-drafts/CompInTop.tex\'}.
\]

The first is the active draft, the second is the historical detailed draft, and the third is an incomplete earlier fragment.

### Specific questions for the rewrite

- Can the mapping objects represented by the permutohedra be replaced by, or recognized as, cofibrant enriched mapping objects?
- Does the coend or derived coend recover the permutohedron boundary decomposition?
- Is the corner/diagonal homotopy simply the bar-construction comparison between composition and the composite?
- If not, what exact coherence is lost by passing to a strict enriched model?
- Which statements from the old file need independent proof or citation before they can be reused?

## Exact deliverable to formulate first

Before choosing a model, write a self-contained target proposition specifying:

1. the source and target coherent chain complexes (or modules);
2. the two composable morphisms and the model used for them;
3. the categorical composition operation;
4. the geometric flow-module or bimodule composition obtained by gluing;
5. the Pontryagin--Thom comparison map;
6. whether the comparison is equality, a canonical equivalence, or a specified coherent homotopy;
7. the amount of naturality and associativity actually used later.

This proposition should be no stronger than what the differential theorem requires.

## Preferred proof route to test

### A. Enriched model

- Identify a topologically or simplicially enriched category presenting the relevant $\infty$-category of coherent chain complexes.
- Describe its mapping objects explicitly.
- Determine whether the chosen source/indexing objects are cofibrant (for example, as enriched representables, cellular objects, or a topological computad).
- State the model-categorical result that allows these objects to calculate derived mapping spaces without an additional replacement.

### B. Composition as a coend

For a right module $W$ and a left module $V$ over the relevant enriched indexing category, test whether composition is represented by an enriched tensor product
\[
W\otimes_{\mathcal J}V
  = \int^{j\in\mathcal J} W(j)\otimes V(j).
\]

Then answer:

- Is the ordinary coend already homotopy invariant because one input is cofibrant?
- If not, which bar construction or derived coend is needed?
- Does the concrete boundary colimit defining the glued manifold present this same (derived) coend?
- What is the minimum cofibrancy/properness hypothesis needed for that identification?

### C. Pontryagin--Thom compatibility

Prove the comparison from standard functorial properties wherever possible:

- products correspond to smash products;
- restriction to faces corresponds to boundary structure;
- collapse maps are compatible with the structure maps;
- the colimit/coend relation yields the collapse map for the glued manifold.

Isolate any smoothing or neat-embedding choice in one geometric lemma and record the contractibility or independence statement actually needed.

## Decision about spine cubes

Do not begin by rebuilding the full spine-cube formalism. First test the enriched/coend route above.

After that test, record one of these outcomes:

- **Unnecessary:** remove spine cubes from the proof.
- **Supporting lemma:** retain only a short comparison lemma that identifies the concrete model with the enriched mapping object.
- **Essential:** explain precisely which coherence cannot be encoded by the enriched/coend formulation alone.

The older observation that strict enriched natural transformations may miss higher coherence is a real constraint; the new proof must address it rather than assume strict composition is sufficient.

## Separation of responsibilities between sections

A likely final organization is:

- `ChModels.tex`: the categorical model, mapping spaces, cofibrancy, derived composition, and an abstract composition proposition.
- `DiffOfFlowCat.tex`: the geometric gluing construction, Pontryagin--Thom compatibility, and the spectral-sequence differential theorem.

Definitions should live once and be referenced, not restated.

## Completion criteria

The rewrite is complete when:

- the target proposition is explicit and exactly sufficient for the application;
- each model-categorical hypothesis is stated and cited or proved;
- the geometric colimit is identified with the categorical composition;
- choices of smoothing and embeddings are controlled;
- duplicate prose and obsolete models are removed;
- `main.tex` compiles and the relevant cross-references resolve;
- the result has been reviewed before the README checklist is updated.

# Composition and gluing rewrite

## Goal

Replace the current multi-stage proof with a short, rigorous explanation that composition of coherent chain-complex maps corresponds, under the Pontryagin--Thom construction, to gluing the relevant manifolds with corners.

The issue is not doubt about the result. The issue is that the current presentation is duplicated and routes through more one-categorical and spine-cube machinery than may be necessary.

## Current source assessment

- \`ChModels.tex\` is the primary algebraic draft. It contains the fuller development of spine cubes, cone categories, flattening, and composition.
- \`DiffOfFlowCat.tex\` is the primary geometric draft. It contains the punctured-cube colimit, gluing construction, comparison statement, and the application to differentials, but also repeats material and contains unfinished passages.
- \`archived-drafts/CompInTop.tex\` is an incomplete earlier start. It introduces horn filling and rigidification and then stops during the definition of a spine cube. No completed result in it currently needs to be restored.
- Relevant exploratory notes include [\`../Ignore/A note on models.md\`](../Ignore/A%20note%20on%20models.md), [\`../Ignore/Models - summary.md\`](../Ignore/Models%20-%20summary.md), and [\`../Ignore/why-move-to-longer-cubes.md\`](../Ignore/why-move-to-longer-cubes.md).

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

- \`ChModels.tex\`: the categorical model, mapping spaces, cofibrancy, derived composition, and an abstract composition proposition.
- \`DiffOfFlowCat.tex\`: the geometric gluing construction, Pontryagin--Thom compatibility, and the spectral-sequence differential theorem.

Definitions should live once and be referenced, not restated.

## Completion criteria

The rewrite is complete when:

- the target proposition is explicit and exactly sufficient for the application;
- each model-categorical hypothesis is stated and cited or proved;
- the geometric colimit is identified with the categorical composition;
- choices of smoothing and embeddings are controlled;
- duplicate prose and obsolete models are removed;
- \`main.tex\` compiles and the relevant cross-references resolve;
- the result has been reviewed before the README checklist is updated.

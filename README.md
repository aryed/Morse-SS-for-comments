# Spectral Sequences of Flow Categories

This repository contains a working draft of a paper constructing spectral sequences from structured flow categories and describing their differentials geometrically.

The mathematical direction is established, but the manuscript is still being reorganized. The main immediate goals are to replace an overly complicated composition/gluing proof and to choose a genuinely computable Grassmannian example. Global English editing, the abstract, and the introduction come later.

AI collaborators should first read [`AGENTS.md`](AGENTS.md).

## Manuscript status

| Status | Files | Current treatment |
| --- | --- | --- |
| Working baseline | `Ch&Fil.tex`, `SSofCh.tex`, `Mfld w. corners & ffcat.tex`, `ChOfFlow.tex`, `StrFF-via spaces diagrams.tex` | Keep in the compiled draft. These provide the current framework and are not the first target of structural rewriting, although local gaps and TODOs remain. |
| Active rewrite | `ChModels.tex`, `DiffOfFlowCat.tex` | Reorganize the algebraic composition model and the comparison between composition and gluing. Remove duplication and make the proof architecture explicit. |
| Later exposition pass | `softIntro.tex`, the abstract in `main.tex`, and prose throughout | Rewrite after the main proof and final example are stable. |
| Archived draft | `research/archived-drafts/CompInTop.tex` | Incomplete duplicate formerly compiled before `ChModels.tex`. It contains no completed argument not already developed more fully in the active draft, but remains available for reference. |
| Exploratory notes | `Ignore/` and `NotebookLM/` | Research material, older drafts, and references. Consult when useful; do not treat these as manuscript sections. |

This is a workflow classification, not a claim that every statement in a baseline file has received a final proofread.

## Progress checklist

Only mark an item complete after reviewing the result and performing the relevant verification (including compiling after LaTeX changes).

### 1. Composition and gluing rewrite

Detailed plan: [`research/composition-rewrite-plan.md`](research/composition-rewrite-plan.md)

- [x] Identify the duplicate model sections and choose `ChModels.tex` as the active source.
- [x] Remove `CompInTop.tex` from the compiled manuscript and preserve it as an archived draft.
- [ ] State precisely the composition/gluing comparison theorem needed by the differential argument.
- [ ] Make a dependency map separating categorical composition, geometric gluing, and Pontryagin--Thom compatibility.
- [ ] Test whether cofibrant enriched mapping objects make ordinary coends compute the required derived composition.
- [ ] Decide whether spine cubes are unnecessary, a supporting lemma, or essential.
- [ ] Rewrite `ChModels.tex` and remove overlap with `DiffOfFlowCat.tex`.
- [ ] Compile and review the complete rewritten argument.

### 2. Grassmannian example and coefficients

Detailed plan: [`research/grassmannian-example-plan.md`](research/grassmannian-example-plan.md)

- [ ] Record exactly which coefficient spectra are formally allowed by the current (M\mathcal X\to A) construction.
- [ ] Compare candidate Grassmannians together with their natural tangential structures.
- [ ] Compare bordism theories, complex-oriented theories, (K)-theory, and sphere-spectrum truncations by both computability and geometric detectability.
- [ ] Determine what additional justification is needed for coefficients whose classes are not represented directly by the chosen bordism theory.
- [ ] Choose the smallest example that exhibits a nontrivial, computable differential.
- [ ] Work out the Morse data, compactified flow manifolds, tangential structures, and class detection in a separate draft.
- [ ] Integrate the example into the paper only after the pilot computation is checked.

### 3. Exposition and final organization

- [ ] Classify remaining TODOs as mathematical, structural, citation, or prose tasks.
- [ ] Remove remaining duplicated passages.
- [ ] Rewrite the abstract and introduction around the final theorem and example.
- [ ] Perform a section-by-section English and notation pass.
- [ ] Run a final compilation and reference audit.

## Updating progress

When completing a task:

1. review the mathematical result and its scope;
2. compile if any LaTeX source changed;
3. update the relevant plan with decisions or rejected approaches;
4. mark the README checkbox and, when helpful, link the commit or resulting section.

Keep detailed research in the two plan files (or in linked notes), and keep this README as the concise project dashboard.

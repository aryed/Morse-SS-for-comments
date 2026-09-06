# Project instructions

This repository contains a work-in-progress paper on spectral sequences of flow categories. The mathematical claims are intended to be correct, but parts of the manuscript are duplicated, unfinished, or unnecessarily complicated. The current priority is structural clarification, not global copy-editing.

## Working method

1. Read `README.md`, the relevant task plan, and the affected LaTeX sections before editing.
2. Respect the status map in the README: preserve baseline sections unless the task requires changing them; work in active-draft sections; archive abandoned drafts rather than silently deleting their ideas.
3. Understand the definitions, theorem, and proof dependencies before rewriting. Prefer a fresh proof-level rewrite from the mathematical core over sentence-by-sentence editing.
4. For the composition/gluing argument, seek the shortest rigorous model-categorical or topologically enriched formulation. In particular, investigate cofibrant models for mapping objects and composition via enriched coends or derived composition. Do not retain spine-cube machinery merely because it appears in an older draft.
5. For examples, choose the manifold, tangential structure, and coefficient spectrum together. Verify the required map $M\mathcal X\to A$, and distinguish formal change of rings from a geometric method for detecting the resulting classes.
6. Preserve established notation, labels, indexing conventions, and citations unless a change is explicitly justified. Do not silently alter a mathematical claim.
7. After a focused LaTeX edit, compile `main.tex` and check references and warnings relevant to the change.
8. A task is complete only after review and verification. Then update the checklist in `README.md`; do not mark speculative work as done.

## Writing standard

Use concise, conventional mathematical English. State the purpose of a construction before its technical details, avoid duplicated explanations, and use theorem environments appropriately. Leave explicit TODOs for genuine gaps. Abstract and introduction editing should come after the proof architecture and example are stable.

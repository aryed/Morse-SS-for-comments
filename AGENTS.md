# Project instructions

This repository contains a work-in-progress mathematical paper on spectral sequences of flow categories. The claims are intended to be correct; the main problem is duplicated, unfinished, and overcomplicated exposition.

Before working:

- Read [`README.md`](README.md) and the relevant plan in `research/`.
- Consult the active LaTeX source and, when relevant, the historical drafts in `Ignore/`; do not maintain abandoned drafts as parallel manuscript sections.
- Rewrite from the understood mathematical argument, preserving notation, labels, citations, and the intended claims.

Current priorities:

- Simplify the composition/gluing proof. Follow the [composition plan](research/composition-rewrite-plan.md); treat the permutohedron and spine-cube drafts as historical material to test against the enriched/coend approach.
- Develop the Grassmannian example only after choosing the manifold, tangential structure, and coefficient spectrum together. Verify the map $M\mathcal X\to A$ and distinguish formal change of rings from geometric class detection.

After a LaTeX edit, compile `main.tex` and review the result. Update the README checklist and the relevant plan only after the task has been checked. Use concise mathematical English and leave genuine unresolved points as explicit TODOs.

# Arye's AI Communication Style & Project Guidelines

This file captures Arye's preferred mathematical terminology, writing style, pair-programming guidelines, and workflow preferences compiled during our collaborative LaTeX refactoring sessions.

---

## 📐 Terminology & Mathematical Style

1. **Modern Flow Module Vocabulary**:
   * Always transition outdated `(X,r,n,p)-extension` language to the modern language of **right flow modules**, **left flow modules**, and **flow bimodules**.
   * Reframe "extending a category" to "extending a module". Proving survival of a class $L \in E_1$ to page $r+2$ corresponds to extending the right module $W$ from $\fC_{[p, p-r]}$ to $\fC_{[p, p-r-1]}$ by adjoining the null-bordism $W_{p-r-1}$ as the next component. This completely eliminates the need to construct categorical composition charts or verify associativity/un-straightening.

2. **Standard Page-Differential Indexing**:
   * Ensure that the differentials on the pages of the spectral sequence use homologically standard indexing: $d_{r+1}$ (representing shift by $r+1$) instead of the outdated $d_r$.
   * Represent the differential geometrically as the **Toda manifold** (the geometric tensor product/coend $W \circ \flowM_{-, p-r-1}$ of the right flow module $W$ and the left flow module representing the subcategory differential).

3. **Geometric Smoothing over Abstract Categorical Machinery**:
   * Prioritize concrete, explicit geometric smoothing constructions (such as the stereographic projection colimits of boundary diagrams in Lemma 6.4) and clearly relate/compare them to the abstract topologically enriched coends or bar constructions found in modern preprints (e.g. Liam Côté's *Equivariant Floer homotopy via Morse-Bott theory*, arXiv:2309.15089).

4. **Rigorous Morse-Smale Parity Analysis**:
   * For complex manifolds (like the Complex Grassmannian $Gr_{\mathbb{C}}(k, n)$ or Complex Projective Spaces $\mathbb{CP}^\ell$), establish critical point indices, show the vanishing of odd-degree differentials $d_{2m+1}=0$ via parity arguments, and identify the closed 1-dimensional moduli spaces representing even page differentials. Keep these analyses in separate research documents (e.g. `grassmannian_research.md`) until core refactoring steps are verified and compiled.

---

## 💻 Pair Programming & Workflow Style

1. **Incremental, Focused Edits**:
   * Break down complex tasks into the smallest useful steps and address them strictly **one-by-one**. Do not skip ahead or bundle unrelated modifications.
   * If a math terminology shift is ambiguous, verify the exact definitions in preceding chapters (e.g. `Mfld w. corners & ffcat.tex` or `softIntro.tex`) to ensure complete logical consistency.

2. **Compilation and Validation Guarantee**:
   * Always run `pdflatex -interaction=nonstopmode main.tex` (or the local compiler) after each completed set of file modifications to verify there are absolutely no syntax or compilation errors before proceeding.

3. **Active Scholar Reference Selection**:
   * Integrate modern algebraic topology and Floer homotopy preprints into the workspace context. Highlight and selected specific papers (such as Liam Côté, arXiv:2309.15089, and Noah Porcelli & Ivan Smith, arXiv:2401.11766) to add to NotebookLM for deep comparative study.

# TODO List

All `\todo{...}` annotations extracted from the LaTeX source files, with exact file and line references.

---

## `main.tex`

- **Line 180** — `only section names?`  
  *(list of todos in the PDF — should it only show section names?)*

- **Line 186** — `We change the intro to use "flow bimod", now we need to change the rest of the paper`

- **Line 187** — `reuse ThB in the body of the paper`

- **Line 188** — `delete half of the intro`

- **Line 189** — `cite "Massey products in M Sp, and its application"??`

- **Line 217** — `Combine with sec 2.2???`  
  *(subsection "The differential from chain complexes viewpoint" — consider merging with Section 2.2)*

- **Line 222** — `do they???`  
  *(in the paragraph "These concepts are then unified" — verify whether the concepts truly are unified)*

- **Line 233** — `add ref to the "main" Th that gives a geo description for the differential`  
  *(cross-reference missing after "constructed in...")*

---

## `softIntro.tex`

- **Line 122** — `remove this "intuitive conclusion of introduction"?`  
  *(bold heading "Gluing it together." — consider deleting)*

- **Line 148** — `add begin defn?`  
  *(label `def:Xrnp-extension` — the definition environment may be missing its opening)*

- **Line 224** — `write as $\bigcup$`  
  *(an equation should be rewritten using the union symbol)*

- **Line 259** — `Delete everything which is not directly related to flow categories (delete all the Khovanov, Arnold, knots,...)`  
  *(subsection "Relation to other work")*

---

## `Intro2.tex`

- **Line 142** — `write as $\bigcup$`  
  *(same equation as in `softIntro.tex` — rewrite using the union symbol)*

- **Line 182** — `Delete everything which is not directly related to flow categories (delete all the Khovanov, Arnold, knots,...)`  
  *(subsection "Relation to other work" — mirrors the note in `softIntro.tex`)*

---

## `Mfld w. corners & ffcat.tex`

- **Line 345** — `do we need this?`  
  *(Remark `rem:Cat_emb` — check whether the remark is necessary)*

---

## `ChOfFlow.tex`

- **Line 1** — `this definition not worthwhile entire subsec`  
  *(subsection "The Topologically Enriched Category J", label `sec:J` — consider demoting or merging)*

- **Line 97** — `rewrite \cref{con:topChOfCat} as a claim about bounded flow cat`  
  *(extension to unbounded flow categories — the referenced construction should first be stated for bounded ones)*

---

## `ChModels.tex`

- **Line 5** — `take $\op$ instead of $[1]$?`  
  *(definition of an $A$-cube — consider using the opposite category)*

- **Line 12** — `maybe we want $\backslash n$ to be from $1$ and not from $0$ in this context`  
  *(the macro `\n` for the set $\{0,\ldots,n-1\}$ vs. $\{1,\ldots,n\}$)*

- **Line 112** — `what is $3$???`  
  *(figure — a label or value "3" is unexplained)*

- **Line 143** — `encapsulate as lemma / prop`  
  *(a result is stated inline; it should become a numbered lemma or proposition)*

- **Line 425** — `combine this subsection with the prev subsec. This subsec has only one lem and also the prev subsec. Also rewrite the foreword a little bit`  
  *(subsection "Composition in the topological model" — merge with the preceding subsection)*

---

## `StrFF.tex`

- **Line 4** — `ref` *(missing cross-reference for `def:MfldCornersFraming`)*

- **Line 48** — `ref` *(missing cross-reference for `constr:FF_to_Ch`)*

- **Line 113** — `Do we need to work first at $\Top$???`  
  *(lemma — clarify whether the argument must pass through $\Top$ before the general case)*

- **Line 146** — *(commented-out todo)* `can be rewritten more clearly. For example just claim that $c_N \otimes_{M\mathcal{X}} M\mathcal{Y} \simeq c_{N^{\mathcal{Y}}}$ for any manifold $N$`

---

## `StrFF-via spaces diagrams.tex`

- **Line 171** — `un-comment this ThA`  
  *(a theorem is currently commented out and should be restored)*

- **Line 192** — `Re-write the proof`  
  *(lemma at line 192 — the proof needs to be rewritten)*

- **Line 225** — *(commented-out todo)* `can be rewritten more clearly. For example just claim that $c_N \otimes_{M\mathcal{X}} M\mathcal{Y} \simeq c_{N^{\mathcal{Y}}}$ for any manifold $N$`

---

## `HardIntro.tex`

- **Line 90** — `ind?`  
  *(definition of the "realization" of a framed flow category — check whether "ind" (inductive?) should appear)*

- **Line 310** — `Later`  
  *(placeholder; content to be added later)*

---

## `DiffOfFlowCat.tex`

- **Line 14** — `looks ugly`  
  *(definition of composable framed flow categories — typesetting needs to be improved)*

- **Line 115** — `another approach is to factor the structure maps $D(B) \to BO(?)$ through $\ast$, not sure if this is too homotopical`  
  *(alternative proof strategy — decide whether to adopt it)*

- **Line 270** — `add ref to the def in the intro`  
  *(statement about $L \in \Omega^{\mathrm{fr}}_{n-p}$ surviving to the $r$-page — cross-reference the definition in the introduction)*

- **Line 301** — `To do it carefully, we need to find a manifold with corners structure on $N_{s,p-r}$, which can be given by taking $\delta_r(L)$, "cap" it with $N_{s,p-r}$, as manifold with boundary, and "un-straighten" it`  
  *(a step in a proof that is not yet fully rigorous)*

---

## `SSofFFCat.tex`

- **Line 188** — `redundant due to \cref{fig:k-boundary}?`  
  *(Example `exmp:boundary_ffcat` — check whether this example is made redundant by the figure)*

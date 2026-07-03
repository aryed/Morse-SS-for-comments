# Refactoring Plan: Transition to Stable Object Bundles $V_x$

This document outlines the detailed refactoring plan for transitioning the paper from **absolute normal framings of morphism spaces** to **relative stable framings using stable vector spaces $V_x$ assigned to each object $x$** (following the framework of Porcelli–Smith Section 4.3).

---

## Part A: Structural Changes by Section

### 1. Section 3: Manifolds with Corners and Framed Flow Categories
*   [ ] **Definition 3.23 (Normal Framing)**
    *   *Change*: Replace the absolute normal framing definition:
        $$\phi_{y,x}\colon \nu M_{y,x} \simeq M_{y,x} \times \mathbb{R}^{N(|y|-|x|)}$$
        with the relative stable framing definition.
    *   *Implementation*: Associate a stable real vector space $V_x$ to each object $x \in \mathcal{C}$ and define the stable normal framing as a stable isomorphism:
        $$st_{yx}\colon V_y \oplus IM_{y,x} \to V_x$$
        where $IM_{y,x} = TM_{y,x} \oplus \mathbb{R}$ is the abstract index bundle of the morphism manifold, equipped with associative embeddings over the boundary faces.
*   [ ] **Equation (31) (Thom Map Commutativity)**
    *   *Change*: Update the commutativity diagram for neat embeddings and collapse maps.
    *   *Implementation*: Replace the target absolute spheres $S^{N(|z|-|x|)}$ with the Thom spaces (or Thom spectra) of the stable vector spaces: $Th(V_x)$, $Th(V_y)$, and $Th(V_z)$.
*   [ ] **Definition 3.26 (Framed Flow Module)**
    *   *Change*: Update the right flow module framing compatibility.
    *   *Implementation*: Revise the boundary equation $\partial_y \phi_x = \phi_y \oplus \phi_{y,x}$ to align with the relative stable framing isomorphisms.

### 2. Section 4: Chain Complex of a Flow Category
*   [ ] **Construction 4.3 (Topological Chain Complex $K_{\mathcal{C}}$)**
    *   *Change*: Update the spaces in each degree from absolute spheres to relative Thom spaces.
    *   *Implementation*: Redefine the chain complex space at degree $i$ as:
        $$K_{\mathcal{C}}(i) = \bigvee_{|x|=i} Th(V_x)$$
    *   *Morphism maps $g_{y,x}$*: Redefine the mapping spaces to act between these Thom spaces:
        $$g_{y,x}\colon \text{Hom}_{\mathcal{J}}(j, i) \wedge Th(V_y) \to Th(V_x)$$
*   [ ] **Construction 4.5 (Spectra Level Chain Complex)**
    *   *Change*: Replace the uniform desuspension $\Sigma^{-Nb}$ with local desuspensions.
    *   *Implementation*: Desuspend each level by the virtual dimension of the stable vector space $V_x$ rather than a uniform integer.

### 3. Section 6: Differential in a Flow Category
*   [ ] **Lemma 6.4 (Punctured Cube Smoothing)**
    *   *Change*: Update the colimit framing proof.
    *   *Implementation*: Show that the relative stable isomorphisms $V_y \oplus IM_{y,x} \simeq V_x$ glue together smoothly and coherently over the colimit Toda manifold.
*   [ ] **Lemma 6.9 (Chain Equivalence $K_{\mathcal{D} \circ \mathcal{C}} \simeq K_{\mathcal{D}} \circ K_{\mathcal{C}}$)**
    *   *Change*: Redefine the transition maps $f_{z,y}$.
    *   *Implementation*: Update the maps to operate on the Thom spaces $Th(V_x)$ instead of absolute spheres.
*   [ ] **Theorem 6.10 (Spectral Sequence Survival & Differential)**
    *   *Change*: Update the survival and Toda differential proof.
    *   *Implementation*: Adjust the proof to show that survival to page $E_{r+1}$ is equivalent to extending maps into relative Thom spectra rather than absolute spheres.

### 4. Section 7: Tangential Structures and Change of Rings
*   [ ] **Definition 7.2 & 7.4 (Generalization to $\mathcal{X}$-structures)**
    *   *Change*: Re-define structured flow categories and structured modules relatively.
    *   *Implementation*: Define the $\mathcal{X}$-structure relative to the stable vector spaces $V_x$ by framing the abstract index bundles via map factorizations into classifying spaces.

---

## Part B: Morse Flow Category Framing Justification

*   [ ] **Refactor Theorem 3.20 (Morse Flow Category)**
    *   *Description*: Update the Morse-theoretic application in the paper to explicitly construct the stable object spaces $V_x$ and justify their stable relative framings.
    *   *Specification*:
        1.  For a critical point $x$ of a Morse function $f: M \to \mathbb{R}$, define the stable vector space $V_x$ to be the tangent space to the **descending manifold** at $x$, which has dimension equal to the Morse index:
            $$\dim V_x = \text{ind}(x)$$
        2.  Justify that the moduli space of flow lines $M(x, y)$ is the quotient of the transverse intersection of the unstable (descending) manifold $W^u(x)$ and the stable (ascending) manifold $W^s(y)$ by the 1-dimensional $\mathbb{R}$-action of translation:
            $$M(x, y) \times \mathbb{R} \cong W^u(x) \cap W^s(y)$$
        3.  Show that the transversality of this intersection gives a canonical isomorphism of tangent bundles, which yields the relative stable framing:
            $$V_x \oplus T_x \simeq TM(x, y) \oplus \mathbb{R} \oplus V_y$$
            relating the object stable spaces $V_x$ and $V_y$ to the tangent bundle of the moduli space and the translation direction.

---

## Part C: Search and Verification of Other Modifications

*   [ ] **Search for Undocumented Terminology and Index Discrepancies**
    *   *Objective*: Scan the entire LaTeX codebase to search for any other hidden occurrences of absolute framings, sphere collapses, or outdated index conventions that might be affected by adding stable vector spaces $V_x$ to the objects.

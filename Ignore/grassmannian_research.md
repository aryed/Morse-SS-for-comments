# Morse Theory and Spectral Sequences on the Complex Grassmannian $Gr_k(\mathbb{C}^n)$

This research note provides a detailed mathematical analysis of the Morse theory on the complex Grassmannian $Gr_k(\mathbb{C}^n)$ and describes the pages and differentials in the associated spectral sequence of its flow category.

---

## 1. Geometric Setup and Morse Function

Let $Gr_k(\mathbb{C}^n)$ be the complex Grassmannian of $k$-dimensional complex linear subspaces of $\mathbb{C}^n$. This is a compact complex manifold of complex dimension:
$$\dim_{\mathbb{C}} Gr_k(\mathbb{C}^n) = k(n-k), \quad \dim_{\mathbb{R}} Gr_k(\mathbb{C}^n) = 2k(n-k).$$

### The Standard Morse Function
We define a Morse function $f: Gr_k(\mathbb{C}^n) \to \mathbb{R}$ using the projection-operator formulation:
$$f(V) = \text{tr}(P_V Z)$$
where:
*   $P_V: \mathbb{C}^n \to \mathbb{C}^n$ is the orthogonal projection onto the subspace $V \in Gr_k(\mathbb{C}^n)$.
*   $Z: \mathbb{C}^n \to \mathbb{C}^n$ is a Hermitian (or real diagonal) operator with **distinct, strictly increasing eigenvalues**:
    $$\lambda_1 < \lambda_2 < \dots < \lambda_n.$$

---

## 2. Critical Points and Morse Indices

### Location of Critical Points
The critical points of $f$ are isolated and correspond to the fixed points of the action of the maximal torus of $U(n)$ on the Grassmannian. Geometrically, these are the coordinate $k$-planes:
$$V_I = \text{span}\{e_i \mid i \in I\}$$
for subsets $I = \{i_1 < i_2 < \dots < i_k\} \subseteq \{1, \dots, n\}$ of size $k$.
There are exactly $\binom{n}{k}$ such critical points, which matches the Euler characteristic of $Gr_k(\mathbb{C}^n)$.

### Morse Indices
Because $Gr_k(\mathbb{C}^n)$ is a complex manifold and $f$ is a Morse-Bott function whose critical manifolds are isolated points, the Morse indices of all critical points are **always even**.
For a coordinate subspace $V_I$ indexed by $I = \{i_1 < i_2 < \dots < i_k\}$, the real Morse index is given by:
$$\ind(V_I) = 2 \sum_{j=1}^k (i_j - j).$$

> [!NOTE]
> The term $\sum_{j=1}^k (i_j - j)$ is exactly the number of boxes in the Young diagram associated with the Schubert cell $e_I$. It measures the distance of $I$ from the minimal coordinate plane $\{1, \dots, k\}$.

---

## 3. Stable, Unstable, and Flow Manifolds (Richardson Cells)

Let $\phi_t$ be the gradient flow of $-f$ on $Gr_k(\mathbb{C}^n)$.

*   **Unstable Manifold ($W^u(V_I)$)**: The set of points converging to $V_I$ as $t \to -\infty$. This is exactly the **Schubert cell** $e_I$, which is diffeomorphic to $\mathbb{C}^{\sum (i_j-j)} \cong \mathbb{R}^{\ind(V_I)}$.
*   **Stable Manifold ($W^s(V_I)$)**: The set of points converging to $V_I$ as $t \to +\infty$. This is the **opposite Schubert cell** $e^I$, which has real codimension $\ind(V_I)$.
*   **Intersection (Richardson Cell)**: For two subsets $J$ and $I$, the intersection of the unstable and stable manifolds is:
    $$W^u(V_J) \cap W^s(V_I) = e_J \cap e^I \eqqcolon R_{J,I}$$
    where $R_{J,I}$ is the **Richardson cell**.
    *   If $I \not\subseteq J$ (in the sense of the natural partial ordering on subsets), then $R_{J,I} = \varnothing$.
    *   If $I \subseteq J$, then $R_{J,I}$ is a smooth manifold of real dimension $\ind(V_J) - \ind(V_I)$.

### Moduli Space of Flow Lines
The unparameterized moduli space of flow lines from $V_J$ to $V_I$ is the quotient of the Richardson cell by the one-dimensional translation action of the flow:
$$M(V_J, V_I) = R_{J,I} / \mathbb{R}.$$
The real dimension of this moduli space is:
$$\dim M(V_J, V_I) = \ind(V_J) - \ind(V_I) - 1.$$

---

## 4. Analysis of the Spectral Sequence Pages & Differentials

Because all Morse indices $\ind(V)$ are even, we obtain very strong topological restrictions on the differentials of the spectral sequence.

### Page 1 and the First Differential ($d_1$)
The first page of our homological spectral sequence (with coefficients in a tangential structure spectrum $M\cX$) is:
$$E_1^{n,p} = \bigoplus_{\ind(V_I)=p} \Omega^{\cX}_{n-p}.$$

The differential $d_1$ shifts the filtration degree by 1:
$$d_1: E_1^{n,p} \to E_1^{n-1, p-1}.$$
This requires pairs of critical points $(V_J, V_I)$ with $\ind(V_J) - \ind(V_I) = 1$.
However, since all Morse indices are even, the difference $\ind(V_J) - \ind(V_I)$ is **always even**.
Thus, there are **no pairs of critical points with index difference 1**, and the moduli spaces $M(V_J, V_I)$ of dimension $0$ are all **empty**.

> [!IMPORTANT]
> The first differential is identically zero:
> $$d_1 = 0.$$
> Therefore, the second page is isomorphic to the first page:
> $$E_2^{n,p} \simeq E_1^{n,p} = \bigoplus_{\ind(V_I)=p} \Omega^{\cX}_{n-p}.$$

---

### Page 2 and the Second Differential ($d_2$)
The second differential $d_2$ shifts the filtration degree by 2:
$$d_2: E_2^{n,p} \to E_2^{n-1, p-2}.$$
This corresponds to pairs of critical points $(V_J, V_I)$ with index difference $\ind(V_J) - \ind(V_I) = 2$.
For these pairs, the moduli space $M(V_J, V_I)$ has real dimension:
$$\dim M(V_J, V_I) = 2 - 1 = 1.$$

What is the boundary of this 1-dimensional moduli space? The boundary structure is given by:
$$\partial M(V_J, V_I) = \bigcup_{p > r > p-2} M(V_J, V_r) \times M(V_r, V_I).$$
However, the intermediate index $r$ must be $p-1$. Since all Morse indices are even, **there are no critical points of index $p-1$**.
Thus, the union is empty, meaning:
$$\partial M(V_J, V_I) = \varnothing.$$

> [!TIP]
> The 1-dimensional flow moduli spaces $M(V_J, V_I)$ are **closed 1-manifolds** (disjoint unions of circles $S^1$).
> The differential $d_2$ is represented by the framed bordism class of these circles:
> $$d_2(W_p) = \bigsqcup_{\ind(V_I)=p-2} [M(V_J, V_I)] \cdot W_p \in \Omega^{\cX}_1.$$

*   **For Unoriented Bordism ($\cX = \text{O}$)**: Since $\Omega^O_1 = 0$, the circle is null-bordant, so $d_2 = 0$.
*   **For Framed Bordism ($\cX = \text{fr}$ / Stable Homotopy $\mathbb{S}$)**: Since $\Omega^{\fr}_1 \simeq \mathbb{Z}/2$ (generated by the circle with its Lie group framing), the differential $d_2$ can be **non-trivial** if the circles have the non-trivial Lie framing!

---

### Page 3 and the Third Differential ($d_3$)
The third differential shifts the filtration degree by 3:
$$d_3: E_3^{n,p} \to E_3^{n-1, p-3}.$$
This requires pairs of critical points with index difference $\ind(V_J) - \ind(V_I) = 3$.
Since the indices are all even, this difference can never be 3.
$$\dim M(V_J, V_I) = 3 - 1 = 2.$$
However, because the index difference cannot be 3, the differential is:
$$d_3 = 0 \quad \text{trivially}.$$

---

## 5. General Theorem for Odd Differentials

By induction, we can state a very general and elegant theorem for the spectral sequence of the complex Grassmannian:

> [!IMPORTANT]
> **Theorem (Vanishing of Odd Differentials)**
> For the complex Grassmannian $Gr_k(\mathbb{C}^n)$ under the standard Morse function, all odd differentials in the spectral sequence are identically zero:
> $$d_{2m+1} = 0 \quad \text{for all } m \geq 0.$$
> Consequently, non-trivial differentials can only occur on even pages:
> *   $d_2$ (determined by 1-dimensional closed flow manifolds $\approx S^1$)
> *   $d_4$ (determined by 3-dimensional closed flow manifolds $\approx S^3$ or other 3-manifolds)
> *   $d_6$ (determined by 5-dimensional closed flow manifolds)
> *   $\dots$

---

## Summary: What Data Do We Need?

1.  **To compute $E_1$ and $E_2$**: We only need the list of subsets $I \subseteq \{1,\dots,n\}$ of size $k$ and their Morse indices $\ind(V_I) = 2 \sum (i_j-j)$.
2.  **To compute $E_3$ (via $d_2$)**: We need to identify all pairs of subsets $J, I$ such that $I \subseteq J$ and $\sum_{j=1}^k (j_s - i_s) = 1$ (index difference 2). For each such pair, we must determine the number and framing of the circles in the 1-dimensional moduli space $M(V_J, V_I)$.
3.  **To compute $E_4$ and $E_5$ (via $d_3$ and $d_4$)**:
    *   $d_3 = 0$ automatically.
    *   For $d_4$, we need to look at pairs with index difference 4 (filtration shift 4), where the moduli space $M(V_J, V_I)$ is a 3-dimensional manifold. By analyzing its cobordism class in $\Omega^{\cX}_3$, we determine $d_4$.

# Spectral Sequences of Filtered Objects: Convergence

## Part 1: Formal Definitions and Claims

### 1. Spectral Sequence of a Filtered Object
**Claim:** A filtered object in a stable $\infty$-category naturally gives rise to a spectral sequence.
*   **Formal Reference**: Jacob Lurie, *Higher Algebra*, Section 1.2.2 ("Filtered Objects and Spectral Sequences"), Definition 1.2.2.9.

### 2. Strong Convergence for Bounded Filtrations
**Claim**: If the filtration $X(n)$ is bounded below (i.e., $X(n) \simeq 0$ for $n \ll 0$), its associated spectral sequence converges. 
*   **Formal Reference**: Jacob Lurie, *Higher Algebra*, Proposition 1.2.2.14.
*   **Definition of Convergence (from the proof of Prop 1.2.2.14)**: Lurie defines convergence in this bounded context to mean three specific conditions hold:
    1. For fixed $p$ and $q$, the differentials $d_r: E_r^{p,q} \to E_r^{p-r, q+r-1}$ vanish for $r \gg 0$, allowing $E_\infty^{p,q}$ to be defined as the colimit of the resulting epimorphisms.
    2. There exists an exhaustive, bounded-below filtration $F^p A_n$ on the target homotopy groups $A_n = \pi_n \lim_{\rightarrow} X$.
    3. There is an explicit isomorphism $E_\infty^{p,q} \simeq F^p A_{p+q} / F^{p-1} A_{p+q}$.

### 3. Conditional Convergence for Complete Filtrations
**Claim**: If a filtration is unbounded but complete (and exhaustive), its associated spectral sequence is conditionally convergent.
*   **Formal Reference**: J. Michael Boardman, *Conditionally convergent spectral sequences*, Homotopy Invariant Algebraic Structures, Contemporary Mathematics, vol. 239, AMS, 1999, pp. 49–84.
*   **Formal Definition**: (Boardman, Definition 5.10) A spectral sequence conditionally converges to a target if the filtration on the target is exhaustive and complete. Formally, for the unrolled exact couple $D^{s,\bullet}$, this means the limit and the derived limit over the filtering both vanish: $\lim_{\longleftarrow s} D^{s, \bullet} = 0$ and $\lim^1_{\longleftarrow s} D^{s, \bullet} = 0$.

---

## Part 2: Intuitive Explanations and Motivation

### Why Bounded Filtrations give "Strong Convergence"
Lurie's definition of convergence in Proposition 1.2.2.14 is exactly what classical mathematicians refer to as **strong convergence**. 
*   **Motivation**: If a filtration is bounded below, you eventually "run out" of non-zero terms. Therefore, differentials on the spectral sequence pages eventually have nowhere to go, or they come from zero. 
*   **What it buys us**: The spectral sequence pages strictly stabilize (meaning $E_r = E_\infty$ for some finite $r$), making calculations highly predictable. We are perfectly guaranteed that the spectral sequence computes the true graded pieces of the exact target object.

### Why Complete (Unbounded) Filtrations give "Conditional Convergence"
When a filtered object is unbounded (e.g. $K_n \neq 0$ forever), the differentials can continue shifting indefinitely. The spectral sequence never reaches strict stabilization at any finite page.
*   **Motivation**: Classical convergence criteria break down here. "Conditional convergence" was developed by Boardman as a topological safety net. It means that even though the pieces change forever, their limits still behave logically.
*   **What it buys us**: Conditional convergence ensures that the spectral sequence accurately computes the **completion** of the target object. It provides a foundational baseline. However, to upgrade to strong convergence (to ensure you are computing the *true* object and no elements have "escaped to infinity"), one must manually check that certain obstruction groups (like $\lim^1 E_r$) vanish.
*   *(Note on the literature: Relying on conditional convergence for complete filtered spectra is currently viewed as a "folk result" in $\infty$-categorical circles, with robust modern proofs appearing in forthcoming work by Hedenlund, Krause, and Nikolaus).*

### The Physical Meaning of Spectral Sequences and Non-Convergence
Saying "$X$ has a spectral sequence $E$" means the internal structure of $X$ functorially generates an exact couple. The pages $(E_r, d_r)$ are successive algebraic approximations of $\mathrm{gr} H_*(X)$.

Non-convergence does not mean zero connection. When $E$ fails to formally converge to $H_*(X)$, the connection survives in three critical ways:
1.  **Derived Completion**: $E$ always converges to $H_*(\mathrm{holim}_s X / F^s X)$. The gap between this completion and $H_*(X)$ is precisely governed by Milnor $\lim^1$ terms.
2.  **Finite-Step Obstructions**: For any finite $r$, a differential $d_r(a) = b$ retains concrete meaning: the class $a$ extends across $r-1$ filtration strata, but hits the permanent obstruction $b$ at step $r$.
3.  **Higher Operations**: The differentials compute secondary and higher operations (e.g., Massey products) intrinsic to the filtration, regardless of whether a global limit exists.

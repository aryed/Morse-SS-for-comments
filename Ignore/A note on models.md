# Nerve Functors and Model-Category Background

## 1. Models for $(\infty,1)$-Categories

### Definition 1 (Models for Higher Categories)
The theory of $(\infty,1)$-categories can be rigorously formalized via several Quillen equivalent model categories:

- **Simplicial sets**: The category of simplicial sets, $sSet$, equipped with the Joyal model structure, models $(\infty,1)$-categories as quasicategories (weak Kan complexes).
- **Simplicially enriched categories**: The category $sSet\text{-}Cat$ of categories enriched over simplicial sets, equipped with the Bergner model structure.
- **Topologically enriched categories**: The category $Cat_{Top}$ of categories enriched over compactly generated topological spaces, equipped with a model structure transferred from $sSet\text{-}Cat$ via the singular complex functor.

### Proposition 1 (Equivalence of Models)
The model categories of simplicial sets (with the Joyal structure), simplicially enriched categories (with the Bergner structure), and topologically enriched categories are Quillen equivalent.

### Proof
**Assumption.** We assume the standard definitions of the Joyal and Bergner model structures.

**Starting point.** Consider the three respective categories: $sSet$, $sSet\text{-}Cat$, and $Cat_{Top}$.

1. **Topological to simplicial.**
	The adjunction between topological spaces and simplicial sets
   
	$|-| : sSet \rightleftarrows Top : Sing_*$
   
	induces a Quillen equivalence between $Cat_{Top}$ and $sSet\text{-}Cat$.

2. **Simplicial to quasicategories.**
	The homotopy coherent nerve
   
	$N^{hc} : sSet\text{-}Cat \to sSet$
   
	admits a left adjoint (the rigidification functor $\mathfrak{C}$), which forms a Quillen equivalence between the Bergner model structure on simplicial categories and the Joyal model structure on simplicial sets.

**Goal.** Composing these Quillen equivalences proves that all three point-set environments are homotopically equivalent models for the underlying theory of $(\infty,1)$-categories.

## 2. Nerve Functors

### Definition 2 (Nerves)
To transition from rigid categorical structures to the quasicategorical (simplicial set) model of $(\infty,1)$-categories, we define three specific nerve functors:

- **Ordinary nerve ($N$).**
  For an ordinary 1-category $\mathcal{C}$ (not enriched), $N(\mathcal{C})$ is the simplicial set whose $n$-simplices are functors $[n] \to \mathcal{C}$. This models strict, decategorified structures.

- **Homotopy coherent nerve ($N^{hc}$).**
  For a simplicially enriched category $\mathcal{C}_\bullet$, $N^{hc}(\mathcal{C}_\bullet)$ is a simplicial set that encodes higher homotopies present in the simplicial hom-spaces. If $\mathcal{C}_\bullet$ is locally Kan, $N^{hc}(\mathcal{C}_\bullet)$ is a quasicategory.

- **Topological nerve ($N^{top}$).**
  For a topologically enriched category $\mathcal{C}$, the topological nerve is defined by
  
  $N^{top}(\mathcal{C}) = N^{hc}(Sing_*(\mathcal{C})).$
  
  This operation first converts the topological enrichment to a simplicial enrichment by applying the singular complex functor level-wise, and then applies the homotopy coherent nerve.

## 3. Model Structure on Topologically Enriched Categories

To perform homotopy theory directly on topologically enriched categories, we use a model structure transferred from the Bergner model structure on simplicial categories. In this framework, the weak equivalences are Dwyer-Kan equivalences.

The most important feature for applications is the characterization of cofibrant objects. In this model structure, a topologically enriched category is cofibrant if it is a **topological computad** (a cellular category).

Informally, this means the category is built iteratively by freely adjoining topological cells (parameter spaces) to mapping spaces. Crucially, in a cofibrant category one does not impose strict algebraic relations (for example, declaring a specific composition strictly equal to a basepoint). Instead, higher-dimensional topological cells are attached to provide continuous paths and homotopies that mediate compositions.

## 4. Cofibrancy of the Flow Category $\mathcal{J}$

The Cohen-Jones-Segal flow category $\mathcal{J}$ is an archetype of a cofibrant topologically enriched category.

Its mapping spaces $J(n,m)_+$ are defined as one-point compactifications of spaces of unparameterized gradient flow trajectories. Since the uncompactified space is

$J(n,m) \cong \mathbb{R}_{\ge 0}^{n-m-1},$

for $n-m-1>0$, the compactified spaces $J(n,m)_+$ are homeomorphic to topological disks $D^{n-m-1}$ with collapsed boundary subspaces. In the boundary case $n-m-1=0$, one has $J(n,m)\cong \mathbb{R}_{\ge 0}^{0}=\{*\}$ and hence $J(n,m)_+\cong S^0$.

The composition law in $\mathcal{J}$ corresponds to concatenation (gluing) of broken flow trajectories. Geometrically, this maps formal compositions of lower-dimensional moduli spaces continuously into the broken boundary of the higher-dimensional disk $J(n,m)_+$.

Because $\mathcal{J}$ is built by freely attaching these disks to resolve broken-flow relations, rather than algebraically crushing relations to a point, it satisfies the definition of a topological computad. Consequently, $\mathcal{J}$ is projectively cofibrant.

## 5. Equivalence of Functor Categories

### Proposition 2 (Strict vs. $\infty$-Functors)
Let $\mathcal{J}$ be the topologically enriched flow category and $Sp^O$ (orthogonal spectra) the full subcategory of fibrant-cofibrant orthogonal spectra. Because $\mathcal{J}$ is cofibrant in $Cat_{Top_*}$, the underlying $\infty$-category of the strict topologically enriched functor category

$\operatorname{Fun}_{Top_*}(\mathcal{J}, Sp^O\text{ (orthogonal spectra)})$

is equivalent to the $\infty$-category

$\operatorname{Fun}_{\infty}(N^{top}(\mathcal{J}), \mathcal{S}p).$

### Proof
**Assumption.** By Lurie, *Higher Topos Theory* (Theorem 4.2.4.4), if a simplicially enriched category $\mathcal{C}$ is cofibrant in the Bergner model structure, then the simplicial nerve of the category of fibrant-cofibrant enriched functors $\operatorname{Fun}_{sSet}(\mathcal{C},\mathcal{M})^\circ$ is equivalent to

$\operatorname{Fun}_{\infty}(N^{sSet}(\mathcal{C}), \mathcal{M}_\infty).$

This transfers to $Cat_{Top}$ via the Quillen equivalence from Proposition 1.

**Starting point.** Consider the strict enriched functor category $\operatorname{Fun}_{Top_*}(\mathcal{J}, Sp^O\text{ (orthogonal spectra)})$.

1. **Resolution requirement.**
	In model category theory, to compute the derived mapping space out of a source object $A$, one typically replaces $A$ by a cofibrant replacement $Q(A) \xrightarrow{\simeq} A$.

2. **Cofibrancy condition.**
	As established above, $\mathcal{J}$ is already a topological computad and hence cofibrant in $Cat_{Top_*}$. Therefore, $Q(\mathcal{J}) = \mathcal{J}$.

**Goal.** Since $\mathcal{J}$ is intrinsically cofibrant, no further free resolution is required. Strict topological functors out of $\mathcal{J}$ already carry the topological parameter spaces (the disks $J(n,m)_+$) needed to model higher coherent homotopies (for example, a nullhomotopy witnessing $d^2 \simeq 0$). Therefore, the strict functor category computes the correct derived mapping spaces, yielding

$\operatorname{Fun}_{Top_*}(\mathcal{J}, Sp^O\text{ (orthogonal spectra)}) \simeq \operatorname{Fun}_{\infty}(N^{top}(\mathcal{J}), \mathcal{S}p).$
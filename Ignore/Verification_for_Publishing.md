<!-- 
Format:
- **Title**: [Issue Title]
- **What was the problem**: [Description of the original issue or ambiguity]
- **What we have done**: [Summary of the changes made to the paper to resolve it]
- **What we need to verify**: [Specific technical or mathematical details that need a final sanity check before publishing]
-->

# Pre-Publication Verification Checklist

- **Title**: Spectral Sequence Convergence (Conditional vs. Strong)
- **What was the problem**: The original main theorems (Theorems A and B) stated that the spectral sequences converged to the target without specifying the required boundedness conditions. Additionally, Theorem 2.4 loosely used the term "complete" instead of the strictly required "bounded below" for Lurie's strong convergence.
- **What we have done**: We restructured the theorems to explicitly declare *(conditional)* convergence as the baseline. We added formal Corollaries and Remarks establishing that: (1) if the input is bounded from below, we obtain *strong convergence* via Lurie 1.2.2.14, and (2) if the input is unbounded, the construction still yields an exact couple that *conditionally converges* via Boardman 1999 Def 5.10 (leveraging the Milnor exact sequence).
- **What we need to verify**: 
  - *All points under this issue have been mathematically verified using Boardman 1999 (Def 5.10 / Thm 7.3) and Lurie (Prop 1.2.2.14) via NotebookLM! The Milnor exact sequence flawlessly translates $\infty$-categorical completeness ($\holim F_p \simeq \zr$) into the vanishing of both classical limits, perfectly satisfying Boardman's condition for conditional convergence.*
  1. Search across the entire paper to verify if we found all the places that we need to add or update this change (and verify that we have good wording and proofs if needed).

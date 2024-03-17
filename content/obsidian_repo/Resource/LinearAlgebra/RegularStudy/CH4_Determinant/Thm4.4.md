---
Definition: 
Theorem: true
Corollary: 
Lemma: 
Related link:
---

## Contents

# Theorem 4.4

The determinant of a square matrix can be evaluated by cofactor expansion along any row. That is, if $A \in M_{n \times n}(F)$, then for any integer $i$ (1 ≤ $i$ ≤ $n$),

$$
\text{det}(A) = \sum_{j=1}^{n} (-1)^{i+j} A_{ij} \cdot \text{det}(A_{ij}).
$$

## Proof

Cofactor expansion along the first row of $A$ gives the determinant of $A$ by definition. So the result is true if $i = 1$. Fix $i > 1$. Row $i$ of $A$ can be written as $\sum_{j=1}^{n} A_{ij} e_j$. For 1 ≤ $j$ ≤ $n$, let $B_j$ denote the matrix obtained from $A$ by replacing row $i$ of $A$ by $e_j$. Then by Theorem 4.3 and the lemma, we have

$$
\text{det}(A) = \sum_{j=1}^{n} A_{ij} \text{det}(B_j) = \sum_{j=1}^{n} (-1)^{i+j} A_{ij} \cdot \text{det}(A_{ij}).
$$

## Corollary

If $A \in M_{n \times n}(F)$ has two identical rows, then $\text{det}(A) = 0$.

### Proof

The proof is by mathematical induction on $n$. We leave the proof of the result to the reader in the case that $n = 2$. Assume that for some integer $n \geq 3$, it is true for $(n - 1) \times (n - 1)$ matrices, and let rows $r$ and $s$ of $A \in M_{n \times n}(F)$ be identical for $r \neq s$. Because $n \geq 3$, we can choose an integer $i$ (1 ≤ $i$ ≤ $n$) other than $r$ and $s$. Now

$$
\text{det}(A) = \sum_{j=1}^{n} (-1)^{i+j} A_{ij} \cdot \text{det}(A_{ij})
$$

by Theorem 4.4. Since each $\widetilde{A}_{ij}$ is an $(n - 1) \times (n - 1)$ matrix with two identical rows, the induction hypothesis implies that each $\text{det}(\widetilde{A}_{ij}) = 0$, and hence $\text{det}(A) = 0$. This completes the proof for $n \times n$ matrices, and so the lemma is true for all square matrices by mathematical induction.

---





## Related



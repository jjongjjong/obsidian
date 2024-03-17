---
Definition: 
Theorem: true
Corollary: 
Lemma: 
Related link:
---

## Contents
---

**Theorem 5.2.** Let $A \in M_{n \times n}(F)$. Then a scalar $\lambda$ is an eigenvalue of $A$ if and only if $\text{det}(A - \lambda I_n) = 0$.

**Proof.** A scalar $\lambda$ is an eigenvalue of $A$ if and only if there exists a nonzero vector $v \in F^n$ such that $Av = \lambda v$, that is, $(A - \lambda I_n)(v) = 0$. By Theorem 2.5 (p. 71), this is true if and only if $A - \lambda I_n$ is not invertible. However, this result is equivalent to the statement that $\text{det}(A - \lambda I_n) = 0$.

---

> [!NOTE]
> 여기서 주의해야할 포인트는 linear operator $A$가 invertible하다고 하지는 않음.  그러나 명확한 것은 $A$의 eigen vector와 value가 있다면  $(A-\lambda I_n)$ 는 invertible하다는 것이다. 


## Questions
## Related
- [ ] #todo #math Thm 2.5


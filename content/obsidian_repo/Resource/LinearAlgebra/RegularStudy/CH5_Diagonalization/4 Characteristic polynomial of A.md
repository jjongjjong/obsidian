---
Definition: true
Theorem: 
Corollary: 
Lemma: 
Related link:
---


## Contents


$$
\begin{gather*}
A\in M_{n}(F) \\
\phi_{A}(t):=Det(\lambda I-A) \\
this \; is \; chrateristic \;polynormial \; of \; A

\end{gather*} 
$$
**Definition.** Let $A \in M_{n \times n}(F)$. The polynomial $f(t) = \text{det}(A - tI_n)$ is called the characteristic polynomial of $A$.

Theorem 5.2 states that the eigenvalues of a matrix are the zeros of its characteristic polynomial. When determining the eigenvalues of a matrix or a linear operator, we normally compute its characteristic polynomial, as in the next example.


---

**Definition.** Let $T$ be a linear operator on an $n$-dimensional vector space $V$ with ordered basis $\beta$. We define the characteristic polynomial $f(t)$ of $T$ to be the characteristic polynomial of $A = [T]_{\beta}$. That is,

$$
f(t) = \text{det}(A - tI_n).
$$

The remark preceding this definition shows that the definition is independent of the choice of ordered basis $\beta$. Thus if $T$ is a linear operator on a finite-dimensional vector space $V$ and $\beta$ is an ordered basis for $V$, then $\lambda$ is an eigenvalue of $T$ if and only if $\lambda$ is an eigenvalue of $[T]_{\beta}$. We often denote the characteristic polynomial of an operator $T$ by $\text{det}(T - tI)$.

---


## Questions
- [ ] #todo #math 왜 책에서는 같은 정의를 두번이나 써놓은걸까? 
## Related
[[3 Thm 5.2]]


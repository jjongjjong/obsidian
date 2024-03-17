---
Definition: true
Theorem: 
Corollary: 
Lemma: 
Related link:
  - "#todo_thm4.4"
---

## Contents
A linear operator $T$ on a finite-dimensional vector space $V$ is called *diagonalizable* if there is an ordered basis $\beta$ for $V$ such that $[T]_{\beta}$ is a diagonal matrix. A square matrix A is diagonalizable if $L_{A}$ is diagonalizable. 

- "대각화 가능한" 이라는 수식어의 대상은 linear operator $T$이다.  
- $[T]_{\beta}$가 diagonal matrix가 되는 ordered basis $\beta$가 존재한다면 diagonalizable이라고 부르게 되는거지
- 그런데 isomorphism으로 인해 matrix $A$ 차원에서도 $L_{A}$가 diagonalizable하면 matrix $A$도 diagonalizable이라고 할 수 있음.  


$$
\begin{align*}
& A\in M_{n}(F) \; is \; diagnalizable\\
& \Leftrightarrow \sideset{_{}^{\exists}}{}{Q,D} \in  M_{n}(F),\; D:diagonal \; s.t. \; A=Q^{-1}DQ
\end{align*}
$$

### Remark
$$
\begin{align*}
& A^{k}= (QDQ^{-1})^{k} =QD^kQ^{-1}\\
& Rank(A)=Rank(QD^kQ^{-1})=Rank(D)
\end{align*}
$$



## Related
- [ ] #todo #math Thm_4.4
- [ ] #todo #math 합성의 rank

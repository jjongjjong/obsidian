---
Definition: 
Theorem: true
Corollary: 
Lemma: 
Related link: 
---

## Contents
**Theorem 5.1**
A linear operator $T$ on a finite-dimensional vector space $V$ is diagonalizable if and only if **there exists an ordered basis $\beta$ for $V$ consisting of eigenvectors of $T$**. 

> [!NOTE]
> $T$의 eigen vectors들은 다양할 수 있다. 그러나 eigen vector들이 $V$를 span하는 것을 보장하지 못한다. 그렇기 때문에 T의 eigen vector들로 V의 basis를 구성할 수 있다면 비로소 $T$는 diagonalizable이라고 할 수 있다. 

Furthermore, if $T$ is diagonalizable, $\beta = \{v_1, v_2, ..., v_n\}$ is an ordered basis of eigenvectors of $T$, and $D = [T]_\beta$, then $D$ is a diagonal matrix and $D_{jj}$ is the eigenvalue corresponding to $v_j$ for $1 \leq j \leq n$.

>[!NOTE]
> $T$를 eigen vectors $\beta$로 표현한 $D=[T]_\beta$는 각 eigenvector에 대응하는 eigen value로 구성된 대각행렬로 표현된다. 

To diagonalize a matrix or a linear operator is to find a basis of eigenvectors and the corresponding eigenvalues.

Before continuing our study of the diagonalization problem, we consider three examples of eigenvalues and eigenvectors.

Example 1

Let
$$
A = \begin{pmatrix}
1 & 3 \\
4 & 2 \\
\end{pmatrix}, \quad v_1 = \begin{pmatrix}
1 \\
-1 \\
\end{pmatrix}, \quad \text{and} \quad v_2 = \begin{pmatrix}
3 \\
4 \\
\end{pmatrix}.
$$

Since
$$
L_A(v_1) = \begin{pmatrix}
1 & 3 \\
4 & 2 \\
\end{pmatrix} \begin{pmatrix}
1 \\
-1 \\
\end{pmatrix} = \begin{pmatrix}
-2 \\
2 \\
\end{pmatrix} = -2 \begin{pmatrix}
1 \\
-1 \\
\end{pmatrix} = -2v_1,
$$

$v_1$ is an eigenvector of $L_A$, and hence of $A$. Here $\lambda_1 = -2$ is the eigenvalue corresponding to $v_1$. Furthermore,
$$
L_A(v_2) = \begin{pmatrix}
1 & 3 \\
4 & 2 \\
\end{pmatrix} \begin{pmatrix}
3 \\
4 \\
\end{pmatrix} = \begin{pmatrix}
15 \\
20 \\
\end{pmatrix} = 5 \begin{pmatrix}
3 \\
4 \\
\end{pmatrix} = 5v_2,
$$

and so $v_2$ is an eigenvector of $L_A$, and hence of $A$, with the corresponding eigenvalue $\lambda_2 = 5$. Note that $\beta = \{v_1, v_2\}$ is an ordered basis for $\mathbb{R}^2$ consisting of eigenvectors of both $A$ and $L_A$, and therefore $A$ and $L_A$ are diagonalizable. Moreover, by Theorem 5.1,

$$
[L_A]_\beta = \begin{pmatrix}
-2 & 0 \\
0 & 5 \\
\end{pmatrix}.
$$




## Questions
- 이건 미리 주어졌으니 확인한거지만, 만약 $T$의 eigenvector를 찾으려면 어떻게 해야할까? 
## Related



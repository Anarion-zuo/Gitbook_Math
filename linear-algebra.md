# Linear Algebra

$I$ for identity.

## Factorization into $A=LU$

To transform a matrix $A$ from itself to an upper triangular form $U$, we apply to it a series of row transformation, which can be represented as:
$$
EA=U
$$
where $E$ is a elementary matrix and $U$ is the result of Gaussian elimination. Take $L=E^{-1}$, $A=LU$, where $L$ would always be a lower triangular matrix. Moreover, $E$ can be a product of a series of elementary matrices, $E=E_n,...,E_1$. Hence, $L=E_1^{-1},...,E_n^{-1}​$.

The reason of $L$ always being lower triangular matrix is if we want to have $U$ transformed back to $A$, which is done by multiplying $L$, we cannot have upward row transformations. Hence, for an elementary matrix implementing this kind of transformation, it is the result of identity putting its 1s downward.

### Permutations

There are $n!$ ways for $I_n$ to permute its rows. For each of the permutation matrices, $P^{-1}=P^T$. We use $P$ for identity matrix with reordered rows. In order to have non-zero numbers to be dealt with when performing elimination, we set the ones with 0 in front to the bottom. Hence, the process of Gaussian elimination is represented as:
$$
PA=LU
$$

### Transpose

For permutation matrices,
$$
PP^T=I
$$
Define a symmetric matrix to be:
$$
A=A^T
$$


Therefore, for all matrices, there is always $AA^T$ or $A^TA​$ is symmetric.

## Vector Space

A vector space is a set of vectors. $R^n$ consists of all vectors with n real components.

### Construction

- Closed for multiplication and addition. Hence, at least forms a line.
- Closed for scalar multiplication.
- (Quick way of saying) Closed for all linear combination.

### Subspaces

Some vectors inside a space, which still make their own vector space, and closed for all linear combinations.

- All of the original space.
- Any line through 0.
- Only 0.
- All of the linear combination of 2 linearly independent vectors.

The union of two different subspaces does not necessarily form a subspace. The intersection of any two different subspaces forms a subspace.

### Linear System’s Point of View

$$
Ax=b
$$

When $b$ is one of the column vector of $A$, the solution is something like $(0,...,1,...,0)^T$. Furthermore, the system is solvable exactly when $b​$ is in the column space.

For the Null space. When $b=0$, the solution of the equation gives a null space inside the column space of $A$. Furthermore, the solution of a equation $b=0$ always gives a subspace.
$$
Av=0,Aw=0\Rightarrow A(v+w)=0,Aav=0\Rightarrow a(Av)=0
$$

### Null Space

$$
Ax=0
$$

For a homogeneous equation, as is mentioned above, the solution always gives a subspace of the column space of $A$, called the null space. Any vector within the null space of $A$ has no effect when having operation upon other vectors within the column space of $A$ in the column space of $A$.
$$
A(x_p+x_n)=Ax_p
$$


 The number of dimension of the subspace depends on the rank of $A$, $d=n-r$. If we continue the process of permutation when doing Gaussian elimination, we would get the RREF form of $A$.
$$
R=\begin{pmatrix}I&F\\O&O\end{pmatrix},\begin{pmatrix}I&F\end{pmatrix}\begin{pmatrix}x_{pivot}\\x_{free}\end{pmatrix}=O
$$
where $I$ is unit submatrix part formed by the free columns, and $F$ is given by the pivot columns. The $I$ and $F$, $x_{pivot}$ and $x_{free}​$ may get mixed up. The matrix consisting of the solution of the equation is:
$$
N=\begin{pmatrix}-F\\I\end{pmatrix}
$$
Obviously,
$$
RN=O
$$
When $b\ne0$, the solution is not a subspace, while it is the subspace moved and going through the particular solution.

### Full Rank

#### Full Column Rank $r=n$

- No free variable.
- $x=x_p$, unique solution if exists.

$$
R=\begin{pmatrix}I\\O\end{pmatrix}
$$



#### Full Row Rank $r=m$

- For every $b$ solvable.
- $n-m$ free variables.

$$
R=\begin{pmatrix}I&F\end{pmatrix}
$$

#### $n=m=r$

- Invertible matrix
- For every $b$ solvable

$$
R=I
$$

The cases of not full rank is simply adding $O$s to $R$.

### Dependence and Independence

Independence term:
$$
\exist c_n\not\equiv0,c_1x_1+...+c_nx_n=0
$$
Zero vector is dependent with any other vector.

Repeat when $v_1,...,v_n$ are columns of $A$,

- They are independent if null space of $A$ contains only $0$. $rank=n$
- They are dependent if $Ac=0$ for some non-zero $c$. $rank<n$

For some set of vectors, we can say that they together span a space, containing all of their linear combinations. We have a special kind of set of vectors that are independent and may form a Basis of the space. Hence, the definition of basis is:

- They are independent.
- They span a space.

Every basis of the same space has the same number of vectors, which is defined to be the dimension of the space. The dimension of the column space is the column rank of the matrix, obviously.

### Four Fundamental Subspaces

- Column space $C(A)$
- Null space $N(A)$
- Row space/Column space of $A$ transpose $C(A^T)$
- Null space of $A$ transpose/Left null space $N(A^T)$

|           | $C(A)$        | $N(A)$   | $C(A^T)$      | $N(A^T)$ |
| --------- | ------------- | -------- | ------------- | -------- |
| Basis     | Pivot columns | Solution | Pivot columns | Solution |
| Dimension | $r$           | $n-r$    | $r$           | $m-r$    |

## Matrix Space

The same rules for vector space can be applied to matrices, thus forms matrix space. The basis and dimension of the matrix space has the same definition also. For a matrix space of general $m\times n$ matrices, the dimension of the matrix is simply $mn$, for the space can be based on matrices with a single 1 and all others 0.

### Sum

The sum of 2 matrix space consists of the union of the spaces and all of the combination of all of the matrices in the space, thus forms a subspace.

### Rank One Matrix

For any matrix with rank 1, it can be partial into the product of a column vector and a row vector.
$$
A=uv^T
$$

Other matrices with different shape are combinations of rank 1 matrices.
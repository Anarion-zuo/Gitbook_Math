# Linear Algebra

$I$ for identity.

## Factorization into $A=LU$

To transform a matrix $A$ from itself to an upper triangular form $U$, we apply to it a series of row transformation, which can be represented as:
$$
EA=U
$$
where $E$ is a elementary matrix and $U$ is the result of Gaussian elimination. Take $L=E^{-1}$, $A=LU$, where $L$ would always be a lower triangular matrix. Moreover, $E$ can be a product of a series of elementary matrices, $E=E_n,...,E_1$. Hence, $L=E_1^{-1},...,E_n^{-1}$.

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


Therefore, for all matrices, there is always $AA^T$ or $A^TA$ is symmetric.

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

When $b$ is one of the column vector of $A$, the solution is something like $(0,...,1,...,0)^T$. Furthermore, the system is solvable exactly when $b$ is in the column space.

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
where $I$ is unit submatrix part formed by the free columns, and $F$ is given by the pivot columns. The $I$ and $F$, $x_{pivot}$ and $x_{free}$ may get mixed up. The matrix consisting of the solution of the equation is:
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

## Graph

A graph consists of a set of nodes and edges, $G=(V,E)$.

### Incidence Matrix

![1555768725452](C:\Users\a\AppData\Roaming\Typora\typora-user-images\1555768725452.png)
$$
\begin{pmatrix}
-1&1&0&0\\
0&-1&1&0\\
-1&0&1&0\\
-1&0&0&1\\
0&0&-1&1\\
\end{pmatrix}
$$

Columns signify nodes and rows signify edges. $-1$ signifies comes out from and $1$ signifies go into. Notice that the top 3 rows are dependent, for there is a loop formed by the nodes and edges.

The rank of the incidence matrix signifies the difference between the number of edges and loops.

#### Null Space

$$
Ax=0\Rightarrow x
$$

Introducing a physical background, we take $x$ as the values of potentials at the node. $Ax$ is the differences between the nodes.
$$
Ax=\begin{pmatrix}x_2-x_1\\x_3-x_2\\x_3-x_1\\x_4-x_1\\x_4-x_3\end{pmatrix},x=c\begin{pmatrix}1\\1\\1\\1\end{pmatrix}
$$
The basis of the null space says the total uprising and downfall of voltage in a closed circuit equals each other, which is the KVL.

#### Null Space of $A^T$

$$
A^Ty=0\Rightarrow y
$$

$$
A^Ty=\begin{pmatrix}-y_1-y_3-y_4\\y_1-y_2\\y_2+y_3-y_5\\y_4+y_5\end{pmatrix}
$$

It can be interpreted that the $y$ signifies current. Negative values stands for outflowing current and positive for inflowing. The equation asks for 5 edges of current satisfy the KCL, as the inflowing current of the whole system equals 0.

When potential differences and current are both determined, there is Ohm’s law.
$$
Cx=y
$$
The rank of the transpose of incidence matrix equals the rank of the incidence matrix, which holds still the same significance.

The basis of the null space of the transpose of the incidence matrix is given by the closed loop got by KVL/KCL analysis.

Considering the relation between dimension and rank, we have a nice formula:
$$
n(loops)+n(nodes)-n(edges)=1,n()=\text{the number of}
$$
which the Euler’s formula.

### Complete Circuit Theory

Difference in potential:
$$
e=Ax
$$
Current in an edge:
$$
y=Ce
$$
Having an input current source:
$$
A^Ty=f
$$
All of the things above:
$$
A^TCAx=f
$$

## Orthogonal

### Definition

Two vectors are orthogonal means that their dot product is 0.
$$
x^Ty=0,||x||_2^2+||y||_2^2=||x+y||_2^2
$$

### Orthogonal Space

The orthogonal space of a vector contains vectors perpendicular to the vector.

The basis of the row space is perpendicular to the vectors in the null space. Hence, we have that the row space is perpendicular to the null space. In fact, the null space forms the orthogonal complements of the row space, which contains all vectors perpendicular to the row space.

### Projection

Some thing about $A^TA$:
$$
(A^TA)_{n\times n},(A^TA)^T=A^TA,rank(A^TA)=rank(A),dim(A^TA)=dim(A)
$$


#### Definition

A projection of a vector $b$ upon another vector $a$ is:
$$
p=\frac{a^Tb}{a^Ta}\cdot a
$$
If the transform is based on some matrix, $p=Pb$,
$$
P=\frac{aa^T}{a^Ta}
$$
Obviously, $P$ is symmetric.

The column space of $P$ is a line through the origin, for $rank(P)=1$.

If we apply the projecting transformation twice upon the vector, the result remains the same as once, $P^2=P$, hence $P^n=P$.

#### Closest Problem of Unsolvable Problems

Under many cases in the real world, we have $Ax=b$ unsolvable, for $b$ is not in the column space of $A$. Therefore, we try to solve its closest problem $A\hat x=p$, where $p$ is projection of $b$ onto column space.

Suppose there is a matrix $A=(a_1,a_2)$, having 2 dimensional column space. There is
$$
p=\hat x_1a_1+\hat x_2a_2=A\hat x
$$
Therefore, the problem is, by which combination of the basis of the column space of $A$ is the projection of $b$ on the column space of $A$ given? Obviously, the difference between the original $b$ and the projection is perpendicular to the column space of $A$ and $e$ is in the null space of $A^T$.
$$
e=b-A\hat x=b-p\Rightarrow (b-Ax)\perp C(A),A^T(b-A\hat x)=0
$$
In another word:
$$
e\in N(A^T)\Leftrightarrow e\perp C(A)
$$
The error part $e$ is perpendicular to the column space of $A$ as is perpendicular to $p$. $e$ and $p$ together form the vector $b$. Obviously, for $e$:
$$
e=(I-P)b
$$
$e$ is also a projection as $p$ is. $I-P$ is also a transformation matrix, as $P$, and holds the same properties.

The problem becomes, formally,
$$
A^T(b-A\hat x)=0\Leftrightarrow A^TA\hat x=A^Tb\Rightarrow\hat x=(A^TA)^{-1}A^Tb,p=A(A^TA)^{-1}A^Tb
$$
Under 1 dimensional cases,
$$
p=\frac{aa^T}{a^Ta}b
$$
which is mentioned before.
$$
P=A(A^TA)^{-1}A^T
$$
By looking at this formula, we may have a illusion that $P=I$. However, since $A$ is not always a square matrix or an invertible matrix here, when $A^{-1}$ is not defined, the illusion goes away. If $A$ is a nice square and invertible matrix, by multiplying $P$ upon the vector, we are simply projecting the vector onto $R^n$, which the vector is already in. Therefore, the presence of $I$ is reasonable.

Other properties also holds,

- $P^T=P$
- $P^n=P$

#### Proof for Invertibility

We try to prove $A^TA$ is always invertible, when the column vectors of $A$ are independent. The statement is equivalent to:
$$
A^TAx=0
$$
The equation only has zero vector as solution.

Take the dot product of $x$ at both sides.
$$
(Ax)^TAx=0\Rightarrow Ax=0\Rightarrow Q.E.D.
$$

#### Least Square

When solving regression problems, we do not expect the result function goes through each points in the samples. In another word, the equation, $Ax=b$, constructed by training set and potential outputs, is unsolvable. Therefore, instead of finding solutions for the original equation, we try to find the projection of $b$ upon $C(A)$.
$$
A^TA\hat x=A^Tb,\hat x=(A^TA)^{-1}A^Tb
$$
By minimization process in calculus, we can get the same result.

##### Quantities

Taking Least Square algorithm upon 2D example: $(1,1),(2,2),(3,2)$.
$$
\begin{cases}C+D=1\\C+2D=2\\C+3D=2\end{cases},A=\begin{pmatrix}1&1\\1&2\\1&3\end{pmatrix},b=\begin{pmatrix}1\\2\\2\end{pmatrix},x=\begin{pmatrix}C\\D\end{pmatrix},\hat x=\begin{pmatrix}\hat C\\\hat D\end{pmatrix}
$$
The goal of the problem is to minimize the error of the regression.
$$
||e||_2^2=||Ax-b||_2^2=e_1^2+e_2^2+e_3^2,e_i=y_i-\hat y_i,\hat y_i=p_i,y_i=b_i
$$
The goal is to find $p$ and $\hat x$.

##### Solution

$$
A^TA=\begin{pmatrix}1&1&1\\1&2&3\end{pmatrix}\begin{pmatrix}1&1\\1&2\\1&3\end{pmatrix}=\begin{pmatrix}3&6\\6&14\end{pmatrix},A^Tb=\begin{pmatrix}5\\11\end{pmatrix}
$$

Solve:
$$
D=\frac{1}{2},C=\frac{2}{3}
$$
Error vector:
$$
e=\begin{pmatrix}-\frac{1}{6}\\\frac{1}{3}\\-\frac{1}{6}\end{pmatrix},e+p=b,p^Te=0
$$

### Orthonormal Vectors

#### Definition

For matrix $Q=(q_1,...,q_n)$, the term of being a matrix with columns to be orthonormal vectors, or orthonormal matrix, is:
$$
q_i^Tq_j=\begin{cases}0&i\ne j\\1&i=j\end{cases}
$$
An obvious property is:
$$
Q^TQ=I
$$
When $Q$ is a square matrix, it is also called a orthogonal matrix, for $Q^T=Q^{-1}$.

#### Projection Matrix

The projection of some vector upon orthonormal $Q$:
$$
P=Q(Q^TQ)^{-1}Q^T=QQ^T
$$
If $Q$ is squared,
$$
P=QQ^T=I
$$

#### Normal Equation

$$
Q^TQA\hat x=A^Tb\Rightarrow \hat x=Q^Tb,\hat x_i=q_i^Tb
$$

#### Gram-Schmidt Procedure

For 2 vectors $a,b$, suppose the result is $A,B$. Take $A=a$, then $B=b-\frac{A^Tb}{A^TA}A$ is perpendicular to $A$. If we add another independent vector $c$, the goal is to find $C$ perpendicular to $A$ and $B$. It is by simple subtraction of the component upon the direction of $A$ and $B$.
$$
C=c-\frac{A^Tc}{A^TA}A-\frac{B^Tc}{B^TB}B
$$

## Determinants

$$
\det A=|A|,\forall A_{n\times n}
$$

### Definition

- $\det I=1$
- Exchanging rows reverses the sign of the determinant. $\det P=\pm1$, derived from the previous property.
- Determinant is linear for each row
  - Multiply any of the row by $t$, the determinant is also multiplied by $t$.
  - Addition is separable.
- 2 equal rows means determinant is 0. This is derived from the properties above.
- Subtract $l\times row_i$ from $row_k$ and determinant remains unchanged. This is for elimination.
- Row of zeros leads to determinant being 0.
- The determinant of an upper triangular matrix is the product of pivots.
- Determinant is 0 when the matrix is not invertible.
- The determinant of the product of matrices is the product of the determinants of matrices. $\det A^{-1}=1/\det A$
- $\det A^T=\det A$

### Formula for Caculation

Big formula:
$$
\det A=\sum\pm a_{1\alpha}a_{2\beta}a_{3\gamma}...a_{n\omega}
$$
where $(\alpha,\beta,...,\omega)$ is some permutation of $(1,...,n)$.

## Eigen

### Definition

$$
Ax=\lambda x
$$

Eigenvectors are some vectors pointing towards the same direction after some transformation. The corresponding coefficient $\lambda$ is the eigenvalue. If $A$ is singular, 0 would be one of the eigenvalues.

Taking the projection’s point of view, for a projection matrix $P$, any vector inside the projecting space would be a eigenvector of $P$, which is $x$. Any vector perpendicular to a space is a eigenvector of the space with eigenvalue 0. There is only 1 and 0 for projection matrices.

A neat fact:
$$
trace(A)=\sum\lambda_i,\det A=\prod\lambda_i
$$

The eigenvalues of the transpose are the same.
$$
\det(A-\lambda I)=\det(A-\lambda I)^T=\det(A^T-\lambda I)
$$


### Solution

$$
Ax=\lambda x\Rightarrow(A-\lambda I)x=0
$$

where $(A-\lambda I)$ is singular. Hence:
$$
\det(A-\lambda I)=0\Rightarrow\lambda
$$
With gotten $\lambda$s, solve $(A-\lambda I)x=0$ for eigenvectors.

#### Addition

The eigenvalues of the addition of 2 matrices are not necessarily the addition of the eigenvalues of the 2 matrices, for the eigenvectors of the 2 matrices are not always identical. Furthermore, the product of 2 matrices means little to their eigenvalues and eigenvectors either. In general, we would say that eigenvalues do not have the property of linearity.

#### Complex Eigenvalues

A symmetric matrix or a symmetric enough matrix has real eigenvalues, while a not-symmetric-at-all matrix has imaginary eigenvalues. Most matrices lie in between these 2 different kinds, holding real or complex eigenvalues.
$$
\begin{pmatrix}0&1\\-1&0\end{pmatrix}\rightarrow\lambda=\pm i
$$
This is a “anti-symmetric” matrix, which means $A^T=-A$.
$$
\det(A-\lambda I)=\det(A-\lambda I)^T=\det(-A-\lambda I)
$$

#### Triangular Matrix

$$
U=\begin{pmatrix}d_1&\dots&\\0&\ddots&\vdots\\0&0&d_n\end{pmatrix},\det(A-\lambda I)=\det\begin{pmatrix}d_1-\lambda&\dots&\\0&\ddots&\vdots\\0&0&d_n-\lambda\end{pmatrix}\Rightarrow\prod_{i=1}^n(d_i-\lambda)=0,\lambda_i=d_i
$$

The eigenvalues of triangular matrices lie in the diagonal.

### Diagonalize

Suppose we have $n$ independent eigenvectors of $A$. Put them in the columns of some matrix $S$.
$$
AS=Ax_1+Ax_2+...+Ax_n=\lambda_1x_1+...+\lambda_nx_n=(x_1,...,x_n)\begin{pmatrix}\lambda_1&...&\\0&\ddots&\vdots\\0&0&\lambda_n\end{pmatrix}=S\Lambda
$$
Beautiful calculation:
$$
AS=S\Lambda,S^{-1}AS=\Lambda,A=S\Lambda S^{-1}
$$

#### Powers

Consider $A^2$:
$$
A^2x=\lambda Ax=\lambda^2x
$$
The eigenvalue becomes squared and eigenvector remains the same. In other word:
$$
A^2=S\Lambda^2S^{-1}
$$
Furthermore:
$$
A^k=S\Lambda^kS^{-1}
$$
Stability:
$$
\lim_{k\rightarrow\infty}A^k=O\Leftrightarrow\lim_{k\rightarrow\infty}\Lambda^k=O\Rightarrow \forall|\lambda_i|<1
$$

#### Diagonalizable

For diagonalizing process to be valid, the matrix has to satisfy some terms. When having a $n$ dimensional matrix, if we have $n$ different eigenvalues, we must have $n$ independent eigenvectors. If the matrix is singular, the duplicated eigenvalues must correspond to independent eigenvectors, and if not, we cannot construct a $S$ for the matrix, thus not diagonalizable.

#### Difference Equation

$$
u_{k+1}=Au_k\Rightarrow u_k=A^ku_0
$$

Write $u_0$ as a combination of eigenvectors of $A$:
$$
u_0=c_1x_1+c_2x_2+...+c_nx_n
$$
Multiply by $A$:
$$
Au_0=c_1\lambda_1x_1+...+c_n\lambda_nx_n,A^ku_0=c_1\lambda_1^kx_1+...+c_n\lambda_n^kx_n=\Lambda^kSc
$$
For example, Fibonacci series:
$$
F_{k+2}=F_{k+1}+F_k,F_0=0,F_1=1
$$
Suppose:
$$
u_k=\begin{pmatrix}F_{k+1}\\F_k\end{pmatrix}
$$
Then:
$$
u_{k+1}=\begin{pmatrix}1&1\\1&0\end{pmatrix}u_k,A=\begin{pmatrix}1&1\\1&0\end{pmatrix},\lambda_1=\frac{1+\sqrt5}{2},\lambda_2=\frac{1-\sqrt5}{2}
$$
Eigenvectors:
$$
x_1=\begin{pmatrix}\lambda_1\\1\end{pmatrix},x_2=\begin{pmatrix}\lambda_2\\1\end{pmatrix},u_0=\begin{pmatrix}1\\0\end{pmatrix}
$$
The result:
$$
u_k=\Lambda^kSc,\Lambda=\begin{pmatrix}\lambda_1&0\\0&\lambda_2\end{pmatrix},S=\begin{pmatrix}\lambda_1&\lambda_2\\1&1\end{pmatrix}
$$

### Markov Matrix

#### Definition

1. All entries greater or equal to 0.
2. All columns add to 1.
3. The power of a Markov matrix is a Markov matrix.
4. Eigenvalues
   1. There is one of the eigenvalues equal to 1.
   2. All other eigenvalues have absolute value smaller than 1.
   3. The matrix has a steady state determined by one of the eigenvectors.
5. The matrix is singular. $(1,1,1)$ is in the null space of the transpose of $A$.

### Example

Suppose a model of population flow between Massachusetts and California.

|                   | California | Massachusetts |       |
| ----------------- | ---------- | ------------- | ----- |
| Stay in           | $0.9$      | $0.2$         | $1.1$ |
| Move to the other | $0.1$      | $0.8$         | $0.9$ |
|                   | $1.0$      | $1.0$         | $2.0$ |


$$
\begin{pmatrix}u_{cal}\\u_{mass}\end{pmatrix}_{k+1}=\begin{pmatrix}0.9&0.2\\0.1&0.8\end{pmatrix}\begin{pmatrix}u_{cal}\\u_{mass}\end{pmatrix}_k,\begin{pmatrix}u_{cal}\\u_{mass}\end{pmatrix}_0=\begin{pmatrix}0\\1000\end{pmatrix}
$$
Eigens:
$$
\lambda_1=1,x_1=(2,1)^T,\lambda_2=0.7,x_2=(1,-1)
$$

Plug in:
$$
u_k=c_1\begin{pmatrix}2\\1\end{pmatrix}+c_20.7^k\begin{pmatrix}-1\\1\end{pmatrix},u_0=\begin{pmatrix}0\\1000\end{pmatrix}=c_1\begin{pmatrix}2\\1\end{pmatrix}+c_2\begin{pmatrix}-1\\1\end{pmatrix}
$$
Final result:
$$
u_k=\frac{1000}{3}\begin{pmatrix}2\\1\end{pmatrix}+\frac{2000}{3}0.7^k\begin{pmatrix}-1\\1\end{pmatrix},\lim_{k\rightarrow\infty}u_k=\frac{1000}{3}\begin{pmatrix}2\\1\end{pmatrix}
$$

### Fourier Series

#### Expansion with Orthonormal Basis

For a given orthonormal basis $q_1,...,q_n$, we may expand any vector $v$ onto it, which is to represent $v$ by a linear combination of $q_1,...,q_n$. The goal is to find the coefficients $x_1,...,x_n$.
$$
v=x_1q_1+x_2q_2++x_nq_n=Qx
$$
By the property of orthonormal basis,
$$
q_i^Tv=x_1\Leftrightarrow x=Q^{-1}v=Q^Tv
$$

#### Definition

$$
f(x)=a_0+a_1\cos x+b_1\sin x+a_2\cos2x+b_2\sin2x+...(\infty)
$$

By changing vectors to functions, we traverse from finite vector space to infinite space. The functions are like to the vectors, only with continuously infinite amount of values, while vectors have discrete finite amount of components. The dot product between functions can be defined.
$$
v^Tw=\sum_{i=1}^nv_iw_i\rightarrow f^Tg=\int_0^xf(x)g(x)dx
$$
For triangular functions, it can be proved by dot product that the $\sin$ and $\cos$ are orthogonal. Therefore, we have a similar way of computing $a_n,b_n$.

## Symmetry

### Definition

For real $A$:
$$
A=A^T
$$
Always true facts:

1. The eigenvalues are real.
2. The eigenvectors can be transformed into orthonormal basis.

$$
A=S\Lambda S^{-1}
$$

where $S$ can be transformed into orthonormal matrices.
$$
A=Q\Lambda Q^{-1}=Q\Lambda Q^T=\sum_{i=1}^n\lambda_iq_iq_i^T
$$

#### Spectrum Theorem

The process is called spectrum theorem, which perfectly shows the beautiful properties of eigenvalues, eigenvectors, symmetry, and inversion.

From another point of view, a symmetric matrix can be represented as a linear combination of perpendicular projection matrices.
$$
A=\sum_{i=1}^n\lambda_iq_iq_i^T
$$

#### Proof for Real Eigenvalues

Conjugate everything:
$$
Ax=\lambda x\Rightarrow A\bar x=\bar\lambda\bar x
$$
Take the transpose:
$$
\bar x^TA^T=\bar\lambda\bar x^T
$$
Multiply by $x$:
$$
\bar x^TAx=\bar x^T\bar\lambda x
$$
Multiply by transpose:
$$
\bar x^TA\bar x=\bar\lambda\bar x^T\bar x
$$
The dot product is not 0:
$$
\bar x^Tx=\bar x_1x_1+...+\bar x_nx_n=\sum_{i=1}^n|x_i|^2>0
$$
Compare and done:
$$
\lambda=\bar\lambda
$$
If we have complex matrices, change the term of symmetry into $A=\bar A^T$.

## Complex Matrices

For a complex vector $z=(z_1,z_2...,z_n)^T\in\C^n$. The length is not $z^Tz$, for the length should be a positive real number or 0. The right answer should be $||z||_2^2=\bar z^Tz$.

Define Hermitian operation:
$$
z^H=\bar z^T
$$
And the dot product should be different too:
$$
a\cdot b=a^Hb
$$
Symmetry, also known as Hermitian matrices:
$$
A^H=A
$$
Orthonormal matrices changed into unitary matrices:
$$
q_i^Hq_j=\begin{cases}0&i\ne j\\1&i=j\end{cases},Q^HQ=I
$$

### Fourier Matrix

#### Definition

$$
F_n=\begin{pmatrix}
1&1&1&\cdots&1\\
1&w&w^2&\cdots&w^{n-1}\\
1&w^2&w^4&\cdots&w^{2(n-1)}\\
\vdots&\vdots&\vdots&\ddots&\vdots\\
1&w^{n-1}&w^{2(n-1)}&\cdots&w^{(n-1)^2}
\end{pmatrix},
(F_n)_{ij}=w^{ij},i,j\in[0,n)
$$

where for $w$:
$$
w=\exp(\frac{2\pi}{n}i)=\cos\frac{2\pi}{n}+i\sin\frac{2\pi}{n}
$$
$w$ is the uniform separation of unit circle on the complex plane.

It can be checked that the Fourier matrix is orthonormal.
$$
F^H_nF_n=I_n
$$

#### Recursive Property

$$
F_{2n}=\begin{pmatrix}I&D\\I&-D\end{pmatrix}\begin{pmatrix}F_n&O\\O&F_n\end{pmatrix}P
$$

$P$ is a permutation matrix, switching the columns. It rearranges the order of the columns from $1,2,...,n$ to $1,n/2+1,2,n/2+2,...,n$.
$$
D=\begin{pmatrix}1\\&w\\&&w^2\\&&&\ddots\\&&&&w^{n-1}\end{pmatrix}
$$
Time complexity:
$$
T(n)=\frac{1}{2}n\log_2n
$$

## Positive Definite (Symmetric) Matrix

The signs of the pivots are same as the signs of the eigenvalues. The number of pivots equals the number of eigenvalues.

### Definition

- The matrix HAS TO BE symmetric.
- The matrices with all eigenvalues positive
- All pivots are positive.
- All sub-determinants are positive.

If $A_1,...,A_n$ is the submatrix of $A$, $\det A_i>0$ means the matrix is positive definite. If $\det A_i\ge0$, the matrix is positive semi definite.

### Quadratic Form

$$
x^TAx
$$

It is a linear combination of all combination of the components of $x$. The coefficient of a certain term $x_ix_j$ is $A_{ij}$. If the quadratic form of a symmetric matrix is always greater than 0 for any $x$, the matrix is positive definite. Same thing goes for semi definite.

Suppose:
$$
f(x,y)=2x^2+12xy+7y^2,A=\begin{pmatrix}2&6\\6&7\end{pmatrix}
$$
Obviously, $A$ is not positive definite, for $\det A<0$.

Derivatives:
$$
f_x=4x+12y,f_y=14y+12x,f_{xx}=4,f_{yy}=14,f_{xy}=12
$$
Therefore, for some little $x,y$, there is $f(x,y)<0$. The origin is a saddle point of the function, which means the first derivative of the function is 0 for some direction.

Suppose:
$$
f(x,y)=2x^2+12xy+20y^2,A=\begin{pmatrix}2&6\\6&20\end{pmatrix}
$$
Obviously, $A$ is positive definite. The origin is where the function “actually” takes minimum value, by looking at the second derivative.

For $f(x,y)=2x^2+12xy+20y^2$, the way of showing that it is always positive is by writing it in the form of a sum of square, or completing square.
$$
f(x,y)=2(x+3y)^2+2y^2
$$
For another case, as it is quite possible, we would have minus square terms. That is when we have a potential negative value.

It is not an accident that we end up with the coefficients in this way. If we apply the process of Gaussian elimination upon the matrix:
$$
\begin{pmatrix}2&6\\6&20\end{pmatrix}\rightarrow\begin{pmatrix}2&6\\0&2\end{pmatrix},L=\begin{pmatrix}1&0\\3&1\end{pmatrix}
$$
The pivots are outside and the multiplier 3 is inside.

The graph would show that it is a ellipsoid, having 3 major direction. By the transform of eigen-defactorization $Q\Lambda Q^T$, we can rotate the graph to a “standard” form, which has the 3 main direction rotated onto the axis.

For the functions of $A$, such as $A^{-1},A^T,...$, we may well decide whether it is positive definite. For $A+B$ or other expressions involving anther matrix, it is not so obvious, as it is not so obvious for $\det(A+B)$ or the eigenvalues of $A+B$.

If $A,B$ are both positive definite, $x^T(A+B)x=x^TAx+x^TBx>0$. It is shown the relation of positive definitive of the sum of the matrices.

For the matrices that are not square, $A_{m\times n}$, we are interested in $A^TA$.
$$
x^TA^TAx=(Ax)^TAx=||Ax||_2^2\ge0
$$
equal when $x$ is $0$, and $x$, by definition, cannot be $0$. Therefore, $A^TA$ for any $A$ is positive definite.

### Hessian

In the world of single variable calculus, the second derivative tells the curvature of the function, by which maximum or minimum can be found or determined. Now, we expand such an idea, and define a matrix of second derivative for functions upon all dimensions.
$$
H_{ij}=f_{x_ix_j}
$$
If the matrix is positive definite, the function is convex.

## Similar Matrices

### Definition

$A$ and $B$ are similar means, for some matrix $M$, there is $B=M^{-1}AM$. The similar matrices have identical eigenvalues. Every matrices sharing the same eigenvalues can be transformed into each other by this process. The relation in eigenvectors is shown as following:
$$
Ax=\lambda x\Rightarrow(M^{-1}AM)M^{-1}x=\lambda M^{-1}x\Rightarrow BM^{-1}x=\lambda M^{-1}x\Rightarrow x_B=M^{-1}x_A
$$

### Bad Case

Sometimes, when we have duplicated eigenvalues, and the matrix is not diagonalizable, we would have a bad special case.

For a matrix $4I$:
$$
4I=\begin{pmatrix}4&0\\0&4\end{pmatrix}
$$
Obviously, $4I$ has 2 duplicated eigenvalues $4$. However, for any matrix $M$,
$$
M^{-1}4IM=4I
$$
The family of matrices with eigenvalues $4$ and $4$ only contains $4I$, for no other matrix is similar to it except itself. Other matrices having the same eigenvalues are not diagonalizable, or the matrix would be similar to $4I$, which none does.
$$
\begin{pmatrix}4&1\\0&4\end{pmatrix},\begin{pmatrix}5&1\\-1&3\end{pmatrix},\begin{pmatrix}4&0\\17&4\end{pmatrix}
$$
We can construct these matrices by intuition as above so that they have trace $8$ and determinant $16$.

Therefore, when 2 matrices have the same duplicated eigenvalues, they are not necessarily similar to each other.

Define Jordan’s block, which is matrices having eigenvalues upon diagonal and 1s beside them.
$$
J_i=\begin{pmatrix}\lambda_i&1\\&\lambda_i&1\\&&\ddots\\&&&\lambda_i&1\\&&&&\lambda_i\end{pmatrix}
$$
For example:
$$
\begin{pmatrix}
0&1&0&0\\
0&0&1&0\\
0&0&0&0\\
0&0&0&0
\end{pmatrix},
\begin{pmatrix}
0&1&0&0\\
0&0&0&0\\
0&0&0&1\\
0&0&0&0
\end{pmatrix}
$$
These 2 matrices have identical duplicated eigenvalues and different Jordan’s blocks. They are not similar to each other, each having a single eigenvector different from the other’s

The Jordan’s theorem says: Every square matrix $A$ is similar to a Jordan matrix $J$, which is constructed by a series of Jordan blocks on their diagonals. The number of blocks is the number of eigenvectors, for from each block we solve a single eigenvector.
$$
J=\begin{pmatrix}
J_1\\
&J_2\\
&&\ddots\\
&&&J_d
\end{pmatrix}
$$
The good case is that $J$ is $\Lambda$, in which case the matrix is perfectly diagonalizable.

## Singular Value Decomposition (SVD)

### Definition

For any matrix $A$, we can write it in such form as:
$$
A=U\Sigma V^T
$$
where $\Sigma$ is diagonal matrix, and $U,V$ are orthonormal.

A special case is $A=Q\Lambda Q^T$.

The decomposition is a process as following. Suppose an equation, $\sigma u=Av$. We are trying to find the orthogonal basis for the row space of $A$ and transform it into the column space of $A$, and express the new orthonormal basis. The orthogonal basis $v$ of the row space of $A$ can be computed by the process of Graham-Schmidt’s method. The key is to find a special setup of which after multiplied by $A$, it is still an orthogonal basis.
$$
A\begin{pmatrix}v_1&v_2&...&v_r\end{pmatrix}=\begin{pmatrix}u_1&...&u_r\end{pmatrix}\begin{pmatrix}
\sigma_1\\
&\sigma_2\\
&&\ddots\\
&&&\sigma_r
\end{pmatrix}\Rightarrow
AV=U\Sigma,A=U\Sigma V^{-1}=U\Sigma V^T
$$
To find $V$:
$$
A^TA=V\Sigma^2V^T
$$
$A^TA$ is certainly a (semi) definite matrix. $V$‘s columns are the eigenvectors of $A^TA$ and $\sigma^2$s are the eigenvalues of $A$.

To find $U$:
$$
AA^T=U\Sigma^2U^T
$$

### Solution

For example:
$$
A=\begin{pmatrix}4&4\\-3&3\end{pmatrix}\Rightarrow\begin{cases}
Av_1=\sigma_1u_1\\
Av_2=\sigma_2u_2
\end{cases}
$$
Compute $A^TA$:
$$
A^TA=\begin{pmatrix}25&7\\7&25\end{pmatrix}
$$
Compute eigenvectors:
$$
\begin{cases}
\lambda_1=32,x_1=\begin{pmatrix}\frac{1}{\sqrt2}&\frac{1}{\sqrt2}\end{pmatrix}^T\\
\lambda_2=18,x_2=\begin{pmatrix}\frac{1}{\sqrt2}&-\frac{1}{\sqrt2}\end{pmatrix}^T
\end{cases}
$$
Plug in for $\Sigma,V$:
$$
\Sigma=\begin{pmatrix}\sqrt{32}&0\\0&\sqrt{18}\end{pmatrix},V^T=\begin{pmatrix}
\frac{1}{\sqrt2}&\frac{1}{\sqrt2}\\
\frac{1}{\sqrt2}&-\frac{1}{\sqrt2}
\end{pmatrix}
$$
Compute $AA^T$:
$$
AA^T=\begin{pmatrix}32&0\\0&18\end{pmatrix}
$$
Compute eigenvectors:
$$
\begin{cases}
\lambda_1=32,x_1=\begin{pmatrix}\frac{1}{\sqrt2}&\frac{1}{\sqrt2}\end{pmatrix}^T\\
\lambda_2=18,x_2=\begin{pmatrix}\frac{1}{\sqrt2}&-\frac{1}{\sqrt2}\end{pmatrix}^T
\end{cases}
$$

### Conclusion

- $v_1,...,v_r$ is the orthonormal basis for row space.
- $u_1,...,u_r$ is the orthonormal basis for column space.
- $v_{r+1},...,v_n$ is the orthonormal basis for null space of the columns.
- $u_{r+1},...,u_n$ is the orthonormal basis for null space of the rows.

## Linear Transformations

### Definition

Linear transformations satisfy linear property.
$$
T(v+w)=T(v)+T(w),T(cv)=cT(v)\Rightarrow T(cv+dw)=cT(v)+dT(w),T(0)=0
$$
Not all straight forward transformations satisfy the properties above. For example,shifting planes:
$$
T(v)=v+v_0
$$
Obviously, $T(2v)=2v+v_0\ne2v+2v_0$.

Other examples, such as rotation, is a linear transformation. The important one is being multiplied by a matrix. Obviously, it is a linear transformation.
$$
T(v)=Av
$$
Suppose:
$$
A=\begin{pmatrix}
1&0\\
0&-1
\end{pmatrix}
$$
It is making a symmetry according to the x-axis.

We can argue that every linear transformation is a multiplication by matrix. To understand a linear transformation is to find the matrix behind it.

### Extension

For 2 independent vectors $v_1,v_2$, we can compute for them: $T(v_1),T(v_2)$. According to linear properties, by computing the linear combination of $v_1,v_2$, we can have all of the results of transformations on the vector space.

Therefore, for any basis $v_1,...,v_n$ as input basis, we can have output basis $T(v_1),...,T(v_n)$. For any $v=c_1v_1+...+c_nv_n$, $T(n)=c_1T(v_1)+...+c_nT(v_n)$.

The coordinates come from a basis. The coordinates of $v$ is given by the coefficients of the combination. Different basis gives different coordinates.

### Matrix Form

Construct matrix $A$ representing linear transformation $T:\R^n\rightarrow\R^m$.

- Choose a basis $v_1,...,v_n$ for input.
- Choose a basis $w_1,...,w_m$ for output.

Take a projection example. We are trying to project vectors in the 2D plane onto a line, representing by a basis $w_1,w_2$, one of which is parallel to the line and the other is perpendicular to the line. Suppose the 2D plane has a basis $v_1,v_2$, where $v_1$ is parallel to the line.

Obviously, for $w_1$, the corresponding output is $w_1$. For $w_2$, the corresponding output is 0.
$$
\begin{pmatrix}c_1\\c_2\end{pmatrix}\rightarrow\begin{pmatrix}c_1\\0\end{pmatrix}
$$
The matrix is:
$$
A=\begin{pmatrix}1&0\\0&0\end{pmatrix},A\begin{pmatrix}c_1\\c_2\end{pmatrix}=\begin{pmatrix}c_1\\0\end{pmatrix}
$$
If we use the eigenvectors of the matrix as basis, we would have diagonals.

### Compression of Images

For an image of $512*512$ pixels, we can consider it as a vector holding $(512)^2$ dimensions. Each dimension is independent to each other. The initial basis is:
$$
\begin{pmatrix}1\\0\\0\\\vdots\end{pmatrix},
\begin{pmatrix}0\\1\\0\\\vdots\end{pmatrix},
\begin{pmatrix}0\\0\\1\\\vdots\end{pmatrix},...
$$
Considering that some blocks, barely change color inside the blocks, may exist in the image, we may try a better set of basis.
$$
\begin{pmatrix}1\\1\\1\\1\\\vdots\end{pmatrix},
\begin{pmatrix}1\\-1\\1\\-1\\\vdots\end{pmatrix},
...
$$
where in all vectors the number of 1 and 0 are the same.

- Change basis of the input vector $x$.
- Express the coefficients of the new vector $C$.
- Throw away some coefficients by making them zero according to some threshold.
- Get a new set of coefficients $\hat C$.
- Get a new set of pixels $\hat x$.

In order to find $C$ and $\hat C$, we would solve $P=WC$, where $P$ is the input vector, $W$ is the transformation matrix, $C$ is the coefficients. A good transformation gives a good $W^{-1}$, which is neat and fast to compute. The new basis needs to be good also, so that it can represent the vector with few enough components.

For the same linear transformation upon different basis, representing by $A$ and $B$,
$$
A=\begin{pmatrix}v_1&...&v_n\end{pmatrix},B=\begin{pmatrix}w_1&...&w_n\end{pmatrix}
$$
when $A$ and $B$ signify a same transformation, they are similar to each other.
$$
\exist M,AM=MB
$$

## Pseudo-inverse

$$
A_{m\times n},rank(A)=r
$$

### Definition

Some normal inverse of a matrix would be inverse of “2 sides”:
$$
AA^{-1}=A^{-1}A=I
$$
where $m=n=r$, full rank.

#### Left Inverse

Left inverse exists when the matrix has full column rank, $r=n$, having independent columns. The null space only contains 0. We have 0 or 1 solution for $Ax=b$.

For $A^TA$, same properties hold. $rank(A^TA)=n$. Obviously, $(A^TA)^{-1}A^T\times A=I$. Therefore, $(A^TA)^{-1}A^T$ is a left inverse of $A$. If we multiply the left inverse to the right, the result is not $I$.
$$
P=A(A^TA)^{-1}A^T
$$
It is a projection matrix upon column space.

#### Right Inverse

Right Inverse exists when the matrix has full row rank, $r=m$, having independent rows. The null space of the transpose only contains 0. The null space is $n-m$ dimensional. By observation, same as before, a right inverse for full row rank $A$ is $A^T(AA^T)^{-1}$.
$$
P=A^T(A^TA)^{-1}A^T
$$
It is a projection onto the row space.

#### General Pseudo Inverse

It is obvious that $x$ and transformation $Ax$ is strictly related to each other, namely, for $y\ne x$, $Ay\ne Ax$.
$$
Ax=Ay\Rightarrow A(x-y)=0\Rightarrow x-y=0
$$
for $x-y$ is in both the row space and the column space. Therefore, for any vector in the row space, it has a single and special vector in the column space related to it by the transformation $A$. A pseudo inverse is defined as the reverse process of such transformation.
$$
y=A^+(Ay)
$$

### Solution

Find $A^+$.


$$
A=U\Sigma V^T
$$
where:
$$
\Sigma=\begin{pmatrix}
\sigma_1&&&&O\\
&\sigma_2\\
&&\ddots\\
&&&\sigma_r\\
O&&&&O
\end{pmatrix}_{m\times n},r<m,r<n
$$
The pseudo inverse of the diagonal matrix is:
$$
\Sigma^+=\begin{pmatrix}
1/\sigma_1&&&&O\\
&1/\sigma_2\\
&&\ddots\\
&&&1/\sigma_r\\
O&&&&O
\end{pmatrix}_{n\times m}
$$
so that:
$$
\Sigma\Sigma^+=\begin{pmatrix}I&O\\O&O\end{pmatrix}_{m\times m},\Sigma^+\Sigma=\begin{pmatrix}I&O\\O&O\end{pmatrix}_{n\times n}
$$
In the end:
$$
A^+=V\Sigma^+U^T
$$

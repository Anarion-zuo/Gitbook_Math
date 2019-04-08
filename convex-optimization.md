# Convex Optimization

## Introduction: What do We Do?

### Context

$$
\min_x f_0(x)\\
s.t.\quad f_i(x)\le b_i
$$

- $x=(x_1,...,x_n)$: optimization variables
- $f_0:R^n-\rightarrow R$: objective function
- $f_i:R^n\rightarrow,i=1,...,m$: constraint functions
- The objective and constraints are convex.

$$
f_i(\alpha x+\alpha y)\le\alpha f_i(x)+\beta f_i(y),\alpha+\beta=1,\alpha\ge0,\beta\ge0
$$

- Does not necessarily have analytical solutions.

### Types

- General optimization problem,
  - very difficult to solve.
  - methods involve some compromise, for example, very long computation time or not always finding the solution.
- Exceptions
  - least-squares problems
  - linear programming problems
  - convex optimization problems

### Least-squares

$$
\min_x||Ax-b||_2^2
$$

with no constraints.

Solutions

- analytical solution: $x^*=(A^TA)^{-1}A^Tb$
- reliable and efficient algorithms and software
- computational time proportional to $n^2k(A\in R^{k\times n})$, less if structured
- a mature technology

### Linear Programming

$$
\min_x c^Tx\\
s.t.a_i^Tx\le b_i,i=1,...,m
$$

## Definitions and Terminology

### Affine Set

An affine set contains the line through any 2 distinct points in the set. All points on a arbitrarily given line crossing 2 arbitrarily given points in the set is in the set.
$$
x=\theta x_1+(1-\theta)x_2
$$
![1554104122130](C:\Users\a\AppData\Roaming\Typora\typora-user-images\1554104122130.png)

If there is a constraint of $1\le\theta\le1​$, the set is a convex set. In other words, a convex set contains line segment between any 2 points in the set.
$$
x_1,x_2\in C,\theta\in[0,1]\Rightarrow\theta x_1+(1-\theta)x_2\in C
$$

### Convex Combination and Convex Hull

A convex combination is defined as:
$$
x=\sum_{i=1}^k\theta_ix_i,\sum_{i=1}^k\theta_i=1,\theta_i\ge0
$$
A convex hull of set $S$ is a set of all convex combinations of points in $S$. For convex shapes, the convex is the inner place of the original shape. For non-convex shapes, the convex hull looks like a minimized filling for the shape to become convex.

![1554104725503](C:\Users\a\AppData\Roaming\Typora\typora-user-images\1554104725503.png)

### Convex Cone

A nonnegative conic combination of $x_1$ and $x_2$ is: at any point of the form
$$
x=\theta_1x_1+\theta_2x_2
$$
with $\theta_1\ge0,\theta_2\ge0​$.

![1554104989538](C:\Users\a\AppData\Roaming\Typora\typora-user-images\1554104989538.png)

It becomes a convex cone when $\theta_1+\theta_2=1$.

### Hyperplanes and Halfspaces

They are similarly defined with equation and inequality.
$$
\{x|a^Tx=b,a\ne0\},\{x|a^Tx\le b,a\ne0\}
$$
A halfspace, obviously, is not a convex space.

### Euclidean Balls and Ellipsoids

An Euclidean ball is defined with a center $x_c$ and radius $r$.
$$
B(x_c,r)=\{x|\text{ }||x-x_c||_2\le r\}=\{x_c+ru|\text{ }||u||_2\le1\}
$$
By a slight transform, we can also define an ellipsoid:
$$
\{x|(x-x_c)^TP^{-1}(x-x_c)\le1\},P\in S^n_{++}
$$

### Norm Balls and Norm Cones

Norm is a function $||\quad||$ that satisfies:

- $||x||\ge0,||x||=0$ if and only if $x=0$.
- $||tx||=|t|||x||,\forall t\in R$.
- $||x+y||\le||x||+||y||$.

A norm with a subscript is a particular norm.
$$
||x||_n=\sqrt{\sum_{i=1}^N|x_i|^n}
$$
Norm ball with center $x_c$ and radius $r$:
$$
\{x|\text{ }||x-x_c||\le r\}
$$
Norm cone:
$$
\{(x,t)|\text{ }||x||\le t\}
$$
Both are solid figures.

### Polyhedra

Polyhedra is a solution set of finitely many linear inequalities and equalities.
$$
\{x|Ax\preceq b,Cx=d\},A,C\in\R^{m\times n},\preceq\text{ is componentwise inequality}
$$
Component-wise inequality means the inequality satisfies for each component of the vector. There fore, a polyhedra signifies a convex shape.

### Positive Semi-definite Cone

Positive semi-definite cone $S^n​$ is a set of symmetric $n\times n​$ matrices. $S^n_+=\{X\in S^n|X\succeq0\}​$. It is a convex cone.
$$
X\in S^n_+\Leftrightarrow z^TXz\ge0,\forall z
$$
A positive definite is $S^n_{++}=\{X\in S^n|X\succ0\}​$.

### Operations preserving Convexity

For a convex set $C​$,

1. Apply definition

$$
x_1,x_2\in C,1\le\theta\le1\Rightarrow\theta x_1+(1-\theta)x_2\in C
$$

2. Put known convex sets together by certain operations.
   1. intersection
   2. affine functions
   3. perspective functions
   4. linear-fractional functions
3. “Matlab” approach, check $\frac{1}{2}(x_1+x_2)$.

### General Inequality

A convex cone $K\subseteq \R^n$ is a proper cone if,

- $K​$ is closed (contains its boundary). $||x||_2\le1​$ is closed and $||x||_1<1​$ is not.
- $K​$ is solid (has nonempty interior).
- $K$ is pointed (contains no line). A line must extend itself to the infinity or it is not a line.

A generalized inequality is defined by a proper cone $K$.
$$
x\preceq_Ky\Leftrightarrow y-x\in K,x\prec_Ky\Leftrightarrow y-x\in \bold{int} K
$$

$\bold{int}$ is the interior of $K​$.

For example,

- $K=\R^n_+$,

$$
x\preceq_{\R_+^n}y\Leftrightarrow x_i\le y_i,i=1,...,n
$$

The properties of $\preceq$ are similar to those of $\le$ upon $R$. Or we should say that $\le$ is a special case for $\preceq$ on $\R^1$.

Similarly, we can define minimum and maximum for our new notation. $x\in S​$ is the minimum element of $S​$ with respect to $\preceq_K​$ if
$$
y\in S\Rightarrow x\preceq_K y
$$
$x\in S$ is a minimal element of $S$ with respect to $\preceq_K​$ if
$$
y\in S,y\preceq_K x\Rightarrow y=x
$$

### Separating Hyperplane Theorem

If $C$ and $D$ are disjoint convex sets, $C\and D=\phi$, there exists $a\ne0,b$ such that
$$
a^Tx\le b,\forall x\in C\\
a^Tx\ge b,\forall x\in D
$$
The hyperplane $\{x|a^Tx=b\}$ separates $C$ and $D$. Strict condition requires the hyperplane does not touch any of the set.

Furthermore, we may define supporting hyperplane to set $C$ at boundary point $x_0$,
$$
\{x|a^Tx=a^Tx_0\}
$$
where $a\ne0$ and $\forall x\in C,a^Tx\le a^Tx_0$. Combine the 2 ideas together, we have the supporting hyperplane theorem: If $C$ is convex, there exists a supporting hyperplane at every boundary point of $C$.

### Dual Cones

Define dual cone for a cone $K$:
$$
K^*=\{y|y^Tx\ge0,\forall x\in K\}
$$
A visual explanation of duality is that the 2 boundary of the new cone is respectively perpendicular to that of the original cone.

![1554719579561](C:\Users\a\AppData\Roaming\Typora\typora-user-images\1554719579561.png)

There are self-dual cones:

- $K=\R_+^n$
- $K=S^n_+​$, semi-definite positive cone.
- $K=\{(x,t)|\text{ }||x||_2\le t\}​$, circle.

Or not:

- $K=\{(x,t)|\text{ }||x||_1\le t\},K^*=\{(x,t)|\text{ }||x||_\infty\le t\}$

Dual cones of proper cones are proper.
$$
y\preceq_{K^*}0\Leftrightarrow y^Tx\ge0,\forall x\succeq_K0
$$

### Minimum and Minimum Elements via Dual Inequalities

## Convex Functions

### Definition

Function $f:\R^n\rightarrow R$ is convex if the domain of $f$ is a convex set and
$$
f(\theta x+(1-\theta)y)\le\theta f(x)+(1-\theta)f(y),\forall x,y\in\bold{dom}f,0\le\theta\le1
$$
In graphs, everything between a certain interval is below the straight line between the boundary of the interval and the curvature is upward. It is defined to be strictly convex if the $\le$ sign is changed into $<$. Obviously, if $f$ is concave, $-f$ is convex.

Examples on $\R^1$,

- Affine: $ax+b$ on $\R$, $\forall a,b\in\R$.
- Exponential: $e^{ax}$.
- Powers: $x_\alpha$ on $R_{++}$, $\forall\alpha\ge1$ or $\forall\alpha\le0$.
- Powers of absolute value: $|x|^p$ on $\R$, $\forall p\ge1$.
- Negative entropy: $x\ln x$ on $R_{++}$.

When a function is both convex and concave, it is a affine function.

Examples on $R^{n}$:

- Affine: $f(x)=a^Tx+b$.
- Norms: $||x||_p,\forall p\ge1$, $||x||_\infty=\max_k|x_k|$.

Examples on $R^{m\times n}$:

- Affine

$$
f(X)=tr(A^TX)+b=A(:)^TX(:)+b=\sum_{i=1}^m\sum_{j=1}^nA_{ij}X_{ij}+b
$$

- Spectral norm

$$
f(X)=||X||_2=\sigma_{max}(X)=\sqrt{\lambda_{max}(X^TX)}
$$

### Restriction of a Convex Function to a Line

For function $g:\R \rightarrow\R​$,
$$
g(t)=f(x+tv),\bold{dom}g=\{t|x+tv\in\bold{dom}f\}
$$
where $f$ is convex, is convex. We can thus check the convexity of functions of $f$ by checking convexity of functions of one variable.

For example, $f:S^n\rightarrow\R,f(X)=\ln\detX,\bold{dom}X=S^n_{++}$,
$$
g(t)=\ln\det(X+tV)=\ln\det X+\ln\det(E+tX^{-1/2}VX^{-1/2})=\ln\det X+\sum_{i=1}^n\ln(1+t\lambda_i)
$$
where $\lambda_i$ are the eigenvalues of $X^{-1/2}VX^{-1/2}$. $g$ is concave in $t,\forall X\succ0,V$, hence $f$ is concave.

### Extended-value Extension

Extended-value extension $\tilde f$ of $f$ is
$$
\tilde f(x)=\begin{cases}
f(x)&x\in\bold{dom}f\\
\infty&x\not\in\bold{dom}f
\end{cases}
$$
The concave functions are quite the opposite. We assign negative infinity to concave functions.

### First-order Condition

$f$ is differentiable if $\bold{dom}f$ is open and the gradient
$$
\nabla f(x)=(\frac{\partial f}{x_1},\frac{\partial f}{x_2},...,\frac{\partial f}{x_n})
$$
exists at each $x\in\bold{dom}f$.

Differentiable $f$ with convex domain is convex if
$$
f(y)\ge f(x)+\nabla f(x)^T(y-x),\forall x,y\in\bold{dom}f
$$
which simply means the first order of Taylor expansion, the tangent line, is wholly beneath the function, or a global under estimation of the function. The gradient is also global, so that the other global features are assured.

### Second-order Condition

$f​$ is twice differentiable if $\bold{dom}f​$ is open and the Hessian $\nabla^2f(x)\in S^n​$,
$$
\nabla^2f(x)_{ij}=\frac{\partial^2f(x)}{\partial x_i\partial x_j},i,j=1,...,n
$$
exists at each $x\in\bold{dom}f$.

Twice differentiable $f$ with convex domain is convex if and only if
$$
\nabla^2f(x)\succeq0,\forall x\in\bold{dom}f
$$
Change the $\succeq$ into $>​$ and the conclusion becomes strictly convex.

For examples, 

#### Quadratic Function

$f(x)=(1/2)x^TPx+q^Tx+r,P\in S^n$,
$$
\nabla^2f(x)=P
$$
It is convex if $P\succeq0$.

#### Least-squares Objective

$$
f(x)=||Ax-b||_2^2,\nabla^2f(x)=2A^TA
$$

It is convex for any $A$.

#### Quadratic-over-linear

$$
f(x,y)=\frac{x^2}{y},\nabla^2f(x,y)=\frac{2}{y^3}\begin{pmatrix}y\\-x\end{pmatrix}\begin{pmatrix}y\\-x\end{pmatrix}^T\succeq0
$$

convex if $y>0$.

#### Log-sum-exp

$$
f(x)=\ln\sum_{k=1}^n\exp(x_k)
$$

The function “softly” tells the largest component of $x$, also called “soft max”, for a larger component effects the sum a lot more when taken exponential function, and $\ln$ squeezes the scale back. From another perspective, the function switches back and forth between the number of macro-states and entropy value.
$$
\nabla^2f(x)=\frac{1}{\bold{1}^Tz}\bold{diag}(z)-\frac{1}{(\bold{1}^Tz)^2}zz^T,z_k=\exp(x_k)
$$
To show $\nabla^2f(x)\succeq0​$, we must verify that $v^T\nabla^2f(x)v\ge0,\forall v​$,
$$
v^T\nabla^2f(x)v\ge0=\frac{(\sum_kz_kv_k^2)(\sum_kz_k)-(\sum_kv_kz_k)^2}{(\sum_kz_k)^2}\ge0
$$
since according to Cauchy-Schwarz inequality,
$$
(\sum_kz_kv_k^2)(\sum_kz_k)\ge(\sum_kv_kz_k)^2
$$

#### Geometric Mean

$$
f(x)=(\prod_{k=1}^nx_k)^{\frac{1}{n}},x\in\R_{++}^n
$$

It is concave.

### Epigraph and Sub-level Set

Define $\alpha$-sub-level set of $f:\R^n\rightarrow R$:
$$
C_\alpha=\{x\in\bold{dom}f|f(x)\le\alpha\}
$$
It simply signifies the input variables that meet the $\alpha$ level spec. The sub-level sets of convex functions are also convex. The real relation between the convexity of $f$ and its sub-level set is given by the definition of epigraph.
$$
\bold{epi}f=\{(x,t)\in\R^{n+1}|x\in\bold{dom}f,f(x)\le t\}
$$
$f$ is convex if and only if $\bold{epi}f$ is a convex set.

### Jensen’s Inequality

By the definition of convex function, for $0\le\theta\le1$, obviously,
$$
f(\theta x+(1-\theta)y)\le\theta f(x)+(1-\theta)f(y)
$$
A simple extension is adding more variables:
$$
f(\sum_{i=1}^n\theta_ix_i)\le\sum_{i=1}^n\theta_if(x_i),\sum_{i=1}^n\theta_i=1
$$
From this prospective, $\theta$ looks like some discrete probability distribution. Therefore, the form of this equation can be written as expectation.
$$
f(\bold{E}z)\le\bold Ef(z)
$$
Here the relation between convex set and probability is revealed.

### Operations that Preserve Convexity

#### Linear Operations

- nonnegative multiple: $\alpha f$ is convex if $f$ is convex and $\alpha\ge0$.
- sum: $f_1+f_2$ is convex if $f_1,f_2$ is convex, extending to sum with more terms and integrals.
- composition with affine function: $f(Ax+b)$ is convex if $f$ is convex.


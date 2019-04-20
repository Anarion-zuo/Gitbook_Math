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
The concave functions are quite the opposite. We assign negative infinity to concave functions. For a convex function with domain undefined, we implicitly refer to its extended version, with positive infinity in undefined places. In this case, some functions seemingly increasing or decreasing would not be so and many other original properties may change.

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
\nabla^2f(x)=\frac{1}{\bold{1}^Tz}\bold{diag}(z)-\frac{1}{(\bold{1}^Tz)^2}zz^T,z_k=\exp(x_k),\bold{1}^Tx=\sum_{i=1}^nx_i
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

#### Point-wise Maximum and Supremum

If $f_1,...,f_m$ are convex, $f(x)=\max\{f_x(x),...,f_m(x)\}$ is convex.

Extend the idea to supremum. If $f(x,y)$ is convex in $x$ for each $y\in A$,
$$
g(x)=\sup_{y\in A}f(x,y)
$$
It is convex.

#### Composition with Scalar Functions

Composition of $g:\R^n\rightarrow\R$ and $h:\R\rightarrow\R$:
$$
f(x)=h(g(x))
$$
$f$ is convex if

- $g$ convex, $h$ convex, $\tilde h$ non-decreasing
- $g$ concave, $h$ convex, $\tilde h$ non-increasing

Because,
$$
f''(x)=h''(g(x))g'(x)^2+h'(g(x))g''(x)
$$
The principle is the result of chain rule, regardless of all other rules and conclusions.

For example,

- $\exp(g(x))$ is convex if $g$ is convex.
- $1/g(x)$ is convex if $g$ is concave and positive.

Expand the idea to multi-dimensional cases. $g:\R^n\rightarrow\R^k,h:\R^k\rightarrow\R​$:
$$
f(x)=h(g(x))=h(g_1(x),g_2(x),...,g_k(x))
$$

$$
f''(x)=g'(x)^T\nabla^2h(g(x))g'(x)+\nabla h(g(x))^Tg''(x)
$$

#### Minimization and Maximization

If $f(x,y)$ is convex in $(x,y)$ and $C$ is a convex set,
$$
g(x)=\begin{cases}\inf_{y\in C}f(x,y)\\
\sup_{y\in C}f(x,y)\end{cases}
$$
It is convex when $\forall y\in C,f(x,...)$ is convex, which is trivial. For example,
$$
f(x,y)=x^TAx+2x^TBy+y^TCy,\begin{pmatrix}A&B\\B^T&C\end{pmatrix}\succeq0,C\succeq0
$$
minimizing over $y$ gives $g(x)=\inf_yf(x,y)=x^T(A-BC^{-1}B^T)x$. $g$ is convex, hence Schur complement $A-BC^{-1}B^T\succeq0$.

#### Perspective

The perspective of a function $f:\R^n\rightarrow\R$ is the function $g:\R^{n+1}\rightarrow\R$,
$$
g(x,t)=tf(\frac{x}{t}),\bold{dom}g=\{(x,t)|\frac{x}{t}\in\bold{dom}f,t>0\}
$$
$g$ is convex if $f$ is convex.

#### Conjugate Function

$$
f^*(y)=\sup_{x\in\bold{dom}f}(y^Tx-f(x))
$$

For example:

- negative logarithm $f(x)=-\ln x$

$$
f^*(y)=\sup_{x>0}(xy+\ln x)=\begin{cases}-1-\ln(-y)&y<0\\\infty&otherwise\end{cases}
$$

### Quasiconvex Functions

$f:\R^n\rightarrow\R​$ is quasiconvex if $\bold{dom}f​$ is convex and the sublevel sets $S_\alpha=\{x\in\bold{dom}f|f(x)\le\alpha\}​$ are convex for all $\alpha​$.

- $f​$ is quasiconcave if $-f​$ is quasiconvex.
- $f​$ is quasilinear if it is quasiconvex and quasiconcave.

#### Examples

- $\sqrt{|x|}$ is quasiconvex on $\R$.
- $ceil(x)=\inf\{z\in\Z|z\ge x\}$ is quasilinear.
- $\ln x$ is quasilinear on $\R_{++}$.
- $f(x_1,x_2)$ is quasiconcave on $\R_{++}^2$.
- linear fractional function is quasilinear

$$
f(x)=\frac{a^Tx+b}{c^Tx+d},\bold{dom}f=\{x|c^Tx+d>0\}
$$

- distance ration is quasiconvex

$$
f(x)=\frac{||x-a||_2}{||x-b||_2},\bold{dom}f=\{x|\text{ }||x-a||_2\le||x-b||_2\}
$$

#### Properties

modified Jensen inequality:
$$
0\le\theta\le1\Rightarrow f(\theta x+(1-\theta)y)\le\max\{f(x),f(y)\}
$$
first-order condition: differentiable $f$ with convex domain is quasiconvex if
$$
f(y)\le f(x)\Rightarrow\nabla f(x)^T(y-x)\le0
$$

### Log-concave and Log-convex Functions

A positive function $f$ is log-concave if $\ln f$ is concave:
$$
f(\theta x+(1-\theta)y)\ge f(x)^\theta f(y)^{(1-\theta)}\forall0\le\theta\le1
$$
$f$ is log-convex if $\ln f$ is convex.

## Terminology of Optimization Problem

### Standard Form Definition

$$
f_0(x)\rightarrow \min\\
s.t.\quad\begin{align*}&f_i(x)\le,i=1,...,m\\&h_i(x)=0,i=1,...,p\end{align*}
$$

- $x\in\R^n$ is the optimization variable
- $f_0:\R^n\rightarrow\R$ is the objective or cost function
- $f_i:\R^n\rightarrow\R,i=1,...,m$ are inequality constraint functions
- $h_i:\R^n\rightarrow\R$ are the equality constraint functions

optimal value:
$$
p^*=\inf\{f_0(x)|f_i(x)\le0,i=1,...,m,h(x_i)=0,i=1,...,p\}
$$

- $p^*=\infty$, if problem is infeasible (no $x$ satisfy the constraints).
- $p^*=-\infty$, if problem is unbounded below.

### Optimal and Locally Optimal Points

- $x$ is feasible if $x\in\bold{dom}f_0$ and it satisfies the constraints.
- A feasible $x$ is optimal if $f_0(x)=p^*$; $X_{opt}$ is the set of optimal points.
- $x$ is locally optimal if there is an $R>0$ such that $x$ is optimal for

$$
f_0(z)\rightarrow \min\\
s.t.\quad\begin{cases}&f_i(z)\le,i=1,...,m\\&h_i(z)=0,i=1,...,p\\&||z-x||_2\le R\end{cases}
$$

Examples:

- $f_0(x)=1/x,\bold{dom}f_0=\R_{++}:p^*=0$, no optimal point.
- $f_0(x)=-\ln x,\bold{dom}f_0=\R_{++}:p^*=0$.
- $f_0(x)=x\ln x,\bold{dom}f_0=\R_{++}:p^*=-1/e,x=1/e$ is optimal.
- $f_0(x)=x^3-3x,p^*=-\infty$, local optimal at $x=1$.

### Implicit Constraints

The standard form optimization problem has an implicit constraint:
$$
x\in D=\bigcap_{i=0}^m\bold{dom}f_i\cap\bigcap_{i=1}^p\bold{dom}h_i
$$

- We call $D$ the domain of the problem.
- The constraints $f_i(x)\le0,h_i(x)=0$ are the explicit constraints.
- A problem is unconstrained if it has no explicit constraints, $m=p=0$.

### Feasibility Problem

$$
\text{find}\quad x\\
s.t.\quad\begin{cases}&f_i(z)\le,i=1,...,m\\&h_i(z)=0,i=1,...,p\end{cases}
$$

can be considered a special case of the general problem of optimization with $f_0(x)=C$.

- $p^*=0$, if constraints are feasible; any feasible $x$ is optimal.
- $p^*=\infty$, if constraints are infeasible.

## Terminology of  Convex Optimization Problem

### Definition

$$
h_i(x)=a_i^Tx-b_i,i=1,...,p
$$

- $f_0,...,f_m$ are convex; equality constraints are affine.
- Problem is quasiconvex if $f_0$ is quasiconvex (and $f_1,...,f_m$ are convex).

Often written as
$$
f_0(z)\rightarrow \min\\
s.t.\quad\begin{cases}&f_i(z)\le,i=1,...,m\\&Ax=b\end{cases}
$$
Important property: feasible set of a convex optimization problem is convex.

Therefore, a natural statement of the definition of convex optimization problem is that it is to minimize a convex function over a convex set.

### Local and Global Optima

Theorem: Any locally optimal point of a convex problem is (globally) optimal.

#### Proof 

Suppose $x$ is locally optimal and $y$ is optimal with $f_0(y)<f_0(x)$. $x$ is locally optimal means there is an $R>0$ such that
$$
z\text{ frasible, }||z-x||_2\le R\Rightarrow f_0(z)\ge f_0(x)
$$
consider $z=\theta y+(1-\theta)x$ with $\theta=R/(2||y-x||_2)$

- $||y-x||_2>R$, so $0<\theta<1/2$.
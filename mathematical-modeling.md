# Computational Science and Engineering

## Differential Equation

If we have a differential equation, how do we transform it into a discrete problem? The key is to replace the differential equation by a difference equation.

### Derivative

#### First Derivative

Forward:
$$
\Delta_Fu=\frac{u(x+h)-u(x)}{h}=u'(x)+o(h)
$$
Backward:
$$
\Delta_Bu=\frac{u(x)-u(x-h)}{h}=u'(x)+o(h)
$$
Centered:
$$
\Delta_Cu=\frac{u(x+h)-u(x-h)}{2h}=u'(x)+o(h^2)
$$
The latter term represents the error, which is known as the first order error. The reason for the centered difference error is given by Taylor’s series.
$$
u(x+h)=u(x)+hu'(x)+\frac{h^2}{2}u''(x)+o(h^2),u(x-h)=u(x)-hu'(x)+\frac{h^2}{2}u''(x)-o(h^2)
$$
Subtract as centered difference:
$$
u(x+h)-u(x-h)=2hu'(x),\Delta_Cu=u'(x)
$$

#### Second Derivative

The second derivative is the difference of the difference. We may take the forward difference of the backward difference, or the backward difference of the forward difference, or the center difference of the center difference. The last is not a very good choice.
$$
\Delta_B\Delta_Fu=\Delta_F\Delta_Bu=-\frac{-u_{i+1}+2u_i-u_{i-1}}{(\Delta x)^2}
$$
Write the expression in matrix form:
$$
\frac{1}{h^2}\begin{pmatrix}2&-1\\-1&2&-1\\&-1&2&-1\\&&-1&2&-1\\&&&&\ddots\\&&&&-1&2\end{pmatrix}\begin{pmatrix}u_1\\u_2\\\vdots\end{pmatrix}=-\begin{pmatrix}u'_1\\u'_2\\\vdots\end{pmatrix}
$$
Mind the top row.

### Procedure for a Simple Case

Solve:
$$
-\frac{d^2u}{dx^2}=1,u(0)=u(1)=0,0\le u\le1
$$
The analytical solution is pretty straight forward:
$$
u(x)=-\frac{1}{2}x^2+\frac{1}{2}x
$$
Suppose the discrete step is $\frac{1}{6}$, so that $1=6h,u_1=u_6=0$.
$$
36\begin{pmatrix}2&-1\\-1&2&-1\\&-1&2&-1\\&&-1&2&-1\\&&&-1&2&-1\\&&&&-1&2\end{pmatrix}\begin{pmatrix}u_1\\u_2\\u_3\\u_4\\u_5\\u_6\end{pmatrix}=\begin{pmatrix}1\\1\\1\\1\\1\\1\end{pmatrix}
$$
Solve the linear system and we are done.

### Set One Side Loose

Change the restriction into:
$$
u'(0)=u(1)=0
$$
The analytical solution is:
$$
u(x)=-\frac{1}{2}x^2+\frac{1}{2}
$$
The boundary condition is:
$$
u_{n+1}=\frac{u_1-u_0}{h}=0
$$
The top row of the matrix has to change:
$$
36\begin{pmatrix}1&-1\\-1&2&-1\\&-1&2&-1\\&&-1&2&-1\\&&&-1&2&-1\\&&&&-1&2\end{pmatrix}\begin{pmatrix}u_1\\u_2\\u_3\\u_4\\u_5\\u_6\end{pmatrix}=\begin{pmatrix}1\\1\\1\\1\\1\\1\end{pmatrix}
$$
The approach is obviously wrong, for the first order approximation is not satisfied. If we look at the first row and its dot product, we have $u_1-u_2=1$, certainly wrong. If we change the first number of the right-hand side to be $1/2$, the solution will be exactly right.

## Linear System

$$
Au=b
$$

### Steps

By the Gaussian elimination process, we transform the matrix into an upper triangular matrix. Before elimination process begins in the next column, sort the columns beforehand, for larger pivots result in lesser multiplier. Most of all, we like zeros up front.

When we have multiple equations with the same $A$ and different right-hand side, we memorize the sequence of process of Gaussian elimination.
$$
AU=B
$$
where $B$ is a matrix.

For example:
$$
\begin{pmatrix}1&-1&0\\-1&2&-1\\0&-1&2\end{pmatrix}
$$
Take row 1 and subtract it to row 2.
$$
\begin{pmatrix}1&-1&0\\0&1&-1\\0&-1&2\end{pmatrix}
$$
We say that $l_{21}=-1$, for $r_2=r_2-r_1l_{21}$. Similarly, $l_{31}=0,l_{32}=-1$.
$$
U=\begin{pmatrix}1&-1&0\\0&1&-1\\0&0&1\end{pmatrix}
$$
The multipliers here goes to a lower triangular matrix $L$.
$$
L=\begin{pmatrix}1&0&0\\-1&1&0\\0&-1&1\end{pmatrix}
$$
In order to keep the symmetry, we further separate $U$ into a diagonal matrix and a upper triangular matrix. The upper triangular matrix can be computed by backward substitution.
$$
\begin{align*}&\begin{pmatrix}2&-1&0\\-1&2&-1\\0&-1&2\end{pmatrix}\\&=\begin{pmatrix}1&&\\-\frac{1}{2}&1&\\0&-\frac{2}{3}&1\end{pmatrix}\begin{pmatrix}2&-1&0\\0&\frac{3}{2}&-1\\0&0&\frac{4}{3}\end{pmatrix}\\&=\begin{pmatrix}1&&\\-\frac{1}{2}&1&\\0&-\frac{2}{3}&1\end{pmatrix}\begin{pmatrix}2\\&\frac{3}{2}\\&&\frac{4}{3}\end{pmatrix}\begin{pmatrix}1&-\frac{1}{2}&0\\
&1&-\frac{2}{3}\\&&1\end{pmatrix}\end{align*}
$$
Generally, for any symmetric matrix:
$$
K=LU=LDL^T
$$

## Line Integral

A vector field is defined by:
$$
\vec{F}=M\hat{i}+N\hat{j}
$$
where $M,N$ is function of $x$ and $y$. Line integral is closely related to work on complicated curves. A piece of work on a piece of displacement is:
$$
\Delta W=\vec{F}\cdot\Delta\vec{r}
$$
Therefore the sum along some trajectory C is:
$$
W=\int_C\vec{F}\cdot d\vec{r}=\int_{t_1}^{t_2}\vec{F}\cdot\frac{d\vec{r}}{dt}dt
$$
Another form of such kind of integral is in the form of components. We can then transform all y into x or backward. Be ware that $y(x)$ might not be a fine function, where a single value of x may correspond to multiple value of y, in which case we have to compute the integral by part.
$$
\vec{F}\cdot d\vec{r}=Mdx+Ndy=(M(x,y(x))+N(x,y(x))\frac{dy}{dx})dx
$$
With the property of geometric, the integral can also be transformed into a intuitive way of expression:
$$
d\vec{r}=(dx,dy)=\hat{T}ds,\frac{d\vec{r}}{dt}=(\frac{dx}{dt},\frac{dy}{dt})=\hat{T}\frac{ds}{dt}
$$
where $\hat{T}$ is the unit tangent of the integral curve. Also:
$$
ds=\sqrt{1+(\frac{dy}{dx})^2}dx
$$


 In general:
$$
\vec{F}\cdot d\vec{r}=Mdx+Ndy=(M+N\frac{dy}{dx})dx=\vec{F}\cdot\hat{T}ds
$$

### Polar Coordinates

A simple transform with single variable calculus:
$$
\begin{cases}
x=\rho\cos\theta\\
y=\rho\sin\theta
\end{cases},\begin{cases}
dx=\cos\theta d\rho-\rho\sin\theta d\theta\\
dy=\sin\theta d\rho+\rho\cos\theta d\theta
\end{cases},d\rho=\rho'(\theta)d\theta
$$

### Gradient Field

Sometimes, the integrated vector field is some gradient of a numeric field, in which case, the process of line integral is the reverse process of taking gradient. We hereby give the fundamental theorem of calculus for line integrals, and hereby prove it.
$$
\int_C\nabla f\cdot d\vec{r}=\int_Cf'_xdx+f'_ydy=\int_Cdf=f(P_1)-f(P_2)
$$
To prove the theorem, we assume there is an appropriate parameterization.
$$
\begin{cases}
x=x(t)\\
y=y(t)
\end{cases},
\int_C\nabla f\cdot d\vec{r}=\int_{t_1}^{t_2}(f'_xx'(t)+f'_yy'(t))dt=\int_C\frac{df}{dt}dt=f(x(t_2),y(t_2))-f(x(t_1),y(t_1))
$$
Thus, proved.

It may be pointed out that the result of integration is independent of the specific path of the integral curve, when the vector field is gradient of some numeric field, but only determined by the starting and ending spot of the integral, which is called the property of Path Independence.

If a vector field is path-independent, line integral along closed trajectory is always 0, and the term and the result is equivalent here. In general, being a gradient, path independence and conservative field means the same thing.

To prove that path independence and 0 result for closed curve are equivalent, we assume in a certain field, we compute line integral along 2 different curves with the same origin and destination. If any of the terms should hold, the other should hold also, for the sum of the line integral along a certain curve and along the same curve backwardly is 0.

 We hereby list the equivalent statements.

1. $\vec{F}$ is conservative. $\int_C\vec{F}\cdot d\vec{r}=0$, for any closed curve $C$.
2. $\int_C\vec{F}\cdot d\vec{r}$ is path independent.
3. $\vec{F}$ is a gradient field.

The integral along closed curve has a special notation.
$$
\oint_C\vec{F}\cdot d\vec{r}
$$


### Testing whether it is a Gradient Field

The useful property here is the second derivative property of continuous functions.
$$
f''_{xy}=f''_{yx}
$$
Therefore, if the following term is true, the vector field is some kind of gradient.
$$
M_y=N_x
$$
If it is proved that the vector field is a gradient, we may try to find the potential field.

### Finding Potential

According to the fundamental theorem of calculus, a potential field may be given by the line integral of its gradient and a certain starting spot. For convenience, we may as well choose the starting to be the origin.
$$
f(x,y)=\int_C\nabla f\cdot d\vec{r}+f(0,0)
$$
Also for convenience, the choice of integral curve, $C$ , is bounded to be the 2 parallel line to the axises. Namely, a horizontal and vertical line, from $(0,0)$ to $(x,0)$, and from $(x,0)$ to $(x,y)$, or $y$ goes first.
$$
\int_{C_x}\vec{F}\cdot d\vec{r}=\int_0^xMdx,\int_{C_y}\vec{F}\cdot d\vec{r}=\int_0^yNdy,f=\int_{C_x}\vec{F}\cdot d\vec{r}+\int_{C_y}\vec{F}\cdot d\vec{r}+C
$$
In addition, we may look at the problem by the prospective of anti-derivative, which means we take the integral by part.
$$
f=\int Mdx+g(y),f_y'=M+g'_y=N
$$

### Curl

$$
curl(\vec{F})=N_x'-M_y'
$$

If curl of a certain field is always 0, the field is conservative. In a velocity field, in particular, curl implies how intense is the rotation of the certain motion. Specifically, the curl measures the 2 times of angular velocity of a rotation component of velocity field.

### Green’s Theorem

If $C$ is a closed curve, enclosing a region $R$, counterclockwise, $\vec{F}$ vector field defined and differentiable in $R$, there is:
$$
\oint_C\vec{F}\cdot d\vec{r}=\iint_Rcurl(\vec{F})dA
$$
The direction of counterclockwise is determined by the general agreement of curl, which is $N_x'-M_y'$, not $M_y'-N_x'$.

If the curl in the given region is not defined, maybe goes to infinity or other values, the result of double integral is defined, while the result is meaning less. Thus, in such case, the curl can not be a factor to determine the conservativeness of the field.

To prove the theorem, we simply prove the case of $N=0$, and automatically add the cases together. First, decompose the region into sub-regions.
$$
\oint_CMdx=\oint_{C_1}Mdx+\oint_{C_2}Mdx
$$
The equation holds, for the directions of integration along the overlapping boundaries of the sub-regions are opposite to one another.


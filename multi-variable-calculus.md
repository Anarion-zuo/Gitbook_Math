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
The equation holds, for the directions of integration along the overlapping boundaries of the sub-regions are opposite to one another. The process of proving $C_1$ and $C_2$ is essentially the same. The goal then becomes:
$$
\oint_{C_1}Mdx=\iint_{R_1}-M_ydA
$$
where $R_1$ is given by 2 function $f_1(x)$ and $f_2(x)$ with 2 vertical boundary $x=a,b$. There is:
$$
\int_{C_1}Mdx=\int_a^bM(x,f_1(x))dx+\int_b^aM(x,f_2(x))dx+0+0
$$
Thus, proved.

An application of line integral according to Green’s Theorem is to compute the area of any shape of region with given boundary.
$$
Area=\iint_RdA=\oint_Cxdy=\frac{1}{2}\oint_Cxdy-ydx
$$

### Flux

For a given plain curve $C$ and vector field $\vec{F}$:
$$
Flux=\int_C\vec{F}\cdot\hat{n}ds
$$
where $\hat{n}$ is the unit normal vector taking the direction of the right-hand-side of the direction moving along the curve and $ds$ is a tiny length of the curve, whereas the line integral for work takes dot product with tangent directions.

Take the vector field to be the velocity field of some fluid. Flux measures how much fluid passes through $C$ per unit time. What flows across $C​$ from left to right is counted positively, while from right to left negatively.

#### Coordinate Calculation

Since $\hat{n}$ can be given by rotated $\hat{T}$, a similar coordinate expression may be given to $\hat{n}$.
$$
\hat{n}ds=(dy,-dx)
$$
For $\vec{F}=(P,Q)​$:
$$
\int_C\vec{F}\cdot\hat{n}ds=\int_C-Qdx+Pdy
$$

#### Green’s Theorem

If $C$ is encloses a region $R$ counterclockwise and $\vec{F}=(P,Q)$, there is:
$$
\oint_C\vec{F}\cdot\hat{n}ds=\iint_Rdiv\vec{F}dA,div\vec{F}=P'_x+Q'_y
$$
If take transformation $N=P,M=-Q$, the form of the equation goes back to the Green Theorem for work.

### Validity of Green’s Theorem

2 different forms of Green’s Theorem:
$$
\oint_C\vec{F}\cdot\hat{T}ds=\iint_Rcurl\vec{F}dA,\oint_C\vec{F}\cdot\hat{n}ds=\iint_Rdiv\vec{F}dA
$$
Only works if $\vec{F}$ is defined everywhere in $R$. However, the region can carry a hole, ruling out the undefined points, while Green’s Theorem still holds.
$$
\oint_{C'}\vec{F}\cdot d\vec{r}-\oint_{C''}\vec{F}\cdot d\vec{r}=\iint_Rcurl\vec{F}dA
$$
where $C'$ is the outer bound, counterclockwise, and $C'$ is the inner bound, clockwise. If take:
$$
\vec{F}=\frac{-y\hat{i}+x\hat{j}}{x^2+y^2}
$$
the undefined point is at $(0,0)$. Then, $C''$ is a tiny circle surrounding the origin, if the original region $R$ contains the origin. In the places not containing the origin, the result of line integral is 0.

#### Simply Connected Region

The interior of any closed curve in $R$ is also in $R$, which gives the definition of simply connected region. Namely, the region contains no holes. If the domain where $\vec{F}$ is defined and differentiable is simply connected, it can always apply Green’s Theorem. A better theorem of the previous sentence may be: If $curl\vec{F}=0$ and domain where $\vec{F}$ is defined is simply connected, $\vec{F}$ is conservative and is a gradient.

## Triple Integral

## Triple Vector Field

$$
\vec{F}=(P(x,y,z),Q(x,y,z),R(x,y,z))
$$

### Flux

Flux will be measured in a surface, therefore it is a surface integral.
$$
\pm Flux=\iint_S\vec{F}\cdot\hat{n}dS=\iint_S\vec{F}\cdot d\vec{S}\
$$
where the positive direction of the normal vector must be previously given. For polar coordinates:
$$
dS=\rho^2\sin\phi d\phi d\theta
$$
The major question continuously asked is:
$$
\hat{n}dS=?
$$


#### Simple Parallel Planes

For planes like:
$$
H:z=a,\pm\hat{n}=(0,0,1),dS=dxdy
$$
The integral becomes a common double integral.

#### Sphere of Radius $a$

$$
\hat{n}=\frac{1}{a}(x,y,z),dS=a^2\sin\phi d\phi d\theta
$$

#### Cylinder of Radius a on z-axis

$$
H:x^2+y^2=a^2,\hat{n}=\frac{1}{a}(x,y,0),dS=adzd\theta
$$

#### Any $z=f(x,y)$

$$
d\vec{S}=\hat{n}dS=\pm(-f_x',-f_y',1)dxdy
$$

The integrating region on xy plane is given by the shadow of the original plane. The transformation is given by:
$$
(dx,0,f_x'dx)\times(0,dy,f_y'dy)
$$

#### General Coordinate Form

For a given transform:
$$
\begin{cases}
x=x(u,v)\\
y=y(u,v)\\
z=z(u,v)
\end{cases},\vec{r}=\vec{r}(u,v)
$$
There is:
$$
\hat{n}dS=(\frac{\partial\vec{r}}{\partial u}du)\times(\frac{\partial\vec{r}}{\partial v}dv)=(\frac{\partial\vec{r}}{\partial u}\times\frac{\partial\vec{r}}{\partial v})dudv
$$
If we know a normal vector $\vec{N}$, not necessarily unit, maybe given by the gradient of the given surface, the surface element is given by the angle between the surface and the axis plane:
$$
dA=\cos\alpha dS,\cos\alpha=\frac{\vec{N}\cdot\hat{k}}{|\vec{N}||\hat{k}|}
$$
where $dA$ is the surface element on the axis plane. Therefore, there is:
$$
\hat{n}dS=\frac{\vec{N}}{\vec{N}\cdot\hat{k}}dA=\frac{\vec{N}}{\vec{N}\cdot\hat{k}}dxdy
$$
The similar form works also for $dxdz$ and $dydz​$.

#### Divergence Theorem

To give a deeper explanation on divergence, we first look at the notation $\nabla$.
$$
\nabla f=(\frac{\partial f}{\partial x},\frac{\partial f}{\partial y},\frac{\partial f}{\partial z})
$$
Abstractly, we consider it as an operator.
$$
\nabla=(\frac{\partial}{\partial x},\frac{\partial}{\partial y},\frac{\partial}{\partial z})
$$
Then, the divergence of a certain vector field $\vec{F}$ is:
$$
\nabla\cdot\vec{F}
$$
Laplace operator uses a similar notation.
$$
\nabla^2f=\nabla\cdot\nabla f=\frac{\partial^2 f}{\partial x^2}+\frac{\partial^2 f}{\partial y^2}+\frac{\partial^2 f}{\partial z^2}
$$
where $f$ is a numeric function.

The divergence theorem is stated as follows.

If $S$ is a closed surface enclosing a region $D$ and $\hat{n}$ points outward and $\vec{F}$ is defined and differentiable everywhere in $D$, there is:
$$
\oiint_S\vec{F}\cdot d\vec{S}=\iiint_D div\vec{F}dV,div\vec{F}=P_x'+Q_y'+R_z'
$$

### Line Integral

The definition is similar to the 2 dimensional case.
$$
\int_C\vec{F}\cdot d\vec{r}=\int_CPdx+Qdy+Rdz
$$
The method of solving, similarly, is to parameterize $C$, thus gets a simple single variable case. The properties of conservative field still apply here.

To check whether the vector field is a gradient, we apply the old ideas of checking second derivatives.
$$
P_y'=Q_x',P_z'=R_x',Q_z'=R_y'
$$
The perspective of anti-derivative is still a good way of computing the numeric conservative field. 

### Curl

For given $\vec{F}=(P,Q,R)​$:
$$
curl\vec{F}=(R_y'-Q_z',P_z'-R_x',Q_x'-P_y')
$$
If $\vec{F}$ is defined in a simply connected region, $\vec{F}$ is conservative is equivalent to $curl\vec{F}=0$. A better notation of curl is:
$$
curl\vec{F}=\nabla\times\vec{F}
$$

### Stoke’s Theorem

For given closed curve $C$, and any surface $S$ bounded by $C​$:
$$
\oint_C\vec{F}\cdot d\vec{r}=\iint_S(\nabla\times\vec{F})\cdot\hat{n}dS=\iint_Scurl\vec{F}\cdot\hat{n}dS
$$
where the direction of the normal vector is given by the direction of right hand curl of the direction of $C$. Another way of deciding the positive direction is to walk along the curve hold the left hand pointing towards the inner surface and the direction is the pointing of head. The theorem can also apply to the 2 dimensional case of line integral, which is Green’s Theorem.

## Colusions

A integral formula consists of 2 parts, one signifies integrating variable and the other signifies integrated variable. Here we categorize the forms of integral according to the forms of these variables.

### Both Scalars

$$
\int f(x)dx,\iint f(x,y)dxdy,\iiint f(x,y,z)dxdydz
$$

These are the simplest forms of integral, which are the goal of other forms.

A little more complex form is when the coordinates get bent.
$$
\int_Lfdl,\iint_SfdS,\iiint_VfdV
$$
By some simple transform, they can go back to the simplest form.
$$
dl=\sqrt{1+(y_x')^2}dx=\sqrt{(x'_t)^2+(y_t')^2}dt,dS=\sqrt{1+z_x'^2+z_y'^2}dxdy
$$
Under polar coordinates:
$$
\begin{cases}
x=\rho\cos\theta\\
y=\rho\sin\theta
\end{cases},\frac{\partial(x,y)}{\partial(\rho,\theta)}=\rho
$$

$$
\begin{cases}
x=\rho\cos\phi\cos\theta\\
y=\rho\cos\phi\sin\theta\\
z=\rho\sin\phi
\end{cases},\frac{\partial(x,y,z)}{\partial(\rho,\theta,\phi)}=\rho^2\cos\phi
$$

### Both Vectors

#### Line Vectors

$$
\int_L\vec{F}\cdot d\vec{r}=\int_LPdx+Qdy+Rdz=\iint_D curl\vec{F}dS
$$

#### Surface Vectors

$$
Flux=\iint_\Sigma Pdydz+Qdxdz+Rdxdy=\iint_\Sigma\vec{F}\cdot\hat{n}dS=\iiint_\Omega div\vec{F}dV
$$

where $L​$ encloses $D​$ and $\Sigma​$ encloses $\Omega​$. In both cases the form of integral is transform into the former case, which does not include any vector. 
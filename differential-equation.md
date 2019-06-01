# Differential Equation

## Second Order Equations

### Homogeneous

We are here to find all of the solutions of the equation.
$$
y''+p(x)y'+q(x)y=0\rightarrow y_1,y_2
$$
By saying ‘all’, we simply means that we must find a independent pair of solutions of the equation.

The definition of ‘independent’ is with $y_1$ and $y_2$.
$$
y_2\ne Cy_1,y_1y_2\ne 0,\forall C
$$
All solutions are:
$$
y=c_1y_1+c_2y_2
$$

#### Why is that all of the solutions?

##### Superposition Principle

The superposition principle says the linear combination of a pair of independent solution is a solution. The proof goes as follows.

Rewrite the equation:
$$
D^2y+pDy+qy=0\rightarrow (D^2+pD+q)y=0
$$
$(D^2+pD+q)$ can be considered as a linear operator, noted as $L$. Therefore the equation means:
$$
Ly=0
$$
The operator holds the properties of linear operator and can be easily proofed.
$$
\begin{align*}
L(u_1+u_2)&=L(u_1)+L(u_2)\\
L(cu)&=cL(u)
\end{align*}
$$
The proof is simple by such way of illustrating:
$$
L(c_1y_1+c_2y_2)=c_1L(y_1)+c_2L(y_2)=0
$$

##### Normalized Solution

So the linear combination is a solution. Now, let us proof it is the all of the solutions. First, we proof for each initial state, the equation gives a unique solution.
$$
\begin{cases}
c_1y_1(x_0)+c_2y_2(x_0)=a\\
c_1y_1'(x_0)+c_2y_2'(x_0)=b
\end{cases}
$$
The equation is solvable if and only if:
$$
y_1y_2'\ne y_2y_1'
$$
In another word, the determination or Wronskian is not 0.

If $y_1$ and $y_2$ is dependent, the $c_1$ and $c_2$ cannot be solved and Wronskian is always 0. If not the case, there always would be a pair of $c_1$ and $c_2$ that represents a solution.

The definition of normalized solution is a solution which satisfies a very unique initial state.
$$
Y_1(x_0)=1,Y_2(x_0)=0,Y_1'(x_0)=0,Y_2'(x_0)=1\quad x_0\text{ is commonly 0}
$$
To get the normalized solution, we simply plug in 0 to a easy solution we have.
$$
y(0)=1,y'(0)=0\rightarrow Y_1\\
y(0)=0,y'(0)=1\rightarrow Y_2\\
$$
Then, the initial value problem is automatically solved, for it is defined in such way.
$$
y=y_0Y_1+y_0'Y_2
$$

##### Existence and Uniqueness Theorem

The theorem for second order differential equation says for a given initial state, the equation gives one and only one solution, as is mentioned somewhere above. Therefore, for every initial state that exists, there is a unique solution that is given by it. For every solution that exists, there is a unique initial state that gives it. The proof is done.

### Inhomogeneous

$$
y''+p(x)y'+q(x)y=f(x),Ly=f(x)
$$

where $f(x)$ is named as put, driving term, forcing term, signal… The solution is called response, output… The solution consists of 2 parts, homogeneous part and the particular part. 
$$
y_c/y_h=c_1y_1+c_2y_2\quad\text{//homogeneous solution}
$$
The particular solution satisfies the inhomogeneous equation, somehow.
$$
y=y_p+c_1y_1+c_2y_2
$$


#### Proof that It is the Solution

$$
Ly=L(y_p)+L(c_1y_1+c_2y_2)=f(x)+0
$$

#### Proof There is No Other Solution

If $u(x)$ is a solution, $L(u)=f(x)$. For a given $y_p$, $L(y_p)=f(x)$.
$$
L(u-y_p)=L(u)-L(y_p)=0
$$
Therefore:
$$
u-y_p=some\_constant
$$
Every solution of the equation can be represented by the previous method.

#### Transient Solution

Consider the case of first order linear equation.
$$
y'+ky=q(t),y=e^{-kt}\int q(t)e^{kt}dt+ce^{-kt}=y_p+y_c
$$
When $k>0$, $y_c$ goes to 0, as $t$ goes to infinity, therefore called the transient solution. Otherwise, there is no such difference. 

From now on, we only talk about linear equations.

For second order equations, if asking for a transient solution, it is to determine when the homogeneous solution goes to 0.

| Roots        | Solutions                       | Stable        |
| ------------ | ------------------------------- | ------------- |
| $r_1\ne r_2$ | $c_1e^{r_1t}+c_2e^{r_2t}$       | $r_1<0,r_2<0$ |
| $r_1=r_2=r$  | $(c_1+c_2t)e^{rt}$              | $r<0$         |
| $r=a\pm bi$  | $e^{at}(c_1\cos bt+c_2\sin bt)$ | $a<0$         |

In general, the stable condition is the characteristic root has negative real part.

### Exponential Input

$$
f(x)=e^{\alpha x},\alpha\in \C
$$

Rewrite the left-hand side of the equation, since we only talk about linear equations here.
$$
p(D)y=(D^2+AD+B)y=f(x)
$$
Hence, obviously, P for polynomial:
$$
P(D)e^{\alpha x}=P(\alpha)e^{\alpha x}
$$
The solution is:
$$
y_p=\frac{e^{\alpha x}}{P(\alpha)}
$$

#### When $P(\alpha)=0$ or More 0s

##### Exponential shift rule

$$
P(D)e^{\alpha x}u(x)=e^{\alpha x}P(D+\alpha)u(x)
$$

##### Result

If $P'(\alpha)\ne 0$:
$$
y_p=\frac{xe^{\alpha x}}{P'(\alpha)}
$$
If not:
$$
y_p=\frac{x^2e^{\alpha x}}{P'(\alpha)}
$$
In general:
$$
y_p=\frac{x^ne^{\alpha x}}{P^{(n)}(\alpha)}
$$

##### Proof of Simple Root Case

Suppose:
$$
P(D)=(D-a)(D-b),a\ne b
$$
Then:
$$
P'_D(D)=2D-a-b,P'_D(a)=a-b
$$
Plug in the target:
$$
P(D)\frac{xe^{\alpha x}}{P'(\alpha)}=e^{\alpha x}\frac{(D+a-b)Dx}{P'(\alpha)}=e^{\alpha x}
$$

#### Example: Resonance

$$
y''+w_0^2y=\cos w_1t,w_0\ne w_1
$$

Operator form:
$$
(D^2+w_0^2)y=\cos w_1t
$$
Complex form of input:
$$
(D^2+w_0^2)\tilde{y}=e^{iw_1t},\tilde{y}_p=\frac{e^{iw_1t}}{w_0^2-w_1^2}
$$
The final result:
$$
Re(\tilde{y}_p)=\frac{\cos w_1t}{w_0^2-w_1^2}
$$
If the frequency is so close, the response will be very large. If equals:
$$
y''+w_0^2y=\cos w_0t,(D^2+w_0^2)\tilde{y}=e^{iw_0t}
$$
The response is:
$$
\tilde{y}_p=\frac{e^{iw_1t}}{2iw_0^2},Re(\tilde{y}_p)=\frac{t\sin w_0t}{2w_0}
$$

The amplitude grows with slop $\frac{1}{2w_0}$. When the 2 frequency equals each other, the result must be found by a limit. First, we find a solution of a better form to compute the limit.
$$
w_0\rightarrow w_1,y_p=\frac{\cos w_1t-\cos w_0t}{w_0^2-w_1^2}=\frac{t\sin w_0t}{2w_0}
$$
By the way:
$$
\cos w_1t-\cos w_0t=2\sin\frac{w_0-w_1}{2}t\sin\frac{w_0+w_1}{2}t
$$
When the 2 frequency get so close, $\sin\frac{w_0-w_1}{2}t$, as the amplitude, gets larger period and tends to linear function, as is computed above.

#### Example: Damped Resonance

Classic Physics expression:
$$
mx''+cx'+kx=f_s(t)
$$
Simplified form:
$$
x''+2px'+w_0^2x=f_s(t)
$$
If drive it with another frequency:
$$
x''+2px'+w_0^2x=\cos wt
$$
The maximum amplitude:
$$
w_r=\sqrt{w_0^2-2p^2}
$$

## Fourier Series

For every function, there is:
$$
f(t)=c_0+\sum_{n=1}^\infty(a_n\cos nt+b_n\sin nt)
$$
For a second order equation:

| Input        | Response                                    |
| ------------ | ------------------------------------------- |
| $b_n\sin nt$ | $b_ny_n^{(s)}(t)$                           |
| $a_n\cos nt$ | $a_ny_n^{(c)}(t)$                           |
| $f(t)$       | $\sum(a_ny_n^{(c)}(t)+b_ny_n^{(s)}(t))+c_1$ |

### Compute Fourier Series

#### Orthogonality

For 2 functions $u(t)$ and $v(t)$ with period $2T$, if:
$$
\int_{-T}^Tu(t)v(t)dt=0
$$
The 2 function are orthogonal. For a set of trig-functions:
$$
\left\{\sin n_1t,...,\cos n_2t,...\right\},n_1,n_2\in \N
$$
Any 2 distinct ones are orthogonal on $[-\pi,\pi]$.

##### Some Proof of Orthogonality

$$
\int_{-\pi}^\pi\cos^2t=\int_{-\pi}^\pi\sin^2t=\pi
$$

1. Trig Identities

2. Complex Exponential
3. ODE

For any function in the set $\sin nt,\cos mt,m\ne n$, they both satisfy:
$$
u''+n^2u=0
$$
Suppose $u_n,v_m$ is some 2 functions from the set. Plug in the definition of orthogonality:
$$
\int_{-\pi}^\pi u_n''v_mdt=u'_nv_m\Big|^{\pi}_{-\pi}-\int_{-\pi}^\pi u_n'v_m'dt
$$

On both sides:
$$
\int_{-\pi}^\pi u_n''v_mdt=-\int_{-\pi}^\pi n^2u_nv_mdt,u'_nv_m\Big|^{\pi}_{-\pi}=0
$$
The equation is:
$$
n^2\int_{-\pi}^\pi u_nv_mdt=\int_{-\pi}^\pi u_n'v_m'dt
$$
LHS is not symmetric with $u$ and $v$ while RHS is. Therefore both sides are 0.

#### Compute each Term

If we write:
$$
f(t)=...+a_n\cos nt+...
$$
In order to find $a_n$, we multiply $\cos nt$ to both sides and take integration:
$$
\int_{-\pi}^\pi f(t)\cos ntdt=a_n\int_{-\pi}^\pi\cos^2 ntdt=a_n\pi
$$
Therefore,
$$
a_n=\frac{1}{\pi}\int_{-\pi}^\pi f(t)\cos ntdt,b_n=\frac{1}{\pi}\int_{-\pi}^\pi f(t)\sin ntdt,n\in \N^+
$$
However, the constant term is different.
$$
\int_{-\pi}^\pi f(t)dt=2\pi c_0,c_0=\frac{1}{2\pi}\int_{-\pi}^\pi f(t)dt
$$
It can be told from the formula that for a certain function there is only one set of Fourier series.

Another way of expressing the constant term is:
$$
c_0=\frac{a_0}{2}
$$


#### Example

For a discontinuous function:
$$
f(x)=(-1)^\left\lfloor\frac{x}{\pi}\right\rfloor
$$

$$
a_n=0,b_n=-\int_{-\pi}^0\sin ntdt+\int^{\pi}_0\sin ntdt=\frac{2}{n}(1-\cos n\pi)=\begin{cases}\frac{4}{n}&\text{n odd}\\0&\text{n even}\\\end{cases}
$$

#### Simplification

The shorten calculation uses the property of even and odd. A even function has no $\sin$ terms. Same thing goes for odd functions. When integrating even functions, we can take half of the integration and times 2.

Even case:
$$
a_n=\frac{2}{\pi}\int_0^\pi f(t)\cos ntdt,b_n=0
$$
Odd case:
$$
b_n=\frac{2}{\pi}\int_0^\pi f(t)\sin ntdt,a_n=0
$$

#### Odd Example

 The function is a periodic function which in $[-\pi,\pi]$ the function is $f(t)\overset{\Delta}= t$.
$$
b_n=\frac{2}{\pi}\int_0^\pi t\sin ntdt=(-1)^{n+1}\frac{2}{n},f(t)=2\sum_{n=1}^\infty(-1)^{n+1}\frac{1}{n}t
$$
Visually, we find the Fourier series analyze functions on a whole perspective, while Taylor series make an approximation at the center. The first terms of Fourier series do not necessarily look the same as the original function. 

#### Convergence Theorem

The Theorem goes:

- If $f(t)$ is continuous at $t_0$, the function strictly equals its Fourier series, while otherwise, not quite.

Therefore, the previous example is not so correct. At the jumping point of the function, the series converges at the midpoint of the upper and lower jumping position. 

#### Extension on Frequency

A simple transform on the coefficient of $t$ can explore the case of variant frequency. Suppose period is $2L$, the series become:
$$
a_n=\frac{2}{L}\int_{-L}^Lf(t)\cos\frac{n\pi}{L}tdt,b_n=\frac{2}{L}\int_{-L}^Lf(t)\sin\frac{n\pi}{L}tdt
$$

#### Extension on Periodicity

For an even function, take an interval $[-L,L]$, and make it repeat to make a periodic function. Then, the Fourier series can be useful. For odd function, things are the same to repeat.

### Finding Response with Fourier Series

Take the example of a square signal:
$$
f(t)=\frac{1}{2}+(-\frac{1}{2})^\left\lfloor t+1\right\rfloor
$$
In order to save some work, use a simple transformation to make $f$ a odd function.
$$
f(t)\leftarrow f(t)-\frac{1}{2}=(-\frac{1}{2})^\left\lfloor t+1\right\rfloor-\frac{1}{2}
$$
![1551273230622](C:\Users\a\AppData\Roaming\Typora\typora-user-images\1551273230622.png)

For another example mentioned above, a square signal with period $2\pi$ and in interval $[-\pi,\pi]$:
$$
g(u)=\begin{cases}1&u\ge0\\-1&u<0\end{cases}
$$
The Fourier series are:
$$
g(u)=\frac{4}{\pi}\sum\frac{\sin nu}{n}
$$
Hence, the Fourier series of $f$ becomes:
$$
f(t)=\frac{1}{2}+\frac{2}{\pi}\sum_{odd}\frac{\sin n\pi t}{n}
$$
For the case of simplified resonance, if the input is:
$$
f(t)=\frac{a_0}{2}+\sum_{n=1}^\infty(a_n\cos w_nt+b_n\sin w_nt)
$$
And the equation is:
$$
x''+w_0^2x=f(t)
$$
According to the superposition principle, a particular response may be:
$$
x_p=\frac{a_0}{2w_0^2}+\sum_{n=1}^\infty\frac{a_n\cos w_nt+b_n\sin w_nt}{w_0^2-w^2}
$$

## Laplace Transform

Take a look at Taylor series, all of the functions can be expressed as:
$$
A(x)=\sum_{n=0}^\infty a_nx^n
$$
Take this idea into the continuous world:
$$
\int_0^\infty a(t)x^tdt=A(x)
$$
which forms a transform between $a$ and $A$. A better form:
$$
x=e^{\ln x},x^t=e^{t\ln x}
$$
For the series to converge:
$$
x\in(0,1)
$$
In general, Laplace transform is:
$$
\int_0^\infty f(t)e^{-st}dt=F(s),\mathscr{L}(f(t))=F(s),s>0
$$
The difference between transform and operator is, obviously, that transform gives a function to another variable while operator does not change the variable of the input. Laplace transform is a linear transform, integration itself is a mean of linear transform.
$$
\mathscr{L}(f+g)=\mathscr{L}(f)+\mathscr{L}(g),\mathscr{L}(cf)=c\mathscr{L}(f)
$$

### Exponential Shift

$$
\mathscr{L}(e^{at}f(t))=\int_0^\infty e^{-(s-a)t}f(t)dt=F(s-a),\text{ when }s>0
$$

Also holds for exponential:
$$
e^{(a+bi)t}\rightarrow\frac{1}{s-(a+bi)}
$$
Hence, for sin and cos:
$$
\cos at=\frac{e^{iat}+e^{-iat}}{2}=\frac{\frac{1}{s-ia}+\frac{1}{s+ia}}{2}=\frac{s}{s^2+a^2},\sin at=\frac{a}{s^2+a^2}
$$

### Polynomial

$$
\int_0^\infty t^ne^{-st}dt
$$

| $t^n$     | $nt^{n-1}$            | …    | 1                            | 0                                    |
| --------- | --------------------- | ---- | ---------------------------- | ------------------------------------ |
| $e^{-st}$ | $-\frac{1}{s}e^{-st}$ | …    | $(-1)^n\frac{1}{s^n}e^{-st}$ | $(-1)^{n+1}\frac{1}{s^{n+1}}e^{-st}$ |

For the first term in the partial integral operation:
$$
\lim_{t\rightarrow\infty}\frac{t^ne^{-st}}{s}=0
$$
Therefore:
$$
\int_0^\infty t^ne^{-st}dt=\frac{n}{s}\int_0^\infty t^{n-1}e^{-st}dt
$$
Hereby gets a reduction form. Finally:
$$
\mathscr{L}(t^n)=\frac{n!}{s^{n+1}}
$$

### Condition of Existence

There is some constant $c,k>0$,
$$
|f(t)|\le ce^{kt}
$$
In other word:
$$
\frac{|f(t)|}{e^{kt}}\text{ exists every where no matter how big is }k
$$

### Inverse Transform

For fractional polynomials, do the partial fraction operation and find the inverse by exponential shift.
$$
\frac{1}{s(s+3)}=\frac{1}{3}(\frac{1}{s}-\frac{1}{s+3})\rightarrow\frac{1}{3}(1-e^{-3t})
$$

### Solve Equations

$$
y''+Ay'+By=h(t)
$$

The initial condition has to be specified at first.
$$
y(0)=y_0,y'(0)=y'_0
$$
The Laplace transform of the response $Y(s)$ is always some fractional polynomial $\frac{p(s)}{q(s)}$. Apply the inverse transform then get the answer. Before everything else, we want to find out the derivative form of Laplace transform by partial integration.
$$
\mathscr{L}(f'(t))=\int_0^\infty e^{-st}f'(t)dt=-f(0)+\int_0^\infty se^{-st}f(t)dt=sF(s)-f(0)
$$
For second derivative:
$$
\mathscr{L}(f''(t))=s\mathscr{L}(f'(t))-f'(0)=s^2F(s)-sf(0)-f'(0)
$$
For nth derivative:
$$
F_n(s)=sF_{n-1}(s)-f^{(n-1)}(0)
$$
Now since the formula table is complete, we can have an example.
$$
y''-y=e^{-t},y(0)=1,y'(0)=0
$$

1. Apply Laplace transform upon the whole equation.
   $$
   (s^2-1)Y=\frac{1+s+s^2}{s+1},Y=\frac{s^2+s+1}{(s+1)^2(s-1)}
   $$

2. Partial fraction and find the inverse transform.
   $$
   \frac{s^2+s+1}{(s+1)^2(s-1)}=\frac{-1/2}{(s+1)^2}+\frac{1/4}{s+1}+\frac{3/4}{s-1}
   $$

   $$
   y=-\frac{1}{4}e^{-t}+\frac{3}{4}e^t
   $$

### Jump Discontinuities

The classic example is the unit jump function:
$$
u(t)=\begin{cases}0&t<0\\1&t>0\\undefined&t=0\end{cases}
$$
To generalize it:
$$
u_a(t)=u(t-a)
$$
Further more, the unit box function:
$$
u_{ab}(t)=u_a(t)-u_b(t)
$$
By multiplying the unit box function to another arbitrary function, we can wipe out the other parts of the function except for a certain interval. It is obvious that the Laplace transform of $u(t)$ is $\frac{1}{s}$. However, the real question is: what is the inverse transform of $\frac{1}{s}$? Such kind of problem may occur for many other functions, where the negative variable is not taken care of. In order to prevent ambiguousness, we define that all of the result of inverse transform is some function times the unit step function and we do not care about the negative half.

#### An Important Fact

There is no such way of describing $\mathscr{L}(f(t-a)),a>0$ in terms of $\mathscr{L}(f(t))$, for there is a part of the function that the transform has never seen or taken into consideration. When taking Laplace transform, we automatically abandon the information in the negative half. If accepting the fact that the information cannot be recovered, we can write down the right formula.
$$
\mathscr{L}(u_a(t)f(t-a))=e^{-as}\mathscr{L}(f(t))
$$
Formal calculation:
$$
\mathscr{L}(u_a(t)f(t-a))=e^{-sa}\int_{-a}^\infty e^{-st}u(t)f(t)dt=e^{-sa}\int_{0}^\infty e^{-st}u(t)f(t)dt
$$

#### Unit Box Function

$$
\mathscr{L}(u_{ab}(t))=\mathscr{L}(u(t-a))-\mathscr{L}(u(t-b))=\frac{e^{-as}-e^{-bs}}{s}
$$

## Convolution

The introduction to convolution is to find a certain transform from $f,g$ to the product of their Laplace transform result. It is hereby defined.
$$
F(s)G(s)=\int_0^\infty e^{-st}(f*g)dt
$$
Following the idea of coming from discrete world to continuous world, the behavior of power series, when multiplied, can be the reference to the convolution operation.
$$
F(x)=\sum_{n=0}^\infty a_nx^n,G(x)=\sum_{n=0}^\infty b_nx^n,F(x)G(x)=\sum_{n=0}^\infty c_nx^n
$$
The convolution formula is:
$$
f(t)*g(t)=\int_0^tf(u)g(t-u)du
$$
Some property can be easily proofed:
$$
f*g=g*f
$$

### Proof of Convolution

Convert the problem into double integral:
$$
F(s)G(s)=\int_0^\infty e^{-su}f(u)du\times\int_0^\infty e^{-sv}g(v)dv=\int_0^\infty\int_0^\infty e^{-s(u+v)}f(u)g(v)dudv
$$
Suppose $t=u+v$, eliminate $v$ in the formula:
$$
\int_0^\infty\int_0^\infty e^{-s(u+v)}f(u)g(v)dudv=\int_0^\infty\int_0^t e^{-st}f(u)g(t-u)dudt
$$
2 things require some thoughts:

1. The change of variable from $u,v$ to $u,t$ results in a new coefficient before $du,dt$.
   $$
   dudv=\frac{\partial(u,v)}{\partial(u,t)}dudt=dudt
   $$

2. The integral limit of $u$ changes to having upper bound $t$.

### Example: Radioactive Dumping

Suppose there is some radioactive waste needing to be dumped. Define $f(t)$ to be the dump rate where $t$ signifies years. $f(t)$ means between 2 close enough time point $t_i,t_{i+1}$ the amount of waste newly dumped.
$$
f(t)\Delta t=\Delta F(t)
$$
For a certain amount of radioactive substance, its mass obeys the law of:
$$
m=A_0e^{-kt}
$$
where $A_0$ is the initial amount and $k$ is a certain constant corresponding to a certain kind of material. 

At a certain point of time $u_i$, the dumping amount is $f(u_i)\Delta u$, while the time that already has passed is $t-u_i$. The total amount of waste left counting from the first time of dumping is:
$$
\lim_{\Delta u\rightarrow0}\sum_{i=1}^\infty f(u_i)e^{-k(t-u_i)}\Delta u=\int_0^tf(u)e^{-k(t-u)}du=f(t)*e^{-kt}
$$
For a special condition, where the waste does not decay, the answer becomes a simple integral.

## Impulse

In Physics or other subjects, there may be some signal with valid input only in a interval of time.
$$
u_{ab}f(t)
$$
We call that a impulse. Here we only talk about unit impulse, which has integral result 1 and constant value.
$$
imp(t)=\frac{1}{h}u_{oh}(t)=\frac{1}{h}[u(t)-u(t-h)],\mathscr{L}(imp)=\frac{1-e^{-hs}}{hs}
$$
When $h$ goes to 0, Laplace transform goes to 1. The special function is named Dirac Delta function.
$$
\delta(t)=\lim_{h\rightarrow0}\frac{1}{h}[u(t)-u(t-h)]
$$

### Properties

1. Integral
   $$
   \int_{-\infty}^\infty\delta (t)dt=1
   $$

2. Convolution
   $$
   \mathscr{L}(u(t)f(t)*\delta(t))=F(s)
   $$

3. Integration
   $$
   u'(t)=\delta(t)
   $$

### Resonance

$$
y''+y=A\delta(t-\frac{\pi}{2}),y(0)=1,y'(0)=0
$$

$$
y=\cos t-u(t-\frac{\pi}{2})A\cos t
$$

# Systems

$$
\begin{cases}
x'=ax+by+r_1(t)\\
y'=cx+dy+r_2(t)
\end{cases}
$$

Linear differential equation system holds dependent $x,y$ in linear relation and arbitrarily dealing with the common variable $t$. Homogeneous case is $r_1=r_2=0$. The number of initial state variables must be the same with the number of arbitrary constant in the solution.

## Heat Conduction: Naive Idea

An object consisting of a outer layer, temperature $T_2$, and a inner core, temperature $T_1$ is put into a water tank with a given temperature function $T_e(t)$. The layer and the core has different conductivity of heat.
$$
\begin{cases}
\frac{dT_1}{dt}=a(T_2-T_1)\\
\frac{dT_2}{dt}=a(T_1-T_2)+b(T_e-T_2)\\
\end{cases}
$$
Take $a=2,b=3,T_e=0,T_1(0)=40,T_2(0)=45$:
$$
\begin{cases}
\frac{dT_1}{dt}=-2T_1+2T_2\\
\frac{dT_2}{dt}=2T_1-5T_2\\
\end{cases}
$$
Eliminate one of the variables and generate a second order equation:
$$
T_2=\frac{1}{2}T_1'+T_1\rightarrow T_1''+7T_1'+6T_1=0
$$
Eliminating variables generate an equation of the sum of the order of the others. We trade in different kinds of complexity. The system has to be stable or the long term solution has to be constant, hence the coefficients of the simplified equation above must be positive.
$$
T_1=c_1e^{-t}+c_2e^{-6t}
$$
Then, $T_2$ can be easily calculated.

## Autonomous System

No $t$ explicitly shown on the right hand side.
$$
\begin{cases}
x'=f(x,y)\\
y'=g(x,y)
\end{cases}
$$
The solution is a parameterized curve and the derivative, for a given initial state.
$$
\begin{cases}
x=x(t)\\
y=y(t)
\end{cases},\begin{cases}
x'=x(t)\\
y'=y(t)
\end{cases}
$$
The derivative can build up a velocity field, also a form of solution.

The equation mentioned above is an autonomous system, which can be solved by variable elimination. In order to derive a more general case for the linear autonomous system, we rewrite the equation in matrix form.
$$
\begin{pmatrix}x\\y\end{pmatrix}'=\begin{pmatrix}-2&2\\2&-5\end{pmatrix}\begin{pmatrix}x\\y\end{pmatrix}
$$
The solution is:
$$
\begin{pmatrix}x\\y\end{pmatrix}=c_1\begin{pmatrix}1\\\frac{1}{2}\end{pmatrix}e^{-t}+c_2\begin{pmatrix}1\\-2\end{pmatrix}e^{-6t}
$$
From the idea of the matrices form of the solution, we try to find a general method of solving the autonomous equations.

Suppose:
$$
\begin{pmatrix}x\\y\end{pmatrix}=\begin{pmatrix}a_1\\a_2\end{pmatrix}e^{\lambda t}
$$
Substitute this into the equation and solve the algebraic equation like we do in single second order equations. The solution, none 0, of the algebraic linear equation is unique. Therefore the determination of the equation is 0. We hereby solve $\lambda$. The relation between $a_1,a_2$ can be obtained by the equation, but not the exact value, which has to be given by the initial state, and if not, the computation process is wrong.

### General Solution

#### $2\times2$

$$
\begin{pmatrix}x\\y\end{pmatrix}'=\begin{pmatrix}a&b\\c&d\end{pmatrix}\begin{pmatrix}x\\y\end{pmatrix},\text{suppose }\begin{pmatrix}x\\y\end{pmatrix}=\begin{pmatrix}a_1\\a_2\end{pmatrix}e^{\lambda t}
$$

$a_1,a_2,\lambda$ is given by:
$$
\begin{pmatrix}a-\lambda&b\\c&d-\lambda\end{pmatrix}\begin{pmatrix}a_1\\a_2\end{pmatrix}=0
$$
The equation is solvable when the coefficient determination is 0, which gives the characteristic equation.
$$
\lambda^2-(a+d)\lambda+ad-bc=0
$$

#### $n\times n$

In general:
$$
\begin{pmatrix}x\\\vdots\end{pmatrix}'=A\begin{pmatrix}x\\\vdots\end{pmatrix}
$$
$\lambda$s can be given by the eigenvalues of $A$. By solving the system, the eigenvectors belong to $A$ make up of the fundamental solution class of the equation, which form the solution by linear combination. The idea of characteristic equation in differential equation is consistent with the one in linear algebra.
$$
\begin{pmatrix}x_1\\x_2\\\vdots\end{pmatrix}=\sum_{i=1}^nc_i\xi_ie^{\lambda_it},\forall\xi\quad\text{independent}
$$


### Duplicated Eigenvalue

Suppose there is a tank full of water separated into 3 parts. Each part contains the same amount of water, separated by barriers conducting heat with the same speed. Suppose the temperature remains constant in connected water and would only differ between the 2 sides of a barrier. The initial state is that the three sub-tanks has the same temperature.

![1551702231390](C:\Users\a\AppData\Roaming\Typora\typora-user-images\1551702231390.png)
$$
\begin{cases}
a&=1\\
x_1'&=a(x_3-x_1)+a(x_2-x_1)=-2x_1+x_2+x_3\\
x_2'&=x_1-2x_2+x_3\\
x_3'&=x_1+x_2-x_3
\end{cases}
$$
Find $\lambda$:
$$
\det(A)=\det\begin{pmatrix}-2-\lambda&1&1\\1&-2-\lambda&1\\1&1&-2-\lambda\end{pmatrix},\lambda_1=0,\lambda_2=\lambda_3=-3
$$
For $\lambda=0$, we find a constant solution. By common sense in Physics fields, we find the constant solution.

For $\lambda=-3$, find the 2 independent solutions.
$$
\begin{pmatrix}x_1\\x_2\\x_3\end{pmatrix}=c_1\begin{pmatrix}1\\0\\-1\end{pmatrix}e^{-3t}+c_2\begin{pmatrix}1\\-1\\0\end{pmatrix}e^{-3t}+c_3\begin{pmatrix}1\\1\\1\end{pmatrix}
$$

### Defective Eigenvalue

Sometimes, the coefficient matrix cannot be similar diagonalized, and we want to ask complex numbers for help.
$$
\begin{pmatrix}x\\y\end{pmatrix}'=\begin{pmatrix}1&2\\-1&-1\end{pmatrix}\begin{pmatrix}x\\y\end{pmatrix},\lambda^2+1=0,\lambda_1=i,\lambda_2=-i
$$
The real part of the solution is:
$$
x=\cos t,y=-\frac{1}{2}(\cos t+\sin t)
$$
It’s an eclipse.

## Inhomogeneous

$$
\begin{cases}
x'=ax+by+r_1(t)\\
y'=cx+dy+r_2(t)
\end{cases}
$$



### Basic Theorem

#### A

The general solution is:
$$
\begin{pmatrix}x_1\\x_2\\\vdots\end{pmatrix}=\sum_{i=1}^nc_i\xi_ie^{\lambda_it},\forall\xi\quad\text{independent}
$$
The proof consists of 2 parts. The easy part is to prove this is a solution. The hard part is to prove this is the only solution.

#### B: Wronskian of All Solutions

$$
W(\vec{x_1},\vec{x_2},...,\vec{x_n})=|\vec{x_1},\vec{x_2},...,\vec{x_n}|=\det(\vec{x_1},\vec{x_2},...,\vec{x_n})
$$

When Wronskian is always 0, the solution is not linearly independent, and when not, is so., obviously. For a set of valid solution vectors, Wronskian is always not 0.

#### C

The final solution computed for the inhomogeneous equations consists of the solution of the homogeneous version, which is the complementary solution, and the particular solution. The key, therefore, is to find the particular solution.
$$
\vec{x_{gen}}=\vec{x_{c}}+\vec{x_{p}}
$$


### Fundamental Matrix

Put all solutions in a single matrix:
$$
X=(\vec{x_1},\vec{x_2},...,\vec{x_n})
$$

#### Properties

1. $\det X\ne 0$, for any $t$.
2. $X'=AX$

### Example: Mixing Problem

![1551713519888](C:\Users\a\AppData\Roaming\Typora\typora-user-images\1551713519888.png)

There are these 2 tanks connected at the top and bottom with given fluid rate in numbers. The fluid rate must remain balanced, which means the sum of the input rates and output rates equals, as is shown in the picture. There are some kinds of substances in the fluid. The x tank has input salt solution, while y tank has input pure water. Suppose $x,y$ correspond to the concentration of the tanks, respectively. The system is described as:
$$
\vec{x}'=\begin{pmatrix}-3&2\\3&-4\end{pmatrix}\vec{x}+\begin{pmatrix}5e^{-t}\\0\end{pmatrix}
$$

### Variation Parameters

It is a classic method to Solve $\vec{x}'=A\vec{x}+\vec{r}$ and Find $\vec{x_p}$. The theorem says look for a solution of such form:
$$
\vec{x_p}=v_1(t)\vec{x_1}+v_2(t)\vec{x_2}
$$
which is the form of variating arbitrary constant of the solution of homogeneous equations. A more general form:
$$
\vec{x_p}=\sum_{i=1}^nv_i(t)\vec{x_i}=X\vec{v}
$$

Then substitute into the system:
$$
X'\vec{v}+X\vec{v}'=\vec{x_p}'=A\vec{x_p}+\vec{r}=AX\vec{v}+\vec{r}\Rightarrow X\vec{v}'=\vec{r},\text{ where }\exists X^{-1}
$$
There, a particular solution is found.
$$
\vec{x_p}=X\int X^{-1}\vec{r}dt
$$
The general solution is the linear expansion of a fundamental matrix.
$$
\vec{x}=XC
$$
where $C\ne 0$ consists of arbitrary constants.

## Exponential Matrix

For a single equation of such form as $x'=Ax$, the solution is, obviously, $x=e^{At}$. Under the matrix case, where $A$ is a matrix and $x$ consists of multiple functions, thus forms a system, we expand the definition, using Taylor series.
$$
e^{At}=E+At+A^2\frac{t^2}{2!}+A^3\frac{t^3}{3!}+...
$$
Obviously, it satisfies the property of fundamental matrix, thus it is so. Therefore, a exponential matrix gives a form of solution of a homogeneous equation.
$$
\vec{x}=e^{At}\vec{C}=e^{At}\vec{x}(0)
$$
By the way, the inverse matrix of a exponential matrix is straight forward.
$$
(e^A)^{-1}=e^{-A}
$$
By such law, the computation of a fundamental matrix is also straight forward.
$$
e^{At}=\vec{x}(\vec{x}(0))^{-1}
$$

## Decoupling

Apply some linear transform upon the original system:
$$
\begin{cases}
u=ax+by\\
v=cx+dy
\end{cases}
$$
Or in a more general form:
$$
\vec{x}'=A\vec{x},\vec{x}=D\vec{u}
$$
Such that after the transformation, the system turns into a system which looks like:
$$
\begin{cases}
u'=k_1u\\
v'=k_2v
\end{cases},\vec{u}'=\Lambda\vec{u}
$$
where the process should be:
$$
\vec{x}'=D\vec{u}'=AD\vec{u},AD=\Lambda D\Rightarrow\vec{u}'=\Lambda\vec{u}
$$


Such a system is called decoupled, where $\Lambda$ is eigenmatrix of the original coefficient matrix $A$. The solution is obvious.

## Autonomous Non-linear System

$$
\begin{cases}
x'=f(x,y)\\
y'=g(x,y)
\end{cases}
$$

### Closed Trajectory and Limited Cycles

The trajectory goes around in finite time and repeat itself. Due to the existence of some arbitrary constants, the cycles may appear to be quite close to one another, thus form a family of curves. There are some kinds of cycles that are isolated and stable. Stability means the close by curves, both inside and outside, would tend to join the limited cycle as time goes to infinity, while an unstable closed curve has nearby curves go further as time goes on. Some physical sense of such a curve may be if some artificial change is set upon the system, once the factor of change is removed, the system goes back to the original periodic state. In many natural phenomenons, there contains a limited cycles. In general, there is no much method of finding it.

#### Non-existence: Bendixson’s Theorem

Calculate the divergence $div\vec{F}=f_x+g_y$. If it is not 0 in a certain region of $D$, there is no closed trajectory in $D$.

To proof the theorem, we use a indirect proof. Suppose there is a closed trajectory in $D$, calculate flux integral along $C$, the edge of $D$, in positive direction, which is 0, since there is no flux.
$$
\oint_C\vec{F}\cdot\hat{n}dS=\iint div\vec{F}dA=0
$$

Since the divergence is never 0 in $D$, the theorem is then proved.

#### Critical Criteria

If there is no critical point inside region $D$, there is no closed trajectory, where critical points are defined as all derivatives are 0.

### Relation between First-order and Systems

Eliminate $t$ by simple division:
$$
\frac{dy}{dx}=\frac{g(x,y)}{f(x,y)}
$$
The solution is simply a equation of $x$ and $y$. Sometimes, the original system is impossible to solve while the new first-order equation is simple.
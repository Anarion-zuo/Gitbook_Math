## Gamma Function

$$
\Gamma(z)=\int_o^\infty x^{z-1}e^{-x}dx,z>0
$$

### Initial Value and Induction

$$
\Gamma(1)=1,\Gamma(z+1)=\int_o^\infty x^{z}e^{-x}dx=[-x^ze^{-x}]_0^\infty+\int_o^\infty zx^{z-1}e^{-x}dx=z\Gamma(z)
$$



### Integer

$$
\Gamma(z+1)=z\Gamma(z)=z!\quad\text{when }z\in\N^+
$$

### Fraction



### e to the nth

$$
\int_0^\infty e^{-x^n}\,dx=\frac{1}{n}\int_0^\infty u^{1/n-1}e^{-u}\,du=\frac{1}{n}\Gamma(1/n)=\Gamma(1+1/n).
$$


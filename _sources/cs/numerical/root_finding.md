# Root Finding

## Newton's Method
[reference](https://ocw.mit.edu/courses/18-s997-introduction-to-matlab-programming-fall-2011/pages/root-finding/newtons-method/)

A nonlinear equation can always be written as 
$$
f(x) = 0
$$

Newton's method (also known as the Newton-Raphson Method) is an **iterative method**. Iterative methods entail doing the exact same thing over and over again. This is perfect for a computer.

The actual iteration starts from an approximation $x_n$ at the $n$-th step and defines the next one, $x_{n + 1}$:
$$
x_{n + 1} = x_n - \frac{f(x_n)}{f'(x_n)}
$$

Notice that not only do we need to evaluate the function $f$ at $x_n$, but also we need to evaluate the derivative $f'(x_n)$. This could be a problem if the derivative is unknown, or complicated to compute (and there are other methods to use in that case).

## Derivation of Newton's Method
Suppose $r$ is the true root and $x_i$ is a good estimate of $r$, and $r = x_i + h$, or $h = r - x_i$. 

We assume that h is 'small' so than we can use linear approximation
$$
0 = f(r) = f(x_i + h) \approx f(x_i) + h f'(x_i)
$$
and therefore, unless $f'(x_i)$ is close to 0,
$$
h \approx - \frac{f(x_i)}{f'(x_i)}\\
r = x_i + h \approx x_i - \frac{f(x_i)}{f'(x_i)}
$$

## The Secant Method
While Newton's method is fast, it has a big downside: you need to know the derivative of $f$ in order to use it. 

A natural way to resolve this would be to estimate the derivative using 
$$
f'(x) \approx \frac{f(x + \varepsilon) - f(x)}{\varepsilon}
$$
for $\varepsilon \ll 1$. 

The secant method uses the previous iteration to do something similar. It approximates the derivative using the previous approximation. As a result it converges a little slower than Newton's method to the solution
$$
x_{n + 1} = x_n - f(x_n) \frac{x_n - x_{n - 1}}{f(x_n) - f(x_{n-1})}
$$

## Convergence
Different root-finding algorithms are compared by the speed at which the approximate solution sonverges (i.e., gets closer) to the true solution. An iterative method $x_{n + 1} = g(x_n)$ is defined as having $p$-th order convergence if for a sequence $x_n$ where $\lim_{n \rightarrow \infty} x_n = \alpha$ exists then
$$
\lim_{n \rightarrow \infty} \frac{|x_{n + 1} - \alpha|}{|x_{n} - \alpha|^p} = L \ne 0
$$

Newton's method has (generally) second-order convergence. 

To find it experimentally, we take the logarithm of the sequence
$$
\log |x_{n + 1} - \alpha| \approx \log L + p \log |x_n - \alpha|
$$
for $n \gg 1$, which means that the points $(\log |x_n - \alpha|, \log |x_{n + 1} - \alpha|)$ will converge to a line with slope $p$.

## Basins of Attraction
It turns out that the end result (the point to which the method converges, if any) is stringly dependent on the initial guess. Furthermore, the dependence on the first guess can be rather surprising. The set of points that converge to a given root is called the **basin of attraction** of that root. 

We could visualize the basins of attraction by coloring each starting point with a color that corresponds to the root it converges to. The different basins will thus be given different colors.

To make the image interesting, we will focus on 2D. Generalizing Newton's method for higher dimensions is quite straightforward. [reference - the logic is exactly the same as 1D derivation](https://wiki.math.ntnu.no/_media/tma4125/2017v/newton.pdf)
$$
\vec f(\vec x) = \vec 0\\
\vec x_{n + 1} = \vec x_n - (\mathbf J \vec f)^{-1} \vec f(\vec x_n)
$$
where $\mathbf J \vec f$ is the **Jacobian matrix** of $\vec f$, that is 
$$
(\mathbf J \vec f)_{ij} = \frac{\partial \vec f_i}{\partial x_j}
$$

The Jacobian depends on $\vec x$ and thus needs to be re-evaluated at every step. 

[more details](http://www.scholarpedia.org/article/Basin_of_attraction#:~:text=Roughly%20speaking%2C%20an%20attractor%20of,attraction%20and%20their%20practical%20implications.)

### Example
Let
$$
\vec x = \begin{pmatrix} x \\ y \end{pmatrix}\\
\vec f(\vec x) = \begin{pmatrix} x^3 - y \\ y^3 - x \end{pmatrix}
$$
then, the Jacobian matrix is
$$
\mathbf J \vec f = \begin{pmatrix} 3x^2 & -1 \\ -1 & 3y^2 \end{pmatrix}
$$


### improvement
Complex numbers can be used in this situation as a single derivative (not a $2 \times 2$ Jacobian) gives the full derivative information (assuming that the function is analytic -> not all 2D real function can be converted into a complex function).

To be **holomorphic** (complex differentiable), a function must satisfy the **Cauchy-Riemann equations**, which impose a very specific relationship between the partial derivatives of the real and imaginary parts. This means:

The function must be infinitely differentiable (analytic).
It must preserve local angles and shapes (conformal).
It must be orientation-preserving (no reflections or folds).
So, many common 2D functions — like rotations with reflections, or functions with discontinuities, or even smooth but non-conformal mappings — cannot be expressed as holomorphic functions.

#### Cauchy-Riemann equations
If a function $f(z) = u(x, y) + i v(x, y)$ is differentiable in the complex sense (i.e., holomorphic), it satisfies the Cauchy-Riemann equations:
$$
\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y}\\
\frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x}
$$

- [ ] TODO#1 put codes in
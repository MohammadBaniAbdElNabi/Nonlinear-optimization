# **Exercises**

**5.1**

Consider the function $f(x, y) = 3x^2 - 2xy + y^2 + 3e^{-x}$. Is this function convex, concave, or neither? Explain your answer.

**5.2**

Consider the function $f(x) = x^4 - 8x^3 + 24x^2 - 32x + 16$. Is this function convex, concave, or neither? Explain your answer.

**5.3**

Consider the following nonlinear problem. Is the feasible region convex?

$$
\begin{align*}
\text{minimize} \quad & f(x, y) = x - 2xy + 2y \\
\text{subject to} \quad &  x^2 + 3y^2 \leq 10 0 \\  
& 3x + 2y \geq 1 \\
& x, y \geq 0
\end{align*}
$$

**5.4**

Consider the following nonlinear problem. Is the feasible region convex?

$$
\begin{align*}
\text{minimize} \quad & f(x, y) = 3x^2 - 2xy + y^2 \\
\text{subject to} \quad &  x^3 - 12x - y \geq 0 \\  
& x \geq 1 
\end{align*}
$$

**5.5**

Use the one dimensional search described in Section 5.2.1 (also known as a bisection search) to find a minimum of the function

$$f(x) = x^4 - 3x^3 + 2x^2 - 2x + 7$$
$$\text{over the range } 1 \leq x \leq 10 \text{. Use } \epsilon = 0.1$$

**5.6**

The *golden section search* is similar to the bisection search for one dimensional problems, except that it uses only function values and it does not require calculating derivatives. This is particularly useful when the function does not have first derivatives defined, or when computing the first derivatives is very expensive computationally. Suppose you are given two initial end-points, $a \le x \le d$, and the minimum of $f(x)$ is known to lie in this range. Evaluate the function at two points $c = a + 0.618 \cdot [d - a]$, and $b = d - 0.618 \cdot [d - a]$. Note that $a < b < c < d$, but they are not evenly spaced. If $f(b) < f(c)$, then let $[a, c]$ be the new interval, and repeat the calculation. Otherwise, let $[b, d]$ be the new interval. The magic aspect of the golden section is that when you have to compute the new interior points between $[a, c]$, you discover that $b$ is precisely $0.618$ of the distance between $a$ and $c$. In other words, you only need to make one additional function evaluation. Similarly, if the new interval is $[b, d]$, then point $c$ is already lined up with one of the new required points.

Use the method of golden section to find the minimum of the function in the previous problem with $\epsilon = 0.1$.

**5.7**

Consider the unconstrained problem:

$$\text{minimize } f(x, y) = 3x^2 - 2xy + y^2 + 3e^{-x}$$

Starting from the solution $(x, y) = (0, 0)$, and an initial step length of 2, perform two iterations of the gradient search algorithm to find a minimum. That is, compute the gradient at the point $(0, 0)$, and perform a one dimensional line search to find a minimum along the line. From this new point, perform a second line search.

**5.8**

Repeat Exercise 5.7, but use Newton's method to find the solution.

**5.9**

*Rosenbrock's function* is a particularly difficult problem that looks deceptively simple. Consider the unconstrained function:

$$\text{minimize } f(x, y) = 100 (y - x^2)^2 + (1 - x)^2$$

The function has a unique minimum at the point $(1, 1)$ (where $f(1, 1) = 0$). This pathological example has also been called the *banana function*. If you plot the function, it follows a narrow banana-shaped valley from the point $(-1, 1)$ to the minimum $(1, 1)$. Because the valley has quite steep sides, anytime an algorithm tries to follow the downward slope in a straight line, the line almost immediately starts going up, resulting in very short steps. It is very difficult for any algorithm to find the way around the banana.

Try using both a gradient search and Newton's method beginning at the point $(-1, 1)$. Perform several iterations. You will likely observe rather poor progress along a narrow zig-zag path.

**5.10**

Consider the problem:

$$
\begin{align*}
\text{minimize} \quad & f(x, y) = x^2y \\
\text{subject to} \quad &  x^2 + y^2 = 1 
\end{align*}
$$

Use the method of Lagrange multipliers to express this problem as an unconstrained minimization problem, and solve the problem using both the gradient method and Newton's method.

**5.11**

Consider the following nonlinear problem with linear constraints:

$$
\begin{align*}
\text{maximize} \quad & f(x, y) = x^2y + 2y^2 \\
\text{subject to} \quad &  x + 3y \leq 9 \\  
& x + 2y \leq 8 \\
& 3x + 2y \leq 18 \\
& 0 \leq x \leq 5 \\
&  0 \leq y \leq 2
\end{align*}
$$

Solve this problem graphically. Begin at the point $(0, 0)$, and check the gradient. If the Karush-Kuhn-Tucker conditions are not satisfied, you should be able to find an improving direction in the feasible region.
`This is a big reference sheet for me to look back to while I'm taking this class. Meant to go over the major points and key ideas of the course, as well as some fun results.`
 $\newcommand{\norm}[1]{\|#1\|}\newcommand{\opnorm}[1]{\|#1\|_{\scriptscriptstyle\text{op}}}\newcommand{\cont}{{\mathscr{C}^1}}\newcommand{\zerov}{\boldsymbol{\vec{0}}}\newcommand{\bs}[1]{\boldsymbol{#1}}\newcommand{\Alt}{\Lambda^k(\R^n)^*}\newcommand{\dx}{\operatorname{d}\!\boldsymbol{x}}\newcommand{\R}{\mathbb{R}}\newcommand{\mat}[2]{\mathcal{M}_{#1 \times #2}}\newcommand{\matmn}{\mathcal{M}_{m \times n}}\newcommand{\matnn}{\mathcal{M}_{n \times n}}\newcommand{\orth}{\text{O}(n)}\newcommand{\sym}{\text{Sym}(n)}\newcommand{\rank}{\text{rank}}\newcommand{\image}[1]{{\text{im}}\{#1\}}\DeclareMathOperator{\sign}{sign}\DeclareMathOperator{\alt}{alt}\renewcommand{d}{\mathop{}\!\mathrm{d}}$
 
# Chapter 6: Solving Nonlinear Problems

## 6.1 The Contraction Mapping Principle

### Convergence of Vector Sums
If you have a convergent sequence of vectors $\{\boldsymbol{a}_k\}$, then this convergent sequence of vectors will converge as long as the norms of the vectors converge

$\sum\limits_{k=1}^\infty \|\boldsymbol{a}_k\|$ converges $\implies$ $\sum\limits_{k=1}^\infty \boldsymbol{a}_k$ converges

### Contraction Mappings
A contraction mapping is a function that always shrinks the distance between two points. 

For $X \subset \mathbb{R}^n, \boldsymbol{f}: X \to X$, $\boldsymbol{f}$ is a contraction mapping if $\exists c \in (0, 1)$ such that $$\| \boldsymbol{f}(\boldsymbol{x}) - \boldsymbol{f}(\boldsymbol{y})\| \leq c \| \boldsymbol{x} - \boldsymbol{y}\|$$
Contraction mappings are always continuous, and have at most one fixed point. If $X$ is closed, we can specify that such a point does exist. This is called the contraction mapping princple. The contraction mapping principle states that if you call a contraction mapping $\boldsymbol{f}$ enough times, then it eventually converges on some point, called the fixed point of $\boldsymbol{f}$. 

if $X$ is closed, then $\exists \boldsymbol{x} \in X$ so that $\boldsymbol{f}(\boldsymbol{x})=\boldsymbol{x}$

### The Mean Value Inequality
The MVT in single-var calc tells us that, on a continuous curve, there is some point where the tangent line at that point has the same slope as the secant line between the two endpoints. i.e. that  $\cfrac{f(b)-f(a)}{b-a} = f'(x)$ for some $x \in (a, b)$. If we rearrange, however, this result tells us how much a function stretches or shrinks two points based on the slope of the function. This idea is is how we generalize the MVT to $\mathbb{R}^n$

If $U \subset \mathbb{R}^n$ is open,  $\boldsymbol{f}: U \to \mathbb{R}^m$, and $\boldsymbol{a}, \boldsymbol{b} \in U$ with a $\mathscr{C}^1$ path in U which joins them, then
$$\| \boldsymbol{f}(\boldsymbol{b}) - \boldsymbol{f}(\boldsymbol{a})\| \leq \left( \displaystyle \max_{\boldsymbol{x} \in [\boldsymbol{a}, \boldsymbol{b}]}\| D\boldsymbol{f}(\boldsymbol{x})\|\right)\|\boldsymbol{b}-\boldsymbol{a}\|$$
This gives us a really useful condition which we can use to prove that certain functions are contraction mappings. (if $0< \displaystyle \max_{\boldsymbol{x} \in [\boldsymbol{a}, \boldsymbol{b}]}\| D\boldsymbol{f}(\boldsymbol{x})\| < 1$). 

### Matrix Theorems
Generalization of a geometric series. If $A\in\mathcal{M}_{n \times n}$ and $\|A\|_{\text{op}}< 1$, then $\sum\limits_{i=0}^\infty A^i=(I-A)^{-1}$

The general linear group $\text{GL}(n)$ of invertible matrices is an open subset of $\mathcal{M}_{n \times n}$, and $f: \text{GL}(n) \to  \text{GL}(n)$ given by $f(A) = A^{-1}$ is smooth.

Since $\mathcal{M}_{m \times n}$ is isomorphic to $\mathbb{R}^{nm}$, we can take derivative maps of matrix-valued functions. For example, consider $f: \mathcal{M}_{n\times n} \to \mathcal{M}_{n\times n}$ given by $f(A) = A^2$. We can use the limit definition similarly to vectors (with respect to the frobenius norm) and show $[Df(A)]B = AB + BA$. What this says, is that if we associate a linear map to $[Df(A)]: \mathbb{R}^{n^2} \to \mathbb{R}^{n^2}$, then that linear map takes a $B \in \mathbb{R}^{n^2}$ to $AB + BA$ (a sort of matrix power rule, which unfortunately doesn't simplify since multiplication is non-commutative).

The symmetric matrices where $A^T = A$ form an $\frac{1}{2}n(n+1)$-dimensional subspace. The orthogonal group $\text{O}(n) \subset \mathcal{M}_{n \times n}$ = {set of matrices where $A^TA = I$}  is a $\frac{1}{2}n(n-1)$-dimensional submanifold, and $T_I\text{O}(n)$ (tangent plane at the identity) is the set of skew-symmetric matrices $\text{Skew}(n)$ = {set of matrices where $A^T = -A$}

## 6.2 The Inverse and Implicit Function Theorems

### Inverse Function Theorem
The Inv. FT is an incredibly powerful theorem which tells us under what conditions a certain function $\boldsymbol{f}$ has a local inverse, and what the derivative of that inverse looks like. To have an inverse, the derivative map must be locally invertable, and the inverse of that derivative map is the derivative of the inverse.

More formally it says if $U \subset \mathbb{R}^n$ is open,  $\boldsymbol{f}: U \to \mathbb{R}^n$ is $\mathscr{C}^1$, $\boldsymbol{x}_0 \in U$ and $D\boldsymbol{f}(\boldsymbol{x}_0)$ is invertible, then $\exists$ two open neighborhoods, $V \subset U$ of $\boldsymbol{x}_0$ and $W$ of $\boldsymbol{y}_0 := \boldsymbol{f}(\boldsymbol{x}_0)$, and a $\mathscr{C}^1$ function between them $\boldsymbol{g}: V \to W$ so that 

$\forall \boldsymbol{x} \in V, \boldsymbol{g}(\boldsymbol{f}(\boldsymbol{x})) = \boldsymbol{x}$
$\forall \boldsymbol{y} \in W, \boldsymbol{f}(\boldsymbol{g}(\boldsymbol{y})) = \boldsymbol{y}$

Furthermore, $D\boldsymbol{g}(\boldsymbol{f}(\boldsymbol{x})) = (D\boldsymbol{f}(\boldsymbol{x}))^{-1}$

### Implicit Function Theorem
The Imp. FT, a consequence of the Inv. FT, is another incredibly powerful result. It tells us that a series of $m$ implicit equations of $n$ variables can be written locally as $m$ explicit functions of $n-m$ variables (as long as the derivative map of the output variables is invertible). It is like a non-linear generalization of pivot and free variables. This is also incredibly useful for our future study of manifolds; it links the implicit description to the explicit description and allows us to think of manifolds locally as spaces where we can perform calculus like it's linear algebra.

More formally, for the Imp. FT we need $n>m$, and a  $\mathscr{C}^1$ function $\boldsymbol{F}: U \subset \mathbb{R}^n \to \mathbb{R}^m$ where $U$ is open. Then, writing a vector $\begin{bmatrix}\boldsymbol{x} \\ \boldsymbol{y}\\\end{bmatrix} \in \mathbb{R}^n$ with $\boldsymbol{x} \in \mathbb{R}^{n-m}$ and $\boldsymbol{y} \in \mathbb{R}^m$, suppose $\boldsymbol{F}\begin{pmatrix} \boldsymbol{x}_0 \\ \boldsymbol{y}_0 \\ \end{pmatrix} = \boldsymbol{\vec{0}}$ describes a series of $m$ implicit equations and $\cfrac{\partial \boldsymbol{F}}{\partial \boldsymbol{y}} \begin{pmatrix} \boldsymbol{x}_0 \\ \boldsymbol{y}_0 \\ \end{pmatrix} \in \mathcal{M}_{m \times m}$ is invertible. 

Then, $\exists$ two neighborhoods, $V$ of $\boldsymbol{x}_0$ and $W$ of $\boldsymbol{y}_0$ and a $\mathscr{C}^1$ function between them $\boldsymbol{\varphi}: V \to W$ so that for all $\boldsymbol{x} \in V$ and $\boldsymbol{y} \in W$,
$$\boldsymbol{F}\begin{pmatrix} \boldsymbol{x} \\ \boldsymbol{y} \\ \end{pmatrix} = \boldsymbol{\vec{0}} \iff \boldsymbol{y} = \boldsymbol{\varphi}(\boldsymbol{x})$$
Furthermore, $D\boldsymbol{\varphi}(\boldsymbol{x})=-\left(\cfrac{\partial \boldsymbol{F}}{\partial \boldsymbol{y}}\begin{pmatrix} \boldsymbol{x} \\ \boldsymbol{\varphi}(\boldsymbol{x})\\ \end{pmatrix}\right)^{-1}\left(\cfrac{\partial \boldsymbol{F}}{\partial \boldsymbol{x}}\begin{pmatrix} \boldsymbol{x} \\ \boldsymbol{\varphi}(\boldsymbol{x})\\ \end{pmatrix}\right)$.

It helps to keep track of dimensions. $\cfrac{\partial \boldsymbol{F}}{\partial \boldsymbol{y}}$ is an $m \times m$ matrix (differentiating *m* functions w.r.t *m* variables, $\cfrac{\partial \boldsymbol{F}}{\partial \boldsymbol{x}}$ is an $m \times (n-m)$ matrix (differentiating *m* functions w.r.t. *(n-m)* variables, so $D\boldsymbol{\varphi}(\boldsymbol{x}) \in \mathcal{M}_{m \times (n-m)}$. 

## 6.3 Manifolds Revisited
Manifolds are essentially special surfaces which are smooth and are very nice to deal with when doing calculus.  

There are three equivalent definitions for a k-dimensional manifold *M*.

1. Explicit: a graph of a smooth function
2. Implicit: solutions to an implicit set of equations
3. Parametric: paramaterized by an injective funtion that never has velocity 0

more formally

1. For any $\boldsymbol{p} \in M$, $\exists$ a neighborhood $W \subset \mathbb{R}^n$ of $\boldsymbol{p}$ so that $W \cap M$ is the graph of a smooth function $\boldsymbol{f}: V \subset \mathbb{R}^{k} \to \mathbb{R}^{n-k}$, where $V$ is open. Remember that $\text{graph}\{\boldsymbol{f}(\boldsymbol{x})\} = \{\begin{bmatrix}\boldsymbol{x} \\ \boldsymbol{f}(\boldsymbol{x}) \\\end{bmatrix} : \boldsymbol{x} \in \mathbb{R}^k\}$, but that the order of the $x_i$'s doesn't matter. 
2. For any $\boldsymbol{p} \in M$, $\exists$ a neighborhood $W \subset \mathbb{R}^n$ of $\boldsymbol{p}$ and a smooth function $\boldsymbol{F}: W \to \mathbb{R}^{n-k}$ so that the preimage (level set) $\boldsymbol{F}^{-1}(\boldsymbol{\vec{0}}) = W \cap M$ and $\text{rank}\{D\boldsymbol{F}(\boldsymbol{x})\} = n-k$ for every $\boldsymbol{x} \in W \cap M$.
3. For any $\boldsymbol{p} \in M$, $\exists$ a neighborhood $W \subset \mathbb{R}^n$ of $\boldsymbol{p}$ so that $W \cap M$ is the image of a smooth function $\boldsymbol{g}: U \subset \mathbb{R}^{k} \to \mathbb{R}^{n}$, where $U$ is open. $\boldsymbol{g}$ must be injective, have $\text{rank}\{D\boldsymbol{g}(\boldsymbol{u})\} = k$ for all $\boldsymbol{u} \in U$, and have $\boldsymbol{g}^{-1}: W \cap M \to U$ be continuous. 

We can also find the tangent planes at $\boldsymbol{p}$ to each respective manifold ($T_\boldsymbol{p}M)$ as follows

1. If $M$ is locally at $\boldsymbol{p}$ a graph of $\boldsymbol{f}$ with $\boldsymbol{p} = \begin{bmatrix}\boldsymbol{a} \\ \boldsymbol{f}(\boldsymbol{a}) \\\end{bmatrix}$, then $T_{\boldsymbol{p}}M = \text{graph}\{D\boldsymbol{f}(\boldsymbol{a})\}$.
2. If $M$ is locally a preimage of $\boldsymbol{F}$,  then $T_{\boldsymbol{p}}M = \text{ker}\{D\boldsymbol{F}(\boldsymbol{p})\}$.
3. If $M$ is locally paramaterized by $\boldsymbol{g}$ with $\boldsymbol{p} = \boldsymbol{g}(\boldsymbol{a})$, then $T_{\boldsymbol{p}}M = \text{im}\{D\boldsymbol{g}(\boldsymbol{a})\}$


# Chapter 7: Integration 

## 7.1 Multiple Integrals

### Defining Integrability (in higher dimensions)
To extend our notion of integration into multiple dimensions, we will be working with something called the Darboux integral. It is much like our notion of 2-D area under the curve, but generalizes to volumes of surfaces/hypersurfaces. 

Given a rectangle $R \subset \mathbb{R}^n$, you can slice up the rectangle into subrectangles into a partition $\mathcal{P} := \mathcal{P}_1  \times ... \times \mathcal{P}_n$ (each $\mathcal{P}_i$ for $1 \leq i \leq n$ is like a list of points where to slice the rectangle in the corresponding dimension), where each $R_{i, j}$ of $\mathcal{P}$ is the i-jth rectangle of $R$. Although for $\mathbb{R}^n$ it should be more like the $(i, j, k, ... , n)$-th rectangle of $R$ for all the *n* coordinates needed to specify which subrectangle it is. For ease of notation I'll stick with $R_{i, j}$.


Recall that for a bounded function $f: R \to \mathbb{R}$, $\displaystyle \sup_{\boldsymbol{x} \in S} f(\boldsymbol{x})$ is the "least upper bound" and $\displaystyle \inf_{\boldsymbol{x} \in S} f(\boldsymbol{x})$ is the "greatest lower bound" of *f* on S. That is to say, *sup* is like a maximum of *f* and *inf* is like a minimum of *f* (although the function might never reach their respective values, only approach them).

We then define two possible sums on a partition $\mathcal{P}$, the upper and lower sums. First, we define a sort of minimum/maximum for a subrectangle $R_{i,j}$ to be  $m_{i,j} := \displaystyle \inf_{\boldsymbol{x} \in R_{i, j}} f(\boldsymbol{x})$ and $M_{i,j} := \displaystyle \sup_{\boldsymbol{x} \in R_{i, j}} f(\boldsymbol{x})$, respectively. Then, the lower sum of a partition is $L(f, \mathcal{P}) := \sum\limits_{i, j}m_{i, j}\text{ area}(R_{i,j})$ and the upper sum is $U(f, \mathcal{P}) := \sum\limits_{i, j}M_{i, j}\text{ area}(R_{i,j})$.

Finally, we define integrability. $f$ is integrable on $R$ if for all partitions $\mathcal{P}$ of $R$ there is a *unique* number $I$ satisfying $L(f, \mathcal{P})\leq I \leq U(f, \mathcal{P})$. If$f$ is integrable we say $\displaystyle \int_R fdV:= I$.

### Proving Integrability
A nice way to prove integrability is the convenient criterion. If $f$ is bounded on $R$, $f$ is integrable on $R$ iff $\forall \epsilon > 0$ , $\exists$ a partition $\mathcal{P}$ of $R$ such that $U(f, \mathcal{P})-L(f, \mathcal{P}) < \epsilon$. 

If $f$ is continuous, and only discontinuous on a set of volume 0, then $f$ is integrable. $X$ having volume 0 means that $\exists$ finite $R_1, . . . , R_s$ so that $X \subset R_1 \cup . . . \cup R_s$ and $\text{vol}(R_1) + . . . + \text{vol}(R_s) < \epsilon$ for any $\epsilon > 0$. 

### Regions
A subset $\Omega$ is a region if it is the closure of a bounded open subset of $\mathbb{R}^n$ and its boundary has volume 0. In other words, if $\Omega = \bar{U}$ for some open $U$, and $\partial\Omega$ has volume 0. 

To integrate $f$ over a region $\Omega$, we pick a retangle $R$ with $\Omega \subset R$. Then, we define $\tilde f = \begin{cases} f(\boldsymbol{x}) & x\in \Omega \\ 0 & \text{otherwise} \end{cases}$. 
Then, $\displaystyle \int_\Omega fdV = \displaystyle \int_R \tilde f dV$
The volume of a region $\Omega$ is given by $\text{vol}(\Omega) = \displaystyle \int_\Omega 1 dV$

### Properties of Integrals
1. Integration is linear
	1. $\displaystyle \int_\Omega (f + g) dV = \displaystyle \int_\Omega fdV + \displaystyle \int_\Omega gdV$
	2.  $\displaystyle \int_\Omega \alpha f dV = \alpha\displaystyle \int_\Omega f dV$
2. $\displaystyle \int_{A\cup B} fdV = \displaystyle \int_{A} fdV + \displaystyle \int_{B} fdV$
3. If $f \leq g$ on $\Omega$, then $\displaystyle \int_\Omega fdV \leq \displaystyle \int_\Omega gdV$


## 7.2 Iterated Integrals and Fubini's Theorem

### Fubini's Theorem

Fubini's Theorem allows us to connect this abstract definition of integration to our familiar definition of integration in single-variable calculus. 

In 2 dimensions, it states that if $f$ is integrable on $R = [a, b] \times [c, d]$, and the sub-integral $\displaystyle\int_c^d f\begin{pmatrix} x \\ y \\ \end{pmatrix}dy$ is integrable, then $\displaystyle\int_R fdV = \displaystyle\int_a^b\int_c^d f\begin{pmatrix} x \\ y \\ \end{pmatrix}dydx$. Furthermore, $\displaystyle\int_a^b\int_c^d f\begin{pmatrix} x \\ y \\ \end{pmatrix}dydx = \displaystyle\int_c^d\int_a^b f\begin{pmatrix} x \\ y \\ \end{pmatrix}dxdy$

In $n$ dimensions, this generalizes similarly. If $f$ is integrable on $[a_1, b_1] \times . . . \times [a_n, b_n]$, and all the subintegrals are integrable, then
$\displaystyle\int_R f(\boldsymbol{x})dV$ = $\displaystyle \int_{a_1}^{b_1} . . . \int_{a_n}^{b_n} f(\boldsymbol{x})dx_n . . . dx_1$ 
and the order of the integrals does not matter. 

## 7.3 Polar, Cylindrical, and Spherical Coordinates

There are alternative coordinate systems which can help us solve problems and allow us to exploit symmetry. These are three very specific yet very useful coordinate systems, which we generalize later with the change of variables theorem. 

### Polar Coordinates
Define $\boldsymbol{g}: [0, \infty) \times [0, 2\pi) \to \mathbb{R}^2$ by $\boldsymbol{g}\begin{pmatrix} r \\ \theta \end{pmatrix} = \begin{bmatrix} r\cos\theta \\ r\sin\theta \end{bmatrix} =  \begin{bmatrix}x \\y \end{bmatrix}$ . 

Then, $\displaystyle \int_{\boldsymbol{g}(\Omega)}f\begin{pmatrix}x\\y\end{pmatrix}dV_{x, y} = \displaystyle \int_\Omega f\begin{pmatrix}r\\\theta\end{pmatrix}rdV_{r, \theta}$

It is useful to know that $x^2 + y^2 = r^2$ 

Visually, we think of $r$ being the distance projected radially outward at an angle of $\theta$ which rotates clockwise around the origin. 

### Cyllindrical Coordinates
Define $\boldsymbol{g}: [0, \infty) \times [0, 2\pi) \times \mathbb{R} \to \mathbb{R}^3$ by $\boldsymbol{g}\begin{pmatrix} r \\ \theta \\z\end{pmatrix} = \begin{bmatrix} r\cos\theta \\ r\sin\theta \\z \end{bmatrix} =  \begin{bmatrix}x \\y \\z\end{bmatrix}$ . 

Then, $\displaystyle \int_{\boldsymbol{g}(\Omega)}f\begin{pmatrix}x\\y\\z\end{pmatrix}dV_{x, y, z} = \displaystyle \int_\Omega f\begin{pmatrix}r\\\theta\\z\end{pmatrix}rdV_{r, \theta, z}$


It is useful to know that $x^2 + y^2 = r^2$ 

Visually, we think of $r$ being the distance projected radially outward at an angle of $\theta$ which rotates clockwise around the origin, at a height of $z$. 

### Spherical Coordinates
Define $\boldsymbol{g}: [0, \infty) \times [0,\pi) \times [0, 2\pi) \to \mathbb{R}^3$ by $\boldsymbol{g}\begin{pmatrix} \rho \\ \phi \\\theta\end{pmatrix} = \begin{bmatrix} \rho\sin\phi\cos\theta \\ \rho\sin\phi\sin\theta \\\rho\cos\phi \end{bmatrix} =  \begin{bmatrix}x \\y \\z\end{bmatrix}$ . 

Then, $\displaystyle \int_{\boldsymbol{g}(\Omega)}f\begin{pmatrix}x\\y\\z\end{pmatrix}dV_{x, y, z} = \displaystyle \int_\Omega f\begin{pmatrix} \rho \\ \phi \\\theta\end{pmatrix}\rho^2\sin\phi dV_{\rho, \phi, \theta}$


It is useful to know that $x^2 + y^2 +z^2 = \rho^2$ 

Visually, we think of $\rho$ being the distance projected radially outward at two angles—$\phi$, which starts at the top of the $z$-axis and rotates down to the bottom, and $\theta$, which rotates all the way about the $z$-axis. 

## 7.4 Physical Applications

Average value of $f$ on $\Omega$ is defined to be $\bar{f} = \cfrac{1}{\text{vol}(\Omega)}\displaystyle\int_\Omega f \text{ dVol}$

We can define the integral of a vector *valued* function $\boldsymbol{f}$ by $\displaystyle\int_\Omega \boldsymbol{f} \text{ dVol} = \begin{bmatrix}\int_\Omega f_1 \text{ dVol} \\ \vdots \\ \int_\Omega f_n \text{ dVol}\end{bmatrix}$

Average value is still $\bar{\boldsymbol{f}} = \cfrac{1}{\text{vol}(\Omega)}\displaystyle\int_\Omega f \text{ dVol}$

And *center of mass* of $\Omega$ with mass density function $\delta(\boldsymbol{x})$ is defined to be the point $\bar{\boldsymbol{x}} = \cfrac{1}{\text{vol}(\Omega)}\displaystyle\int_\Omega \delta(\boldsymbol{x})\boldsymbol{x} \text{ dVol}$

For a rigid body $\Omega$, its *moment of inertia* about an axis $l$ is defined to be $\displaystyle\int_\Omega \delta(\boldsymbol{x})r^2 \text{ dVol}$, where $r$ is the distance from the point to the axis $l$. 

The gravitational force exerted on the origin by a mass $\Omega$ is  $\boldsymbol{F} = G\displaystyle\int_\Omega \delta(\boldsymbol{x})\cfrac{\boldsymbol{x}}{\|\boldsymbol{x}\|^3} \text{ dVol}$

## 7.5 Determinants and n-Dimensional Volume

### The Determinant
For every $n \geq 1$, there is exactly one function $\mathcal{D}:\underbrace{\mathbb{R}^n\times\cdots\times\mathbb{R}^n}_{n\text{ times}} \to \mathbb{R}$ that is alternating, multilinear, and has $\mathcal{D}(\boldsymbol{e}_1, ..., \boldsymbol{e}_n) = 1$ 

**Alternating:** 
$\mathcal{D}(\boldsymbol{v}_1, \cdots, \boldsymbol{v}_i, \cdots, \boldsymbol{v}_j, \cdots, \boldsymbol{v}_n) = -\mathcal{D}(\boldsymbol{v}_1, \cdots, \boldsymbol{v}_j, \cdots, \boldsymbol{v}_i, \cdots, \boldsymbol{v}_n)$

**Multilinear** (linear in all inputs)**:** 
$\mathcal{D}(\boldsymbol{v}_1, \cdots, c\boldsymbol{v}_i, \cdots, \boldsymbol{v}_n) = c\mathcal{D}(\boldsymbol{v}_1, \cdots, \boldsymbol{v}_i, \cdots, \boldsymbol{v}_n)$
and
$\mathcal{D}(\boldsymbol{v}_1, \cdots, \boldsymbol{v}_i+\boldsymbol{v}_i', \cdots, \boldsymbol{v}_n)= \mathcal{D}(\boldsymbol{v}_1, \cdots, \boldsymbol{v}_i, \cdots, \boldsymbol{v}_n) + \mathcal{D}(\boldsymbol{v}_1, \cdots, \boldsymbol{v}_i', \cdots, \boldsymbol{v}_n)$

**Standard:** 
$\mathcal{D}(\boldsymbol{e}_1, ..., \boldsymbol{e}_n) = 1$ 

This function is the determinant. For an $n\times n$ matrix $A$, $\det A = \mathcal{D}(\boldsymbol{a}_1, \cdots, \boldsymbol{a}_n)$

### Properties

1. If two columns of a matrix are equal, $\det A = 0$
2. Performing row or column operations on a matrix changes the determinant nicely
	1. Swapping two rows or columns leaves $\det A' = - \det A$
	2. Scaling one row or column by $c$ leaves $\det A' = c \det A$
	3. Adding a multiple of one row or column to another leaves $\det A' =  \det A$
3. A is nonsingular $\iff \det A \neq 0$ 
4. $\det(AB) = \det(A)\det(B)$
5. $\det A^{-1} = \cfrac{1}{\det A}$
6.  $\det A^\intercal = \det A$
7. if A is triangular, $\det A$ is the product of the diagonal entries
8. if $T$ is a linear map, and $\Omega$ is a region, $\text{vol}(T(\Omega)) = |\det T|\text{vol}(\Omega)$ 

**Cofactors:**
The cofactor $c_{i,j}= (-1)^{i+j}\det A_{i,j}$ , where $A_{i, j} =$ the matrix formed by removing row $i$ and column $j$. 

The cofactor matrix $C_A$ is the matrix where $(C_A)_{i,j} = c_{i,j}$

**Cramers Rule:**
The $i^{\text{th}}$ coordinate of $\boldsymbol{x}$ which solves $A\boldsymbol{x}=\boldsymbol{b}$ is given by $\boldsymbol{x}_i =\cfrac{\det B_i}{\det A}$, where $B_i$ is the matrix obtained by replacing the ith column of $A$ by $\boldsymbol{b}$

**Inverse matrix "formula"**:
$A^{-1} = \cfrac{1}{\det A}C^\intercal$

**Permuations**: 
A permuation $\sigma \in S_n$ is a bijective mapping $\sigma: \{1, \cdots,n\} \to \{1, \cdots,n\}$ 
Set of all permutations is denoted $S_n$
The sign of a permutation $\text{sign}(\sigma) = \begin{cases}+1&\text{odd \# of exchanges}\\-1&\text{even \# of exchanges}\end{cases}$ 

where $\text{\# of exchanges}$ is the number of swaps required to change the ordered list $(1, \cdots, n)$ to $(\sigma(1), \cdots, \sigma(n))$

### Formulas for the Determinant

**Expansion by cofactors:**
For any fixed row $i$
$\det A =\sum\limits_{j=1}^n a_{i,j}c_{i,j}$
For any fixed column $j$
$\det A =\sum\limits_{i=1}^n a_{i,j}c_{i,j}$

**Sum of row/column permuations:**
$\det A = \sum\limits_{\sigma \in S_n}\text{sign}(\sigma)a_{\sigma(1), 1}a_{\sigma(2), 2}\cdots a_{\sigma(n), n}$
$\det A = \sum\limits_{\sigma \in S_n}\text{sign}(\sigma)a_{1, \sigma(1)}a_{2, \sigma(2)}\cdots a_{n, \sigma(n)}$

## 7.6 Change of Variables Theorem

Let $\Omega \subset \mathbb{R}^n$ be a region and let there be an open $U$ with $\Omega \subset U$ so that $\boldsymbol{g}: U \to \mathbb{R}^n$ is injective, $\mathscr{C}^1$, and has a derivative that is mostly invertible (only fails to be invertible on a set of volume 0).

if $f:\boldsymbol{g}(\Omega) \to \mathbb{R}$ and $(f \circ \boldsymbol{g})|\det D\boldsymbol{g}|: \Omega \to \mathbb{R}$ are both integrable, then $\displaystyle\int_{\boldsymbol{g}(\Omega)}f(\boldsymbol{y})\text{ dVol}_\boldsymbol{y} = \displaystyle\int_{\Omega}(f \circ \boldsymbol{g})(\boldsymbol{x})|\det D\boldsymbol{g}(\boldsymbol{x})|\text{ dVol}_\boldsymbol{x}$



# Chapter 8: Differential Forms and Integration on Manifold

## 8.2 Differential Forms

### Linear forms
The basis  1-forms $\{\d x_1, ..., \d x_n\}$ are defined by $\d x_i(\bs{v})=v_i$. 

The set of linear maps from $\R^n$ to $\R$ is an $n$ dimensional vector space $(\R^n)^*$ spanned by the basis 1-forms $\{\d x_1, ..., \d x_n\}$. This space is the *dual space* of $\R^n$.

Let $I = (i_1, ..., i_k)$ be a multi-index. Using this, we want to define an alternating, multilinear function $\dx_I : \underbrace{\R^n \times \cdots \times \R^n}_{k \text{ times}} \to \R$$ that takes $k$ vectors in $\R^n$ to $\R$ by $\dx_I(\bs{v}_1, ..., \bs{v}_k) =\det V_I$, where $V_I$ is formed by taking the $i_1, ..., i_k$th rows of the matrix $\begin{bmatrix}\uparrow&&\uparrow\\\bs{v_1}&\cdots&\bs{v}_k\\\downarrow&&\downarrow\end{bmatrix}$. This calculates the volume of the parallelipiped of the vectors $\bs{v}_1, ..., \bs{v}_k$ projected onto the $x_{i_1}, ..., x_{i_k}$ plane. 

The set of alternating, multilinear functions from $(\R^n)^k$ to $\R$ is denoted by $\Alt$. This is the dual space of the exterior power of $\R^n$. This space is spanned by the basis k-forms which are given by all $\dx_I$ where the $(i_1, ..., i_k)$ are increasing. The dimension of this space $\dim(\Alt) = \binom{n}{k}$. So every $T \in \Alt$ is described by $\binom{n}{k}$ coefficients $a_I$ so that $T = \displaystyle\sum\limits_{I \text{ increasing}}a_I\dx_I$. 

The wedge product $\wedge: \Alt\times \Lambda^l(\R^n)^* \to \Lambda^{k+l}(\R^n)^*$ can be defined in multiple ways for two forms $\omega = \sum\limits_{I \text{ increasing}}a_I\dx_I \in \Alt$ and $\eta = \sum\limits_{J \text{ increasing}}b_J\dx_J \in \Lambda^l(\R^n)^*$.

**Concatenation:**
For the basis forms, we simply concatenate the multi-indeces so that $\dx_I \wedge \dx_J = \dx_{(I, J)} =  \dx_{(i_1, ..., i_k, j_1, ..., j_l)}$. By linearity then, we have $\omega \wedge \eta = \sum\limits_{I \text{ increasing}}\sum\limits_{J \text{ increasing}}(a_I b_J)\dx_{(I,J)}$.

**Alternization of Tensor Product**: 
$\omega \wedge \eta = \alt(\omega \otimes \eta)$, 

where $\otimes$ is the tensor product which is defined by $(\omega\otimes\eta)(\bs{v}_1, ..., \bs{v}_{k+l})= \omega(\bs{v}_1, ..., \bs{v}_k)\cdot\eta(\bs{v}_{k+1}, ..., \bs{v}_{k+l})$ 

and $\alt$ is the alternization for a multilinear $\gamma:(\R^n)^k \to \R$ defined by $\alt(\gamma)(\bs{v}_1, ..., \bs{v}_{k}) = \sum\limits_{\sigma \in S_k}\sign(\sigma)\gamma(\bs{v}_{\sigma(1)}, ..., \bs{v}_{\sigma(k)})$. 

Note that every $\dx_I = \dx_{i_1} \wedge \cdots \wedge \dx_{i_k}$

**Properties:**
$\omega \in \Lambda^k(\R^n)^*, \eta \in \Lambda^l(\R^n)^*, \mu \in \Lambda^m(\R^n)^*$
1. Bilinear
	1. $(\omega + \eta)\wedge \mu = \omega \wedge \mu + \eta \wedge \mu$
	2. $(c\omega)\wedge \eta = c(\omega \wedge \eta)$
2. Skew-commutative
	1. $\omega \wedge \eta = (-1)^{kl} \eta \wedge \omega$
3. Associative
	1. $(\omega \wedge \eta)\wedge \mu = \omega \wedge (\eta \wedge \mu)$

### Differential Forms
A differential form associates a function to each of the $\binom{n}{k}$ basis forms. A differential $k$-form on $\R^n$ is an expression $\omega =\sum\limits_{I \text{ increasing}}f_I(\bs{x})\dx_I$. 

**Special cases:** 
A 0-form is a smooth function. 
An n-form is an expression of the form $\omega = f(\bs{x})\d x_1\wedge\cdots\wedge\d x_n$. 

The set of $k$ forms on $\R^n$ forms a vector space $\mathcal{A}^k(\R^n)$

**Properties:**
$\omega \in \mathcal{A}^k(\R^n), \eta \in \mathcal{A}^l(\R^n), \mu \in \mathcal{A}^m(\R^n)$
1. Distributes (when $k=l$)
	1. $(\omega + \eta)\wedge \mu = \omega \wedge \mu + \eta \wedge \mu$
2. Skew-commutative
	1. $\omega \wedge \eta = (-1)^{kl} \eta \wedge \omega$
3.  Associative
	1. $(\omega \wedge \eta)\wedge \mu = \omega \wedge (\eta \wedge \mu)$
4. 1. Associative / commutative (when $k=l=m$)
	1. $(\omega + \eta) + \mu = \omega + (\eta + \mu)$
	2. $\omega + \eta = \eta + \omega$


### Exterior derivative
The exterior derivative $\d$ allows us to differentiate differential forms. The exterior derivative turns $k$ forms into $k+1$ forms. 

For 0-forms, $f: U \subset \R^n \to \R$ we want $\d f(\bs{x}) = Df(\bs{x})$ as a linear map $\R^n \to \R$. This motivates us to define $$\d f = \sum\limits_{i=1}^n\cfrac{\partial f}{\partial x_i}\d x_i$$
For a general $k$ form $\omega = \sum\limits_I f_I(\bs{x})\dx_I$, we define $$\d \omega = \sum\limits_I df_I\wedge \dx_I = \sum\limits_I \sum\limits_{j=1}^n\cfrac{\partial f}{\partial x_j}\d x_j\wedge \dx_{i_1}\wedge \cdots \wedge \dx_{i_k} $$
**Properties:**
$\omega \in \mathcal{A}^k(\R^n), \eta \in \mathcal{A}^l(\R^n), f \in \mathcal{A}^0(\R^n)$ (smooth function)
1. Distributes (when k = l)
	1. $\d(\omega + \eta) = \d\omega + \d\eta$
2. Scalar function product rule
	1. $\d(f\omega)  = \d f \wedge \omega + f \d\omega$
3. General product rule
	1. $d(\omega \wedge \eta) = \d\omega \wedge \eta + (-1)^k\omega\wedge\d\eta$
4. Derivative twice is 0
	1. $\d(\d\omega)=0$

### Pullback
Pullback is a sort of differential-forms generalization of the chain rule. 

If (for open $U$) $\bs{g}: U \subset \R^m \to \R^n$ is smooth, and $\omega \in \mathcal{A}^k(\R^n)$, then we define $\bs{g}^*\omega \in \mathcal{A}^k(U)$ in multiple steps

To pull back a 0-form (function), we compose by $$\bs{g}^*f=f\circ\bs{g}$$
To pull back a basis 1-form, we set $$\bs{g}^*\d x_i = \d g_i = \sum\limits_{j=1}^m\cfrac{\partial g_i}{\partial u_j}\d u_j$$
and to pull back a basis k-form, we set 
$$\bs{g}^*(\d x_{i_1} \wedge \cdots \wedge \d x_{i_k}) = \bs{g}^*\d x_{i_1} \wedge \cdots \wedge \bs{g}^*\d x_{i_k} = \d g_{i_1} \wedge \cdots \wedge \d g_{i_k} = \d \bs{g}_I$$

and finally, to take the pullback of a general form, we distribute the pullback so, $$\bs{g}^*\omega = \bs{g}^*\left(\sum\limits_I f_I(\bs{x})\dx_I\right) = \sum\limits_I (f_I\circ\bs{g})(\bs{x})\d \bs{g}_I = \sum\limits_I (f_I\circ\bs{g})(\bs{x})\d g_{i_1} \wedge \cdots \wedge \d g_{i_k}$$
This tells us that 
$\bs{g}^*\dx_I = \sum\limits_{J \text{ increasing}} \det[\cfrac{\partial \bs{g}_I}{\partial \bs{u}_J}]\d \bs{u}_J = \sum\limits_{J \text{ increasing}} \begin{vmatrix} \cfrac{\partial g_{i_1}}{\partial u_{j_1}} & \cdots & \cfrac{\partial g_{i_1}}{\partial u_{j_k}} \\ \vdots & \ddots& \vdots \\ \cfrac{\partial g_{i_k}}{\partial u_{j_1}} & \cdots & \cfrac{\partial g_{i_k}}{\partial u_{j_k}}\end{vmatrix}\d u_{j_1}\wedge\cdots\wedge\d u_{j_k}$ 

also note that $\bs{g}^*(\d \omega) = \d(\bs{g}^*\omega)$

### Defining integration

Given an $n$-form $\omega = f(\bs{x}) = \d x_1 \wedge \cdots \wedge \d x_n$ on a region $\Omega \subset \R^n$, we define $$\displaystyle\int_\Omega\omega := \displaystyle \int_\Omega f\text{ dVol}$$
With this definition, we can nicely restate the change of variables theorem in a nice way. If $\bs{g}: \Omega \subset \R^n \to \R^n$ is smooth, injective, and has $\det(D\bs{g}) > 0$ on a region $\Omega$, then for any $\omega \in \mathcal{A}^n(\R^n)$ we have$\displaystyle\int_{\bs{g}(\Omega)}\omega = \displaystyle \int_\Omega \bs{g}^*\omega$. This motivates us to define integration on a manifold. 

If $\bs{g}: \Omega \subset \R^n \to \R^n$ is smooth, injective, and has $\rank(\det D\bs{g})=k$ on a region $\Omega$, and only doesn't have this rank on a set of volume 0, then for a paramaterized k-dimensional manifold $M=\bs{g}(\Omega)\subset\R^n$ and for any $\omega \in \mathcal{A}^n(\R^n)$ we define $$\displaystyle\int_{M}\omega := \displaystyle \int_\Omega \bs{g}^*\omega$$

This is well defined, and has the same result for different paramaterizations (as long as both paramaterizations orient $M$ in the same way)

## 8.3 Line Integrals and Green's Theorem


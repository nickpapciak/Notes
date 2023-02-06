This is a big reference sheet for me to look back to while I'm taking this class. Meant to go over the major points and key ideas of the course, as well as some fun results. 


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

### Matrix Theorems (we prove these in HW)
Generalization of a geometric series. If $A\in\mathcal{M}_{n \times n}$ and $\|A\|_{\text{op}}< 1$, then $\sum\limits_{i=0}^\infty A^i=(I-A)^{-1}$

The general linear group $\text{GL}(n)$ of invertible matrices is an open subset of $\mathcal{M}_{n \times n}$, and $f: \text{GL}(n) \to  \text{GL}(n)$ given by $f(A) = A^{-1}$ is continuous.

## 6.2 The Inverse and Implicit Function Theorems

### Inverse Function Theorem
The Inv. FT is an incredibly powerful theorem which tells us under what conditions a certain function $\boldsymbol{f}$ has a local inverse, and what the derivative of that inverse looks like. To have an inverse, the derivative map must be locally invertable, and the inverse of that derivative map is the derivative of the inverse.

More formally it says if $U \subset \mathbb{R}^n$ is open,  $\boldsymbol{f}: U \to \mathbb{R}^n$ is $\mathscr{C}^1$, $\boldsymbol{x}_0 \in U$ and $D\boldsymbol{f}(\boldsymbol{x}_0)$ is invertible, then $\exists$ two open neighborhoods, $V \subset U$ of $\boldsymbol{x}_0$ and $W$ of $\boldsymbol{y}_0 := \boldsymbol{f}(\boldsymbol{x}_0)$, and a $\mathscr{C}^1$ function between them $\boldsymbol{g}: V \to W$ so that 

$\forall \boldsymbol{x} \in V, \boldsymbol{g}(\boldsymbol{f}(\boldsymbol{x})) = \boldsymbol{x}$
$\forall \boldsymbol{y} \in W, \boldsymbol{f}(\boldsymbol{g}(\boldsymbol{y})) = \boldsymbol{y}$

Furthermore, $D\boldsymbol{g}(\boldsymbol{f}(\boldsymbol{x})) = (D\boldsymbol{f}(\boldsymbol{x}))^{-1}$

### Implicit Function Theorem
The Imp. FT, a consequence of the Inv. FT, is another incredibly powerful theorem. It tells us that a series of $m$ implicit equations of $n$ variables can be written locally as $m$ explicit functions of $n-m$ variables, as long as the derivative map of the output variables is invertible. It is like a non-linear generalization of linear independence and pivot variables. This is also incredibly useful for our future study of manifolds; it links the implicit description to the explicit description.

More formally, for the Imp. FT we need $n>m$, $U \subset \mathbb{R}^n$ to be open, and $\boldsymbol{F}: U \to \mathbb{R}^m$ to be $\mathscr{C}^1$. Then, writing a vector $\begin{bmatrix}\boldsymbol{x} \\ \boldsymbol{y}\\\end{bmatrix} \in \mathbb{R}^n$ with $\boldsymbol{x} \in \mathbb{R}^{n-m}$ and $\boldsymbol{y} \in \mathbb{R}^m$, suppose $\boldsymbol{F}\begin{pmatrix} \boldsymbol{x}_0 \\ \boldsymbol{y}_0 \\ \end{pmatrix} = \boldsymbol{\vec{0}}$ describes a series of $m$ implicit equations and $\cfrac{\partial \boldsymbol{F}}{\partial \boldsymbol{y}} \begin{pmatrix} \boldsymbol{x}_0 \\ \boldsymbol{y}_0 \\ \end{pmatrix} \in \mathcal{M}_{m \times m}$ is invertible. 

Then, $\exists$ two neighborhoods, $V$ of $\boldsymbol{x}_0$ and $W$ of $\boldsymbol{y}_0$ and a $\mathscr{C}^1$ function between them $\boldsymbol{\varphi}: V \to W$ so that for all $\boldsymbol{x} \in V$ and $\boldsymbol{y} \in W$,
$$\boldsymbol{F}\begin{pmatrix} \boldsymbol{x} \\ \boldsymbol{y} \\ \end{pmatrix} = \boldsymbol{\vec{0}} \iff \boldsymbol{y} = \boldsymbol{\varphi}(\boldsymbol{x})$$
Furthermore, $D\boldsymbol{\varphi}(\boldsymbol{x})=-\left(\cfrac{\partial \boldsymbol{F}}{\partial \boldsymbol{y}}\begin{pmatrix} \boldsymbol{x} \\ \boldsymbol{\varphi}(\boldsymbol{x})\\ \end{pmatrix}\right)^{-1}\left(\cfrac{\partial \boldsymbol{F}}{\partial \boldsymbol{x}}\begin{pmatrix} \boldsymbol{x} \\ \boldsymbol{\varphi}(\boldsymbol{x})\\ \end{pmatrix}\right)$.
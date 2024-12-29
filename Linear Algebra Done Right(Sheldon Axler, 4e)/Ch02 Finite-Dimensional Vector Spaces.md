# Ch02 Finite-Dimensional Vector Spaces  

In the last chapter we learned about vector spaces. Linear algebra focuses not on arbitrary vector spaces, but on finite-dimensional vector spaces, which we introduce in this chapter.  

We begin this chapter by considering linear combinations of lists of vectors. This leads us to the crucial concept of linear independence. The linear dependence lemma will become one of our most useful tools.  

A list of vectors in a vector space that is small enough to be linearly independent and big enough so the linear combinations of the list fill up the vector space is called a basis of the vector space. We will see that every basis of a vector space has the same length, which will allow us to define the dimension of a vector space.  

This chapter ends with a formula for the dimension of the sum of two subspaces.  

standing assumptions for this chapter  

+ 𝐅 denotes 𝐑 or 𝐂.   
+ 𝑉 denotes a vector space over 𝐅.

We have been writing lists of numbers surrounded by parentheses, and we will continue to do so for elements of $\mathbf{F}^{n}$ ; for example, $(2,-7,8)\in\mathbf{F}^{3}$ . However, now we need to consider lists of vectors (which may be elements of $\mathbf{F}^{n}$ or of other vector spaces). To avoid confusion, we will usually write lists of vectors without surrounding parentheses. For example, (4, 1, 6), (9, 5, 7) is a list of length two of vectors in $\mathbf{R}^{3}.$ .  

2.1 notation: list of vectors  

We will usually write lists of vectors without surrounding parentheses.  

## Linear Combinations and Span  

A sum of scalar multiples of the vectors in a list is called a linear combination of the list. Here is the formal definition.  

## 2.2 definition: linear combination  

A linear combination of a list $v_{1},...,v_{m}$ of vectors in $V$ is a vector of the form  

$$
a_{1}v_{1}+\cdots+a_{m}v_{m},
$$  

where $\textstyle{a_{1},...,a_{m}}\in\mathbf{F}$ .  

2.3 example: linear combinations in $\mathbf{R}^{3}$  

• $(17,-4,2)$ is a linear combination of $(2,1,-3),(1,-2,4)$ , which is a list of length two of vectors in $\mathbf{R}^{3}{}$ , because  

$$
(17,-4,2)=6(2,1,-3)+5(1,-2,4).
$$  

• $(17,-4,5)$ is not a linear combination of $(2,1,-3),(1,-2,4)$ , which is a list of length two of vectors in $\mathbf{R}^{3}$ , because there do not exist numbers $a_{1},a_{2}\in\mathbf{F}$ such that  

$$
(17,-4,5)=a_{1}(2,1,-3)+a_{2}(1,-2,4).
$$  

In other words, the system of equations  

$$
\begin{array}{c}{{17=2a_{1}+a_{2}}}\\ {{-4=a_{1}-2a_{2}}}\\ {{5=-3a_{1}+4a_{2}}}\end{array}
$$  

has no solutions (as you should verify).  

The set of all linear combinations of a list of vectors $v_{1},...,v_{m}$ in $V$ is called the span of $v_{1},...,v_{m}$ , denoted by span $(v_{1},...,v_{m})$ . In other words,  

$$
\operatorname{span}(v_{1},...,v_{m})=\{a_{1}v_{1}+\cdots+a_{m}v_{m}:a_{1},...,a_{m}\in\mathbf{F}\}.
$$  

The span of the empty list ( ) is defined to be $\{0\}$ .  

2.5 example: span  

The previous example shows that in $\mathbf{F}^{3}$ ,  

$$
(17,-4,2)\in\mathrm{span}\bigl((2,1,-3),(1,-2,4)\bigr)
$$  

• $(17,-4,5)\not\in\mathrm{span}\bigl((2,1,-3),(1,-2,4)\bigr).$  

Some mathematicians use the term linear span, which means the same as span.  

2.6 span is the smallest containing subspace  

The span of a list of vectors in $V$ is the smallest subspace of $V$ containing all vectors in the list.  

Proof Suppose $v_{1},...,v_{m}$ is a list of vectors in $V.$  

First we show that span $(v_{1},...,v_{m})$ is a subspace of $V.$ The additive identity is in span $(v_{1},...,v_{m})$ because  

$$
0=0v_{1}+\cdots+0v_{m}.
$$  

Also, span $(v_{1},...,v_{m})$ is closed under addition because  

$a_{1}v_{1}+\cdots+a_{m}v_{m})+(c_{1}v_{1}+\cdots+c_{m}v_{m})=(a_{1}+c_{1})v_{1}+\cdots+(a_{m}+c_{m})v_{m}$ 𝑚)𝑣𝑚.  

Furthermore, span $(v_{1},...,v_{m})$ is closed under scalar multiplication because  

$$
\lambda(a_{1}v_{1}+\cdots+a_{m}v_{m})=\lambda a_{1}v_{1}+\cdots+\lambda a_{m}v_{m}.
$$  

Thus span $(v_{1},...,v_{m})$ is a subspace of $V\,({\sf b y}\ 1.34)$ .  

Each $v_{k}$ is a linear combination of $v_{1},...,v_{m}$ (to show this, set $a_{k}=1$ and let the other $a$ ’s in 2.2 equal 0). Thus span $(v_{1},...,v_{m})$ contains each $v_{k}$ . Conversely, because subspaces are closed under scalar multiplication and addition, every subspace of $V$ that contains each $v_{k}$ contains span $(v_{1},...,v_{m})$ . Thus span $(v_{1},...,v_{m})$ is the smallest subspace of $V$ containing all the vectors $v_{1},...,v_{m}$ .  

## 2.7 definition: spans  

If span $(v_{1},...,v_{m})$ equals $V,$ , we say that the list $v_{1},...,v_{m}$ spans 𝑉.  

Suppose $n$ is a positive integer. We want to show that  

$$
(1,0,...,0),(0,1,0,...,0),...,(0,...,0,1)
$$  

spans $\mathbf{F}^{n}$ . Here the $k^{\mathrm{th}}$ vector in the list above has 1 in the $k^{\mathrm{th}}$ slot and 0 in all other slots.  

Suppose $(x_{1},...,x_{n})\in\mathbf{F}_{\cdot}^{n}$ . Then  

$$
(x_{1},...,x_{n})=x_{1}(1,0,...,0)+x_{2}(0,1,0,...,0)+\cdots+x_{n}(0,...,0,1).\nonumber
$$  

Thus $(x_{1},...,x_{n})\in\mathrm{span}\big((1,0,...,0),(0,1,0,...,0),...,(0,...,0,1)\big),$ as desired.  

Now we can make one of the key definitions in linear algebra.  

2.9 definition: finite-dimensional vector space  

A vector space is called finite-dimensional if some list of vectors in it spans the space.  

Example 2.8 above shows that $\mathbf{F}^{n}$ is a finite-dimensional vector space for every positive integer $n$ .  

Recall that by definition every list has finite length.  

The definition of a polynomial is no doubt already familiar to you.  

## 2.10 definition: polynomial, ${\mathcal{P}}(\mathbf{F})$  

• A function $p\colon\mathbf{F}\rightarrow\mathbf{F}$ is called a polynomial with coefficients in 𝐅if there exist $a_{0},...,a_{m}\in\mathbf{F}$ such that  

$$
p(z)=a_{0}+a_{1}z+a_{2}z^{2}+\cdots+a_{m}z^{m}
$$  

for all $z\in\mathbf{F}$ .  

• ${\mathcal{P}}(\mathbf{F})$ is the set of all polynomials with coefficients in 𝐅.  

With the usual operations of addition and scalar multiplication, ${\mathcal{P}}(\mathbf{F})$ is a vector space over 𝐅, as you should verify. Hence ${\mathcal{P}}(\mathbf{F})$ is a subspace of $\mathbf{F}^{\mathbf{F}},$ , the vector space of functions from 𝐅to 𝐅.  

If a polynomial (thought of as a function from 𝐅to 𝐅) is represented by two sets of coefficients, then subtracting one representation of the polynomial from the other produces a polynomial that is identically zero as a function on 𝐅and hence has all zero coefficients (if you are unfamiliar with this fact, just believe it for now; we will prove it later—see 4.8). Conclusion: the coefficients of a polynomial are uniquely determined by the polynomial. Thus the next definition uniquely defines the degree of a polynomial.  

## 2.11 definition: degree of a polynomial, deg $p$  

• A polynomial $p\,\in\,\mathcal{P}(\mathbf{F})$ is said to have degree 𝑚if there exist scalars $a_{0},a_{1},...,a_{m}\in\mathbf{F}$ with $a_{m}\neq0$ such that for every $z\in\mathbf{F}$ , we have  

$$
p(z)=a_{0}+a_{1}z+\cdots+a_{m}z^{m}\!.
$$  

• The polynomial that is identically 0 is said to have degree $-\infty$ .  

• The degree of a polynomial $p$ is denoted by $\deg p$ .  

In the next definition, we use the convention that $-\infty<m$ , which means that the polynomial 0 is in ${\mathcal P}_{m}({\bf F})$ .  

2.12 notation: ${\mathcal P}_{m}({\bf F})$  

For 𝑚a nonnegative integer, ${\mathcal P}_{m}({\bf F})$ denotes the set of all polynomials with coefficients in $\mathbf{F}$ and degree at most $m$ .  

If $m$ is a nonnegative integer, then $\mathcal{P}_{m}(\mathbf{F})=\operatorname{span}(1,z,...,z^{m})$ [here we slightly abuse notation by letting $z^{k}$ denote a function]. Thus ${\mathcal P}_{m}({\bf F})$ is a finite-dimensional vector space for each nonnegative integer $m$ .  

2.13 definition: infinite-dimensional vector space  

A vector space is called infinite-dimensional if it is not finite-dimensional.  

2.14 example: ${\mathcal{P}}(\mathbf{F})$ is infinite-dimensional.  

Consider any list of elements of ${\mathcal{P}}(\mathbf{F})$ . Let $m$ denote the highest degree of the polynomials in this list. Then every polynomial in the span of this list has degree at most $m$ . Thus $z^{m+1}$ is not in the span of our list. Hence no list spans ${\mathcal{P}}(\mathbf{F})$ . Thus ${\mathcal{P}}(\mathbf{F})$ is infinite-dimensional.  

## Linear Independence  

Suppose $v_{1},...,v_{m}\in V$ and 𝑣∈span $(v_{1},...,v_{m})$ . By the definition of span, there exist $\textstyle{a_{1},...,a_{m}}\in\mathbf{F}$ such that  

$$
v=a_{1}v_{1}+\cdots+a_{m}v_{m}.
$$  

Consider the question of whether the choice of scalars in the equation above is unique. Suppose $c_{1},...,c_{m}$ is another set of scalars such that  

$$
v=c_{1}v_{1}+\cdots+c_{m}v_{m}.
$$  

Subtracting the last two equations, we have  

$$
0=(a_{1}-c_{1})v_{1}+\cdots+(a_{m}-c_{m})v_{m}.
$$  

Thus we have written 0 as a linear combination of $(v_{1},...,v_{m})$ . If the only way to do this is by using 0 for all the scalars in the linear combination, then each $a_{k}-c_{k}$ equals 0, which means that each $a_{k}$ equals $c_{k}$ (and thus the choice of scalars was indeed unique). This situation is so important that we give it a special name—linear independence—which we now define.  

## 2.15 definition: linearly independent  

• A list $v_{1},...,v_{m}$ of vectors in $V$ is called linearly independent if the only choice of $\textstyle{a_{1},...,a_{m}}\in\mathbf{F}$ that makes  

$$
a_{1}v_{1}+\cdots+a_{m}v_{m}=0
$$  

is 𝑎 $a_{1}=\cdots=a_{m}=0$ .  

• The empty list ( ) is also declared to be linearly independent.  

The reasoning above shows that $v_{1},...,v_{m}$ is linearly independent if and only if each vector in span $(v_{1},...,v_{m})$ has only one representation as a linear combination of $v_{1},...,v_{m}$ .  

2.16 example: linearly independent lists  

(a) To see that the list $(1,0,0,0),(0,1,0,0),(0,0,1,0)$ is linearly independent in $\mathbf{F}_{\mathrm{~}}^{4}$ suppose $a_{1},a_{2},a_{3}\in\mathbf{F}$ and  

$$
a_{1}(1,0,0,0)+a_{2}(0,1,0,0)+a_{3}(0,0,1,0)=(0,0,0,0).
$$  

Thus  

$$
(a_{1},a_{2},a_{3},0)=(0,0,0,0).
$$  

Hence $a_{1}=a_{2}=a_{3}=0$ . Thus the list $(1,0,0,0),(0,1,0,0),(0,0,1,0)$ is linearly independent in $\mathbf{F}_{\cdot}^{4}$ .  

(b) Suppose $m$ is a nonnegative integer. To see that the list $1,z,...,z^{m}$ is linearly independent in ${\mathcal{P}}(\mathbf{F})$ , suppose $a_{0},a_{1},...,a_{m}\in\mathbf{F}$ and  

$$
a_{0}+a_{1}z+\cdots+a_{m}z^{m}=0,
$$  

where we think of both sides as elements of ${\mathcal{P}}(\mathbf{F})$ . Then  

$$
a_{0}+a_{1}z+\cdots+a_{m}z^{m}=0
$$  

for all $z\in\mathbf{F}$ . As discussed earlier (and as follows from 4.8), this implies that $a_{0}=a_{1}=\cdots=a_{m}=0$ . Thus $1,z,...,z^{m}$ is a linearly independent list in ${\mathcal{P}}(\mathbf{F})$ .  

(c) A list of length one in a vector space is linearly independent if and only if the vector in the list is not 0.  

(d) A list of length two in a vector space is linearly independent if and only if neither of the two vectors in the list is a scalar multiple of the other.  

If some vectors are removed from a linearly independent list, the remaining list is also linearly independent, as you should verify.  

## 2.17 definition: linearly dependent  

• A list of vectors in $V$ is called linearly dependent if it is not linearly independent. In other words, a list $v_{1},...,v_{m}$ of vectors in $V$ is linearly dependent if there exist $\textstyle{a_{1},...,a_{m}}\in\mathbf{F}$ , not all 0, such that $a_{1}v_{1}+\cdots+a_{m}v_{m}=0.$ .  

2.18 example: linearly dependent lists • $(2,3,1),(1,-1,2),(7,3,8)$ is linearly dependent in $\mathbf{F}^{3}$ because  

$$
2(2,3,1)+3(1,-1,2)+(-1)(7,3,8)=(0,0,0).
$$  

• The list (2, 3, 1), $(1,-1,2)$ , $(7,3,c)$ is linearly dependent in $\mathbf{F}^{3}$ if and only if $c=8$ , as you should verify.  

• If some vector in a list of vectors in $V$ is a linear combination of the other vectors, then the list is linearly dependent. (Proof: After writing one vector in the list as equal to a linear combination of the other vectors, move that vector to the other side of the equation, where it will be multiplied by $-1.$ .)  

• Every list of vectors in $V$ containing the 0 vector is linearly dependent. (This is a special case of the previous bullet point.)  

The next lemma is a terrific tool. It states that given a linearly dependent list of vectors, one of the vectors is in the span of the previous ones. Furthermore, we can throw out that vector without changing the span of the original list.  

2.19 linear dependence lemma  

Suppose $v_{1},...,v_{m}$ is a linearly dependent list in $V.$ Then there exists $k\in\{1,2,...,m\}$ such that  

$$
v_{k}\in\operatorname{span}(v_{1},...,v_{k-1}).
$$  

Furthermore, if $k$ satisfies the condition above and the $k^{\mathrm{th}}$ term is removed from $v_{1},...,v_{m}$ , then the span of the remaining list equals span $(v_{1},...,v_{m})$ .  

Proof Because the list $v_{1},...,v_{m}$ is linearly dependent, there exist numbers $\textstyle{a_{1},...,a_{m}}\in\mathbf{F}$ , not all 0, such that  

which proves that $v_{k}\in\operatorname{span}(v_{1},...,v_{k-1})$ , as desired.  

$$
a_{1}v_{1}+\cdots+a_{m}v_{m}=0.
$$  

Let $k$ be the largest element of $\{1,...,m\}$ such that $a_{k}\neq0$ . Then  

$$
v_{k}=-{\frac{a_{1}}{a_{k}}}v_{1}-\cdots-{\frac{a_{k-1}}{a_{k}}}v_{k-1},
$$  

Now suppose $k$ is any element of $\{1,...,m\}$ such that $v_{k}\in\operatorname{span}(v_{1},...,v_{k-1})$ . Let $b_{1},...,b_{k-1}\in\mathbf{F}$ be such that  

2.20  

$$
v_{k}=b_{1}v_{1}+\cdots+b_{k-1}v_{k-1}.
$$  

Suppose $u\in\mathrm{span}(v_{1},...,v_{m})$ . Then there exist $c_{1},...,c_{m}\in\mathbf{F}$ such that  

$$
u=c_{1}v_{1}+\cdots+c_{m}v_{m}.
$$  

In the equation above, we can replace $v_{k}$ with the right side of 2.20, which shows that $u$ is in the span of the list obtained by removing the $k^{\mathrm{th}}$ term from $v_{1},...,v_{m}$ . Thus removing the $k^{\mathrm{th}}$ term of the list $v_{1},...,v_{m}$ does not change the span of the list.  

If $k=1$ in the linear dependence lemma, then $v_{k}\in\operatorname{span}(v_{1},...,v_{k-1})$ means that $v_{1}=0$ , because span $(\mathbf{\epsilon})=\{0\}$ . Note also that parts of the proof of the linear dependence lemma need to be modified if $k=1$ . In general, the proofs in the rest of the book will not call attention to special cases that must be considered involving lists of length 0, the subspace $\{0\}$ , or other trivial cases for which the result is true but needs a slightly different proof. Be sure to check these special cases yourself.  

2.21 example: smallest $k$ in linear dependence lemma  

Consider the list  

$$
(1,2,3),(6,5,4),(15,16,17),(8,9,7)
$$  

in $\mathbf{R}^{3}.$ This list of length four is linearly dependent, as we will soon see. Thus the linear dependence lemma implies that there exists $k\in\{1,2,3,4\}$ such that the $k^{\mathrm{th}}$ vector in this list is a linear combination of the previous vectors in the list. Let’s see how to find the smallest value of $k$ that works.  

Taking $k=1$ in the linear dependence lemma works if and only if the first vector in the list equals 0. Because (1, 2, 3) is not the 0 vector, we cannot take $k=1$ for this list.  

Taking $k=2$ in the linear dependence lemma works if and only if the second vector in the list is a scalar multiple of the first vector. However, there does not exist $c\in\mathbb{R}$ such that $(6,5,4)=c(1,2,3)$ . Thus we cannot take $k=2$ for this list.  

Taking $k=3$ in the linear dependence lemma works if and only if the third vector in the list is a linear combination of the first two vectors. Thus for the list in this example, we want to know whether there exist $a,b\in\mathbb{R}$ such that  

$$
(15,16,17)=a(1,2,3)+b(6,5,4).
$$  

The equation above is equivalent to a system of three linear equations in the two unknowns $a,b$ . Using Gaussian elimination or appropriate software, we find that $a=3$ , $b=2$ is a solution of the equation above, as you can verify. Thus for the list in this example, taking $k=3$ is the smallest value of $k$ that works in the linear dependence lemma.  

Now we come to a key result. It says that no linearly independent list in $V$ is longer than a spanning list in $V.$  

## 2.22 length of linearly independent list $\leq$ length of spanning list  

In a finite-dimensional vector space, the length of every linearly independent list of vectors is less than or equal to the length of every spanning list of vectors.  

Proof Suppose that $u_{1},...,u_{m}$ is linearly independent in $V.$ . Suppose also that $w_{1},...,w_{n}$ spans $V.$ We need to prove that $m\le n$ . We do so through the process described below with $m$ steps; note that in each step we add one of the $u$ ’s and remove one of the 𝑤’s.  

## Step 1  

Let $B$ be the list $w_{1},...,w_{n}$ , which spans $V.$ Adjoining $u_{1}$ at the beginning of this list produces a linearly dependent list (because $u_{1}$ can be written as a linear combination of $w_{1},...,w_{m})$ . In other words, the list  

$$
u_{1},w_{1},...,w_{n}
$$  

is linearly dependent.  

Thus by the linear dependence lemma (2.19), one of the vectors in the list above is a linear combination of the previous vectors in the list. We know that $u_{1}\neq0$ because the list $u_{1},...,u_{m}$ is linearly independent. Thus $u_{1}$ is not in the span of the previous vectors in the list above (because $u_{1}$ is not in $\{0\}$ , which is the span of the empty list). Hence the linear dependence lemma implies that we can remove one of the $w$ ’s so that the new list $B$ (of length $n$ ) consisting of $u_{1}$ and the remaining $w$ ’s spans $V.$ .  

## Step $\pmb{k}$ , for $k=2,...,m$  

The list $B$ (of length $n$ ) from step $k\!-\!1$ spans $V.$ In particular, $u_{k}$ is in the span of the list $B$ . Thus the list of length $(n+1)$ obtained by adjoining $u_{k}$ to $B$ , placing it just after $u_{1},...,u_{k-1}$ , is linearly dependent. By the linear dependence lemma (2.19), one of the vectors in this list is in the span of the previous ones, and because $u_{1},...,u_{k}$ is linearly independent, this vector cannot be one of the $u$ ’s. Hence there still must be at least one remaining $w$ at this step. We can remove from our new list (after adjoining $u_{k}$ in the proper place) a $w$ that is a linear combination of the previous vectors in the list, so that the new list $B$ (of length $^{n)}$ consisting of $u_{1},...,u_{k}$ and the remaining 𝑤’s spans $V.$ .  

After step $m$ , we have added all the $u$ ’s and the process stops. At each step as we add a $u$ to $B$ , the linear dependence lemma implies that there is some $w$ to remove. Thus there are at least as many $w$ ’s as 𝑢’s.  

The next two examples show how the result above can be used to show, without any computations, that certain lists are not linearly independent and that certain lists do not span a given vector space.  

2.23 example: no list of length 4 is linearly independent in $\mathbf{R}^{3}$  

The list $(1,0,0)$ , (0, 1, 0), (0, 0, 1), which has length three, spans $\mathbf{R}^{3}.$ . Thus no list of length larger than three is linearly independent in $\mathbf{R}^{3}$ .  

For example, we now know that (1, 2, 3), (4, 5, 8), (9, 6, 7), (−3, 2, 8), which is a list of length four, is not linearly independent in $\mathbf{R}^{3}.$ .  

2.24 example: no list of length 3 spans $\mathbf{R}^{4}$  

The list $(1,0,0,0)$ , $(0,1,0,0)$ , $(0,0,1,0)$ , $(0,0,0,1)$ , which has length four, is linearly independent in $\mathbf{R}^{4}.$ . Thus no list of length less than four spans $\mathbf{R}^{4}.$ .  

For example, we now know that $(1,2,3,-5)$ , (4, 5, 8, 3), $(9,6,7,-1)$ , which is a list of length three, does not span $\mathbf{R}^{4}.$ .  

Our intuition suggests that every subspace of a finite-dimensional vector space should also be finite-dimensional. We now prove that this intuition is correct.  

## 2.25 finite-dimensional subspaces  

Every subspace of a finite-dimensional vector space is finite-dimensional.  

Proof Suppose $V$ is finite-dimensional and $U$ is a subspace of $V.$ We need to prove that $U$ is finite-dimensional. We do this through the following multistep construction.  

## Step 1  

If $U=\{0\}$ , then $U$ is finite-dimensional and we are done. If $U\neq\{0\}$ , then choose a nonzero vector $u_{1}\in U$ .  

## Step $\pmb{k}$  

If $U=\mathrm{span}(u_{1},...,u_{k-1})$ , then $U$ is finite-dimensional and we are done. If $U\neq\operatorname{span}(u_{1},...,u_{k-1})$ , then choose a vector $u_{k}\in U$ such that  

$$
u_{k}\notin\operatorname{span}(u_{1},...,u_{k-1}).
$$  

After each step, as long as the process continues, we have constructed a list of vectors such that no vector in this list is in the span of the previous vectors. Thus after each step we have constructed a linearly independent list, by the linear dependence lemma (2.19). This linearly independent list cannot be longer than any spanning list of $V$ (by 2.22). Thus the process eventually terminates, which means that $U$ is finite-dimensional.  

1 Find a list of four distinct vectors in $\mathbf{F}^{3}$ whose span equals  

$$
\{(x,y,z)\in\mathbf{F}^{3}:x+y+z=0\}.
$$  

2 Prove or give a counterexample: If $v_{1},v_{2},v_{3},v_{4}$ spans $V,$ then the list  

$$
v_{1}-v_{2},v_{2}-v_{3},v_{3}-v_{4},v_{4}
$$  

also spans $V.$  

3 Suppose $v_{1},...,v_{m}$ is a list of vectors in $V.$ For $k\in\{1,...,m\}$ , let  

$$
w_{k}=v_{1}+\cdots+v_{k}.
$$  

Show that span $(v_{1},...,v_{m})=\operatorname{span}(w_{1},...,w_{m}).$  

4 (a) Show that a list of length one in a vector space is linearly independent if and only if the vector in the list is not 0. (b) Show that a list of length two in a vector space is linearly independent if and only if neither of the two vectors in the list is a scalar multiple of the other.  

5 Find a number $t$ such that  

$$
(3,1,4),(2,-3,5),(5,9,t)
$$  

is not linearly independent in $\mathbf{R}^{3}.$ .  

6 Show that the list $(2,3,1),(1,-1,2),(7,3,c)$ is linearly dependent in $\mathbf{F}^{3}$ if and only if $c=8$ .  

7 (a) Show that if we think of $\mathbf{C}$ as a vector space over $\mathbf{R}$ , then the list $1+i,1-i$ is linearly independent. (b) Show that if we think of $\mathbf{C}$ as a vector space over $\mathbf{C}$ , then the list $1+i,1-i$ is linearly dependent.  

8 Suppose $v_{1},v_{2},v_{3},v_{4}$ is linearly independent in $V.$ Prove that the list  

$$
v_{1}-v_{2},v_{2}-v_{3},v_{3}-v_{4},v_{4}
$$  

is also linearly independent.  

9 Prove or give a counterexample: If $v_{1},v_{2},...,v_{m}$ is a linearly independent list of vectors in $V,$ , then  

$$
5v_{1}-4v_{2},v_{2},v_{3},...,v_{m}
$$  

is linearly independent.  

10 Prove or give a counterexample: If $v_{1},v_{2},...,v_{m}$ is a linearly independent list of vectors in $V$ and $\lambda\in\mathbf{F}$ with $\lambda\ne0$ , then $\lambda v_{1},\lambda v_{2},...,\lambda v_{m}$ is linearly independent.   
11 Prove or give a counterexample: If $v_{1},...,v_{m}$ and $w_{1},...,w_{m}$ are linearly independent lists of vectors in $V,$ then the list $v_{1}+w_{1},...,v_{m}+w_{m}$ is linearly independent.   
12 Suppose $v_{1},...,v_{m}$ is linearly independent in $V$ and $w\in V.$ Prove that if $v_{1}+w,...,v_{m}+w$ is linearly dependent, then 𝑤∈span $(v_{1},...,v_{m})$ . $V$ $w\in V.$  

13 Suppose $v_{1},...,v_{m}$ is linearly independent in and Show that $v_{1},...,v_{m},w$ is linearly independent $\Longleftrightarrow\ \boldsymbol{w}$ ∉span $(v_{1},...,v_{m})$ .  

14 Suppose $v_{1},...,v_{m}$ is a list of vectors in $V.$ For $k\in\{1,...,m\}$ , let  

$$
w_{k}=v_{1}+\cdots+v_{k}.
$$  

Show that the list $v_{1},...,v_{m}$ is linearly independent if and only if the list $w_{1},...,w_{m}$ is linearly independent.   
5 Explain why there does not exist a list of six polynomials that is linearly independent in ${\mathcal{P}}_{4}(\mathbf{F})$ .   
16 Explain why no list of four polynomials spans ${\mathcal{P}}_{4}(\mathbf{F})$ .   
7 Prove that $V$ is infinite-dimensional if and only if there is a sequence $v_{1},v_{2},\ldots$ of vectors in $V$ such that $v_{1},...,v_{m}$ is linearly independent for every positive integer $m$ .   
18 Prove that $\mathbf{F}^{\infty}$ is infinite-dimensional.   
9 Prove that the real vector space of all continuous real-valued functions on the interval [0, 1] is infinite-dimensional.   
20 Suppose $p_{0},p_{1},...,p_{m}$ are polynomials in ${\mathcal P}_{m}({\bf F})$ such that $p_{k}(2)=0$ for each $k\in\{0,...,m\}$ . Prove that $p_{0},p_{1},...,p_{m}$ is not linearly independent in ${\mathcal P}_{m}({\bf F})$  

In the previous section, we discussed linearly independent lists and we also discussed spanning lists. Now we bring these concepts together by considering lists that have both properties.  

## 2.26 definition: basis  

A basis of $V$ is a list of vectors in $V$ that is linearly independent and spans $V.$  

## 2.27 example: bases  

(a) The list $(1,0,...,0)$ , $(0,1,0,...,0),...,(0,...,0,1)$ is a basis of $\mathbf{F}_{\,:}^{n}$ called the standard basis of $\mathbf{F}^{n}$ .  

(b) The list (1, 2), (3, 5) is a basis of $\mathbf{F}^{2}.$ . Note that this list has length two, which is the same as the length of the standard basis of $\mathbf{F}^{2}.$ . In the next section, we will see that this is not a coincidence.  

(c) The list $(1,2,-4)$ , $(7,-5,6)$ is linearly independent in $\mathbf{F}^{3}$ but is not a basis of $\mathbf{F}^{3}$ because it does not span $\mathbf{F}^{3}.$ .  

(d) The list (1, 2), (3, 5), (4, 13) spans $\mathbf{F}^{2}$ but is not a basis of $\mathbf{F}^{2}$ because it is not linearly independent.  

(e) The list (1, 1, 0), (0, 0, 1) is a basis of $\{(x,x,y)\in\mathbf{F}^{3}\colon x,y\in\mathbf{F}\}.$  

(f) The list $(1,-1,0)$ , $(1,0,-1)$ is a basis of  

$$
\big\{(x,y,z)\in\mathbf{F}^{3}\colon x+y+z=0\big\}.
$$  

(g) The list $1,z,...,z^{m}$ is a basis of ${\mathcal P}_{m}({\bf F})$ , called the standard basis of ${\mathcal P}_{m}({\bf F})$ .  

In addition to the standard basis, $\mathbf{F}^{n}$ has many other bases. For example,  

$$
(7,5),(-4,9)\quad\mathrm{and}\quad(1,2),(3,5)
$$  

are both bases of $\mathbf{F}^{2}.$  

The next result helps explain why bases are useful. Recall that “uniquely” means “in only one way”.  

## 2.28 criterion for basis  

A list $v_{1},...,v_{n}$ of vectors in $V$ is a basis of $V$ if and only if every $v\in V$ can be written uniquely in the form  

2.29  

$$
v=a_{1}v_{1}+\cdots+a_{n}v_{n},
$$  

where $\textstyle{a_{1},...,a_{n}}\in\mathbf{F}$ .  

Proof First suppose that $v_{1},...,v_{n}$ is a basis of 𝑉. Let 𝑣∈𝑉. Because 𝑣1, …, 𝑣𝑛 spans $V,$ there exist $a_{1},...,a_{n}\,\in\,\mathbf{F}$ such that 2.29 holds. To show that the repre  

This proof is essentially a repetition of the ideas that led us to the definition of linear independence.  

sentation in 2.29 is unique, suppose $c_{1},...,c_{n}$ are scalars such that we also have  

$$
v=c_{1}v_{1}+\cdots+c_{n}v_{n}.
$$  

Subtracting the last equation from 2.29, we get  

$$
0=(a_{1}-c_{1})v_{1}+\cdots+(a_{n}-c_{n})v_{n}.
$$  

This implies that each $a_{k}-c_{k}$ equals 0 (because $v_{1},...,v_{n}$ is linearly independent). Hence $a_{1}=c_{1},...,a_{n}=c_{n}$ . We have the desired uniqueness, completing the proof in one direction.  

For the other direction, suppose every $v\in V$ can be written uniquely in the form given by 2.29. This implies that the list $v_{1},...,v_{n}$ spans $V.$ . To show that $v_{1},...,v_{n}$ is linearly independent, suppose $\textstyle{a_{1},...,a_{n}}\in\mathbf{F}$ are such that  

$$
0=a_{1}v_{1}+\cdots+a_{n}v_{n}.
$$  

The uniqueness of the representation 2.29 (taking $v~=~0,$ ) now implies that $a_{1}=\cdots=a_{n}=0$ . Thus $v_{1},...,v_{n}$ is linearly independent and hence is a basis of $V.$  

A spanning list in a vector space may not be a basis because it is not linearly independent. Our next result says that given any spanning list, some (possibly none) of the vectors in it can be discarded so that the remaining list is linearly independent and still spans the vector space.  

As an example in the vector space $\mathbf{F}_{\mathrm{:}}^{2}$ , if the procedure in the proof below is applied to the list (1, 2), (3, 6), (4, 7), (5, 9), then the second and fourth vectors will be removed. This leaves (1, 2), (4, 7), which is a basis of $\mathbf{F}^{2}.$ .  

2.30 every spanning list contains a basis  

Every spanning list in a vector space can be reduced to a basis of the vector space.  

Proof Suppose $v_{1},...,v_{n}$ spans $V.$ We want to remove some of the vectors from $v_{1},...,v_{n}$ so that the remaining vectors form a basis of $V.$ We do this through the multistep process described below.  

Start with $B$ equal to the list $v_{1},...,v_{n}$ .  

## Step 1  

If $v_{1}=0$ , then delete $v_{1}$ from $B$ . If $v_{1}\neq0$ , then leave $B$ unchanged.  

## Step $\pmb{k}$  

If $v_{k}$ is in span $(v_{1},...,v_{k-1})$ , then delete $v_{k}$ from the list $B$ . If $v_{k}$ is not in span $(v_{1},...,v_{k-1})$ , then leave $B$ unchanged.  

Stop the process after step $n$ , getting a list $B$ . This list $B$ spans $V$ because our original list spanned $V$ and we have discarded only vectors that were already in the span of the previous vectors. The process ensures that no vector in $B$ is in the span of the previous ones. Thus $B$ is linearly independent, by the linear dependence lemma (2.19). Hence $B$ is a basis of $V.$ .  

We now come to an important corollary of the previous result.  

2.31 basis of finite-dimensional vector space  

Every finite-dimensional vector space has a basis.  

Proof By definition, a finite-dimensional vector space has a spanning list. The previous result tells us that each spanning list can be reduced to a basis.  

Our next result is in some sense a dual of 2.30, which said that every spanning list can be reduced to a basis. Now we show that given any linearly independent list, we can adjoin some additional vectors (this includes the possibility of adjoining no additional vectors) so that the extended list is still linearly independent but also spans the space.  

2.32 every linearly independent list extends to a basis  

Every linearly independent list of vectors in a finite-dimensional vector space can be extended to a basis of the vector space.  

Proof Suppose $u_{1},...,u_{m}$ is linearly independent in a finite-dimensional vector space $V.$ Let $w_{1},...,w_{n}$ be a list of vectors in $V$ that spans $V.$ Thus the list  

$$
u_{1},...,u_{m},w_{1},...,w_{n}
$$  

spans $V.$ Applying the procedure of the proof of 2.30 to reduce this list to a basis of $V$ produces a basis consisting of the vectors $u_{1},...,u_{m}$ and some of the 𝑤’s (none of the $u$ ’s get deleted in this procedure because $u_{1},...,u_{m}$ is linearly independent).  

As an example in $\mathbf{F}_{\mathrm{~}}^{3}$ suppose we start with the linearly independent list (2, 3, 4), (9, 6, 8). If we take $w_{1}$ ${\mathbf{\Omega}}_{1},w_{2},w_{3}$ to be the standard basis of $\mathbf{F}_{:}^{3}$ , then applying the procedure in the proof above produces the list  

$$
(2,3,4),(9,6,8),(0,1,0),
$$  

which is a basis of $\mathbf{F}^{3}.$  

As an application of the result above, we now show that every subspace of a finite-dimensional vector space can be paired with another subspace to form a direct sum of the whole space.  

Using the same ideas but more advanced tools, the next result can be proved without the hypothesis that 𝑉is finite-dimensional.  

Suppose $V$ is finite-dimensional and $U$ is a subspace of $V.$ Then there is a subspace $W$ of $V$ such that $V=U\oplus W$ .  

Proof Because $V$ is finite-dimensional, so is $U$ (see 2.25). Thus there is a basis $u_{1},...,u_{m}$ of $U$ (by 2.31). Of course $u_{1},...,u_{m}$ is a linearly independent list of vectors in $V.$ . Hence this list can be extended to a basis $u_{1},...,u_{m},w_{1},...,w_{n}$ of $V$ (by 2.32). Let $W=\operatorname{span}(w_{1},...,w_{n})$ .  

To prove that $V=U\oplus W$ , by 1.46 we only need to show that  

$$
V=U+W\quad{\mathrm{and}}\quad U\cap W=\{0\}.
$$  

To prove the first equation above, suppose $v\in V.$ Then, because the list $u_{1},...,u_{m},w_{1},...,w_{n}$ spans $V,$ , there exist $a_{1},...,a_{m},b_{1},...,b_{n}\in\mathbf{F}$ such that  

$$
v=\underbrace{a_{1}u_{1}+\cdots+a_{m}u_{m}}_{u}+\underbrace{b_{1}w_{1}+\cdots+b_{n}w_{n}}_{w}.
$$  

We have $\boldsymbol{v}\;=\;\boldsymbol{u}\;+\;\boldsymbol{w}$ , where $u\,\in\,U$ and $w\,\in\,W$ are defined as above. Thus $v\in U+W$ , completing the proof that $V=U+W$ .  

To show that $U\cap W=\{0\}$ , suppose $v\in U\cap W.$ Then there exist scalars $a_{1},...,a_{m},b_{1},...,b_{n}\in\mathbf{F}$ such that  

$$
v=a_{1}u_{1}+\cdots+a_{m}u_{m}=b_{1}w_{1}+\cdots+b_{n}w_{n}.
$$  

Thus  

$$
a_{1}u_{1}+\cdots+a_{m}u_{m}-b_{1}w_{1}-\cdots-b_{n}w_{n}=0.
$$  

Because $u_{1},...,u_{m},w_{1},...,w_{n}$ is linearly independent, this implies that  

$$
a_{1}=\cdots=a_{m}=b_{1}=\cdots=b_{n}=0.
$$  

Thus $v=0$ , completing the proof that $U\cap W=\{0\}$ .  

## Exercises 2B  

1 Find all vector spaces that have exactly one basis.  

2 Verify all assertions in Example 2.27.  

3 (a) Let $U$ be the subspace of $\mathbf{R}^{5}$ defined by  

$$
U=\left\{(x_{1},x_{2},x_{3},x_{4},x_{5})\in\mathbf{R}^{5}:x_{1}=3x_{2}
$$  

Find a basis of $U$ .  

(b) Extend the basis in (a) to a basis of $\mathbf{R}^{5}.$ .   
(c) Find a subspace $W$ of $\mathbf{R}^{5}$ such that $\mathbf{R}^{5}=U\oplus W.$ .  

4 (a) Let $U$ be the subspace of $\mathbf{C}^{5}$ defined by  

$U=\big\{(z_{1},z_{2},z_{3},z_{4},z_{5})\in\mathbf{C}^{5}:6z_{1}=z_{2}$  

Find a basis of $U$ .  

(b) Extend the basis in (a) to a basis of $\mathbf{C}^{5}.$ . (c) Find a subspace $W$ of $\mathbf{C}^{5}$ such that $\mathbf{C}^{5}=U\oplus W.$  

5 Suppose $V$ is finite-dimensional and $U,W$ are subspaces of $V$ such that $V=U+W.$ . Prove that there exists a basis of $V$ consisting of vectors in $U\cup W.$ .  

6 Prove or give a counterexample: If $p_{0},p_{1},p_{2},p_{3}$ is a list in ${\mathcal P}_{3}({\bf F})$ such that none of the polynomials $p_{0},p_{1},p_{2},p_{3}$ has degree 2, then $p_{0},p_{1},p_{2},p_{3}$ is not a basis of ${\mathcal P}_{3}({\bf F})$ .  

7 Suppose $v_{1},v_{2},v_{3},v_{4}$ is a basis of $V.$ . Prove that  

$$
v_{1}+v_{2},v_{2}+v_{3},v_{3}+v_{4},v_{4}
$$  

is also a basis of $V.$ .  

8 Prove or give a counterexample: If $v_{1},v_{2},v_{3},v_{4}$ is a basis of $V$ and $U$ is a subspace of $V$ such that $v_{1},v_{2}\in U$ and $v_{3}\notin U$ and $v_{4}\notin U$ , then $v_{1},v_{2}$ is a basis of $U$ .  

9 Suppose $v_{1},...,v_{m}$ is a list of vectors in $V.$ For $k\in\{1,...,m\}$ , let  

$$
w_{k}=v_{1}+\cdots+v_{k}.
$$  

Show that $v_{1},...,v_{m}$ is a basis of $V$ if and only if $w_{1},...,w_{m}$ is a basis of $V.$ .  

10 Suppose $U$ and $W$ are subspaces of $V$ such that $V=U\oplus W.$ . Suppose also that $u_{1},...,u_{m}$ is a basis of $U$ and $w_{1},...,w_{n}$ is a basis of $W.$ . Prove that  

$$
u_{1},...,u_{m},w_{1},...,w_{n}
$$  

is a basis of $V.$ .  

11 Suppose $V$ is a real vector space. Show that if $v_{1},...,v_{n}$ is a basis of $V$ (as a real vector space), then $v_{1},...,v_{n}$ is also a basis of the complexification $V_{\mathbf{C}}$ (as a complex vector space).  

See Exercise 8 in Section 1B for the definition of the complexification $V_{\mathbf{C}}$ .  

Although we have been discussing finite-dimensional vector spaces, we have not yet defined the dimension of such an object. How should dimension be defined? A reasonable definition should force the dimension of $\mathbf{F}^{n}$ to equal $n$ . Notice that the standard basis  

$$
(1,0,...,0),(0,1,0,...,0),...,(0,...,0,1)
$$  

of $\mathbf{F}^{n}$ has length $n$ . Thus we are tempted to define the dimension as the length of a basis. However, a finite-dimensional vector space in general has many different bases, and our attempted definition makes sense only if all bases in a given vector space have the same length. Fortunately that turns out to be the case, as we now show.  

2.34 basis length does not depend on basis  

Any two bases of a finite-dimensional vector space have the same length.  

Proof Suppose $V$ is finite-dimensional. Let $B_{1}$ and $B_{2}$ be two bases of $V.$ Then $B_{1}$ is linearly independent in $V$ and $B_{2}$ spans $V,$ , so the length of $B_{1}$ is at most the length of $B_{2}$ (by 2.22). Interchanging the roles of $B_{1}$ and $B_{2}$ , we also see that the length of $B_{2}$ is at most the length of $B_{1}$ . Thus the length of $B_{1}$ equals the length of $B_{2}$ , as desired.  

Now that we know that any two bases of a finite-dimensional vector space have the same length, we can formally define the dimension of such spaces.  

## 2.35 definition: dimension, dim 𝑉  

• The dimension of a finite-dimensional vector space is the length of any basis of the vector space.  

• The dimension of a finite-dimensional vector space $V$ is denoted by dim 𝑉.  

2.36 example: dimensions  

• dim ${\bf F}^{n}=n$ because the standard basis of $\mathbf{F}^{n}$ has length $n$ .  

• dim $\mathcal{P}_{m}(\mathbf{F})=m+1$ because the standard basis $1,z,...,z^{m}$ of ${\mathcal P}_{m}({\bf F})$ has length $m+1$ .  

• If $U=\left\{(x,x,y)\in\mathbf{F}^{3}\colon x,y\in\mathbf{F}\right\}$ , then dim $U=2$ because $(1,1,0),(0,0,1)$ is a basis of $U$ .  

• If $U\;=\;\left\{(x,y,z)\;\in\;\mathbf{F}^{3}\colon x\,+\,y\,+\,z\;=\;0\right\}$ , then dim $U\,=\,2$ because the list $(1,-1,0)$ , $(1,0,-1)$ is a basis of $U$ .  

Every subspace of a finite-dimensional vector space is finite-dimensional (by 2.25) and so has a dimension. The next result gives the expected inequality about the dimension of a subspace.  

2.37 dimension of a subspace  

If $V$ is finite-dimensional and $U$ is a subspace of $V,$ , then dim $U\leq\dim V.$  

Proof Suppose $V$ is finite-dimensional and $U$ is a subspace of $V.$ Think of a basis of $U$ as a linearly independent list in $V,$ , and think of a basis of $V$ as a spanning list in $V.$ Now use 2.22 to conclude that dim $U\leq\dim V.$  

To check that a list of vectors in $V$ is a basis of $V,$ we must, according to the definition, show that the list in question satisfies two properties: it must be linearly independent and it must span $V.$ The next two results show that if the list in question has the right length, then we only need to check that it satisfies one of the two required properties. First we prove that every linearly independent list of the right length is a basis.  

The real vector space $\mathbf{R}^{2}$ has dimension two; the complex vector space $\mathbf{C}$ has dimension one. As sets, $\mathbf{R}^{2}$ can be identified with 𝐂(and addition is the same on both spaces, as is scalar multiplication by real numbers). Thus when we talk about the dimension of a vector space, the role played by the choice of 𝐅cannot be neglected.  

## 2.38 linearly independent list of the right length is a basis  

Suppose $V$ is finite-dimensional. Then every linearly independent list of vectors in $V$ of length dim $V$ is a basis of $V.$  

Proof Suppose $\dim V=n$ and $v_{1},...,v_{n}$ is linearly independent in $V.$ The list $v_{1},...,v_{n}$ can be extended to a basis of $V\,(\log2.32)$ . However, every basis of $V$ has length $n$ , so in this case the extension is the trivial one, meaning that no elements are adjoined to $v_{1},...,v_{n}$ . Thus $v_{1},...,v_{n}$ is a basis of $V,$ as desired.  

The next result is a useful consequence of the previous result.  

2.39 subspace of full dimension equals the whole space  

Suppose that $V$ is finite-dimensional and $U$ is a subspace of $V$ such that $\dim U=\dim V.$ Then $U=V.$  

Proof Let $u_{1},...,u_{n}$ be a basis of $U$ . Thus $n\,=\,\dim U$ , and by hypothesis we also have $n=\dim V.$ Thus $u_{1},...,u_{n}$ is a linearly independent list of vectors in $V$ (because it is a basis of $U$ ) of length dim $V.$ . From 2.38, we see that $u_{1},...,u_{n}$ is a basis of $V.$ In particular every vector in $V$ is a linear combination of $u_{1},...,u_{n}$ . Thus $U=V.$ .  

Consider the list (5, 7), (4, 3) of vectors in $\mathbf{F}^{2}.$ This list of length two is linearly independent in $\mathbf{F}^{2}$ (because neither vector is a scalar multiple of the other). Note that $\mathbf{F}^{2}$ has dimension two. Thus 2.38 implies that the linearly independent list (5, 7), (4, 3) of length two is a basis of $\mathbf{F}^{2}$ (we do not need to bother checking that it spans $\mathbf{F}^{2}$ ).  

2.41 example: a basis of a subspace of ${\mathcal P}_{3}({\bf R})$  

Let $U$ be the subspace of ${\mathcal{P}}_{3}(\mathbf{R})$ defined by  

$$
U=\{p\in{\mathcal{P}}_{3}(\mathbf{R}):p^{\prime}(5)=0\}.
$$  

To find a basis of $U$ , first note that each of the polynomials 1, $(x\!-\!5)^{2}$ , and $(x\!-\!5)^{3}$ is in $U$ .  

Suppose $a,b,c\in\mathbb{R}$ and  

$$
a+b(x-5)^{2}+c(x-5)^{3}=0
$$  

for every $x\in\mathbb{R}$ . Without explicitly expanding the left side of the equation above, we can see that the left side has a $c x^{3}$ term. Because the right side has no $x^{3}$ term, this implies that $c=0$ . Because $c=0$ , we see that the left side has a $b x^{2}$ term, which implies that $b=0$ . Because $b=c=0$ , we can also conclude that $a\,=\,0$ . Thus the equation above implies that $\;a\,=\,b\,=\,c\,=\,0$ . Hence the list $1,(x-5)^{2},(x-5)^{3}$ is linearly independent in $U$ . Thus $3\leq\dim U$ . Hence  

$$
\begin{array}{r}{3\leq\dim U\leq\dim\mathcal{P}_{3}(\mathbf{R})=4,}\end{array}
$$  

where we have used 2.37.  

The polynomial $x$ is not in $U$ because its derivative is the constant function 1. Thus $U\neq\mathcal{P}_{3}(\mathbb{R})$ . Hence dim $U\neq4$ (by 2.39). The inequality above now implies that dim $U=3$ . Thus the linearly independent list 1, $(x-5)^{2}$ , $(x-5)^{3}$ in $U$ has length dim $U$ and hence is a basis of $U$ (by 2.38).  

Now we prove that a spanning list of the right length is a basis.  

## 2.42 spanning list of the right length is a basis  

Suppose $V$ is finite-dimensional. Then every spanning list of vectors in $V$ of length dim $V$ is a basis of $V.$ .  

Proof Suppose $\dim V\;=\;n$ and $v_{1},...,v_{n}$ spans $V.$ The list $v_{1},...,v_{n}$ can be reduced to a basis of $V\,(\mathrm{by}\ 2.30)$ . However, every basis of $V$ has length $n$ , so in this case the reduction is the trivial one, meaning that no elements are deleted from $v_{1},...,v_{n}$ . Thus $v_{1},...,v_{n}$ is a basis of $V,$ as desired.  

The next result gives a formula for the dimension of the sum of two subspaces of a finite-dimensional vector space. This formula is analogous to a familiar counting formula: the number of elements in the union of two finite sets equals the number of elements in the first set, plus the number of elements in the second set, minus the number of elements in the intersection of the two sets.  

2.43 dimension of a sum  

If $V_{1}$ and $V_{2}$ are subspaces of a finite-dimensional vector space, then  

$$
\dim(V_{1}+V_{2})=\dim V_{1}+\dim V_{2}-\dim(V_{1}\cap V_{2}).
$$  

Proof Let $v_{1},...,v_{m}$ be a basis of $V_{1}\cap V_{2}$ ; thus $\dim(V_{1}\cap V_{2})=m$ . Because $v_{1},...,v_{m}$ is a basis of $V_{1}\cap V_{2}$ , it is linearly independent in $V_{1}$ . Hence this list can be extended to a basis $v_{1},...,v_{m},u_{1},...,u_{j}$ of $V_{1}$ (by 2.32). Thus dim $V_{1}=m+j$ . Also extend $v_{1},...,v_{m}$ to a basis $v_{1},...,v_{m},w_{1},...,w_{k}$ of $V_{2}$ ; thus dim $V_{2}=m+k$ . We will show that  

2.44  

$$
v_{1},...,v_{m},u_{1},...,u_{j},w_{1},...,w_{k}
$$  

is a basis of $V_{1}+V_{2}$ . This will complete the proof, because then we will have  

$$
\begin{array}{l}{\dim(V_{1}+V_{2})=m+j+k}\\ {\qquad\qquad=(m+j)+(m+k)-m}\\ {\qquad\qquad=\dim V_{1}+\dim V_{2}-\dim(V_{1}\cap V_{2}).}\end{array}
$$  

The list 2.44 is contained in $V_{1}\cup V_{2}$ and thus is contained in $V_{1}+V_{2}$ . The span of this list contains $V_{1}$ and contains $V_{2}$ and hence is equal to $V_{1}+V_{2}$ . Thus to show that 2.44 is a basis of $V_{1}+V_{2}$ we only need to show that it is linearly independent.  

To prove that 2.44 is linearly independent, suppose  

$$
a_{1}v_{1}+\cdots+a_{m}v_{m}+b_{1}u_{1}+\cdots+b_{j}u_{j}+c_{1}w_{1}+\cdots+c_{k}w_{k}=0,
$$  

where all the 𝑎’s, $b$ ’s, and $c$ ’s are scalars. We need to prove that all the $a$ ’s, $b$ ’s, and $c$ ’s equal 0. The equation above can be rewritten as  

$$
c_{1}w_{1}+\cdots+c_{k}w_{k}=-a_{1}v_{1}-\cdots-a_{m}v_{m}-b_{1}u_{1}-\cdots-b_{j}u_{j},
$$  

which shows that $c_{1}w_{1}+\cdots+c_{k}w_{k}\in V_{1}$ . All the $w$ ’s are in $V_{2}$ , so this implies that $c_{1}w_{1}+\cdots+c_{k}w_{k}\in V_{1}\cap V_{2}$ . Because $v_{1},...,v_{m}$ is a basis of $V_{1}\cap V_{2}$ , we have  

$$
c_{1}w_{1}+\cdots+c_{k}w_{k}=d_{1}v_{1}+\cdots+d_{m}v_{m}
$$  

for some scalars $d_{1},...,d_{m}$ . But $v_{1},...,v_{m},w_{1},...,w_{k}$ is linearly independent, so the last equation implies that all the $c$ ’s (and $d$ ’s) equal 0. Thus 2.45 becomes the equation  

$$
a_{1}v_{1}+\cdots+a_{m}v_{m}+b_{1}u_{1}+\cdots+b_{j}u_{j}=0.
$$  

Because the list $v_{1},...,v_{m},u_{1},...,u_{j}$ is linearly independent, this equation implies that all the $a$ ’s and $b$ ’s are 0, completing the proof.  

For $S$ a finite set, let #𝑆denote the number of elements of 𝑆. The table below compares finite sets with finite-dimensional vector spaces, showing the analogy between $\#S$ (for sets) and dim $V$ (for vector spaces), as well as the analogy between unions of subsets (in the context of sets) and sums of subspaces (in the context of vector spaces).  

<html><body><table><tr><td>sets</td><td>vector spaces</td></tr><tr><td>Sis afiniteset</td><td>V is afinite-dimensionalvector space</td></tr><tr><td>#S</td><td>dim V</td></tr><tr><td>for subsets S1, S2 of S, the union S1 U S2 is the smallest subset of S containing S1 and S2</td><td>for subspaces V1, V2 of V, the sum V + V2 is the smallest subspace of V containing V, and V2</td></tr><tr><td>#(S1 U S2) = #S1 + #S2-#(S1 ∩ S2)</td><td>dim(V + V2) = dim V + dim V2 - dim(V ∩ V2)</td></tr><tr><td>#(S1 U S2)= #S1 + #S2 S nS2 =</td><td>dim(V1 + V2) = dim V1 + dim V2 = V nV2 ={0}</td></tr><tr><td>S1 U ... U Sm is a disjoint union 1 #(S1 U ..·U Sm) = #S1 + .· + #Sm</td><td>V1 + ... + Vm is a direct sum 1 dim(V1 + .….+ Vm) = dim V1 + . + dim Vm</td></tr></table></body></html>  

The last row above focuses on the analogy between disjoint unions (for sets) and direct sums (for vector spaces). The proof of the result in the last box above will be given in 3.94.  

You should be able to find results about sets that correspond, via analogy, to the results about vector spaces in Exercises 12 through 18.  

## Exercises 2C  

1 Show that the subspaces of $\mathbf{R}^{2}$ are precisely $\{0\}$ , all lines in $\mathbf{R}^{2}$ containing the origin, and $\mathbf{R}^{2}.$  

2 Show that the subspaces of $\mathbf{R}^{3}$ are precisely $\{0\}$ , all lines in $\mathbf{R}^{3}$ containing the origin, all planes in $\mathbf{R}^{3}$ containing the origin, and $\mathbf{R}^{3}.$ .  

3 (a) Let $U=\left\{p\in\mathcal{P}_{4}(\mathbf{F}):p(6)=0\right\}$ . Find a basis of $U$ . (b) Extend the basis in (a) to a basis of ${\mathcal{P}}_{4}(\mathbf{F})$ . (c) Find a subspace $W$ of ${\mathcal{P}}_{4}(\mathbf{F})$ such that $\mathcal{P}_{4}(\mathbf{F})=U\oplus W.$  

4 (a) Let $U=\{p\in\mathcal{P}_{4}(\mathbb{R}):p^{\prime\prime}(6)=0\}$ . Find a basis of $U$ . (b) Extend the basis in (a) to a basis of ${\mathcal{P}}_{4}(\mathbf{R})$ . (c) Find a subspace $W$ of ${\mathcal{P}}_{4}(\mathbf{R})$ such that $\mathcal{P}_{4}(\mathbb{R})=U\oplus W.$  

5 (a) Let $U=\left\{p\in{\mathcal{P}}_{4}(\mathbf{F}):p(2)=p(5)\right\}$ . Find a basis of $U$ . (b) Extend the basis in (a) to a basis of ${\mathcal{P}}_{4}(\mathbf{F})$ . (c) Find a subspace $W$ of ${\mathcal{P}}_{4}(\mathbf{F})$ such that $\mathcal{P}_{4}(\mathbf{F})=U\oplus W.$  

6 (a) Let $U=\left\{p\in{\mathcal{P}}_{4}(\mathbf{F}):p(2)=p(5)=p(6)\right\}$ . Find a basis of $U$ . (b) Extend the basis in (a) to a basis of ${\mathcal{P}}_{4}(\mathbf{F})$ . (c) Find a subspace $W$ of ${\mathcal{P}}_{4}(\mathbf{F})$ such that $\mathcal{P}_{4}(\mathbf{F})=U\oplus W.$  

7 (a) Let $U=\left\{p\in\mathcal{P}_{4}(\mathbb{R}):\int_{-1}^{1}p=0\right\}$ . Find a basis of $U$ . (b) Extend the basis in (a) to a basis of ${\mathcal{P}}_{4}(\mathbf{R})$ . (c) Find a subspace $W$ of ${\mathcal{P}}_{4}(\mathbf{R})$ such that $\mathcal{P}_{4}(\mathbb{R})=U\oplus W.$  

8 Suppose $v_{1},...,v_{m}$ is linearly independent in $V$ and $w\in V.$ . Prove that  

$$
\dim\operatorname{span}(v_{1}+w,...,v_{m}+w)\geq m-1.
$$  

9 Suppose $m$ is a positive integer and $p_{0},p_{1},...,p_{m}\in\mathcal{P}(\mathbf{F})$ are such that each $p_{k}$ has degree $k$ . Prove that $p_{0},p_{1},...,p_{m}$ is a basis of ${\mathcal P}_{m}({\bf F})$ .  

10 Suppose $m$ is a positive integer. For $0\leq k\leq m$ , let  

$$
p_{k}(x)=x^{k}(1-x)^{m-k}.
$$  

Show that $p_{0},...,p_{m}$ is a basis of ${\mathcal P}_{m}({\bf F})$ .  

The basis in this exercise leads to what are called Bernstein polynomials. You can do a web search to learn how Bernstein polynomials are used to approximate continuous functions on [0, 1].  

11 Suppose $U$ and $W$ are both four-dimensional subspaces of $\mathbf{C}^{6}.$ . Prove that there exist two vectors in $U\cap W$ such that neither of these vectors is a scalar multiple of the other.  

12 Suppose that $U$ and $W$ are subspaces of $\mathbf{R}^{8}$ such that dim $U=3$ , dim $W=5$ , and $U+W=\mathbf{R}^{8}.$ . Prove that $\mathbf{R}^{8}=U\oplus W.$ .  

13 Suppose $U$ and $W$ are both five-dimensional subspaces of $\mathbf{R}^{9}.$ . Prove that $U\cap W\neq\{0\}$ .  

14 Suppose $V$ is a ten-dimensional vector space and $V_{1},V_{2},V_{3}$ are subspaces of $V$ with dim $V_{1}=\dim V_{2}=\dim V_{3}=7.$ Prove that $V_{1}\cap V_{2}\cap V_{3}\neq\{0\}$  

15 Suppose $V$ is finite-dimensional and $V_{1},V_{2},V_{3}$ are subspaces of $V$ with dim $V_{1}+\dim V_{2}+\dim V_{3}>2\dim V.$ Prove that $V_{1}\cap V_{2}\cap V_{3}\neq\{0\}$ .  

16 Suppose $V$ is finite-dimensional and $U$ is a subspace of $V$ with $U\neq V.$ Let $n\,=\,\dim V$ and $m\,=\,\dim U.$ . Prove that there exist $n-m$ subspaces of $V.$ each of dimension $n-1$ , whose intersection equals $U$ .  

17 Suppose that $V_{1},...,V_{m}$ are finite-dimensional subspaces of $V.$ . Prove that $V_{1}+\cdots+V_{m}$ is finite-dimensional and  

$$
\dim(V_{1}+\cdots+V_{m})\leq\dim V_{1}+\cdots+\dim V_{m}.
$$  

The inequality above is an equality if and only if $V_{1}+\cdots+V_{m}$ is a direct sum, as will be shown in 3.94.  

18 Suppose $V$ is finite-dimensional, with dim $V=n\geq1$ . Prove that there exist one-dimensional subspaces $V_{1},...,V_{n}$ of $V$ such that  

—Frankenstein, Mary Wollstonecraft Shelley  

$$
V=V_{1}\oplus\cdots\oplus V_{n}.
$$  

19 Explain why you might guess, motivated by analogy with the formula for the number of elements in the union of three finite sets, that if $V_{1},V_{2},V_{3}$ are subspaces of a finite-dimensional vector space, then  

$$
\begin{array}{l}{\dim(V_{1}+V_{2}+V_{3})}\\ {\qquad\qquad=\dim V_{1}+\dim V_{2}+\dim V_{3}}\\ {\qquad\qquad-\dim(V_{1}\cap V_{2})-\dim(V_{1}\cap V_{3})-\dim(V_{2}\cap V_{3})}\\ {\qquad\qquad+\dim(V_{1}\cap V_{2}\cap V_{3}).}\end{array}
$$  

Then either prove the formula above or give a counterexample.  

20 Prove that if $V_{1},V_{2}$ , and $V_{3}$ are subspaces of a finite-dimensional vector space, then  

$$
\begin{array}{l}{{\operatorname{lim}(V_{1}+V_{2}+V_{3})}}\\ {{\quad=\dim V_{1}+\dim V_{2}+\dim V_{3}}}\\ {{\quad-\dim(V_{1}\cap V_{2})+\dim(V_{1}\cap V_{3})+\dim(V_{2}\cap V_{3})}}\\ {{\quad-\dim((V_{1}\!+\!V_{2})\cap V_{3})+\dim((V_{1}\!+\!V_{3})\cap V_{2})+\dim((V_{2}\!+\!V_{3})\cap V_{1})}}\end{array}
$$  

The formula above may seem strange because the right side does not look like an integer.  

I at once gave up my former occupations, set down natural history and all its progeny as a deformed and abortive creation, and entertained the greatest disdain for a would-be science which could never even step within the threshold of real knowledge. In this mood I betook myself to the mathematics and the branches of study appertaining to that science as being built upon secure foundations, and so worthy of my consideration.  


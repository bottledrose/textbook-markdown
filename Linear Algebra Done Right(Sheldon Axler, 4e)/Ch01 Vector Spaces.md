# Ch01 Vector Spaces  

Linear algebra is the study of linear maps on finite-dimensional vector spaces. Eventually we will learn what all these terms mean. In this chapter we will define vector spaces and discuss their elementary properties.  

In linear algebra, better theorems and more insight emerge if complex numbers are investigated along with real numbers. Thus we will begin by introducing the complex numbers and their basic properties.  

We will generalize the examples of a plane and of ordinary space to ${\mathbf{R}}^{n}$ and $\mathbf{C}^{n}$ , which we then will generalize to the notion of a vector space. As we will see, a vector space is a set with operations of addition and scalar multiplication that satisfy natural algebraic properties.  

Then our next topic will be subspaces, which play a role for vector spaces analogous to the role played by subsets for sets. Finally, we will look at sums of subspaces (analogous to unions of subsets) and direct sums of subspaces (analogous to unions of disjoint sets).  

## Complex Numbers  

You should already be familiar with basic properties of the set $\mathbf{R}$ of real numbers. Complex numbers were invented so that we can take square roots of negative numbers. The idea is to assume we have a square root of $-1$ , denoted by $i,$ , that obeys the usual rules of arithmetic. Here are the formal definitions.  

## 1.1 definition: complex numbers, 𝐂  

• A complex number is an ordered pair $(a,b)$ , where $a,b\in\mathbb{R}$ , but we will write this as $a+b i$ .  

• The set of all complex numbers is denoted by $\mathbf{C}$ :  

$$
\mathbf{C}=\{a+b i:a,b\in\mathbf{R}\}.
$$  

Addition and multiplication on $\mathbf{C}$ are defined by  

$$
(a+b i)+(c+d i)=(a+c)+(b+d)i,
$$  

$$
(a+b i)(c+d i)=(a c-b d)+(a d+b c)i;
$$  

here $a,b,c,d\in\mathbb{R}$ .  

If $a\in\mathbb{R}$ , we identify $a+0i$ with the real number $a$ . Thus we think of $\mathbf{R}$ as a subset of 𝐂. We usually write $0+b i$ as just $b i$ , and we usually write $0+1i$ as just $i$ .  

To motivate the definition of complex The symbol 𝑖was first used to denote multiplication given above, pretend that $\sqrt{-1}$ by Leonhard Euler in 1777. we knew that $i^{2}=-1$ and then use the  

usual rules of arithmetic to derive the formula above for the product of two complex numbers. Then use that formula to verify that we indeed have  

$$
i^{2}=-1.
$$  

Do not memorize the formula for the product of two complex numbers—you can always rederive it by recalling that $i^{2}=-1$ and then using the usual rules of arithmetic (as given by 1.3). The next example illustrates this procedure.  

### 1.2 example: complex arithmetic  

The product $(2+3i)(4+5i)$ can be evaluated by applying the distributive and commutative properties from 1.3:  

$$
{\begin{array}{r l}&{(2+3i)(4+5i)=2\cdot(4+5i)+(3i)(4+5i)}\\ &{\qquad\qquad\qquad=2\cdot4+2\cdot5i+3i\cdot4+(3i)(5i)}\\ &{\qquad\qquad\qquad=8+10i+12i-15}\\ &{\qquad\qquad\qquad=-7+22i.}\end{array}}
$$  

Our first result states that complex addition and complex multiplication have the familiar properties that we expect.  

### 1.3 properties of complex arithmetic  

## commutativity  

$\alpha+\beta=\beta+\alpha$ and $\alpha\beta=\beta\alpha$ for all $\alpha,\beta\in\mathbf{C}$ .  

## associativity  

$(\alpha+\beta)+\lambda=\alpha+(\beta+\lambda)$ and $(\alpha\beta)\lambda=\alpha(\beta\lambda)$ for all $\alpha,\beta,\lambda\in\mathbf{C}$ .  

## identities  

$\lambda+0=\lambda$ and $\lambda1=\lambda$ for all $\lambda\in\mathbf{C}$ .  

## additive inverse  

For every $\alpha\in\mathbf{C}$ , there exists a unique $\beta\in\mathbf{C}$ such that $\alpha+\beta=0$ .  

## multiplicative inverse  

For every $\alpha\in\mathbf{C}$ with $\alpha\neq0$ , there exists a unique $\beta\in\mathbf{C}$ such that $\alpha\beta=1$ .  

## distributive property  

$$
\lambda(\alpha+\beta)=\lambda\alpha+\lambda\beta\;\mathrm{for\;all}\;\lambda,\alpha,\beta\in{\bf C}.
$$  

The properties above are proved using the familiar properties of real numbers and the definitions of complex addition and multiplication. The next example shows how commutativity of complex multiplication is proved. Proofs of the other properties above are left as exercises.  

### 1.4 example: commutativity of complex multiplication  

To show that $\alpha\beta=\beta\alpha$ for all $\alpha,\beta\in\mathbf{C}$ , suppose  

$$
\alpha=a+b i\quad{\mathrm{and}}\quad\beta=c+d i,
$$  

where $a,b,c,d\in\mathbb{R}$ . Then the definition of multiplication of complex numbers shows that  

$$
\begin{array}{c}{\alpha\beta=(a+b i)(c+d i)}\\ {=(a c-b d)+(a d+b c)i}\end{array}
$$  

and  

$$
\begin{array}{l}{\beta\alpha=(c+d i)(a+b i)}\\ {\qquad=(c a-d b)+(c b+d a)i.}\end{array}
$$  

The equations above and the commutativity of multiplication and addition of real numbers show that $\alpha\beta=\beta\alpha$ .  

Next, we define the additive and multiplicative inverses of complex numbers, and then use those inverses to define subtraction and division operations with complex numbers.  

### 1.5 definition: $-\alpha$ , subtraction, $1/\alpha$ , division  

Suppose $\alpha,\beta\in\mathbf{C}$ .  

• Let $-\alpha$ denote the additive inverse of $\alpha$ . Thus $-\alpha$ is the unique complex number such that  

$$
\alpha+(-\alpha)=0.
$$  

Subtraction on $\mathbf{C}$ is defined by  

$$
\beta-\alpha=\beta+(-\alpha).
$$  

For $\alpha\neq0$ , let $1/\alpha$ and $\frac{1}{\alpha}$ denote the multiplicative inverse of $\alpha$ . Thus $1/\alpha$ is the unique complex number such that  

$$
\alpha(1/\alpha)=1.
$$  

• For $\alpha\neq0$ , division by $\alpha$ is defined by  

$$
\beta/\alpha=\beta(1/\alpha).
$$  

So that we can conveniently make definitions and prove theorems that apply to both real and complex numbers, we adopt the following notation.  

### 1.6 notation: 𝐅  

Throughout this book, 𝐅stands for either 𝐑or 𝐂.  

Thus if we prove a theorem involving 𝐅, we will know that it holds when 𝐅is replaced with $\mathbf{R}$ and when 𝐅is replaced with 𝐂.  

The letter 𝐅is used because 𝐑and 𝐂 are examples of what are called fields.  

Elements of 𝐅are called scalars. The word “scalar” (which is just a fancy word for “number”) is often used when we want to emphasize that an object is a number, as opposed to a vector (vectors will be defined soon).  

For $\alpha\in\mathbf{F}$ and $m$ a positive integer, we define $\alpha^{m}$ to denote the product of $\alpha$ with itself $m$ times:  

for all $\alpha,\beta\in\mathbf{F}$ and all positive integers $m,n$ .  

$$
\alpha^{m}=\underbrace{\alpha\cdots\alpha}_{m{\mathrm{~times}}}.
$$  

This definition implies that  

$$
\left(\alpha^{m}\right)^{n}=\alpha^{m n}\quad{\mathrm{and}}\quad(\alpha\beta)^{m}=\alpha^{m}\beta^{m}
$$  

## Before defining ${\mathbf{R}}^{n}$ and $\mathbf{{C}}_{:}^{n}$ , we look at two important examples.  

### 1.7 example: 𝐑2 and 𝐑3  

• The set $\mathbf{R}^{2},$ which you can think of as a plane, is the set of all ordered pairs of real numbers:  

$$
\mathbf{R}^{2}=\{(x,y):x,y\in\mathbf{R}\}.
$$  

• The set $\mathbf{R}^{3},$ , which you can think of as ordinary space, is the set of all ordered triples of real numbers:  

$$
\mathbf{R}^{3}=\{(x,y,z):x,y,z\in\mathbf{R}\}.
$$  

To generalize $\mathbf{R}^{2}$ and $\mathbf{R}^{3}$ to higher dimensions, we first need to discuss the concept of lists.  

### 1.8 definition: list, length  

Suppose $n$ is a nonnegative integer. A list of length $n$ is an ordered collection of $n$ elements (which might be numbers, other lists, or more abstract objects). Two lists are equal if and only if they have the same length and the same elements in the same order.  

Lists are often written as elements separated by commas and surrounded by parentheses. Thus a list of length two is  

Many mathematicians call a list of length 𝑛an 𝑛-tuple.  

an ordered pair that might be written as $(a,b)$ . A list of length three is an ordered triple that might be written as $(x,y,z)$ . A list of length $n$ might look like this:  

$$
(z_{1},...,z_{n}).
$$  

Sometimes we will use the word list without specifying its length. Remember, however, that by definition each list has a finite length that is a nonnegative integer. Thus an object that looks like $(x_{1},x_{2},\dots)$ , which might be said to have infinite length, is not a list.  

A list of length 0 looks like this: ( ). We consider such an object to be a list so that some of our theorems will not have trivial exceptions.  

Lists differ from sets in two ways: in lists, order matters and repetitions have meaning; in sets, order and repetitions are irrelevant.  

### 1.9 example: lists versus sets  

• The lists (3, 5) and (5, 3) are not equal, but the sets $\{3,5\}$ and $\{5,3\}$ are equal.  

• The lists (4, 4) and (4, 4, 4) are not equal (they do not have the same length), although the sets $\{4,4\}$ and $\{4,4,4\}$ both equal the set $\lbrace4\rbrace$ .  

To define the higher-dimensional analogues of $\mathbf{R}^{2}$ and $\mathbf{R}^{3},$ , we will simply replace 𝐑with 𝐅(which equals $\mathbf{R}$ or $\mathbf{C}$ ) and replace the 2 or 3 with an arbitrary positive integer.  

### 1.10 notation: 𝑛  

Fix a positive integer $n$ for the rest of this chapter.  

1.11 definition: $\mathbf{F}^{n}$ , coordinate  

$\mathbf{F}^{n}$ is the set of all lists of length $n$ of elements of 𝐅:  

$$
{\bf F}^{n}=\{(x_{1},...,x_{n}):x_{k}\in{\bf F}\;\mathrm{for}\,k=1,...,n\}.
$$  

For $(x_{1},...,x_{n})\in\mathbf{F}^{n}$ and $k\in\{1,...,n\}$ , we say that $x_{k}$ is the $k^{\mathrm{th}}$ coordinate of $(x_{1},...,x_{n})$ .  

If $\mathbf{F}=\mathbf{R}$ and $n$ equals 2 or 3, then the definition above of $\mathbf{F}^{n}$ agrees with our previous notions of $\mathbf{R}^{2}$ and $\mathbf{R}^{3}.$ .  

### 1.12 example: 𝐂4  

${\mathbf{C}}^{4}$ is the set of all lists of four complex numbers:  

$$
{\bf C}^{4}=\{(z_{1},z_{2},z_{3},z_{4}):z_{1},z_{2},z_{3},z_{4}\in{\bf C}\}.
$$  

If $n\geq4$ , we cannot visualize $\mathbf{R}^{n}$ as a physical object. Similarly, $\boldsymbol{C}^{1}$ can be thought of as a plane, but for $n\geq2$ , the human brain cannot provide a full image of $\mathbf{C}^{n}.$ However, even if $n$ is large, we can perform algebraic manipulations in $\mathbf{F}^{n}$ as easily as in $\mathbf{R}^{2}$ or $\mathbf{R}^{3}.$ . For example, addition in $\mathbf{F}^{n}$ is defined as follows.  

Read Flatland: A Romance of Many Dimensions, by Edwin A. Abbott, for an amusing account of how $\mathbf{R}^{3}$ would be perceived by creatures living in $\mathbf{R}^{2}.$ This novel, published in 1884, may help you imagine a physical space of four or more dimensions.  

## 1.13 definition: addition in $\mathbf{F}^{n}$  

Addition in $\mathbf{F}^{n}$ is defined by adding corresponding coordinates:  

$$
(x_{1},...,x_{n})+(y_{1},...,y_{n})=(x_{1}+y_{1},...,x_{n}+y_{n}).
$$  

Often the mathematics of $\mathbf{F}^{n}$ becomes cleaner if we use a single letter to denote a list of $n$ numbers, without explicitly writing the coordinates. For example, the next result is stated with $x$ and $y$ in $\mathbf{F}^{n}$ even though the proof requires the more cumbersome notation of $(x_{1},...,x_{n})$ and $(y_{1},...,y_{n})$ .  

## 1.14 commutativity of addition in $\mathbf{F}^{n}$  

If $x,y\in\mathbf{F}_{:}^{n}$ , then $x+y=y+x$ .  

Proof Suppose $x=(x_{1},...,x_{n})\in\mathbf{F}^{n}$ and $y=(y_{1},...,y_{n})\in\mathbf{F}^{n}$ . Then  

$$
\begin{array}{l}{{x+y=(x_{1},...,x_{n})+(y_{1},...,y_{n})}}\\ {{\ \ \ \ \ =(x_{1}+y_{1},...,x_{n}+y_{n})}}\\ {{\ \ \ \ =(y_{1}+x_{1},...,y_{n}+x_{n})}}\\ {{\ \ \ \ =(y_{1},...,y_{n})+(x_{1},...,x_{n})}}\\ {{\ \ \ \ =y+x,}}\end{array}
$$  

where the second and fourth equalities above hold because of the definition of addition in $\mathbf{F}^{n}$ and the third equality holds because of the usual commutativity of addition in 𝐅.  

The symbol means “end of proof ”.  

If a single letter is used to denote an element of $\mathbf{F}_{\mathrm{~}}^{n}$ , then the same letter with appropriate subscripts is often used when  

coordinates must be displayed. For example, if $x\:\in\:\mathbf{F}_{:}^{n}$ , then letting $x$ equal $(x_{1},...,x_{n})$ is good notation, as shown in the proof above. Even better, work with just $x$ and avoid explicit coordinates when possible.  

## 1.15 notation: 0  

Let 0 denote the list of length $n$ whose coordinates are all 0:  

$$
0=(0,...,0).
$$  

Here we are using the symbol 0 in two different ways—on the left side of the equation above, the symbol 0 denotes a list of length $n$ , which is an element of $\mathbf{F}^{n}.$ , whereas on the right side, each 0 denotes a number. This potentially confusing practice actually causes no problems because the context should always make clear which 0 is intended.  

### 1.16 example: context determines which 0 is intended  

Consider the statement that 0 is an additive identity for $\mathbf{F}^{n}$ :  

$$
x+0=x\quad{\mathrm{for~all~}}x\in\mathbf{F}^{n}.
$$  

Here the 0 above is the list defined in 1.15, not the number 0, because we have not defined the sum of an element of $\mathbf{F}^{n}$ (namely, $x$ ) and the number 0.  

A picture can aid our intuition. We will draw pictures in $\mathbf{R}^{2}$ because we can sketch this space on two-dimensional surfaces such as paper and computer screens. A typical element of $\mathbf{R}^{2}$ is a point $v=(a,b)$ . Sometimes we think of $v$ not as a point but as an arrow starting at the origin and ending at $(a,b)$ , as shown here. When we think of an element of $\mathbf{R}^{2}$ as an arrow, we refer to it as a vector.  

When we think of vectors in $\mathbf{R}^{2}$ as arrows, we can move an arrow parallel to itself (not changing its length or direction) and still think of it as the same vector. With that viewpoint, you will often gain better understanding by dispensing with the coordinate axes and the explicit coordinates and just thinking of the vector, as shown in the figure here. The two arrows shown here have the same length and same direction, so we think of them as the same vector.  

![](images/3032abb735668ad1a01d4fbbae3f6c1b612835c94854be83a0d717d898744cc6.jpg)  
Elements of $\mathbf{R}^{2}$ can be thought of as points or as vectors.  

![](images/832a020b081c651213111639972846b766b50bb34ae6d228cf198f4860450a37.jpg)  
A vector.  

Whenever we use pictures in $\mathbf{R}^{2}$ or use the somewhat vague language of points and vectors, remember that these are just aids to our understanding, not substitutes for the actual mathematics that we will develop. Although we cannot draw good pictures in high-dimensional spaces, the elements of these spaces are as rigorously defined as elements of $\mathbf{R}^{2}.$ .  

Mathematical models of the economy can have thousands of variables, say $x_{1},...,x_{5000}$ , which means that we must work in $\mathbf{R}^{5000}$ . Such a space cannot be dealt with geometrically. However, the algebraic approach works well. Thus our subject is called linear algebra.  

For example, $\left(2,-3,17,\pi,{\sqrt{2}}\right)$ is an element of $\mathbf{R}^{5},$ and we may casually refer to it as a point in $\mathbf{R}^{5}$ or a vector in $\mathbf{R}^{5}$ without worrying about whether the geometry of $\mathbf{R}^{5}$ has any physical meaning.  

Recall that we defined the sum of two elements of $\mathbf{F}^{n}$ to be the element of $\mathbf{F}^{n}$ obtained by adding corresponding coordinates; see 1.13. As we will now see, addition has a simple geometric interpretation in the special case of $\mathbf{R}^{2}$ .  

Suppose we have two vectors $u$ and $v$ in $\mathbf{R}^{2}$ that we want to add. Move the vector $v$ parallel to itself so that its initial point coincides with the end point of the vector $u$ , as shown here. The sum $u+v$ then equals the vector whose initial point equals the initial point of $u$ and whose end point equals the end point of the vector $v$ , as shown here.  

![](images/83531c4f09be18ff1573acd625e9ca34676e1b65b622cf5d8b030f9be806cfbe.jpg)  
The sum of two vectors.  

In the next definition, the 0 on the right side of the displayed equation is the list $0\in\mathbf{F}^{n}$ .  

For $x\in\mathbf{F}^{n};$ , the additive inverse of $x$ , denoted by $-x$ , is the vector $-x\in\mathbf{F}^{n}$ such that  

$$
x+(-x)=0.
$$  

Thus if $\boldsymbol{x}=(x_{1},...,x_{n})$ , then $-x=(-x_{1},...,-x_{n}).$  

The additive inverse of a vector in $\mathbf{R}^{2}$ is the vector with the same length but pointing in the opposite direction. The figure here illustrates this way of thinking about the additive inverse in $\mathbf{R}^{2}.$ As you can see, the vector labeled $-x$ has the same length as the vector labeled $x$ but points in the opposite direction.  

![](images/dde4c7b31b76cfd377352907d8a83d4feea8205d017ce31207fb7f16f00b2899.jpg)  
A vector and its additive inverse.  

Having dealt with addition in $\mathbf{F}^{n}$ , we now turn to multiplication. We could define a multiplication in $\mathbf{F}^{n}$ in a similar fashion, starting with two elements of $\mathbf{F}^{n}$ and getting another element of $\mathbf{F}^{n}$ by multiplying corresponding coordinates. Experience shows that this definition is not useful for our purposes. Another type of multiplication, called scalar multiplication, will be central to our subject. Specifically, we need to define what it means to multiply an element of $\mathbf{F}^{n}$ by an element of 𝐅.  

## 1.18 definition: scalar multiplication in $\mathbf{F}^{n}$  

The product of a number $\lambda$ and a vector in $\mathbf{F}^{n}$ is computed by multiplying each coordinate of the vector by $\lambda$ :  

$$
\lambda(x_{1},...,x_{n})=(\lambda x_{1},...,\lambda x_{n});
$$  

here $\lambda\in\mathbf{F}$ and $(x_{1},...,x_{n})\in\mathbf{F}_{\cdot}^{n}$ .  

Scalar multiplication has a nice geometric interpretation in $\mathbf{R}^{2}.$ If $\lambda>0$ and $\boldsymbol{x}\in\mathbb{R}^{2},$ then $\lambda x$ is the vector that points in the same direction as $x$ and whose length is $\lambda$ times the length of $x$ . In other words, to get $\lambda x$ , we shrink or stretch $x$ by a factor of $\lambda$ , depending on whether $\lambda<1$ or $\lambda>1$ .  

If $\lambda<0$ and $\boldsymbol{x}\in\mathbb{R}^{2},$ , then $\lambda x$ is the vector that points in the direction opposite to that of $x$ and whose length is $|\lambda|$ times the length of $x$ , as shown here.  

Scalar multiplication in $\mathbf{F}^{n}$ multiplies together a scalar and a vector, getting a vector. In contrast, the dot product in $\mathbf{R}^{2}$ or $\mathbf{R}^{3}$ multiplies together two vectors and gets a scalar. Generalizations of the dot product will become important in Chapter 6.  

![](images/6d0b1ff5db8555285f6027579691955ce63b0f05871084e8dacfc9d0ebd490cb.jpg)  

Scalar multiplication.  

A field is a set containing at least two distinct elements called 0 and 1, along with operations of addition and multiplication satisfying all properties listed in 1.3. Thus $\mathbf{R}$ and 𝐂are fields, as is the set of rational numbers along with the usual operations of addition and multiplication. Another example of a field is the set $\{0,1\}$ with the usual operations of addition and multiplication except that $1+1$ is defined to equal 0.  

In this book we will not deal with fields other than 𝐑and 𝐂. However, many of the definitions, theorems, and proofs in linear algebra that work for the fields $\mathbf{R}$ and 𝐂also work without change for arbitrary fields. If you prefer to do so, throughout much of this book (except for Chapters 6 and 7, which deal with inner product spaces) you can think of 𝐅as denoting an arbitrary field instead of $\mathbf{R}$ or 𝐂. For results (except in the inner product chapters) that have as a hypothesis that 𝐅is $\mathbf{C}$ , you can probably replace that hypothesis with the hypothesis that 𝐅 is an algebraically closed field, which means that every nonconstant polynomial with coefficients in 𝐅has a zero. A few results, such as Exercise 13 in Section 1C, require the hypothesis on $\mathbf{F}$ that $1+1\neq0$ .  

## Exercises 1A  

1 Show that $\alpha+\beta=\beta+\alpha$ for all $\alpha,\beta\in\mathbf{C}$ .  

2 Show that $(\alpha+\beta)+\lambda=\alpha+(\beta+\lambda)$ for all $\alpha,\beta,\lambda\in\mathbf{C}$ .   
3 Show that $(\alpha\beta)\lambda=\alpha(\beta\lambda)$ for all $\alpha,\beta,\lambda\in\mathbf{C}$ .   
4 Show that $\lambda(\alpha+\beta)=\lambda\alpha+\lambda\beta\;\mathrm{for\;all}\;\lambda,\alpha,\beta\in{\bf C}.$   
5 Show that for every $\alpha\in\mathbf{C}$ , there exists a unique $\beta\in\mathbf{C}$ such that $\alpha+\beta=0$ .   
6 Show that for every $\alpha\in\mathbf{C}$ with $\alpha\neq0$ , there exists a unique $\beta\in\mathbf{C}$ such   
that $\alpha\beta=1$ .  

7 Show that  

$$
\frac{-1+{\sqrt{3}}i}{2}
$$  

is a cube root of 1 (meaning that its cube equals 1).  

8 Find two distinct square roots of $i$  

9 Find $\boldsymbol{x}\in\mathbb{R}^{4}$ such that  

$$
(4,-3,1,7)+2x=(5,9,-6,8).
$$  

10 Explain why there does not exist $\lambda\in\mathbf{C}$ such that  

$$
\lambda(2-3i,5+4i,-6+7i)=(12-5i,7+22i,-32-9i).
$$  

11 Show that $(x+y)+z=x+(y+z)$ for all $x,y,z\in\mathbf{F}^{n}$ .   
12 Show that $(a b)x=a(b x)$ for all $x\in\mathbf{F}^{n}$ and all $a,b\in\mathbf{F}$ .   
13 Show that $1x=x$ for all $x\in\mathbf{F}^{n}.$ .   
14 Show that $\lambda(x+y)=\lambda x+\lambda y$ for all $\lambda\in\mathbf{F}$ and all $x,y\in\mathbf{F}^{n}$ .   
15 Show that $(a+b)x=a x+b x$ for all $a,b\in\mathbf{F}$ and all $x\in\mathbf{F}^{n}$ .  

The motivation for the definition of a vector space comes from properties of addition and scalar multiplication in $\mathbf{F}^{n}$ : Addition is commutative, associative, and has an identity. Every element has an additive inverse. Scalar multiplication is associative. Scalar multiplication by 1 acts as expected. Addition and scalar multiplication are connected by distributive properties.  

We will define a vector space to be a set $V$ with an addition and a scalar multiplication on $V$ that satisfy the properties in the paragraph above.  

### 1.19 definition: addition, scalar multiplication  

• An addition on a set $V$ is a function that assigns an element $u+v\in V$ to each pair of elements $u,v\in V.$   
• A scalar multiplication on a set $V$ is a function that assigns an element $\lambda v\in V$ to each $\lambda\in\mathbf{F}$ and each $v\in V.$  

Now we are ready to give the formal definition of a vector space.  

### 1.20 definition: vector space  

A vector space is a set $V$ along with an addition on $V$ and a scalar multiplication on $V$ such that the following properties hold.  

## commutativity  

$u+v=v+u$ for all $u,v\in V.$  

## associativity  

$(u+v)+w=u+(v+w)$ and $(a b)v=a(b v)$ for all $u,v,w\in V$ and for all $a,b\in\mathbf{F}$ .  

## additive identity  

There exists an element $0\in V$ such that $v+0=v$ for all $v\in V.$  

## additive inverse  

For every $v\in V,$ there exists $w\in V$ such that $v+w=0$ .  

multiplicative identity $1v=v$ for all $v\in V.$ .  

## distributive properties  

$a(u+v)=a u+a v$ and $(a+b)v=a v+b v$ for all $a,b\in\mathbf{F}$ and all $u,v\in V.$  

The following geometric language sometimes aids our intuition.  

## 1.21 definition: vector, point  

Elements of a vector space are called vectors or points.  

The scalar multiplication in a vector space depends on 𝐅. Thus when we need to be precise, we will say that $V$ is a vector space over 𝐅instead of saying simply that $V$ is a vector space. For example, $\mathbf{R}^{n}$ is a vector space over $\mathbf{R}$ , and $\mathbf{C}^{n}$ is a vector space over 𝐂.  

## 1.22 definition: real vector space, complex vector space  

• A vector space over $\mathbf{R}$ is called a real vector space.   
• A vector space over 𝐂is called a complex vector space.  

Usually the choice of $\mathbf{F}$ is either clear from the context or irrelevant. Thus we often assume that 𝐅is lurking in the background without specifically mentioning it.  

With the usual operations of addition The simplest vector space is {0}, which and scalar multiplication, $\mathbf{F}^{n}$ is a vector contains only one point. space over 𝐅, as you should verify. The example of $\mathbf{F}^{n}$ motivated our definition of vector space.  

## 1.2 3 example: 𝐅∞  

$\mathbf{F}^{\infty}$ is defined to be the set of all sequences of elements of 𝐅:  

$$
\mathbf{F}^{\infty}=\{(x_{1},x_{2},\ldots):x_{k}\in\mathbf{F}{\mathrm{~for}}\,k=1,2,\ldots\}.
$$  

Addition and scalar multiplication on $\mathbf{F}^{\infty}$ are defined as expected:  

$$
\begin{array}{c}{{(x_{1},x_{2},\ldots)+(y_{1},y_{2},\ldots)=(x_{1}+y_{1},x_{2}+y_{2},\dots),}}\\ {{\lambda(x_{1},x_{2},\ldots)=(\lambda x_{1},\lambda x_{2},\ldots).}}\end{array}
$$  

With these definitions, $\mathbf{F}^{\infty}$ becomes a vector space over $\mathbf{F}.$ , as you should verify.   
The additive identity in this vector space is the sequence of all $\mathrm{0\,\dot{s}}$ .  

Our next example of a vector space involves a set of functions.  

## 1.24 notation: 𝐅𝑆  

$\bullet$ If $S$ is a set, then $\mathbf{F}^{S}$ denotes the set of functions from $S$ to $\mathbf{F}$ .  

$\bullet$ For $f,g\in\mathbf{F}^{S},$ , the sum $f+g\in\mathbf{F}^{S}$ is the function defined by  

$$
(f\!+g)(x)=f(x)+g(x)
$$  

for all $x\in S$ .  

• For $\lambda\in\mathbf{F}$ and $f\in\mathbf{F}^{S}$ , the product $\lambda f\in\mathbf{F}^{S}$ is the function defined by  

$$
(\lambda f)(x)=\lambda f(x)
$$  

for all $x\in S$ .  

As an example of the notation above, if $S$ is the interval [0, 1] and $\mathbf{F}=\mathbf{R}$ , then $\mathbf{R}^{[0,1]}$ is the set of real-valued functions on the interval [0, 1]. You should verify all three bullet points in the next example.  

1.25 example: $\mathbf{F}^{S}$ is a vector space  

• If $S$ is a nonempty set, then $\mathbf{F}^{S}$ (with the operations of addition and scalar multiplication as defined above) is a vector space over 𝐅.  

• The additive identity of $\mathbf{F}^{S}$ is the function $0:S\rightarrow\mathbf{F}$ defined by  

$$
0(x)=0
$$  

for all $x\in S$ .  

• For $f\in\mathbf{F}^{S},$ , the additive inverse of $f$ is the function $-f\colon S\to\mathbf{F}$ defined by  

$$
(-f)(x)=-f(x)
$$  

for all $x\in S$ .  

The vector space $\mathbf{F}^{n}$ is a special case of the vector space $\mathbf{F}^{S}$ because each $(x_{1},...,x_{n})\,\in\,{\bf F}^{n}$ can be thought of as a function $x$ from the set $\{1,2,...,n\}$ to $\mathbf{F}$ by writing $x(k)$ instead of $x_{k}$ for the $k^{\mathrm{th}}$ coordinate of $(x_{1},...,x_{n})$ . In other words,  

The elements of the vector space $\mathbf{R}^{[0,1]}$ are real-valued functions on [0, 1], not lists. In general, a vector space is an abstract entity whose elements might be lists, functions, or weird objects.  

we can think of $\mathbf{F}^{n}$ as $\mathbf{F}^{\{1,2,...,n\}}.$ . Similarly, we can think of $\mathbf{F}^{\infty}$ as $\mathbf{F}^{\{1,2,\dots\}}$ .  

Soon we will see further examples of vector spaces, but first we need to develop some of the elementary properties of vector spaces.  

The definition of a vector space requires it to have an additive identity. The next result states that this identity is unique.  

1.26 unique additive identity  

A vector space has a unique additive identity.  

Proof Suppose 0 and $0^{\prime}$ are both additive identities for some vector space $V.$ Then  

$$
0^{\prime}=0^{\prime}+0=0+0^{\prime}=0,
$$  

where the first equality holds because 0 is an additive identity, the second equality comes from commutativity, and the third equality holds because $0^{\prime}$ is an additive identity. Thus $0^{\prime}=0$ , proving that $V$ has only one additive identity.  

Each element $v$ in a vector space has an additive inverse, an element $w$ in the vector space such that $v+w=0$ . The next result shows that each element in a vector space has only one additive inverse.  

Every element in a vector space has a unique additive inverse.  

Proof Suppose $V$ is a vector space. Let $v\in V.$ Suppose $w$ and $w^{\prime}$ are additive inverses of $v$ . Then  

$$
w=w+0=w+(v+w^{\prime})=(w+v)+w^{\prime}=0+w^{\prime}=w^{\prime}.
$$  

Thus $w=w^{\prime}$ , as desired.  

Because additive inverses are unique, the following notation now makes sense.  

1.28 notation: −𝑣, 𝑤−𝑣  

Let $v,w\in V.$ Then $-v$ denotes the additive inverse of $v$ ; $w-v$ is defined to be $w+(-v)$ .  

Almost all results in this book involve some vector space. To avoid having to restate frequently that $V$ is a vector space, we now make the necessary declaration once and for all.  

## 1.29 notation:  

For the rest of this book, $V$ denotes a vector space over 𝐅.  

In the next result, 0 denotes a scalar (the number $0\in\mathbf{F}$ ) on the left side of the equation and a vector (the additive identity of $V$ ) on the right side of the equation.  

1.30 the number 0 times a vector  

$0v=0$ for every $v\in V.$ .  

Proof For $v\in V,$ , we have  

$$
0v=(0+0)v=0v+0v.
$$  

Adding the additive inverse of $_{0v}$ to both sides of the equation above gives $0=0v$ , as desired.  

In the next result, 0 denotes the additive identity of $V.$ . Although their proofs  

The result in 1.30 involves the additive identity of 𝑉and scalar multiplication. The only part of the definition of a vector space that connects vector addition and scalar multiplication is the distributive property. Thus the distributive property must be used in the proof of 1.30.  

are similar, 1.30 and 1.31 are not identical. More precisely, 1.30 states that the product of the scalar 0 and any vector equals the vector 0, whereas 1.31 states that the product of any scalar and the vector 0 equals the vector 0.  

1.31 a number times the vector 0 $a0=0$ for every $a\in\mathbf{F}$ .  

Proof For $a\in\mathbf{F}$ , we have  

$$
a0=a(0+0)=a0+a0.
$$  

Adding the additive inverse of $a0$ to both sides of the equation above gives $0=a0$ , as desired.  

Now we show that if an element of $V$ is multiplied by the scalar $-1$ , then the result is the additive inverse of the element of $V.$ .  

1.32 the number $-1$ times a vector  

$(-1)v=-v$ for every $v\in V.$  

Proof For $v\in V,$ , we have  

$$
v+(-1)v=1v+(-1)v=\big(1+(-1)\big)v=0v=0.
$$  

This equation says that $(-1)v$ , when added to $v$ , gives 0. Thus $(-1)v$ is the additive inverse of $v$ , as desired.  

## Exercises 1B  

1 Prove that $-(-v)=v$ for every $v\in V.$ .  

2 Suppose $a\in\mathbf{F}$ , $v\in V,$ and $a v=0$ . Prove that $a=0$ or $v=0$ .  

3 Suppose $v,w\,\in\,V.$ Explain why there exists a unique $x\in V$ such that $v+3x=w$ .  

4 The empty set is not a vector space. The empty set fails to satisfy only one of the requirements listed in the definition of a vector space (1.20). Which one?  

5 Show that in the definition of a vector space (1.20), the additive inverse condition can be replaced with the condition that  

$$
0v=0{\mathrm{~for~all~}}v\in V.
$$  

Here the 0 on the left side is the number 0, and the 0 on the right side is the additive identity of $V.$ .  

The phrase a “condition can be replaced” in a definition means that the collection of objects satisfying the definition is unchanged if the original condition is replaced with the new condition.  

6 Let $\infty$ and $-\infty$ denote two distinct objects, neither of which is in $\mathbf{R}$ . Define an addition and scalar multiplication on $\mathbf{R}\cup\{\infty,-\infty\}$ as you could guess from the notation. Specifically, the sum and product of two real numbers is as usual, and for $t\in\mathbb{R}$ define  

$$
t\infty={\left\{\begin{array}{l l}{-\infty}&{{\mathrm{if~}}t<0,}\\ {0}&{{\mathrm{if~}}t=0,}\\ {\infty}&{{\mathrm{if~}}t>0,}\end{array}\right.}\quad t(-\infty)={\left\{\begin{array}{l l}{\infty}&{{\mathrm{if~}}t<0,}\\ {0}&{{\mathrm{if~}}t=0,}\\ {-\infty}&{{\mathrm{if~}}t>0,}\end{array}\right.}
$$  

and  

$$
\begin{array}{c}{{t+\infty=\infty+t=\infty+\infty=\infty,}}\\ {{t+(-\infty)=(-\infty)+t=(-\infty)+(-\infty)=-\infty,}}\\ {{\infty+(-\infty)=(-\infty)+\infty=0.}}\end{array}
$$  

With these operations of addition and scalar multiplication, is $\mathbf{R}\cup\{\infty,-\infty\}$ a vector space over 𝐑? Explain.  

7 Suppose $S$ is a nonempty set. Let $V^{S}$ denote the set of functions from $S$ to $V_{\cdot}$ . Define a natural addition and scalar multiplication on $V^{S},$ and show that $V^{S}$ is a vector space with these definitions.  

8 Suppose $V$ is a real vector space.  

The complexification of $V,$ , denoted by $V_{\mathbf{C}}$ , equals $V\times V.$ An element of $V_{C}$ is an ordered pair $(u,v)$ , where $u,v\in V,$ , but we write this as $u+i v$ . Addition on $V_{C}$ is defined by  

$$
(u_{1}+i v_{1})+(u_{2}+i v_{2})=(u_{1}+u_{2})+i(v_{1}+v_{2})
$$  

for all $u_{1},v_{1},u_{2},v_{2}\in V.$  

Complex scalar multiplication on $V_{\mathbf{C}}$ is defined by  

$$
(a+b i)(u+i v)=(a u-b v)+i(a v+b u)
$$  

for all $a,b\in\mathbf{R}$ and all $u,v\in V.$ .  

Prove that with the definitions of addition and scalar multiplication as above, $V_{C}$ is a complex vector space.  

Think of $V$ as a subset of $V_{\mathbf{C}}$ by identifying $u\in V$ with $u+i0$ . The construction of $V_{\mathbf{C}}$ from $V$ can then be thought of as generalizing the construction of $\mathbf{C}^{n}$ from $\mathbf{R}^{n}.$  

By considering subspaces, we can greatly expand our examples of vector spaces.  

## 1.33 definition: subspace  

A subset $U$ of $V$ is called a subspace of $V$ if $U$ is also a vector space with the same additive identity, addition, and scalar multiplication as on $V.$  

The next result gives the easiest way to check whether a subset of a vector space is a subspace.  

Some people use the terminology linear subspace, which means the same as subspace.  

1.34 conditions for a subspace  

A subset $U$ of $V$ is a subspace of $V$ if and only if $U$ satisfies the following three conditions.  

additive identity $0\in U$ .  

closed under addition $u,w\in U$ implies $u+w\in U$ .  

closed under scalar multiplication $a\in\mathbf{F}$ and $u\in U$ implies $a u\in U$ .  

Proof If $U$ is a subspace of $V_{v}$ , then $U$ satisfies the three conditions above by the definition of vector space.  

Conversely, suppose $U$ satisfies the three conditions above. The first condition ensures that the additive identity of $V$ is in $U$ . The second condition ensures that addition makes sense on $U$ . The third condition ensures that scalar multiplication makes sense on $U$ .  

The additive identity condition above could be replaced with the condition that $U$ is nonempty (because then taking $u~\in~U$ and multiplying it by 0 would imply that $0\,\in\,U$ ). However, if a subset $U$ of $V$ is indeed a subspace, then usually the quickest way to show that $U$ is nonempty is to show that $0\in U.$ .  

If $u\in U$ , then $-u$ [which equals $(-1)u$ by 1.32] is also in $U$ by the third condition above. Hence every element of $U$ has an additive inverse in $U$ .  

The other parts of the definition of a vector space, such as associativity and commutativity, are automatically satisfied for $U$ because they hold on the larger space $V.$ . Thus $U$ is a vector space and hence is a subspace of $V.$ .  

The three conditions in the result above usually enable us to determine quickly whether a given subset of $V$ is a subspace of $V.$ You should verify all assertions in the next example.  

## (a) If $b\in\mathbf{F}$ , then  

$$
\{(x_{1},x_{2},x_{3},x_{4})\in\mathbf{F}^{4}:x_{3}=5x_{4}+b\}
$$  

is a subspace of $\mathbf{F}^{4}$ if and only if $b=0$ .  

(b) The set of continuous real-valued functions on the interval [0, 1] is a subspace of 𝐑[0,1].   
(c) The set of differentiable real-valued functions on $\mathbf{R}$ is a subspace of $\mathbf{R}^{\mathbb{R}}$ .   
(d) The set of differentiable real-valued functions $f$ on the interval $(0,3)$ such that $f^{\prime}(2)=b$ is a subspace of $\mathbf{R}^{(0,3)}$ if and only if $b=0$ .  

(e) The set of all sequences of complex numbers with limit 0 is a subspace of $\mathbf{C}^{\infty},$ .  

Verifying some of the items above shows the linear structure underlying parts of calculus. For example, (b) above requires the result that the sum of two continuous functions is continuous. As another example, (d) above requires the result that for a constant $c$ , the derivative of $c f$ equals $c$ times the derivative of $f.$ .  

The set {0} is the smallest subspace of $V,$ and $V$ itself is the largest subspace of $V.$ The empty set is not a subspace of $V$ because a subspace must be a vector space and hence must contain at least one element, namely, an additive identity.  

The subspaces of $\mathbf{R}^{2}$ are precisely $\{0\}$ , all lines in $\mathbf{R}^{2}$ containing the origin, and $\mathbf{R}^{2}.$ . The subspaces of $\mathbf{R}^{3}$ are precisely $\{0\}$ , all lines in $\mathbf{R}^{3}$ containing the origin, all planes in $\mathbf{R}^{3}$ containing the origin, and $\mathbf{R}^{3}.$ To prove that all these objects are indeed subspaces is straightforward—the hard part is to show that they are the only subspaces of $\mathbf{R}^{2}$ and $\mathbf{R}^{3}.$ . That task will be easier after we introduce some additional tools in the next chapter.  

## Sums of Subspaces  

When dealing with vector spaces, we are usually interested only in subspaces, as opposed to arbitrary subsets. The notion of the sum of subspaces will be useful.  

## 1.36 definition: sum of subspaces  

The union of subspaces is rarely a subspace (see Exercise 12), which is why we usually work with sums rather than unions.  

Suppose $V_{1},...,V_{m}$ are subspaces of $V.$ . The sum of $V_{1},...,V_{m}$ , denoted by $V_{1}+\cdots+V_{m}$ , is the set of all possible sums of elements of $V_{1},...,V_{m}$ . More precisely,  

## 1.37 example: a sum of subspaces of $\mathbf{F}^{3}$  

Suppose $U$ is the set of all elements of $\mathbf{F}^{3}$ whose second and third coordinates equal 0, and $W$ is the set of all elements of $\mathbf{F}^{3}$ whose first and third coordinates equal 0:  

$$
U=\big\{(x,0,0)\in\mathbf{F}^{3}:x\in\mathbf{F}\big\}\quad\mathrm{and}\quad W=\big\{(0,y,0)\in\mathbf{F}^{3}:y\in\mathbf{F}\big\}.
$$  

Then  

$$
U+W=\{(x,y,0)\in\mathbf{F}^{3}:x,y\in\mathbf{F}\},
$$  

as you should verify.  

1.38 example: a sum of subspaces of $\mathbf{F}^{4}$  

Suppose  

$$
I=\left\{(x,x,y,y)\in{\bf F}^{4}:x,y\in{\bf F}\right\}\quad{\mathrm{and}}\quad W=\left\{(x,x,x,y)\in{\bf F}^{4}:x,y\in{\bf F}^{4}\right\}.
$$  

Using words rather than symbols, we could say that $U$ is the set of elements of $\mathbf{F}^{4}$ whose first two coordinates equal each other and whose third and fourth coordinates equal each other. Similarly, $W$ is the set of elements of $\mathbf{F}^{4}$ whose first three coordinates equal each other.  

To find a description of $U+W,$ , consider a typical element $(a,a,b,b)$ of $U$ and a typical element $(c,c,c,d)$ of $W$ , where $a,b,c,d\in\mathbf{F}$ . We have  

$$
(a,a,b,b)+(c,c,c,d)=(a+c,a+c,b+c,b+d),
$$  

which shows that every element of $U+W$ has its first two coordinates equal to each other. Thus  

$$
U+W\subseteq\{(x,x,y,z)\in\mathbf{F}^{4}:x,y,z\in\mathbf{F}\}.
$$  

To prove the inclusion in the other direction, suppose $x,y,z\in\mathbf{F}$ . Then  

$$
(x,x,y,z)=(x,x,y,y)+(0,0,0,z-y),
$$  

where the first vector on the right is in $U$ and the second vector on the right is in $W.$ Thus $(x,x,y,z)\in U+W,$ showing that the inclusion 1.39 also holds in the opposite direction. Hence  

$$
U+W=\{(x,x,y,z)\in\mathbf{F}^{4}:x,y,z\in\mathbf{F}\},
$$  

which shows that $U+W$ is the set of elements of $\mathbf{F}^{4}$ whose first two coordinates equal each other.  

The next result states that the sum of subspaces is a subspace, and is in fact the smallest subspace containing all the summands (which means that every subspace containing all the summands also contains the sum).  

## 1.40 sum of subspaces is the smallest containing subspace  

Suppose $V_{1},...,V_{m}$ are subspaces of $V.$ . Then $V_{1}+\cdots+V_{m}$ is the smallest subspace of 𝑉containing 𝑉1, …, 𝑉𝑚.  

Proof The reader can verify that $V_{1}+\cdots+V_{m}$ contains the additive identity 0 and is closed under addition and scalar multiplication. Thus 1.34 implies that $V_{1}+\cdots+V_{m}$ is a subspace of $V.$  

The subspaces $V_{1},...,V_{m}$ are all contained in $V_{1}\!+\!\cdots\!+\!V_{m}$ (to see this, consider sums $v_{1}+\cdots+v_{m}$ where all except one of the $v_{k}$ ’s are 0). Conversely, every subspace of $V$ containing $V_{1},...,V_{m}$ contains $V_{1}+\cdots+V_{m}$ (because subspaces must contain all finite sums of their elements). Thus $V_{1}\!+\!\cdots\!+\!V_{m}$ is the smallest subspace of 𝑉containing 𝑉1, …, 𝑉𝑚.  

Sums of subspaces in the theory of vector spaces are analogous to unions of subsets in set theory. Given two subspaces of a vector space, the smallest subspace containing them is their sum. Analogously, given two subsets of a set, the smallest subset containing them is their union.  

## Direct Sums  

Suppose $V_{1},...,V_{m}$ are subspaces of $V.$ . Every element of $V_{1}+\cdots+V_{m}$ can be written in the form  

$$
v_{1}+\cdots+v_{m},
$$  

where each $\ v_{k}\in\ V_{k}$ . Of special interest are cases in which each vector in $V_{1}+\cdots+V_{m}$ can be represented in the form above in only one way. This situation is so important that it gets a special name (direct sum) and a special symbol $\left(\oplus\right)$ .  

## 1.41 definition: direct sum, ⊕  

Suppose $V_{1},...,V_{m}$ are subspaces of $V.$  

The sum $V_{1}+\cdots+V_{m}$ is called a direct sum if each element of $V_{1}+\cdots+V_{m}$ can be written in only one way as a sum $v_{1}+\cdots+v_{m}$ , where each $v_{k}\in V_{k}$ . If $V_{1}+\cdots+V_{m}$ is a direct sum, then $V_{1}\oplus\cdots\oplus V_{m}$ denotes $V_{1}+\cdots+V_{m}$ , with the $\oplus$ notation serving as an indication that this is a direct sum.  

## 1.42 example: a direct sum of two subspaces  

Suppose $U$ is the subspace of $\mathbf{F}^{3}$ of those vectors whose last coordinate equals 0, and $W$ is the subspace of $\mathbf{F}^{3}$ of those vectors whose first two coordinates equal 0:  

$$
U=\big\{(x,y,0)\in\mathbf{F}^{3}:x,y\in\mathbf{F}\big\}\quad\mathrm{and}\quad W=\big\{(0,0,z)\in\mathbf{F}^{3}:z\in\mathbf{F}\big\}.
$$  

Then $\mathbf{F}^{3}=U\oplus W,$ , as you should verify.  

Suppose $V_{k}$ is the subspace of $\mathbf{F}^{n}$ of those vectors whose coordinates are all  

To produce $\oplus$ in TEX, type \oplus.  

0, except possibly in the $k^{\mathrm{th}}$ slot; for example, $V_{2}=\left\{(0,x,0,...,0)\in\mathbf{F}^{n}:x\in\mathbf{F}\right\}$ . Then  

$$
\mathbf{F}^{n}=V_{1}\oplus\cdots\oplus V_{n},
$$  

as you should verify.  

Sometimes nonexamples add to our understanding as much as examples.  

1.44 example: a sum that is not a direct sum  

Suppose  

$$
\begin{array}{r l}&{V_{1}=\big\{(x,y,0)\in{\bf F}^{3}:x,y\in{\bf F}\big\},}\\ &{V_{2}=\big\{(0,0,z)\in{\bf F}^{3}:z\in{\bf F}\big\},}\\ &{V_{3}=\big\{(0,y,y)\in{\bf F}^{3}:y\in{\bf F}\big\}.}\end{array}
$$  

Then $\mathbf{F}^{3}=V_{1}+V_{2}+V_{3}$ because every vector $(x,y,z)\in\mathbf{F}^{3}$ can be written as  

$$
(x,y,z)=(x,y,0)+(0,0,z)+(0,0,0),
$$  

where the first vector on the right side is in $V_{1}$ , the second vector is in $V_{2}$ , and the third vector is in $V_{3}$ .  

However, $\mathbf{F}^{3}$ does not equal the direct sum of $V_{1},V_{2},V_{3}$ , because the vector $(0,0,0)$ can be written in more than one way as a sum $v_{1}+v_{2}+v_{3}$ , with each $v_{k}\in V_{k}$ . Specifically, we have  

$$
(0,0,0)=(0,1,0)+(0,0,1)+(0,-1,-1)
$$  

and, of course,  

$$
(0,0,0)=(0,0,0)+(0,0,0)+(0,0,0),
$$  

where the first vector on the right side of each equation above is in $V_{1}$ , the second vector is in $V_{2}$ , and the third vector is in $V_{3}$ . Thus the sum $V_{1}+V_{2}+V_{3}$ is not a direct sum.  

The definition of direct sum requires every vector in the sum to have a unique representation as an appropriate sum. The next result shows that when deciding whether a sum of subspaces is a direct sum, we only need to consider whether 0 can be uniquely written as an appropriate sum.  

The symbol $\oplus$ , which is a plus sign inside a circle, reminds us that we are dealing with a special type of sum of subspaces—each element in the direct sum can be represented in only one way as a sum of elements from the specified subspaces.  

Suppose $V_{1},...,V_{m}$ are subspaces of $V.$ Then $V_{1}+\cdots+V_{m}$ is a direct sum if and only if the only way to write 0 as a sum $v_{1}+\cdots+v_{m}$ , where each $v_{k}\in V_{k}$ , is by taking each $v_{k}$ equal to 0.  

Proof First suppose $V_{1}+\cdots+V_{m}$ is a direct sum. Then the definition of direct sum implies that the only way to write 0 as a sum $v_{1}+\cdots+v_{m}$ , where each $v_{k}\in V_{k}$ , is by taking each $v_{k}$ equal to 0.  

Now suppose that the only way to write 0 as a sum $v_{1}+\cdots+v_{m}$ , where each $v_{k}\in V_{k}$ , is by taking each $v_{k}$ equal to 0. To show that $V_{1}+\cdots+V_{m}$ is a direct sum, let $v\in V_{1}+\cdots+V_{m}$ . We can write  

$$
v=v_{1}+\cdots+v_{m}
$$  

for some $v_{1}\,\in\,V_{1},...,v_{m}\,\in\,V_{m}$ . To show that this representation is unique, suppose we also have  

$$
v=u_{1}+\cdots+u_{m},
$$  

where $u_{1}\in V_{1},...,u_{m}\in V_{m}$ . Subtracting these two equations, we have  

$$
0=(v_{1}-u_{1})+\cdots+(v_{m}-u_{m}).
$$  

Because $v_{1}-u_{1}\in V_{1},...,v_{m}-u_{m}\in V_{m}$ , the equation above implies that each $v_{k}-u_{k}$ equals 0. Thus $v_{1}=u_{1},...,v_{m}=u_{m}$ , as desired.  

The next result gives a simple condition for testing whether a sum of two subspaces is a direct sum.  

The symbol $\Longleftrightarrow$ used below means “if and only if ”; this symbol could also be read to mean “is equivalent to”.  

1.46 direct sum of two subspaces  

Suppose $U$ and $W$ are subspaces of $V.$ Then  

$$
U+W{\mathrm{~is~a~direct~sum}}\iff U\cap W=\{0\}.
$$  

Proof First suppose that $U+W$ is a direct sum. If $v\in U\cap W_{\mathrm{s}}$ , then $0=v+(-v)$ , where $v\in U$ and $-v\in W.$ . By the unique representation of 0 as the sum of a vector in $U$ and a vector in $W_{s}$ , we have $v=0$ . Thus $U\cap W=\{0\}$ , completing the proof in one direction.  

To prove the other direction, now suppose $U\cap W=\{0\}$ . To prove that $U+W$ is a direct sum, suppose $u\in U,w\in W_{}$ , and  

$$
0=u+w.
$$  

To complete the proof, we only need to show that $u\,=\,w\,=\,0$ (by 1.45). The equation above implies that $u=-w\in W.$ . Thus $u\in U\cap W.$ . Hence $u=0$ , which by the equation above implies that $w=0$ , completing the proof.  

The result above deals only with the case of two subspaces. When asking about a possible direct sum with more than two subspaces, it is not enough to test that each pair of the subspaces intersect only at 0. To see this, consider Example 1.44. In that nonexample of a direct sum, we have $V_{1}\cap V_{2}=V_{1}\cap V_{3}=V_{2}\cap V_{3}=\{0\}$ .  

Sums of subspaces are analogous to unions of subsets. Similarly, direct sums of subspaces are analogous to disjoint unions of subsets. No two subspaces of a vector space can be disjoint, because both contain 0. So disjointness is replaced, at least in the case of two subspaces, with the requirement that the intersection equal $\{0\}$ .  

## Exercises 1C  

1 For each of the following subsets of $\mathbf{F}_{:}^{3}$ , determine whether it is a subspace of $\mathbf{F}^{3}$ .  

$$
\begin{array}{r l}&{\bigl\{(x_{1},x_{2},x_{3})\in\mathbf{F}^{3}:x_{1}+2x_{2}+3x_{3}=0\bigr\}}\\ &{\bigl\{(x_{1},x_{2},x_{3})\in\mathbf{F}^{3}:x_{1}+2x_{2}+3x_{3}=4\bigr\}}\\ &{\bigl\{(x_{1},x_{2},x_{3})\in\mathbf{F}^{3}:x_{1}x_{2}x_{3}=0\bigr\}}\\ &{\bigl\{(x_{1},x_{2},x_{3})\in\mathbf{F}^{3}:x_{1}=5x_{3}\bigr\}}\end{array}
$$  

2 Verify all assertions about subspaces in Example 1.35.  

3 Show that the set of differentiable real-valued functions $f$ on the interval $(-4,4)$ such that $f^{\prime}(-1)=3f(2)$ is a subspace of $\mathbf{R}^{(-4,4)}$ .  

4 Suppose $b\in\mathbb{R}$ . Show that the set of continuous real-valued functions $f$ on the interval [0, 1] such that $\textstyle\int_{0}^{1}f=b$ is a subspace of $\mathbf{R}^{[0,1]}$ if and only if $b=0$ .  

5 Is $\mathbf{R}^{2}$ a subspace of the complex vector space $C^{2}?$  

6 (a) Is $\{(a,b,c)\in\mathbb{R}^{3}:a^{3}=b^{3}\}$ a subspace of $\mathbf{R}^{3}$ ? (b) Is $\{(a,b,c)\in\mathbf{C}^{3}:a^{3}=b^{3}\}$ a subspace of $\mathbf{C}^{3}\mathrm{?}$  

7 Prove or give a counterexample: If $U$ is a nonempty subset of $\mathbf{R}^{2}$ such that $U$ is closed under addition and under taking additive inverses (meaning $-u\in U$ whenever $u\in U_{\star}$ ), then $U$ is a subspace of $\mathbf{R}^{2}.$  

8 Give an example of a nonempty subset $U$ of $\mathbf{R}^{2}$ such that $U$ is closed under scalar multiplication, but $U$ is not a subspace of $\mathbf{R}^{2}$ .  

9 A function $f\colon\ensuremath{\mathbf{R}}\to\ensuremath{\mathbf{R}}$ is called periodic if there exists a positive number $p$ such that $f(x)\,=\,f(x+p)$ for all $x\in\mathbb{R}$ . Is the set of periodic functions from $\mathbf{R}$ to $\mathbf{R}$ a subspace of $\mathbf{R}^{\mathbb{R}}$ ? Explain.  

10 Suppose $V_{1}$ and $V_{2}$ are subspaces of $V.$ . Prove that the intersection $V_{1}\cap V_{2}$ is a subspace of $V.$  

11 Prove that the intersection of every collection of subspaces of $V$ is a subspace of $V.$  

12 Prove that the union of two subspaces of $V$ is a subspace of $V$ if and only if one of the subspaces is contained in the other.  

13 Prove that the union of three subspaces of $V$ is a subspace of $V$ if and only if one of the subspaces contains the other two.  

This exercise is surprisingly harder than Exercise 12, possibly because this exercise is not true if we replace 𝐅with a field containing only two elements.  

14 Suppose  

$$
U=\left\{(x,-x,2x)\in\mathbf{F}^{3}:x\in\mathbf{F}\right\}\quad{\mathrm{and}}\quad W=\left\{(x,x,2x)\in\mathbf{F}^{3}:x\in\mathbf{F}\right\}
$$  

Describe $U+W$ using symbols, and also give a description of $U+W$ that uses no symbols.  

15 Suppose $U$ is a subspace of $V.$ What is $U+U?$  

Is the operation of addition on the subspaces of $V$ commutative? In other words, if $U$ and $W$ are subspaces of $V,$ is $U+W=W+U?$  

Is the operation of addition on the subspaces of $V$ associative? In other words, if $V_{1},V_{2},V_{3}$ are subspaces of $V,$ is  

$$
(V_{1}+V_{2})+V_{3}=V_{1}+(V_{2}+V_{3})?
$$  

Does the operation of addition on the subspaces of $V$ have an additive identity? Which subspaces have additive inverses?  

9 Prove or give a counterexample: If $V_{1},V_{2},U$ are subspaces of $V$ such that  

$$
V_{1}+U=V_{2}+U,
$$  

then $V_{1}=V_{2}$ .  

20 Suppose  

$$
U=\big\{(x,x,y,y)\in\mathbf{F}^{4}:x,y\in\mathbf{F}\big\}.
$$  

Find a subspace $W$ of $\mathbf{F}^{4}$ such that $\mathbf{F}^{4}=U\oplus W$ .  

21 Suppose  

$$
U=\big\{(x,y,x+y,x-y,2x)\in\mathbf{F}^{5}:x,y\in\mathbf{F}\big\}.
$$  

Find a subspace $W$ of $\mathbf{F}^{5}$ such that $\mathbf{F}^{5}=U\oplus W.$  

22 Suppose  

$$
U=\big\{(x,y,x+y,x-y,2x)\in\mathbf{F}^{5}:x,y\in\mathbf{F}\big\}.
$$  

Find three subspaces $W_{1},W_{2},W_{3}$ of $\mathbf{F}_{:}^{5}$ , none of which equals $\{0\}$ , such that $\mathbf{F}^{5}=U\oplus W_{1}\oplus W_{2}\oplus W_{3}$ .  

$$
V=V_{1}\oplus U\quad{\mathrm{and}}\quad V=V_{2}\oplus U,
$$  

then $V_{1}=V_{2}$ .  

Hint: When trying to discover whether a conjecture in linear algebra is true or false, it is often useful to start by experimenting in $\mathbf{F}^{2}.$ .  

24 A function $f$ $\mathbf{\nabla}:\mathbf{R}\rightarrow\mathbf{R}$ is called even if  

$$
f(-x)=f(x)
$$  

for all $x\in\mathbb{R}$ . A function $f\colon\ensuremath{\mathbf{R}}\to\ensuremath{\mathbf{R}}$ is called odd if  

$$
f(-x)=-f(x)
$$  

for all $x\in\mathbb{R}$ . Let $V_{\mathrm{e}}$ denote the set of real-valued even functions on 𝐑 and let $V_{\mathrm{{o}}}$ denote the set of real-valued odd functions on $\mathbf{R}$ . Show that 𝐑𝐑= 𝑉e ⊕𝑉o.  


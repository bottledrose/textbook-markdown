# Ch05 Eigenvalues and Eigenvectors  

Linear maps from one vector space to another vector space were the objects of study in Chapter 3. Now we begin our investigation of operators, which are linear maps from a vector space to itself. Their study constitutes the most important part of linear algebra.  

To learn about an operator, we might try restricting it to a smaller subspace. Asking for that restriction to be an operator will lead us to the notion of invariant subspaces. Each one-dimensional invariant subspace arises from a vector that the operator maps into a scalar multiple of the vector. This path will lead us to eigenvectors and eigenvalues.  

We will then prove one of the most important results in linear algebra: every operator on a finite-dimensional nonzero complex vector space has an eigenvalue. This result will allow us to show that for each operator on a finite-dimensional complex vector space, there is a basis of the vector space with respect to which the matrix of the operator has at least almost half its entries equal to 0.  

standing assumptions for this chapter
+ 𝐅 denotes 𝐑 or 𝐂
+ 𝑉 denotes a vector space over 𝐅.  

## Eigenvalues  

## 5.1 definition: operator  

A linear map from a vector space to itself is called an operator.  

Suppose $T\in{\mathcal{L}}(V)$ . If $m\geq2$ and $V=V_{1}\oplus\cdots\oplus V_{m}\,,$  

Recall that we defined the notation ${\mathcal{L}}(V)$ to mean ${\mathcal{L}}(V,V)$ .  

where each $V_{k}$ is a nonzero subspace of $V,$ then to understand the behavior of $T$ we only need to understand the behavior of each $T|_{V_{k}}$ ; here $T|_{V_{k}}$ denotes the restriction of $T$ to the smaller domain $V_{k}$ . Dealing with $T|_{V_{k}}$ should be easier than dealing with $T$ because $V_{k}$ is a smaller vector space than $V.$ .  

However, if we intend to apply tools useful in the study of operators (such as taking powers), then we have a problem: $T|_{V_{k}}$ may not map $V_{k}$ into itself; in other words, $T|_{V_{k}}$ may not be an operator on $V_{k}$ . Thus we are led to consider only decompositions of $V$ of the form above in which $T$ maps each $V_{k}$ into itself. Hence we now give a name to subspaces of $V$ that get mapped into themselves by $T.$ .  

## 5.2 definition: invariant subspace  

Suppose $T\in{\mathcal{L}}(V)$ . A subspace $U$ of $V$ is called invariant under $T$ if $T u\in U$ for every $u\in U$ .  

Thus $U$ is invariant under $T$ if $T|_{U}$ is an operator on $U$ .  

5.3 example: subspace invariant under differentiation operator  

Suppose that $T\in{\mathcal{L}}({\mathcal{P}}(\mathbf{R}))$ is defined by $T p=p^{\prime}$ . Then ${\mathcal{P}}_{4}(\mathbf{R})$ , which is a subspace of ${\mathcal{P}}(\mathbf{R})$ , is invariant under $T$ because if $p\in{\mathcal{P}}(\mathbb{R})$ has degree at most 4, then $p^{\prime}$ also has degree at most 4.  

5.4 example: four invariant subspaces, not necessarily all different  

If $T\in{\mathcal{L}}(V)$ , then the following subspaces of $V$ are all invariant under $T$ . $\{0\}$ The subspace $\{0\}$ is invariant under $T$ because if $u\in\{0\}$ , then $u=0$ and hence $T u=0\in\{0\}$ . $V$ The subspace $V$ is invariant under $T$ because if $u\in V,$ then $T u\in V.$   
null $T$ The subspace null $T$ is invariant under $T$ because if $u\in\mathrm{null}\:T$ , then $T u=0$ , and hence $T u\in\mathrm{null}\,T.$ .   
range $T$ The subspace range $T$ is invariant under $T$ because if $u\in$ range $T$ , then $T u\in$ range $T.$ .  

Must an operator $T\,\in\,{\mathcal{L}}(V)$ have any invariant subspaces other than $\{0\}$ and 𝑉? Later we will see that this question has an affirmative answer if $V$ is finite-dimensional and dim $V>1$ (for $\mathbf{F}=\mathbf{C}_{}$ ) or dim $V>2$ (for $\mathbf{F}=\mathbf{R}\,,$ ); see 5.19 and Exercise 29 in Section 5B.  

The previous example noted that null $T$ and range $T$ are invariant under $T$ . However, these subspaces do not necessarily provide easy answers to the question above about the existence of invariant subspaces other than $\{0\}$ and $V,$ , because null $T$ may equal $\{0\}$ and range $T$ may equal $V$ (this happens when $T$ is invertible).  

We will return later to a deeper study of invariant subspaces. Now we turn to an investigation of the simplest possible nontrivial invariant subspaces—invariant subspaces of dimension one.  

Take any $v\in V$ with $v\neq0$ and let $U$ equal the set of all scalar multiples of $v$ :  

$$
U=\{\lambda v:\lambda\in\mathbf{F}\}=\operatorname{span}(v).
$$  

Then $U$ is a one-dimensional subspace of $V$ (and every one-dimensional subspace of $V$ is of this form for an appropriate choice of $v$ ). If $U$ is invariant under an operator $T\in{\mathcal{L}}(V)$ , then $T v\in U$ , and hence there is a scalar $\lambda\in\mathbf{F}$ such that  

$$
T v=\lambda v.
$$  

Conversely, if $T v\;=\;\lambda v$ for some $\lambda\in\mathbf{F}$ , then span $(v)$ is a one-dimensional subspace of $V$ invariant under $T$ .  

The equation $T v=\lambda v.$ , which we have just seen is intimately connected with one-dimensional invariant subspaces, is important enough that the scalars $\lambda$ and vectors $v$ satisfying it are given special names.  

<html><body><table><tr><td colspan="2">5.5 definition:eigenvalue</td></tr><tr><td colspan="2">Suppose T E L(V). A number A E F is called an eigenvalue of T if there exists 7 E V such that v ≠ O and T = 入v.</td></tr><tr><td>In the definition above,we require that v ≠ O because every scalar 入 E F satisfies TO=AO. ThecommentsaboveshowthatV has a one-dimensional subspace invariant under Tif and only if T has an eigenvalue.</td><td>Thewordeigenvalueishalf-German, half-English.TheGermanprefixeigen means“own"in the senseofcharac- terizinganintrinsicproperty.</td></tr></table></body></html>  

## 5.6 example: eigenvalue  

Define an operator $T\in{\mathcal{L}}(\mathbf{F}^{3})$ by  

$$
T(x,y,z)=(7x+3z,3x+6y+9z,-6y)
$$  

for $(x,y,z)\,\in\,\mathbf{F}^{3}$ . Then $T(3,1,-1)\,=\,(18,6,-6)\,=\,6(3,1,-1)$ . Thus 6 is an eigenvalue of $T$ .  

The equivalences in the next result, along with many deep results in linear algebra, are valid only in the context of finite-dimensional vector spaces.  

## 5.7 equivalent conditions to be an eigenvalue  

Suppose $V$ is finite-dimensional, $T\in{\mathcal{L}}(V)$ , and $\lambda\in\mathbf{F}$ . Then the following are equivalent.  

(a) $\lambda$ is an eigenvalue of $T.$ .  

(b) $T-\lambda I$ is not injective. Reminder: $I\,\in\,{\mathcal{L}}(V)$ is the identity operator. Thus $I v=v$ for all $v\in V.$ . (c) $T-\lambda I$ is not surjective.  

Proof Conditions (a) and (b) are equivalent because the equation $T v\;=\;\lambda v$ is equivalent to the equation $(T-\lambda I)v\,=\,0$ . Conditions (b), (c), and (d) are equivalent by 3.65.  

## 5.8 definition: eigenvector  

Suppose $T\in{\mathcal{L}}(V)$ and $\lambda\in\mathbf{F}$ is an eigenvalue of $T.$ A vector $v\in V$ is called an eigenvector of $T$ corresponding to $\lambda$ if $v\neq0$ and $T v=\lambda v$ .  

In other words, a nonzero vector $v\,\in\,V$ is an eigenvector of an operator $T\in{\mathcal{L}}(V)$ if and only if $T v$ is a scalar multiple of $v$ . Because $T v=\lambda v$ if and only if $(T-\lambda I)v=0$ , a vector $v\in V$ with $v\neq0$ is an eigenvector of $T$ corresponding to $\lambda$ if and only if $v\in\mathrm{null}(T-\lambda I)$ .  

5.9 example: eigenvalues and eigenvectors  

Suppose $T\in\mathcal{L}(\mathbf{F}^{2})$ is defined by $T(w,z)=(-z,w)$ .  

(a) First consider the case $\mathbf{F}=\mathbf{R}$ . Then $T$ is a counterclockwise rotation by $90^{\circ}$ about the origin in $\mathbf{R}^{2}.$ . An operator has an eigenvalue if and only if there exists a nonzero vector in its domain that gets sent by the operator to a scalar multiple of itself. A $90^{\circ}$ counterclockwise rotation of a nonzero vector in $\mathbf{R}^{2}$ cannot equal a scalar multiple of itself. Conclusion: if $\mathbf{F}=\mathbf{R}$ , then $T$ has no eigenvalues (and thus has no eigenvectors).  

(b) Now consider the case $\mathbf{F}=\mathbf{C}$ . To find eigenvalues of $T$ , we must find the scalars $\lambda$ such that $T(w,z)=\lambda(w,z)$ has some solution other than $w=z=0$ . The equation $T(w,z)=\lambda(w,z)$ is equivalent to the simultaneous equations  

5.10  

$$
-z=\lambda w,\quad w=\lambda z.
$$  

Substituting the value for $w$ given by the second equation into the first equation gives  

$$
-z=\lambda^{2}z.
$$  

Now $z$ cannot equal 0 [otherwise 5.10 implies that $w=0$ ; we are looking for solutions to 5.10 such that $(w,z)$ is not the 0 vector], so the equation above leads to the equation  

$$
-1=\lambda^{2}.
$$  

The solutions to this equation are $\lambda=i$ and $\lambda=-i$ .  

You can verify that $i$ and $-i$ are eigenvalues of $T.$ . Indeed, the eigenvectors corresponding to the eigenvalue $i$ are the vectors of the form $(w,-w i)$ , with $w\in\mathbf{C}$ and $w\ne\,0$ . Furthermore, the eigenvectors corresponding to the eigenvalue $-i$ are the vectors of the form $(w,w i)$ , with $w\in\mathbf{C}$ and $w\ne0$ .  

In the next proof, we again use the equivalence  

$$
T v=\lambda v\iff(T-\lambda I)v=0.
$$  

5.11 linearly independent eigenvectors  

Suppose $T\in{\mathcal{L}}(V)$ . Then every list of eigenvectors of $T$ corresponding to distinct eigenvalues of $T$ is linearly independent.  

Proof Suppose the desired result is false. Then there exists a smallest positive integer $m$ such that there exists a linearly dependent list $v_{1},...,v_{m}$ of eigenvectors of $T$ corresponding to distinct eigenvalues $\lambda_{1},...,\lambda_{m}$ of $T$ (note that $m\geq2$ because an eigenvector is, by definition, nonzero). Thus there exist $\textstyle{a_{1},...,a_{m}}\in\mathbf{F}$ , none of which are 0 (because of the minimality of $m$ ), such that  

$$
a_{1}v_{1}+\cdots+a_{m}v_{m}=0.
$$  

Apply $T-\lambda_{m}I$ to both sides of the equation above, getting  

$$
a_{1}(\lambda_{1}-\lambda_{m})v_{1}+\cdots+a_{m-1}(\lambda_{m-1}-\lambda_{m})v_{m-1}=0.
$$  

Because the eigenvalues $\lambda_{1},...,\lambda_{m}$ are distinct, none of the coefficients above equal 0. Thus $v_{1},...,v_{m-1}$ is a linearly dependent list of $m-1$ eigenvectors of $T$ corresponding to distinct eigenvalues, contradicting the minimality of $m$ . This contradiction completes the proof.  

The result above leads to a short proof of the result below, which puts an upper bound on the number of distinct eigenvalues that an operator can have.  

5.12 operator cannot have more eigenvalues than dimension of vector space  

Suppose $V$ is finite-dimensional. Then each operator on $V$ has at most dim $V$ distinct eigenvalues.  

Proof Let $T\,\in\,{\mathcal{L}}(V)$ . Suppose $\lambda_{1},...,\lambda_{m}$ are distinct eigenvalues of $T.$ . Let $v_{1},...,v_{m}$ be corresponding eigenvectors. Then 5.11 implies that the list $v_{1},...,v_{m}$ is linearly independent. Thus $m\leq\dim V$ (see 2.22), as desired.  

The main reason that a richer theory exists for operators (which map a vector space into itself) than for more general linear maps is that operators can be raised to powers. In this subsection we define that notion and the concept of applying a polynomial to an operator. This concept will be the key tool that we use in the next section when we prove that every operator on a nonzero finite-dimensional complex vector space has an eigenvalue.  

If $T$ is an operator, then $T T$ makes sense (see 3.7) and is also an operator on the same vector space as $T.$ . We usually write $T^{2}$ instead of 𝑇𝑇. More generally, we have the following definition of $T^{m}.$ .  

## 5.13 notation: 𝑇𝑚  

Suppose $T\in{\mathcal{L}}(V)$ and $m$ is a positive integer.  

$T^{m}\in{\mathcal{L}}(V)$ is defined by $T^{m}=\underbrace{T\cdots T}_{\phantom{}}$ 𝑚times  

• $T^{0}$ is defined to be the identity operator $I$ on $V.$ .  

• If $T$ is invertible with inverse $T^{-1}$ , then $T^{-m}\in{\mathcal{L}}(V)$ is defined by  

$$
T^{-m}=(T^{-1})^{m}.
$$  

You should verify that if $T$ is an operator, then  

$$
T^{m}T^{n}=T^{m+n}\quad{\mathrm{and}}\quad\left(T^{m}\right)^{n}=T^{m n},
$$  

where $m$ and $n$ are arbitrary integers if $T$ is invertible and are nonnegative integers if $T$ is not invertible.  

Having defined powers of an operator, we can now define what it means to apply a polynomial to an operator.  

5.14 notation: $p(T)$  

Suppose $T\in{\mathcal{L}}(V)$ and $p\in\mathcal{P}(\mathbf{F})$ is a polynomial given by  

$$
p(z)=a_{0}+a_{1}z+a_{2}z^{2}+\cdots+a_{m}z^{m}
$$  

for all $z\in\mathbf{F}$ . Then $p(T)$ is the operator on $V$ defined by  

$$
p(T)=a_{0}I+a_{1}T+a_{2}T^{2}+\cdots+a_{m}T^{m}\!.
$$  

This is a new use of the symbol $p$ because we are applying $p$ to operators, not just elements of 𝐅. The idea here is that to evaluate $p(T)$ , we simply replace $z$ with $T$ in the expression defining $p$ . Note that the constant term $a_{0}$ in $p(z)$ becomes the operator $a_{0}I$ (which is a reasonable choice because $a_{0}=a_{0}z^{0}$ and thus we should replace $a_{0}$ with $a_{0}T^{0}.$ , which equals $a_{0}I_{.}$ ).  

Suppose $D\in{\mathcal{L}}({\mathcal{P}}(\mathbf{R}))$ is the differentiation operator defined by ${\cal D}q=q^{\prime}$ and $p$ is the polynomial defined by $p(x)=7-3x+5x^{2}$ . Then $p(D)=7I-3D+5D^{2}$ . Thus  

$$
(p(D))q=7q-3q^{\prime}+5q^{\prime\prime}
$$  

for every $q\in\mathcal{P}(\mathbb{R})$ .  

If we fix an operator $T\in{\mathcal{L}}(V)$ , then the function from ${\mathcal{P}}(\mathbf{F})$ to ${\mathcal{L}}(V)$ given by $p\mapsto p(T)$ is linear, as you should verify.  

5.16 definition: product of polynomials  

If $p,q\in\mathcal{P}(\mathbf{F})$ , then $p q\in\mathcal{P}(\mathbf{F})$ is the polynomial defined by  

$$
(p q)(z)=p(z)q(z)
$$  

for all $z\in\mathbf{F}$ .  

The order does not matter in taking products of polynomials of a single operator, as shown by (b) in the next result.  

5.17 multiplicative properties  

<html><body><table><tr><td>Suppose p,q E P(F) a and T E L(V). Then (a) (pq)(T) = p(T)q(T); (b) p(T)q(T) = q(T)p(T).</td><td>Informal proof: Whenaproduct of polynomials is expanded using the dis- tributive property, it does not matter whether the symbol is z or T.</td></tr></table></body></html>  

## Proof  

(a) Suppose $p(z)=\sum_{j\mathop{=}0}^{m}a_{j}z^{j}$ and $q(z)=\sum_{k\,=\,0}^{n}b_{k}z^{k}$ for all $z\in\mathbf{F}$ . Then  

$$
(p q)(z)=\sum_{j\mathop{=}0}^{m}\sum_{k\mathop{=}0}^{n}a_{j}b_{k}z^{j+k}.
$$  

Thus  

$$
\begin{array}{l}{{\displaystyle(p q)(T)=\sum_{j=0}^{m}\sum_{k=0}^{n}a_{j}b_{k}T^{j+k}}}\\ {{\displaystyle\qquad\quad=\Bigg(\sum_{j=0}^{m}a_{j}T^{j}\Bigg)\Bigg(\sum_{k=0}^{n}b_{k}T^{k}\Bigg)}}\\ {{\displaystyle\qquad\quad=p(T)q(T).}}\end{array}
$$  

We observed earlier that if $T\in{\mathcal{L}}(V)$ , then the subspaces null $T$ and range $T$ are invariant under $T$ (see 5.4). Now we show that the null space and the range of every polynomial of $T$ are also invariant under $T$ .  

## 5.18 null space and range of $p(T)$ are invariant under $T$  

Suppose $T\ \in\ {\mathcal{L}}(V)$ and $p\,\in\,\mathcal{P}(\mathbf{F})$ . Then null $p(T)$ and range $p(T)$ are invariant under $T$ .  

Proof Suppose $u\in\mathrm{null}\,p(T)$ . Then $p(T)u=0$ . Thus  

$$
\bigl(p(T)\bigr)(T u)=T\bigl(p(T)u\bigr)=T(0)=0.
$$  

Hence $T u\in\mathrm{null}\,p(T)$ . Thus null $p(T)$ is invariant under $T$ , as desired. Suppose $u\in$ range $p(T)$ . Then there exists $v\in V$ such that $u=p(T)v$ . Thus  

$$
T u=T\big(p(T)v\big)=p(T)(T v).
$$  

Hence $T u\in$ range $p(T)$ . Thus range $p(T)$ is invariant under $T$ , as desired.  

## Exercises 5A  

1 Suppose $T\in{\mathcal{L}}(V)$ and $U$ is a subspace of $V.$  

(a) Prove that if $U\subseteq{\mathrm{null}}\,T$ , then $U$ is invariant under $T.$ .  

(b) Prove that if range $T\subseteq U$ , then $U$ is invariant under $T$ .   
2 Suppose that $T\in{\mathcal{L}}(V)$ and $V_{1},...,V_{m}$ are subspaces of $V$ invariant under $T$ . Prove that $V_{1}+\cdots+V_{m}$ is invariant under $T$ .   
3 Suppose $T\ \in\ {\mathcal{L}}(V)$ . Prove that the intersection of every collection of subspaces of $V$ invariant under $T$ is invariant under $T$ .   
4 Prove or give a counterexample: If $V$ is finite-dimensional and $U$ is a subspace of $V$ that is invariant under every operator on $V,$ then $U\,=\,\{0\}$ or $U=V.$   
5 Suppose $T\in{\mathcal{L}}(\mathbb{R}^{2})$ is defined by $T(x,y)=(-3y,x)$ . Find the eigenvalues of $T.$ .   
6 Define $T\in{\mathcal{L}}(\mathbf{F}^{2})$ by $T(w,z)=(z,w)$ . Find all eigenvalues and eigenvectors of $T.$ .   
7 Define $T\in\mathcal{L}(\mathbf{F}^{3})$ by $T(z_{1},z_{2},z_{3})=(2z_{2},0,5z_{3})$ . Find all eigenvalues and eigenvectors of $T$ .   
8 Suppose $P\in{\mathcal{L}}(V)$ is such that $P^{2}=P.$ . Prove that if $\lambda$ is an eigenvalue of $P.$ , or  

then $\lambda=0$ $\lambda=1$ .  

9 Define $T\colon{\mathcal{P}}(\mathbf{R})\rightarrow{\mathcal{P}}(\mathbf{R})$ by $T p=p^{\prime}$ . Find all eigenvalues and eigenvectors of $T.$ .  

10 Define $T\in\mathcal{L}\big(\mathcal{P}_{4}(\mathbf{R})\big)$ by $(T p)(x)=x p^{\prime}(x)$ for all $x\in\mathbb{R}$ . Find all eigenvalues and eigenvectors of $T$ .  

11 Suppose $V$ is finite-dimensional, $T\in{\mathcal{L}}(V)$ , and $\alpha\in\mathbf{F}$ . Prove that there exists $\delta>0$ such that $T{-}\lambda I$ is invertible for all $\lambda\in\mathbf{F}$ such that $0<|\alpha-\lambda|<\delta$ .  

12 Suppose $V=U\oplus W,$ where $U$ and $W$ are nonzero subspaces of $V.$ Define $P\in{\mathcal{L}}(V)$ by $P(u+w)\,=\,u$ for each $u\,\in\,U$ and each $w\in W.$ . Find all eigenvalues and eigenvectors of $P.$  

13 Suppose $T\in{\mathcal{L}}(V)$ . Suppose $S\in{\mathcal{L}}(V)$ is invertible.  

(a) Prove that $T$ and $S^{-1}T S$ have the same eigenvalues. (b) What is the relationship between the eigenvectors of $T$ and the eigenvectors of $S^{-1}T S?$  

14 Give an example of an operator on $\mathbf{R}^{4}$ that has no (real) eigenvalues.  

15 Suppose $V$ is finite-dimensional, $T\in{\mathcal{L}}(V)$ , and $\lambda\in\mathbf{F}$ . Show that $\lambda$ is an eigenvalue of $T$ if and only if $\lambda$ is an eigenvalue of the dual operator $T^{\prime}\in\mathcal{L}(V^{\prime})$ .  

16 Suppose $v_{1},...,v_{n}$ is a basis of $V$ and $T\,\in\,{\mathcal{L}}(V)$ . Prove that if $\lambda$ is an eigenvalue of $T$ , then  

$$
|\lambda|\leq n\operatorname*{max}\{\left|\mathcal{M}(T)_{j,k}\right|:1\leq j,k\leq n\},
$$  

where $\mathcal{M}(T)_{j,k}$ denotes the entry in row $j$ , column $k$ of the matrix of $T$ with respect to the basis $v_{1},...,v_{n}$ .  

See Exercise 19 in Section 6A for a different bound on $|\lambda|$ .  

17 Suppose $\mathbf{F}=\mathbf{R}$ , $T\in{\mathcal{L}}(V)$ , and $\lambda\in\mathbb{R}$ . Prove that $\lambda$ is an eigenvalue of $T$ if and only if $\lambda$ is an eigenvalue of the complexification $T_{\mathbf{C}}$ .  

See Exercise 33 in Section $3B$ for the definition of $T_{\mathbf{C}}$ .  

18 Suppose $\mathbf{F}=\mathbf{R}$ , $T\in{\mathcal{L}}(V)$ , and $\lambda\in\mathbf{C}$ . Prove that $\lambda$ is an eigenvalue of the complexification $T_{\mathbf{C}}$ if and only if $\overline{{\lambda}}$ is an eigenvalue of $T_{\mathbf{C}}$ .  

19 Show that the forward shift operator $T\in{\mathcal{L}}(\mathbf{F}^{\infty})$ defined by  

$$
T(z_{1},z_{2},\dots)=(0,z_{1},z_{2},\dots)
$$  

has no eigenvalues.  

20 Define the backward shift operator $S\in{\mathcal{L}}(\mathbf{F}^{\infty})$ by  

$$
S(z_{1},z_{2},z_{3},\dots)=(z_{2},z_{3},\dots).
$$  

(a) Show that every element of $\mathbf{F}$ is an eigenvalue of $S$ .   
(b) Find all eigenvectors of $S$ .  

21 Suppose $T\in{\mathcal{L}}(V)$ is invertible.  

(a) Suppose $\lambda\in\mathbf{F}$ with $\lambda\neq0$ . Prove that $\lambda$ is an eigenvalue of $T$ if and only if $\frac1\lambda$ is an eigenvalue of $T^{-1}$ .   
(b) Prove that $T$ and $T^{-1}$ have the same eigenvectors.  

22 Suppose $T\in{\mathcal{L}}(V)$ and there exist nonzero vectors $u$ and $w$ in $V$ such that  

$$
T u=3w\quad{\mathrm{and}}\quad T w=3u.
$$  

Prove that 3 or $-3$ is an eigenvalue of $T$ .  

23 Suppose $V$ is finite-dimensional and $S,T\in{\mathcal{L}}(V)$ . Prove that $S T$ and 𝑇𝑆 have the same eigenvalues.  

24 Suppose $A$ is an $n$ -by- $\cdot n$ matrix with entries in 𝐅. Define $T\,\in\,{\mathcal{L}}(\mathbf{F}^{n})$ by $T x=A x$ , where elements of $\mathbf{F}^{n}$ are thought of as $n$ -by-1 column vectors.  

(a) Suppose the sum of the entries in each row of $A$ equals 1. Prove that 1 is an eigenvalue of $T$ .   
(b) Suppose the sum of the entries in each column of $A$ equals 1. Prove that 1 is an eigenvalue of $T$ .  

25 Suppose $T\in{\mathcal{L}}(V)$ and $u,w$ are eigenvectors of $T$ such that $u+w$ is also an eigenvector of $T.$ Prove that $u$ and $w$ are eigenvectors of $T$ corresponding to the same eigenvalue.  

26 Suppose $T\in{\mathcal{L}}(V)$ is such that every nonzero vector in $V$ is an eigenvector of $T.$ . Prove that $T$ is a scalar multiple of the identity operator.  

27 Suppose that $V$ is finite-dimensional and $k\in\{1,...,\dim V-1\}$ . Suppose $T\,\in\,{\mathcal{L}}(V)$ is such that every subspace of $V$ of dimension $k$ is invariant under $T.$ . Prove that $T$ is a scalar multiple of the identity operator.  

28 Suppose $V$ is finite-dimensional and $T\in{\mathcal{L}}(V)$ . Prove that $T$ has at most $^{1+}$ dim range $T$ distinct eigenvalues.  

29 Suppose $T\in{\mathcal{L}}(\mathbb{R}^{3})$ and $-4,\,5.$ , and $\sqrt{7}$ are eigenvalues of $T.$ . Prove that there exists $\boldsymbol{x}\in\mathbb{R}^{3}$ such that $T x-9x=(-4,5,\sqrt{7})$ .  

30 Suppose $T\in{\mathcal{L}}(V)$ and $(T-2I)(T-3I)(T-4I)=0$ . Suppose $\lambda$ is an eigenvalue of $T.$ . Prove that $\lambda=2$ or $\lambda=3$ or $\lambda=4$ .  

31 Give an example of $T\in{\mathcal{L}}(\mathbb{R}^{2})$ such that $T^{4}=-I.$  

32 Suppose $T\in{\mathcal{L}}(V)$ has no eigenvalues and $T^{4}=I.$ . Prove that $T^{2}=-I$ .  

33 Suppose $T\in{\mathcal{L}}(V)$ and $m$ is a positive integer.  

(a) Prove that $T$ is injective if and only if $T^{m}$ is injective.   
(b) Prove that $T$ is surjective if and only if $T^{m}$ is surjective.  

34 Suppose $V$ is finite-dimensional and $v_{1},...,v_{m}\;\in\;V.$ . Prove that the list $v_{1},...,v_{m}$ is linearly independent if and only if there exists $T\in{\mathcal{L}}(V)$ such that $v_{1},...,v_{m}$ are eigenvectors of $T$ corresponding to distinct eigenvalues.  

35 Suppose that $\lambda_{1},...,\lambda_{n}$ is a list of distinct real numbers. Prove that the list $e^{\lambda_{1}x},...,e^{\lambda_{n}x}$ is linearly independent in the vector space of real-valued functions on $\mathbf{R}$ .  

Hint: Let $V=\operatorname{span}(e^{\lambda_{1}x},...,e^{\lambda_{n}x})$ , and define an operator $D\in{\mathcal{L}}(V)$ by $D f=f^{\prime}$ ′. Find eigenvalues and eigenvectors of $D$ .  

36 Suppose that $\lambda_{1},...,\lambda_{n}$ is a list of distinct positive numbers. Prove that the list co $\mathbf{s}(\lambda_{1}x),...,\cos(\lambda_{n}x)$ is linearly independent in the vector space of real-valued functions on $\mathbf{R}$ .  

37 Suppose $V$ is finite-dimensional and $T\in{\mathcal{L}}(V)$ . Define $\mathcal{A}\in\mathcal{L}\big(\mathcal{L}(V)\big)$ by  

$$
{\mathcal{A}}(S)=T S
$$  

for each $S\in{\mathcal{L}}(V)$ . Prove that the set of eigenvalues of $T$ equals the set of eigenvalues of $\mathcal{A}$ .  

38 Suppose $V$ is finite-dimensional, $T\,\in\,{\mathcal{L}}(V)$ , and $U$ is a subspace of $V$ invariant under $T.$ The quotient operator $T/U\in{\mathcal{L}}(V/U)$ is defined by  

$$
(T/U)(v+U)=T v+U
$$  

for each $v\in V.$  

(a) Show that the definition of $T/U$ makes sense (which requires using the condition that $U$ is invariant under $T$ ) and show that $T/U$ is an operator on $V/U$ .  

(b) Show that each eigenvalue of $T/U$ is an eigenvalue of $T$ .  

39 Suppose $V$ is finite-dimensional and $T\in{\mathcal{L}}(V)$ . Prove that $T$ has an eigenvalue if and only if there exists a subspace of $V$ of dimension dim $V-1$ that is invariant under $T$ .  

40 Suppose $S,T\in{\mathcal{L}}(V)$ and $S$ is invertible. Suppose $p\in\mathcal{P}(\mathbf{F})$ is a polynomial. Prove that  

$$
p\big(S T S^{-1}\big)=S p(T)S^{-1}\!.
$$  

41 Suppose $T\in{\mathcal{L}}(V)$ and $U$ is a subspace of $V$ invariant under $T.$ . Prove that $U$ is invariant under $p(T)$ for every polynomial $p\in\mathcal{P}(\mathbf{F})$ .  

42 Define $T\in{\mathcal{L}}(\mathbf{F}^{n})$ by $T(x_{1},x_{2},x_{3},...,x_{n})=(x_{1},2x_{2},3x_{3},...,n x_{n}).$  

(a) Find all eigenvalues and eigenvectors of $T$ .   
(b) Find all subspaces of $\mathbf{F}^{n}$ that are invariant under $T$ .  

43 Suppose that $V$ is finite-dimensional, dim $V>1$ , and $T\in{\mathcal{L}}(V)$ . Prove that $\left\{p(T):p\in{\mathcal{P}}(\mathbf{F})\right\}\neq{\mathcal{L}}(V)$ .  

Existence of Eigenvalues on Complex Vector Spaces  

Now we come to one of the central results about operators on finite-dimensional complex vector spaces.  

5.19 existence of eigenvalues  

Every operator on a finite-dimensional nonzero complex vector space has an eigenvalue.  

Proof Suppose $V$ is a finite-dimensional complex vector space of dimension $n>0$ and $T\in{\mathcal{L}}(V)$ . Choose $v\in V$ with $v\ne0$ . Then  

$$
v,T v,T^{2}v,...,T^{n}v
$$  

is not linearly independent, because $V$ has dimension $n$ and this list has length $n+1$ . Hence some linear combination (with not all the coefficients equal to 0) of the vectors above equals 0. Thus there exists a nonconstant polynomial $p$ of smallest degree such that  

$$
p(T)v=0.
$$  

By the first version of the fundamental theorem of algebra (see 4.12), there exists $\lambda\in\mathbf{C}$ such that $p(\lambda)=0$ . Hence there exists a polynomial $q\in\mathcal{P}(\mathbf{C})$ such that  

$$
p(z)=(z-\lambda)q(z)
$$  

for every $z\in\mathbf{C}$ (see 4.6). This implies (using 5.17) that  

$$
0=p(T)v=(T-\lambda I)\bigl(q(T)v\bigr).
$$  

Because $q$ has smaller degree than $p$ , we know that $q(T)v\neq0$ . Thus the equation above implies that $\lambda$ is an eigenvalue of $T$ with eigenvector $q(T)v$ .  

The proof above makes crucial use of the fundamental theorem of algebra. The comment following Exercise 16 helps explain why the fundamental theorem of algebra is so tightly connected to the result above.  

The hypothesis in the result above that $\mathbf{F}=\mathbf{C}$ cannot be replaced with the hypothesis that $\mathbf{F}=\mathbf{R}$ , as shown by Example 5.9. The next example shows that the finite-dimensional hypothesis in the result above also cannot be deleted.  

In this subsection we introduce an important polynomial associated with each operator. We begin with the following definition.  

## 5.21 definition: monic polynomial  

A monic polynomial is a polynomial whose highest-degree coefficient equals 1.  

For example, the polynomial $2+9z^{2}+z^{7}$ is a monic polynomial of degree 7.  

5.22 existence, uniqueness, and degree of minimal polynomial  

Suppose $V$ is finite-dimensional and $T\in{\mathcal{L}}(V)$ . Then there is a unique monic polynomial $p\in\mathcal{P}(\mathbf{F})$ of smallest degree such that $p(T)=0$ . Furthermore, $\deg p\leq\dim V.$ .  

Proof If $\dim V=0$ , then $I$ is the zero operator on $V$ and thus we take $p$ to be the constant polynomial 1.  

Now use induction on dim $V.$ Thus assume that dim $V>0$ and that the desired result is true for all operators on all complex vector spaces of smaller dimension. Let $v\,\in\,V$ be such that $v\ne0$ . The list $v,T v,...,T^{\dim V}v$ has length $1+\dim V$ and thus is linearly dependent. By the linear dependence lemma (2.19), there is a smallest positive integer $m\leq\dim V$ such that $T^{m}v$ is a linear combination of $v,T v,...,T^{m-1}v.$ . Thus there exist scalars $c_{0},c_{1},c_{2},...,c_{m-1}\in\mathbf{F}$ such that  

$$
c_{0}v+c_{1}T v+\cdots+c_{m-1}T^{m-1}v+T^{m}v=0.
$$  

Define a monic polynomial $q\in\mathcal{P}_{m}(\mathbf{F})$ by  

$$
q(z)=c_{0}+c_{1}z+\cdots+c_{m-1}z^{m-1}+z^{m}.
$$  

Then 5.23 implies that $q(T)v=0$ .  

If $k$ is a nonnegative integer, then  

$$
q(T)\bigl(T^{k}v\bigr)=T^{k}\bigl(q(T)v\bigr)=T^{k}(0)=0.
$$  

The linear dependence lemma (2.19) shows that $v,T v,...,T^{m-1}v$ is linearly independent. Thus the equation above implies that dim null $q(T)\geq m$ . Hence  

$$
\mathtt{e}\,q(T)=\dim V-\dim\mathrm{null}\,q(T)\leq\dim V-m.
$$  

Because range $q(T)$ is invariant under $T$ (by 5.18), we can apply our induction hypothesis to the operator $T|_{\mathrm{range}q(T)}$ on the vector space range $q(T)$ . Thus there is a monic polynomial $s\in{\mathcal{P}}(\mathbf{F})$ with  

$$
\deg s\leq\dim V-m\quad{\mathrm{and}}\quad s(T|_{\mathrm{range}q(T)})=0.
$$  

Hence for all $v\in V$ we have  

$$
(s q)(T)(v)=s(T)\big(q(T)v\big)=0
$$  

because $q(T)v\in$ range $q(T)$ and $s(T)|_{\mathrm{range}q(T)}=s(T|_{\mathrm{range}q(T)})=0.$ . Thus $s q$ is a monic polynomial such that deg $s q\leq\dim V$ and $(s q)(T)=0$ .  

The paragraph above shows that there is a monic polynomial of degree at most dim $V$ that when applied to $T$ gives the 0 operator. Thus there is a monic polynomial of smallest degree with this property, completing the existence part of this result.  

Let $p\in\mathcal{P}(\mathbf{F})$ be a monic polynomial of smallest degree such that $p(T)=0$ . To prove the uniqueness part of the result, suppose $r\in\mathcal{P}(\mathbf{F})$ is a monic polynomial of the same degree as $p$ and $r(T)\,=\,0$ . Then $(p-r)(T)\,=\,0$ and also $\deg(p-r)<\deg p$ . If $p-r$ were not equal to 0, then we could divide $p-r$ by the coefficient of the highest-order term in $p-r$ to get a monic polynomial (of smaller degree than $p$ ) that when applied to $T$ gives the 0 operator. Thus $p-r=0$ , as desired.  

The previous result justifies the following definition.  

## 5.24 definition: minimal polynomial  

Suppose $V$ is finite-dimensional and $T\in{\mathcal{L}}(V)$ . Then the minimal polynomial of $T$ is the unique monic polynomial $p\in\mathcal{P}(\mathbf{F})$ of smallest degree such that $p(T)=0$ .  

To compute the minimal polynomial of an operator $T\in{\mathcal{L}}(V)$ , we need to find the smallest positive integer $m$ such that the equation  

$$
c_{0}I+c_{1}T+\cdots+c_{m-1}T^{m-1}=-T^{m}
$$  

has a solution $c_{0},c_{1},...,c_{m-1}\in\mathbf{F}$ . If we pick a basis of $V$ and replace $T$ in the equation above with the matrix of $T$ , then the equation above can be thought of as a system of $(\dim V)^{2}$ linear equations in the $m$ unknowns $c_{0},c_{1},...,c_{m-1}\in\mathbf{F}$ . Gaussian elimination or another fast method of solving systems of linear equations can tell us whether a solution exists, testing successive values $m=1,2,\ldots$ until a solution exists. By 5.22, a solution exists for some smallest positive integer $m\leq\dim V.$ The minimal polynomial of $T$ is then $c_{0}+c_{1}z+\cdots+c_{m-1}z^{m-1}+z^{m}\!.$  

Even faster (usually), pick $v\in V$ and consider the equation  

$$
c_{0}v+c_{1}T v+\cdots+c_{\dim V-1}T^{\dim V-1}v=-T^{\dim V}v.
$$  

Use a basis of $V$ to convert the equation above to a system of $\dim V$ linear equations in $\dim V$ unknowns $c_{0},c_{1},...,c_{\mathrm{dim}V-1}$ . If this system of equations has a unique solution $c_{0},c_{1},...,c_{\mathrm{dim}V-1}$ (as happens most of the time), then the scalars $c_{0},c_{1},...,c_{\dim V-1},1$ are the coefficients of the minimal polynomial of $T$ (because 5.22 states that the degree of the minimal polynomial is at most dim $V$ ).  

Consider operators on $\mathbf{R}^{4}$ (thought of as 4-by-4 matrices with respect to the standard basis), and take $v=(1,0,0,0)$  

These estimates are based on testing millions of random matrices.  

in the paragraph above. The faster method described above works on over $99.8\%$ of the 4-by-4 matrices with integer entries in the interval [−10, 10] and on over $99.999\%$ of the 4-by-4 matrices with integer entries in $[-100,100]$ .  

5.26 example: minimal polynomial of an operator on $\mathbf{F}^{5}$  

Suppose $T\in{\mathcal{L}}(\mathbf{F}^{5})$ and  

$$
\mathcal{M}(T)=\left(\begin{array}{c c c c c}{0}&{0}&{0}&{0}&{-3}\\ {1}&{0}&{0}&{0}&{6}\\ {0}&{1}&{0}&{0}&{0}\\ {0}&{0}&{1}&{0}&{0}\\ {0}&{0}&{0}&{1}&{0}\end{array}\right)
$$  

with respect to the standard basis $e_{1},e_{2},e_{3},e_{4},e_{5}$ . Taking $\boldsymbol{v}=\boldsymbol{e}_{1}$ for 5.25, we have  

$$
\begin{array}{c c c}{{T e_{1}=e_{2},}}&{{\begin{array}{c}{{T^{4}e_{1}=T(T^{3}e_{1})=T e_{4}=e_{5},}}\\ {{T^{2}e_{1}=T(T e_{1})=T e_{2}=e_{3},}}\end{array}}}&{{\begin{array}{c}{{T^{5}e_{1}=T(T^{4}e_{1})=T e_{5}=-3e_{1}+3,}}\\ {{T^{5}e_{1}=T(T^{4}e_{1})=T e_{5}=-3e_{1}+3.}}\end{array}}}\\ {{T^{3}e_{1}=T(T^{2}e_{1})=T e_{3}=e_{4},}}&{{}}&{{}}\end{array}
$$  

Thus $3e_{1}-6T e_{1}=-T^{5}e_{1}$ . The list $e_{1},T e_{1},T^{2}e_{1},T^{3}e_{1},T^{4}e_{1}$ , which equals the list $e_{1},e_{2},e_{3},e_{4},e_{5}$ , is linearly independent, so no other linear combination of this list equals $-T^{5}e_{1}$ . Hence the minimal polynomial of $T$ is $3-6z+z^{5}.$ .  

Recall that by definition, eigenvalues of operators on $V$ and zeros of polynomials in ${\mathcal{P}}(\mathbf{F})$ must be elements of 𝐅. In particular, if $\mathbf{F}=\mathbf{R}$ , then eigenvalues and zeros must be real numbers.  

5.27 eigenvalues are the zeros of the minimal polynomial  

Suppose $V$ is finite-dimensional and $T\in{\mathcal{L}}(V)$ .  

(a) The zeros of the minimal polynomial of $T$ are the eigenvalues of $T$ .  

(b) If $V$ is a complex vector space, then the minimal polynomial of $T$ has the form  

$$
(z-\lambda_{1})\cdots(z-\lambda_{m}),
$$  

where $\lambda_{1},...,\lambda_{m}$ is a list of all eigenvalues of $T$ , possibly with repetitions.  

## Proof Let $p$ be the minimal polynomial of $T$ .  

(a) First suppose $\lambda\in\mathbf{F}$ is a zero of $p$ . Then $p$ can be written in the form  

$$
p(z)=(z-\lambda)q(z),
$$  

where $q$ is a monic polynomial with coefficients in $\mathbf{F}$ (see 4.6). Because $p(T)=0$ , we have  

$$
0=(T-\lambda I)\big(q(T)v\big)
$$  

for all $v\in V.$ Because the degree of $q$ is less than the degree of the minimal polynomial $p$ , there exists at least one vector $v\in V$ such that $q(T)v\neq0$ . The equation above thus implies that $\lambda$ is an eigenvalue of $T$ , as desired.  

To prove that every eigenvalue of $T$ is a zero of $p$ , now suppose $\lambda\in\mathbf{F}$ is an eigenvalue of $T.$ . Thus there exists $v\in V$ with $v\ne0$ such that $T v=\lambda v$ . Repeated applications of $T$ to both sides of this equation show that $T^{k}v=\lambda^{k}v$ for every nonnegative integer $k$ . Thus  

$$
p(T)v=p(\lambda)v.
$$  

Because $p$ is the minimal polynomial of $T$ , we have $p(T)v=0$ . Hence the equation above implies that $p(\lambda)=0$ . Thus $\lambda$ is a zero of $p$ , as desired.  

(b) To get the desired result, use (a) and the second version of the fundamental theorem of algebra (see 4.13).  

A nonzero polynomial has at most as many distinct zeros as its degree (see 4.8). Thus (a) of the previous result, along with the result that the minimal polynomial of an operator on $V$ has degree at most $\dim V,$ gives an alternative proof of 5.12, which states that an operator on $V$ has at most $\dim V$ distinct eigenvalues.  

Every monic polynomial is the minimal polynomial of some operator, as shown by Exercise 16, which generalizes Example 5.26. Thus 5.27(a) shows that finding exact expressions for the eigenvalues of an operator is equivalent to the problem of finding exact expressions for the zeros of a polynomial (and thus is not possible for some operators).  

5.28 example: An operator whose eigenvalues cannot be found exactly  

Let $T\in{\mathcal{L}}(\mathbf{C}^{5})$ be the operator defined by  

$$
T(z_{1},z_{2},z_{3},z_{4},z_{5})=(-3z_{5},z_{1}+6z_{5},z_{2},z_{3},z_{4}).
$$  

The matrix of $T$ with respect to the standard basis of $\mathbf{C}^{5}$ is the 5-by-5 matrix in Example 5.26. As we showed in that example, the minimal polynomial of $T$ is the polynomial  

$$
3-6z+z^{5}.
$$  

No zero of the polynomial above can be expressed using rational numbers, roots of rational numbers, and the usual rules of arithmetic (a proof of this would take us considerably beyond linear algebra). Because the zeros of the polynomial above are the eigenvalues of $T\left[\mathrm{by}\;5.27(\mathrm{a})\right]$ , we cannot find an exact expression for any eigenvalue of $T$ in any familiar form.  

Numeric techniques, which we will not discuss here, show that the zeros of the polynomial above, and thus the eigenvalues of $T$ , are approximately the following five complex numbers:  

$$
-1.67,\quad0.51,\quad1.40,\quad-0.12+1.59i,\quad-0.12-1.59i.
$$  

Note that the two nonreal zeros of this polynomial are complex conjugates of each other, as we expect for a polynomial with real coefficients (see 4.14).  

The next result completely characterizes the polynomials that when applied to an operator give the 0 operator.  

5.29 $q(T)=0\iff q$ is a polynomial multiple of the minimal polynomial Suppose $V$ is finite-dimensional, $T\in{\mathcal{L}}(V)$ , and $q\in\mathcal{P}(\mathbf{F})$ . Then $q(T)=0$ if and only if $q$ is a polynomial multiple of the minimal polynomial of $T.$ .  

## Proof Let $p$ denote the minimal polynomial of $T$  

First suppose $q(T)=0$ . By the division algorithm for polynomials (4.9), there exist polynomials $s,r\in\mathcal{P}(\mathbf{F})$ such that  

5.30  

$$
q=p s+r
$$  

and deg $r<\deg p$ . We have  

$$
0=q(T)=p(T)s(T)+r(T)=r(T).
$$  

The equation above implies that $r=0$ (otherwise, dividing $r$ by its highest-degree coefficient would produce a monic polynomial that when applied to $T$ gives 0; this polynomial would have a smaller degree than the minimal polynomial, which would be a contradiction). Thus 5.30 becomes the equation $q=p s$ . Hence $q$ is a polynomial multiple of $p$ , as desired.  

To prove the other direction, now suppose $q$ is a polynomial multiple of $p$ . Thus there exists a polynomial $s\in{\mathcal{P}}(\mathbf{F})$ such that $q=p s$ . We have  

$$
q(T)=p(T)s(T)=0\,s(T)=0,
$$  

as desired.  

The next result is a nice consequence of the result above.  

5.31 minimal polynomial of a restriction operator  

Suppose $V$ is finite-dimensional, $T\in{\mathcal{L}}(V)$ , and $U$ is a subspace of $V$ that is invariant under $T.$ Then the minimal polynomial of $T$ is a polynomial multiple of the minimal polynomial of $T|_{U}$ .  

Proof Suppose $p$ is the minimal polynomial of $T.$ . Thus $p(T)v=0$ for all $v\in V.$ In particular,  

$$
p(T)u=0\;{\mathrm{for~all~}}u\in U.
$$  

Thus $p(T|_{U})=0$ . Now 5.29, applied to the operator $T|_{U}$ in place of $T.$ , implies that $p$ is a polynomial multiple of the minimal polynomial of $T|_{U}$ .  

See Exercise 25 for a result about quotient operators that is analogous to the result above.  

The next result shows that the constant term of the minimal polynomial of an operator determines whether the operator is invertible.  

Suppose $V$ is finite-dimensional and $T\in{\mathcal{L}}(V)$ . Then $T$ is not invertible if and only if the constant term of the minimal polynomial of $T$ is 0.  

Proof Suppose $T\in{\mathcal{L}}(V)$ and $p$ is the minimal polynomial of $T.$ Then  

where the first equivalence holds by 5.7, the second equivalence holds by 5.27(a), and the last equivalence holds because the constant term of $p$ equals $p(0)$ .  

## Eigenvalues on Odd-Dimensional Real Vector Spaces  

The next result will be the key tool that we use to show that every operator on an odd-dimensional real vector space has an eigenvalue.  

## 5.33 even-dimensional null space  

Suppose $\mathbf{F}=\mathbf{R}$ and $V$ is finite-dimensional. Suppose also that $T\in{\mathcal{L}}(V)$ and $b,c\in\mathbb{R}$ with $b^{2}<4c$ . Then dim null $(T^{2}+b T+c I)$ is an even number.  

Proof Recall that null $(T^{2}+b T+c I)$ is invariant under $T\,(\mathrm{by}\,5.18)$ . By replacing $V$ with null $(T^{2}+b T+c I)$ and replacing $T$ with $T$ restricted to null $(T^{2}+b T+c I)$ , we can assume that $T^{2}+b T+c I=0$ ; we now need to prove that dim $V$ is even. Suppose $\lambda\in\mathbb{R}$ and $v\in V$ are such that $T v=\lambda v$ . Then  

$$
\begin{array}{r}{0=(T^{2}+b T+c I)v=(\lambda^{2}+b\lambda+c)v=\bigg(\Big(\lambda+\frac{b}{2}\Big)^{2}+c-\frac{b^{2}}{4}\bigg)v.}\end{array}
$$  

The term in large parentheses above is a positive number. Thus the equation above implies that $v=0$ . Hence we have shown that $T$ has no eigenvectors.  

Let $U$ be a subspace of $V$ that is invariant under $T$ and has the largest dimension among all subspaces of $V$ that are invariant under $T$ and have even dimension. If $U=V,$ then we are done; otherwise assume there exists $w\in V$ such that $w\notin U$ .  

Let $W\;=\;\operatorname{span}(w,T w)$ . Then $W$ is invariant under $T$ because $T(T w)\;=\;$ $-b T w-c w$ . Furthermore, dim $W=2$ because otherwise $w$ would be an eigenvector of $T.$ . Now  

$$
\dim(U+W)=\dim U+\dim W-\dim(U\cap W)=\dim U+2,
$$  

where $U\cap W\,=\,\{0\}$ because otherwise $U\cap W$ would be a one-dimensional subspace of $V$ that is invariant under $T$ (impossible because $T$ has no eigenvectors).  

Because $U+W$ is invariant under $T.$ , the equation above shows that there exists a subspace of $V$ invariant under $T$ of even dimension larger than dim $U$ . Thus the assumption that $U\neq V$ was incorrect. Hence $V$ has even dimension.  

The next result states that on odd-dimensional vector spaces, every operator has an eigenvalue. We already know this result for finite-dimensional complex vectors spaces (without the odd hypothesis). Thus in the proof below, we will assume that $\mathbf{F}=\mathbf{R}$ .  

5.34 operators on odd-dimensional vector spaces have eigenvalues  

Every operator on an odd-dimensional vector space has an eigenvalue.  

Proof Suppose $\mathbf{F}=\mathbf{R}$ and $V$ is finite-dimensional. Let $n=\dim V,$ and suppose $n$ is an odd number. Let $T\in{\mathcal{L}}(V)$ . We will use induction on $n$ in steps of size two to show that $T$ has an eigenvalue. To get started, note that the desired result holds if dim $V=1$ because then every nonzero vector in $V$ is an eigenvector of $T$  

Now suppose that $n\geq3$ and the desired result holds for all operators on all odd-dimensional vector spaces of dimension less than $n$ . Let $p$ denote the minimal polynomial of $T.$ . If $p$ is a polynomial multiple of $x-\lambda$ for some $\lambda\in\mathbb{R}$ , then $\lambda$ is an eigenvalue of $T$ [by 5.27(a)] and we are done. Thus we can assume that there exist $b,c\in\mathbb{R}$ such that $b^{2}<4c$ and $p$ is a polynomial multiple of $x^{2}+b x+c$ (see 4.16).  

There exists a monic polynomial $q\in\mathcal{P}(\mathbb{R})$ such that $p(x)=q(x)\big(x^{2}+b x+c\big)$ for all $x\in\mathbf{R}$ . Now  

$$
0=p(T)=\bigl(q(T)\bigr)\bigl(T^{2}+b T+c I\bigr),
$$  

which means that $q(T)$ equals 0 on range $(T^{2}+b T+c I)$ . Because deg $q<\deg p$ and $p$ is the minimal polynomial of $T_{\mathbf{\delta}}$ , this implies that range $(T^{2}+b T+c I)\neq V.$ . The fundamental theorem of linear maps (3.21) tells us that  

$$
\dim V=\dim\mathrm{null}\big(T^{2}+b T+c I\big)+\dim\mathrm{range}\big(T^{2}+b T+c I\big).
$$  

Because dim $V$ is odd (by hypothesis) and dim null $(T^{2}+b T+c I)$ is even (by 5.33), the equation above shows that dim range $(T^{2}+b T+c I)$ is odd.  

Hence range $(T^{2}+b T+c I)$ is a subspace of $V$ that is invariant under $T$ (by 5.18) and that has odd dimension less than dim $V$ . Our induction hypothesis now implies that $T$ restricted to range $(T^{2}+b T+c I)$ has an eigenvalue, which means that $T$ has an eigenvalue.  

See Exercise 23 in Section 8B and Exercise 10 in Section 9C for alternative proofs of the result above.  

## Exercises 5B  

1 Suppose $T\in{\mathcal{L}}(V)$ . Prove that 9 is an eigenvalue of $T^{2}$ if and only if 3 or $-3$ is an eigenvalue of $T$ .  

2 Suppose $V$ is a complex vector space and $T\in{\mathcal{L}}(V)$ has no eigenvalues. Prove that every subspace of $V$ invariant under $T$ is either $\{0\}$ or infinitedimensional.  

3 Suppose $n$ is a positive integer and $T\in{\mathcal{L}}(\mathbf{F}^{n})$ is defined by  

$$
T(x_{1},...,x_{n})=(x_{1}+\cdots+x_{n},...,x_{1}+\cdots+x_{n}).
$$  

(a) Find all eigenvalues and eigenvectors of $T$ .   
(b) Find the minimal polynomial of $T.$ .  

The matrix of $T$ with respect to the standard basis of $\mathbf{F}^{n}$ consists of all $1\,\dot{s}$ .  

4 Suppose ${\textbf{F}}={\textbf{C}}$ , $T\,\in\,{\mathcal{L}}(V)$ , $p\,\in\,\mathcal{P}(\mathbf{C})$ , and $\alpha\in\mathbf{C}$ . Prove that $\alpha$ is an eigenvalue of $p(T)$ if and only if $\alpha=p(\lambda)$ for some eigenvalue $\lambda$ of $T$ .  

5 Give an example of an operator on $\mathbf{R}^{2}$ that shows the result in Exercise 4 does not hold if $\mathbf{C}$ is replaced with $\mathbf{R}$ .  

Suppose $T\,\in\,\mathcal{L}(\mathbf{F}^{2})$ is defined by $T(w,z)\,=\,(-z,w)$ . Find the minimal polynomial of $T.$ .  

7 (a) Give an example of $S,T\in\mathcal{L}(\mathbf{F}^{2})$ such that the minimal polynomial of 𝑆𝑇does not equal the minimal polynomial of $T S$ .  

(b) Suppose $V$ is finite-dimensional and $S,T\in{\mathcal{L}}(V)$ . Prove that if at least one of $S,T$ is invertible, then the minimal polynomial of $S T$ equals the minimal polynomial of $T S$ .  

Hint: Show that if $S$ is invertible and $p\in\mathcal{P}(\mathbf{F})$ , then $p(T S)=S^{-1}p(S T)S.$  

8 Suppose $T\in{\mathcal{L}}(\mathbb{R}^{2})$ is the operator of counterclockwise rotation by $1^{\circ}$ . Find the minimal polynomial of $T.$ .  

Because dim $\mathbf{R}^{2}=2$ , the degree of the minimal polynomial of $T$ is at most 2. Thus the minimal polynomial of $T$ is not the tempting polynomial $x^{180}+1$ , even though $T^{180}=-I.$  

9 Suppose $T\in{\mathcal{L}}(V)$ is such that with respect to some basis of $V.$ , all entries of the matrix of $T$ are rational numbers. Explain why all coefficients of the minimal polynomial of $T$ are rational numbers.  

10 Suppose $V$ is finite-dimensional, $T\in{\mathcal{L}}(V)$ , and $v\in V.$ Prove that  

$$
\operatorname{span}(v,T v,...,T^{m}v)=\operatorname{span}(v,T v,...,T^{\dim V-1}v)
$$  

for all integers $m\geq\dim V-1$ .  

11 Suppose $V$ is a two-dimensional vector space, $T\in{\mathcal{L}}(V)$ , and the matrix of $T$ with respect to some basis of $V$ is $\left(\begin{array}{l l}{{\bar{a}}}&{{c}}\\ {{b}}&{{d}}\end{array}\right)$  

(a) Show that $T^{2}-(a+d)T+(a d-b c)I=0.$ . (b) Show that the minimal polynomial of $T$ equals  

$$
\left\{{z-a}\atop{z^{2}-(a+d)z+(a d-b c)}\right.
$$  

12 Define $T\in{\mathcal{L}}(\mathbf{F}^{n})$ by $T(x_{1},x_{2},x_{3},...,x_{n})=(x_{1},2x_{2},3x_{3},...,n x_{n})$ . Find the minimal polynomial of $T$ .  

13 Suppose $T\in{\mathcal{L}}(V)$ and $p\in\mathcal{P}(\mathbf{F})$ . Prove that there exists a unique $r\in{\mathcal{P}}(\mathbf{F})$ such that $p(T)\;=\;r(T)$ and deg $r$ is less than the degree of the minimal polynomial of $T.$ .  

14 Suppose $V$ is finite-dimensional and $T\in{\mathcal{L}}(V)$ has minimal polynomial $4+5z-6z^{2}-7z^{3}+2z^{4}+z^{5}.$ . Find the minimal polynomial of $T^{-1}$ .  

15 Suppose $V$ is a finite-dimensional complex vector space with dim $V>0$ and $T\in{\mathcal{L}}(V)$ . Define $f\colon\mathbf{C}\rightarrow\mathbf{R}$ by  

$$
f(\lambda)=\dim\operatorname{range}(T-\lambda I).
$$  

Prove that $f$ is not a continuous function.  

16 Suppose $a_{0},...,a_{n-1}\in\mathbf{F}$ . Let $T$ be the operator on $\mathbf{F}^{n}$ whose matrix (with respect to the standard basis) is  

$$
\left(\begin{array}{c c c c c c}{{0}}&{{}}&{{}}&{{}}&{{-a_{0}}}\\ {{1}}&{{0}}&{{}}&{{}}&{{-a_{1}}}\\ {{}}&{{1}}&{{\ddots}}&{{}}&{{-a_{2}}}\\ {{}}&{{}}&{{\ddots}}&{{}}&{{\vdots}}\\ {{}}&{{}}&{{}}&{{0}}&{{-a_{n-2}}}\\ {{}}&{{}}&{{}}&{{}}&{{1}}&{{-a_{n-1}}}\end{array}\right).
$$  

Here all entries of the matrix are 0 except for all 1’s on the line under the diagonal and the entries in the last column (some of which might also be 0). Show that the minimal polynomial of $T$ is the polynomial  

$$
a_{0}+a_{1}z+\cdots+a_{n-1}z^{n-1}+z^{n}.
$$  

The matrix above is called the companion matrix of the polynomial above. This exercise shows that every monic polynomial is the minimal polynomial of some operator. Hence a formula or an algorithm that could produce exact eigenvalues for each operator on each $\mathbf{F}^{n}$ could then produce exact zeros for each polynomial $[b\mathrm{y}\,5.27(a)]$ . Thus there is no such formula or algorithm. However, efficient numeric methods exist for obtaining very good approximations for the eigenvalues of an operator.  

17 Suppose $V$ is finite-dimensional, $T\in{\mathcal{L}}(V)$ , and $p$ is the minimal polynomial of $T.$ . Suppose $\lambda\in\mathbf{F}$ . Show that the minimal polynomial of $T-\lambda I$ is the polynomial $q$ defined by $q(z)=p(z+\lambda)$ .  

18 Suppose $V$ is finite-dimensional, $T\in{\mathcal{L}}(V)$ , and $p$ is the minimal polynomial of $T.$ . Suppose $\lambda\in\mathbf{F}\backslash\{0\}$ . Show that the minimal polynomial of $\lambda T$ is the polynomial $q$ defined by $q(z)=\lambda^{\deg p}\,p\!\left({\frac{z}{\lambda}}\right)$ .  

19 Suppose $V$ is finite-dimensional and $T\in{\mathcal{L}}(V)$ . Let $\mathcal{E}$ be the subspace of ${\mathcal{L}}(V)$ defined by  

$$
{\mathcal{E}}=\{q(T):q\in{\mathcal{P}}(\mathbf{F})\}.
$$  

Prove that dim $\mathcal{E}$ equals the degree of the minimal polynomial of $T$ .  

Suppose $T\in\mathcal{L}(\mathbf{F}^{4})$ is such that the eigenvalues of $T$ are 3, 5, 8. Prove that $(T-3I)^{2}(T-5I)^{2}(T-8I)^{2}=0.$ .  

21 Suppose $V$ is finite-dimensional and $T\in{\mathcal{L}}(V)$ . Prove that the minimal polynomial of $T$ has degree at most $^{1+}$ dim range $T$ .  

If dim range $T<\dim V-1,$ , then this exercise gives a better upper bound than 5.22 for the degree of the minimal polynomial of $T.$ .  

22 Suppose $V$ is finite-dimensional and $T\in{\mathcal{L}}(V)$ . Prove that $T$ is invertible if and only if $I\in\operatorname{span}(T,T^{2},...,T^{\dim V})$ .  

23 Suppose $V$ is finite-dimensional and $T\in{\mathcal{L}}(V)$ . Let $n=\dim V.$ . Prove that if $v\in V,$ then span $(v,T v,...,T^{n-1}v)$ is invariant under $T$ .  

24 Suppose $V$ is a finite-dimensional complex vector space. Suppose $T\in{\mathcal{L}}(V)$ is such that 5 and 6 are eigenvalues of $T$ and that $T$ has no other eigenvalues. Prove that $(T-5I)^{\dim V-1}(T-6I)^{\dim V-1}=0.$ .  

25 Suppose $V$ is finite-dimensional, $T\in{\mathcal{L}}(V)$ , and $U$ is a subspace of $V$ that is invariant under $T$ .  

(a) Prove that the minimal polynomial of $T$ is a polynomial multiple of the minimal polynomial of the quotient operator $T/U$ .   
(b) Prove that  

(minimal polynomial of $T|_{U}\rangle\times$ (minimal polynomial of $T/U_{\star}$ is a polynomial multiple of the minimal polynomial of $T$ .  

The quotient operator $T/U$ was defined in Exercise 38 in Section 5A.  

26 Suppose $V$ is finite-dimensional, $T\in{\mathcal{L}}(V)$ , and $U$ is a subspace of $V$ that is invariant under $T.$ Prove that the set of eigenvalues of $T$ equals the union of the set of eigenvalues of $T|_{U}$ and the set of eigenvalues of $T/U$ .  

27 Suppose $\mathbf{F}\,=\,\mathbf{R}$ , $V$ is finite-dimensional, and $T\,\in\,{\mathcal{L}}(V)$ . Prove that the minimal polynomial of $T_{\mathbf{C}}$ equals the minimal polynomial of $T.$ .  

The complexification $T_{\mathbf{C}}$ was defined in Exercise 33 of Section 3B.  

28 Suppose $V$ is finite-dimensional and $T\in{\mathcal{L}}(V)$ . Prove that the minimal polynomial of $T^{\prime}\in{\mathcal{L}}(V^{\prime})$ equals the minimal polynomial of $T$ .  

The dual map $T^{\prime}$ was defined in Section $3F$ .  

29 Show that every operator on a finite-dimensional vector space of dimension at least two has an invariant subspace of dimension two.  

Exercise 6 in Section $5C$ will give an improvement of this result when $\mathbf{F}=\mathbf{C}$ .  

In Chapter 3 we defined the matrix of a linear map from a finite-dimensional vector space to another finite-dimensional vector space. That matrix depends on a choice of basis of each of the two vector spaces. Now that we are studying operators, which map a vector space to itself, the emphasis is on using only one basis.  

5.35 definition: matrix of an operator, ${\mathcal{M}}(T)$  

Suppose $T\in{\mathcal{L}}(V)$ . The matrix of $T$ with respect to a basis $v_{1},...,v_{n}$ of $V$ is the $n$ -by- $\cdot n$ matrix  

$$
\mathcal{M}(T)=\left(\begin{array}{c c c}{A_{1,1}}&{\cdots}&{A_{1,n}}\\ {\vdots}&{}&{\vdots}\\ {A_{n,1}}&{\cdots}&{A_{n,n}}\end{array}\right)
$$  

whose entries $A_{j,k}$ are defined by  

$$
T v_{k}=A_{1,k}v_{1}+\cdots+A_{n,k}v_{n}.
$$  

The notation $\mathcal{M}(T,(v_{1},...,v_{n}))$ is used if the basis is not clear from the context.  

Operators have square matrices (meaning that the number of rows equals the number of columns), rather than the more general rectangular matrices that we considered earlier for linear maps.  

If $T$ is an operator on $\mathbf{F}^{n}$ and no basis is specified, assume that the basis in question is the standard one (where the $k^{\mathrm{{th}}}$ basis vector is 1 in the $k^{\mathrm{th}}$ slot and 0 in all other slots). You can then think of  

The $k^{t h}$ column of the matrix ${\mathcal{M}}(T)$ is formed from the coefficients used to write $T\boldsymbol{v}_{k}$ as a linear combination of the basis $v_{1},...,v_{n}$ .  

the $k^{\mathrm{{th}}}$ column of ${\mathcal{M}}(T)$ as $T$ applied to the $k^{\mathrm{th}}$ basis vector, where we identify $n$ -by-1 column vectors with elements of $\mathbf{F}^{n}$ .  

5.36 example: matrix of an operator with respect to standard basis  

Define $T\in\mathcal{L}(\mathbf{F}^{3})$ by $T(x,y,z)=(2x+y,5y+3z,8z)$ . Then the matrix of $T$ with respect to the standard basis of $\mathbf{F}^{3}$ is  

$$
\mathcal{M}(T)=\left(\begin{array}{c c c}{{2}}&{{1}}&{{0}}\\ {{0}}&{{5}}&{{3}}\\ {{0}}&{{0}}&{{8}}\end{array}\right)\!,
$$  

as you should verify.  

A central goal of linear algebra is to show that given an operator $T$ on a finitedimensional vector space $V,$ there exists a basis of $V$ with respect to which $T$ has a reasonably simple matrix. To make this vague formulation a bit more precise, we might try to choose a basis of $V$ such that ${\mathcal{M}}(T)$ has many $0\,\mathrm{\dot{s}}$ .  

If $V$ is a finite-dimensional complex vector space, then we already know enough to show that there is a basis of $V$ with respect to which the matrix of $T$ has 0’s everywhere in the first column, except possibly the first entry. In other words, there is a basis of $V$ with respect to which the matrix of $T$ looks like  

$$
{\left(\begin{array}{l l l l l}{\lambda}&{}&{}&{}&{}\\ {0}&{}&{*}&{}&{}\\ {\vdots}&{}&{}&{}&{}\\ {0}&{}&{}&{}&{}\end{array}\right)};
$$  

here $^*$ denotes the entries in all columns other than the first column. To prove this, let $\lambda$ be an eigenvalue of $T$ (one exists by 5.19) and let $v$ be a corresponding eigenvector. Extend $v$ to a basis of $V.$ . Then the matrix of $T$ with respect to this basis has the form above. Soon we will see that we can choose a basis of $V$ with respect to which the matrix of $T$ has even more $0\,\mathrm{\dot{s}}$ .  

5.37 definition: diagonal of a matrix  

The diagonal of a square matrix consists of the entries on the line from the upper left corner to the bottom right corner.  

For example, the diagonal of the matrix  

$$
\mathcal{M}(T)=\left(\begin{array}{l l l}{2}&{1}&{0}\\ {0}&{5}&{3}\\ {0}&{0}&{8}\end{array}\right)
$$  

from Example 5.36 consists of the entries 2, 5, 8, which are shown in red in the matrix above.  

5.38 definition: upper-triangular matrix  

A square matrix is called upper triangular if all entries below the diagonal are 0.  

For example, the 3-by-3 matrix above is upper triangular. Typically we represent an upper-triangular matrix in the form  

$$
{\left(\begin{array}{l l l}{\lambda_{1}}&{}&{*}\\ {}&{\ddots}&{}\\ {0}&{}&{\lambda_{n}}\end{array}\right)};
$$  

the 0 in the matrix above indicates that all entries below the diagonal in this $n$ -by- $_n$ matrix equal 0. Upper-triangular matrices can be considered reasonably  

We often use $^*$ to denote matrix entries that we do not know or that are irrelevant to the questions being discussed.  

simple—if $n$ is large, then at least almost half the entries in an $n$ -by- $_n$ uppertriangular matrix are 0.  

The next result provides a useful connection between upper-triangular matrices and invariant subspaces.  

5.39 conditions for upper-triangular matrix  

Suppose $T\,\in\,{\mathcal{L}}(V)$ and $v_{1},...,v_{n}$ is a basis of $V.$ Then the following are equivalent.  

(a) The matrix of $T$ with respect to $v_{1},...,v_{n}$ is upper triangular.  

(b) span $(v_{1},...,v_{k})$ is invariant under $T$ for each $k=1,...,n$ .  

(c) $T v_{k}\in\operatorname{span}(v_{1},...,v_{k})$ for each $k=1,...,n$ .  

Proof First suppose (a) holds. To prove that (b) holds, suppose $k\in\{1,...,n\}$ . If $j\in\{1,...,n\}$ , then  

$$
T v_{j}\in\operatorname{span}(v_{1},...,v_{j})
$$  

because the matrix of $T$ with respect to $v_{1},...,v_{n}$ is upper triangular. Because span $(v_{1},...,v_{j})\subseteq\operatorname{span}(v_{1},...,v_{k})$ if $j\leq k$ , we see that  

$$
T v_{j}\in\operatorname{span}(v_{1},...,v_{k})
$$  

for each $j\in\{1,...,k\}$ . Thus span $(v_{1},...,v_{k})$ is invariant under $T$ , completing the proof that (a) implies (b).  

Now suppose (b) holds, so span $(v_{1},...,v_{k})$ is invariant under $T$ for each $k=1,...,n$ . In particular, $T v_{k}\,\in\,\mathrm{span}(v_{1},...,v_{k})$ for each $k\;=\;1,...,n$ . Thus (b) implies (c).  

Now suppose (c) holds, so $T v_{k}\in\operatorname{span}(v_{1},...,v_{k})$ for each $k=1,...,n$ . This means that when writing each $T v_{k}$ as a linear combination of the basis vectors $v_{1},...,v_{n}$ , we need to use only the vectors $v_{1},...,v_{k}$ . Hence all entries under the diagonal of ${\mathcal{M}}(T)$ are 0. Thus ${\mathcal{M}}(T)$ is an upper-triangular matrix, completing the proof that (c) implies (a).  

We have shown that (a) $\implies(\mathbf{b})\implies(\mathbf{c})\implies$ (a), which shows that (a), (b), and (c) are equivalent.  

The next result tells us that if $T\in{\mathcal{L}}(V)$ and with respect to some basis of $V$ we have  

$$
\mathcal{M}(T)=\left(\begin{array}{c c c}{{\lambda_{1}}}&{{}}&{{*}}\\ {{}}&{{\ddots}}&{{}}\\ {{0}}&{{}}&{{\lambda_{n}}}\end{array}\right),
$$  

then $T$ satisfies a simple equation depending on $\lambda_{1},...,\lambda_{n}$ .  

5.40 equation satisfied by operator with upper-triangular matrix  

Suppose $T\in{\mathcal{L}}(V)$ and $V$ has a basis with respect to which $T$ has an uppertriangular matrix with diagonal entries $\lambda_{1},...,\lambda_{n}$ . Then  

$$
(T-\lambda_{1}I)\cdots(T-\lambda_{n}I)=0.
$$  

Proof Let $v_{1},...,v_{n}$ denote a basis of $V$ with respect to which $T$ has an uppertriangular matrix with diagonal entries $\lambda_{1},...,\lambda_{n}$ . Then $T v_{1}\;=\;\lambda_{1}v_{1}$ , which means that $(T-\lambda_{1}I)v_{1}=0$ , which implies that $(T-\lambda_{1}I)\cdots(T-\lambda_{m}I)v_{1}=0$ for $m=1,...,n$ (using the commutativity of each $T-\lambda_{j}I$ with each $T-\lambda_{k}I)$ .  

Note that $(T-\lambda_{2}I)v_{2}\,\in\,\mathrm{span}(v_{1})$ . Thus $(T\,\dot{-}\,\lambda_{1}I)(T\,-\,\lambda_{2}I)v_{2}\,=\,0$ (by the previous paragraph), which implies that $(T-\lambda_{1}I)\cdots(T-\lambda_{m}I)v_{1}\,=\,0$ for $m=2,...,n$ (using the commutativity of each $T-\lambda_{j}I$ with each $T-\lambda_{k}I)$ .  

Note that $(T-\lambda_{3}I)v_{3}\;\in\;\mathrm{span}(v_{1},v_{2})$ . Thus by the previous paragraph, $(T-\lambda_{1}I)(T-\lambda_{2}I)(T-\lambda_{3}I)v_{3}=0$ , which implies that $(T\!-\!\lambda_{1}I)\!\cdots\!(T\!-\!\lambda_{m}I)v_{1}=0$ for $m=3,...,n$ (using the commutativity of each $T-\lambda_{j}I$ with each $T-\lambda_{k}I)$ .  

Continuing this pattern, we see that $(T-\lambda_{1}I)\cdots(T-\lambda_{n}I)v_{k}\,=\,0$ for each $k=1,...,n$ . Thus $(T-\lambda_{1}I)\{\cdots(T-\lambda_{n}I)$ is the 0 operator because it is 0 on each vector in a basis of $V.$ .  

Unfortunately no method exists for exactly computing the eigenvalues of an operator from its matrix. However, if we are fortunate enough to find a basis with respect to which the matrix of the operator is upper triangular, then the problem of computing the eigenvalues becomes trivial, as the next result shows.  

5.41 determination of eigenvalues from upper-triangular matrix  

Suppose $T\in{\mathcal{L}}(V)$ has an upper-triangular matrix with respect to some basis of $V.$ Then the eigenvalues of $T$ are precisely the entries on the diagonal of that upper-triangular matrix.  

Proof Suppose $v_{1},...,v_{n}$ is a basis of $V$ with respect to which $T$ has an uppertriangular matrix  

$$
\mathcal{M}(T)=\left(\begin{array}{c c c}{\lambda_{1}}&{}&{*}\\ {}&{\ddots}&{}\\ {0}&{}&{\lambda_{n}}\end{array}\right).
$$  

Because $T v_{1}=\lambda_{1}v_{1}$ , we see that $\lambda_{1}$ is an eigenvalue of $T.$  

Suppose $k\in\{2,...,n\}$ . Then $(T-\lambda_{k}I)v_{k}\in\mathsf{s p a n}(v_{1},...,v_{k-1})$ . Thus $T-\lambda_{k}I$ maps span $(v_{1},...,v_{k})$ into span $(v_{1},...,v_{k-1})$ ). Because  

$$
\dim\operatorname{span}(v_{1},...,v_{k})=k\quad{\mathrm{and}}\quad\dim\operatorname{span}(v_{1},...,v_{k-1})=k-1,
$$  

this implies that $T-\lambda_{k}I$ restricted to span $(v_{1},...,v_{k})$ is not injective (by 3.22). Thus there exists $v\in\mathrm{span}(v_{1},...,v_{k})$ such that $v\neq0$ and $(T-\lambda_{k}I)v=0$ . Thus $\lambda_{k}$ is an eigenvalue of $T.$ . Hence we have shown that every entry on the diagonal of ${\mathcal{M}}(T)$ is an eigenvalue of $T.$ .  

To prove $T$ has no other eigenvalues, let $q$ be the polynomial defined by $q(z)=(z-\lambda_{1})\cdots(z-\lambda_{n})$ . Then $q(T)=0$ (by 5.40). Hence $q$ is a polynomial multiple of the minimal polynomial of $T\,({\mathrm{by}}\,5.29)$ . Thus every zero of the minimal polynomial of $T$ is a zero of $q$ . Because the zeros of the minimal polynomial of $T$ are the eigenvalues of $T$ (by 5.27), this implies that every eigenvalue of $T$ is a zero of $q$ . Hence the eigenvalues of $T$ are all contained in the list $\lambda_{1},...,\lambda_{n}$ .  

Define $T\in\mathcal{L}(\mathbf{F}^{3})$ by $T(x,y,z)=(2x+y,5y+3z,8z)$ . The matrix of $T$ with respect to the standard basis is  

$$
\mathcal{M}(T)=\left(\begin{array}{c c c}{{2}}&{{1}}&{{0}}\\ {{0}}&{{5}}&{{3}}\\ {{0}}&{{0}}&{{8}}\end{array}\right)\!.
$$  

Now 5.41 implies that the eigenvalues of $T$ are 2, 5, and 8.  

The next example illustrates 5.44: an operator has an upper-triangular matrix with respect to some basis if and only if the minimal polynomial of the operator is the product of polynomials of degree 1.  

5.43 example: whether 𝑇has an upper-triangular matrix can depend on 𝐅 Define $T\in\mathcal{L}(\mathbf{F}^{4})$ by  

$$
T(z_{1},z_{2},z_{3},z_{4})=(-z_{2},z_{1},2z_{1}+3z_{3},z_{3}+3z_{4}).
$$  

Thus with respect to the standard basis of $\mathbf{F}^{4}$ , the matrix of $T$ is  

$$
{\left(\begin{array}{l l l l}{0}&{-1}&{0}&{0}\\ {1}&{0}&{0}&{0}\\ {2}&{0}&{3}&{0}\\ {0}&{0}&{1}&{3}\end{array}\right)}.
$$  

You can ask a computer to verify that the minimal polynomial of $T$ is the polynomial $p$ defined by  

$$
p(z)=9-6z+10z^{2}-6z^{3}+z^{4}.
$$  

First consider the case $\mathbf{F}=\mathbf{R}$ . Then the polynomial $p$ factors as  

$$
p(z)=\bigl(z^{2}+1\bigr)(z-3)(z-3),
$$  

with no further factorization of $z^{2}+1$ as the product of two polynomials of degree 1 with real coefficients. Thus 5.44 states that there does not exist a basis of $\mathbf{R}^{4}$ with respect to which $T$ has an upper-triangular matrix.  

Now consider the case $\mathbf{F}=\mathbf{C}$ . Then the polynomial $p$ factors as  

$$
p(z)=(z-i)(z+i)(z-3)(z-3),
$$  

where all factors above have the form $z\!-\!\lambda_{k}$ . Thus 5.44 states that there is a basis of ${\mathbf{C}}^{4}$ with respect to which $T$ has an upper-triangular matrix. Indeed, you can verify that with respect to the basis $(4-3i,-3-4i,-3+i,1)$ , $(4+3i,-3+4i,-3-i,1)$ , $(0,0,0,1)$ , $(0,0,1,0)$ of ${\mathbf{C}}^{4}$ , the operator $T$ has the upper-triangular matrix  

$$
{\left(\begin{array}{l l l l}{i}&{0}&{0}&{0}\\ {0}&{-i}&{0}&{0}\\ {0}&{0}&{3}&{1}\\ {0}&{0}&{0}&{3}\end{array}\right)}.
$$  

Suppose $V$ is finite-dimensional and $T\ \in\ {\mathcal{L}}(V)$ . Then $T$ has an uppertriangular matrix with respect to some basis of $V$ if and only if the minimal polynomial of $T$ equals $(z-\lambda_{1})\cdots(z-\lambda_{m})$ for some $\lambda_{1},...,\lambda_{m}\in\mathbf{F}$ .  

Proof First suppose $T$ has an upper-triangular matrix with respect to some basis of $V.$ . Let $\alpha_{1},...,\alpha_{n}$ denote the diagonal entries of that matrix. Define a polynomial $q\in\mathcal{P}(\mathbf{F})$ by  

$$
q(z)=(z-\alpha_{1})\cdots(z-\alpha_{n}).
$$  

Then $q(T)=0$ , by 5.40. Hence $q$ is a polynomial multiple of the minimal polynomial of $T$ , by 5.29. Thus the minimal polynomial of $T$ equals $(z-\lambda_{1})\cdots(z-\lambda_{m})$ for some $\lambda_{1},...,\lambda_{m}\in\mathbf{F}$ with $\{\lambda_{1},...,\lambda_{m}\}\subseteq\{\alpha_{1},...,\alpha_{n}\}$ .  

To prove the implication in the other direction, now suppose the minimal polynomial of $T$ equals $(z-\lambda_{1})\cdots(z-\lambda_{m})$ for some $\lambda_{1},...,\lambda_{m}\in\mathbf{F}$ . We will use induction on $m$ . To get started, if $m=1$ then $z-\lambda_{1}$ is the minimal polynomial of $T$ , which implies that $T=\lambda_{1}I$ , which implies that the matrix of $T$ (with respect to any basis of $V$ ) is upper triangular.  

Now suppose $m\,>\,1$ and the desired result holds for all smaller positive integers. Let  

$$
U={\mathrm{range}}(T-\lambda_{m}I).
$$  

From 5.45 and 5.46, we conclude (using 5.39) that $T$ has an upper-triangular matrix with respect to the basis $u_{1},...,u_{M},v_{1},...,v_{N}$ of $V,$ , as desired.  

Then $U$ is invariant under $T$ [this is a special case of 5.18 with $p(z)=z-\lambda_{m}]$ .   
Thus $T|_{U}$ is an operator on $U$ .  

If $u\in U$ , then $u=(T-\lambda_{m}I)v$ for some $v\in V$ and  

$$
(T-\lambda_{1}I)\cdots(T-\lambda_{m-1}I)u=(T-\lambda_{1}I)\cdots(T-\lambda_{m}I)v=0.
$$  

Hence $(z-\lambda_{1})\cdots(z-\lambda_{m-1})$ is a polynomial multiple of the minimal polynomial of $T|_{U}$ , by 5.29. Thus the minimal polynomial of $T|_{U}$ is the product of at most $m-1$ terms of the form $z-\lambda_{k}$ .  

By our induction hypothesis, there is a basis $u_{1},...,u_{M}$ of $U$ with respect to which $T|_{U}$ has an upper-triangular matrix. Thus for each $k\in\{1,...,M\}$ , we have (using 5.39)  

5.45  

$$
T u_{k}=(T|_{U})(u_{k})\in\mathrm{span}(u_{1},...,u_{k}).
$$  

Extend $u_{1},...,u_{M}$ to a basis $u_{1},...,u_{M},v_{1},...,v_{N}$ of $V.$ For each $k\in\{1,...,N\}$ , we have  

$$
T v_{k}=(T-\lambda_{m}I)v_{k}+\lambda_{m}v_{k}.
$$  

The definition of $U$ shows that $(T-\lambda_{m}I)v_{k}\in U=\operatorname{span}(u_{1},...,u_{M})$ . Thus the equation above shows that  

5.46  

$$
T v_{k}\in\operatorname{span}(u_{1},...,u_{M},v_{1},...,v_{k}).
$$  

The set of numbers $\{\lambda_{1},...,\lambda_{m}\}$ from the previous result equals the set of eigenvalues of $T$ (because the set of zeros of the minimal polynomial of $T$ equals the set of eigenvalues of $T,$ , by 5.27), although the list $\lambda_{1},...,\lambda_{m}$ in the previous result may contain repetitions.  

In Chapter 8 we will improve even the wonderful result below; see 8.37 and 8.46.  

5.47 if $\mathbf{F}=\mathbf{C}$ , then every operator on $V$ has an upper-triangular matrix Suppose $V$ is a finite-dimensional complex vector space and $T\in{\mathcal{L}}(V)$ . Then $T$ has an upper-triangular matrix with respect to some basis of $V.$ .  

Proof The desired result follows immediately from 5.44 and the second version of the fundamental theorem of algebra (see 4.13).  

For an extension of the result above to two operators $S$ and $T$ such that  

$$
S T=T S,
$$  

see 5.80. Also, for an extension to more than two operators, see Exercise 9(b) in Section 5E.  

Caution: If an operator $T\in{\mathcal{L}}(V)$ has a upper-triangular matrix with respect to some basis $v_{1},...,v_{n}$ of $V,$ then the eigenvalues of $T$ are exactly the entries on the diagonal of ${\mathcal{M}}(T)$ , as shown by 5.41, and furthermore $v_{1}$ is an eigenvector of $T.$ However, $v_{2},...,v_{n}$ need not be eigenvectors of $T.$ . Indeed, a basis vector $v_{k}$ is an eigenvector of $T$ if and only if all entries in the $k^{\mathrm{th}}$ column of the matrix of $T$ are 0, except possibly the $k^{\mathrm{th}}$ entry.  

You may recall from a previous course that every matrix of numbers can be changed to a matrix in what is called row echelon form. If one begins with a square matrix, the matrix in row echelon form will be an upper-triangular matrix. Do not confuse this upper-triangular matrix with the upper-triangular matrix of an operator with respect to some basis whose existence is proclaimed by 5.47 (if $\mathbf{F}=\mathbf{C}_{\mathrm{{c}}}$ )—there is no connection between these upper-triangular matrices.  

The row echelon form of the matrix of an operator does not give us a list of the eigenvalues of the operator. In contrast, an upper-triangular matrix with respect to some basis gives us a list of all the eigenvalues of the operator. However, there is no method for computing exactly such an uppertriangular matrix, even though 5.47 guarantees its existence if $\mathbf{F}=\mathbf{C}$ .  

1 Prove or give a counterexample: If $T\in{\mathcal{L}}(V)$ and $T^{2}$ has an upper-triangular matrix with respect to some basis of $V,$ then $T$ has an upper-triangular matrix with respect to some basis of $V.$ .  

2 Suppose $A$ and $B$ are upper-triangular matrices of the same size, with $\alpha_{1},...,\alpha_{n}$ on the diagonal of $A$ and $\beta_{1},...,\beta_{n}$ on the diagonal of $B$ .  

(a) Show that $A+B$ is an upper-triangular matrix with $\alpha_{1}+\beta_{1},...,\alpha_{n}+\beta_{n}$ on the diagonal.   
(b) Show that $A B$ is an upper-triangular matrix with $\alpha_{1}\beta_{1},...,\alpha_{n}\beta_{n}$ on the diagonal.  

The results in this exercise are used in the proof of 5.81.  

3 Suppose $T\in{\mathcal{L}}(V)$ is invertible and $v_{1},...,v_{n}$ is a basis of $V$ with respect to which the matrix of $T$ is upper triangular, with $\lambda_{1},...,\lambda_{n}$ on the diagonal. Show that the matrix of $T^{-1}$ is also upper triangular with respect to the basis $v_{1},...,v_{n}$ , with  

$$
{\frac{1}{\lambda_{1}}},...,{\frac{1}{\lambda_{n}}}
$$  

on the diagonal.  

4 Give an example of an operator whose matrix with respect to some basis contains only 0’s on the diagonal, but the operator is invertible.  

This exercise and the exercise below show that 5.41 fails without the hypothesis that an upper-triangular matrix is under consideration.  

5 Give an example of an operator whose matrix with respect to some basis contains only nonzero numbers on the diagonal, but the operator is not invertible.  

6 Suppose $\textbf{F}=\textbf{C}$ , $V$ is finite-dimensional, and $T\,\in\,{\mathcal{L}}(V)$ . Prove that if $k\in\{1,...,\dim V\}$ , then $V$ has a $k$ -dimensional subspace invariant under $T$ .  

7 Suppose $V$ is finite-dimensional, $T\in{\mathcal{L}}(V)$ , and $v\in V.$  

(a) Prove that there exists a unique monic polynomial $p_{v}$ of smallest degree such that $p_{v}(T)v=0$ . (b) Prove that the minimal polynomial of $T$ is a polynomial multiple of $p_{v}$ .  

8 Suppose $V$ is finite-dimensional, $T\,\in\,{\mathcal{L}}(V)$ , and there exists a nonzero vector $v\in V$ such that $T^{2}v+2T v=-2v$ .  

(a) Prove that if $\mathbf{F}=\mathbf{R}$ , then there does not exist a basis of $V$ with respect to which $T$ has an upper-triangular matrix.   
(b) Prove that if $\mathbf{F}\,=\,\mathbf{C}$ and $A$ is an upper-triangular matrix that equals the matrix of $T$ with respect to some basis of $V,$ , then $-1+i$ or $-1-i$ appears on the diagonal of $A$ .  

9 Suppose $B$ is a square matrix with complex entries. Prove that there exists an invertible square matrix $A$ with complex entries such that $A^{-1}B A$ is an upper-triangular matrix.  

10 Suppose $T\in{\mathcal{L}}(V)$ and $v_{1},...,v_{n}$ is a basis of $V.$ Show that the following are equivalent.  

(a) The matrix of $T$ with respect to $v_{1},...,v_{n}$ is lower triangular.   
(b) span $(v_{k},...,v_{n})$ is invariant under $T$ for each $k=1,...,n$ .   
(c) $T v_{k}\in\operatorname{span}(v_{k},...,v_{n})$ for each $k=1,...,n$ . A square matrix is called lower triangular if all entries above the diagonal are 0.  

11 Suppose $\mathbf{F}=\mathbf{C}$ and $V$ is finite-dimensional. Prove that if $T\in{\mathcal{L}}(V)$ , then there exists a basis of $V$ with respect to which $T$ has a lower-triangular matrix.  

12 Suppose $V$ is finite-dimensional, $T\in{\mathcal{L}}(V)$ has an upper-triangular matrix with respect to some basis of $V.$ , and $U$ is a subspace of $V$ that is invariant under $T.$ .  

(a) Prove that $T|_{U}$ has an upper-triangular matrix with respect to some basis of $U$ .   
(b) Prove that the quotient operator $T/U$ has an upper-triangular matrix with respect to some basis of $V/U$ .  

The quotient operator $T/U$ was defined in Exercise 38 in Section 5A.  

13 Suppose $V$ is finite-dimensional and $T\ \in\ {\mathcal{L}}(V)$ . Suppose there exists a subspace $U$ of $V$ that is invariant under $T$ such that $T|_{U}$ has an uppertriangular matrix with respect to some basis of $U$ and also $T/U$ has an upper-triangular matrix with respect to some basis of $V/U$ . Prove that $T$ has an upper-triangular matrix with respect to some basis of $V.$ .  

14 Suppose $V$ is finite-dimensional and $T\in{\mathcal{L}}(V)$ . Prove that $T$ has an uppertriangular matrix with respect to some basis of $V$ if and only if the dual operator $T^{\prime}$ has an upper-triangular matrix with respect to some basis of the dual space $V^{\prime}$ .  

## Diagonal Matrices  

## 5.48 definition: diagonal matrix  

A diagonal matrix is a square matrix that is 0 everywhere except possibly on the diagonal.  

5.49 example: diagonal matrix  

$$
\left(\begin{array}{l l l}{8}&{0}&{0}\\ {0}&{5}&{0}\\ {0}&{0}&{5}\end{array}\right)
$$  

is a diagonal matrix.  

If an operator has a diagonal matrix with respect to some basis, then the entries on the diagonal are precisely the eigenvalues of the operator; this follows from 5.41 (or find an easier direct proof for diagonal matrices).  

Every diagonal matrix is upper triangular. Diagonal matrices typically have many more 0’s than most uppertriangular matrices of the same size.  

## 5.50 definition: diagonalizable  

An operator on $V$ is called diagonalizable if the operator has a diagonal matrix with respect to some basis of $V.$  

5.51 example: diagonalization may require a different basis  

Define $T\in{\mathcal{L}}(\mathbb{R}^{2})$ by  

$$
T(x,y)=(41x+7y,-20x+74y).
$$  

The matrix of $T$ with respect to the standard basis of $\mathbf{R}^{2}$ is  

$$
{\left(\begin{array}{c c}{41}&{7}\\ {-20}&{74}\end{array}\right)},
$$  

which is not a diagonal matrix. However, $T$ is diagonalizable. Specifically, the matrix of $T$ with respect to the basis (1, 4), (7, 5) is  

$$
\left(\begin{array}{c c}{{69}}&{{0}}\\ {{0}}&{{46}}\end{array}\right)
$$  

because $T(1,4)=(69,276)=69(1,4)$ and $T(7,5)=(322,230)=46(7,5).$ .  

For $\lambda\in\mathbf{F}$ , we will find it convenient to have a name and a notation for the set of vectors that an operator $T$ maps to $\lambda$ times the vector.  

## 5.52 definition: eigenspace, $E(\lambda,T)$  

Suppose $T\in{\mathcal{L}}(V)$ and $\lambda\in\mathbf{F}$ . The eigenspace of $T$ corresponding to $\lambda$ is the subspace $E(\lambda,T)$ of $V$ defined by  

$$
E(\lambda,T)=\mathrm{{null}}(T-\lambda I)=\{v\in V:T v=\lambda v\}.
$$  

Hence $E(\lambda,T)$ is the set of all eigenvectors of $T$ corresponding to $\lambda$ , along with the 0 vector.  

For $T\in{\mathcal{L}}(V)$ and $\lambda\in\mathbf{F}$ , the set $E(\lambda,T)$ is a subspace of $V$ because the null space of each linear map on $V$ is a subspace of $V.$ The definitions imply that $\lambda$ is an eigenvalue of $T$ if and only if $E(\lambda,T)\neq\{0\}$ .  

5.53 example: eigenspaces of an operator  

Suppose the matrix of an operator $T\in{\mathcal{L}}(V)$ with respect to a basis $v_{1},v_{2},v_{3}$ of $V$ is the matrix in Example 5.49. Then  

$$
E(8,T)=\mathrm{span}(v_{1}),\quad E(5,T)=\mathrm{span}(v_{2},v_{3}).
$$  

If $\lambda$ is an eigenvalue of an operator $T\in{\mathcal{L}}(V)$ , then $T$ restricted to $E(\lambda,T)$ is just the operator of multiplication by $\lambda$ .  

5.54 sum of eigenspaces is a direct sum  

Suppose $T\in{\mathcal{L}}(V)$ and $\lambda_{1},...,\lambda_{m}$ are distinct eigenvalues of $T.$ Then  

$$
E(\lambda_{1},T)+\cdots+E(\lambda_{m},T)
$$  

is a direct sum. Furthermore, if $V$ is finite-dimensional, then  

$$
\dim E(\lambda_{1},T)+\dots+\dim E(\lambda_{m},T)\leq\dim V.
$$  

Proof To show that $E(\lambda_{1},T)+\cdots+E(\lambda_{m},T)$ is a direct sum, suppose  

$$
v_{1}+\cdots+v_{m}=0,
$$  

where each $v_{k}$ is in $E(\lambda_{k},T)$ . Because eigenvectors corresponding to distinct eigenvalues are linearly independent (by 5.11), this implies that each $v_{k}$ equals 0. Thus $E(\lambda_{1},T)+\cdots+E(\lambda_{m},T)$ is a direct sum (by 1.45), as desired.  

Now suppose $V$ is finite-dimensional. Then  

$$
\begin{array}{r l}&{\dim E(\lambda_{1},T)+\cdots+\dim E(\lambda_{m},T)=\dim\!\big(E(\lambda_{1},T)\oplus\cdots\oplus E(\lambda_{m},T)\big)}\\ &{\qquad\qquad\qquad\qquad\quad\leq\dim V,}\end{array}
$$  

where the first line follows from 3.94 and the second line follows from 2.37.  

The following characterizations of diagonalizable operators will be useful.  

5.55 conditions equivalent to diagonalizability  

Suppose $V$ is finite-dimensional and $T\in{\mathcal{L}}(V)$ . Let $\lambda_{1},...,\lambda_{m}$ denote the distinct eigenvalues of $T.$ . Then the following are equivalent.  

(a) $T$ is diagonalizable.  

(b) $V$ has a basis consisting of eigenvectors of $T$ . (c) $V=E(\lambda_{1},T)\oplus\cdots\oplus E(\lambda_{m},T).$ . (d) $\dim V=\dim E(\lambda_{1},T)+\cdots+\dim E(\lambda_{m},T).$  

Proof An operator $T\in{\mathcal{L}}(V)$ has a diagonal matrix  

$$
\left(\begin{array}{c c c}{{\lambda_{1}}}&{{}}&{{0}}\\ {{}}&{{\ddots}}&{{}}\\ {{0}}&{{}}&{{\lambda_{n}}}\end{array}\right)
$$  

with respect to a basis $v_{1},...,v_{n}$ of $V$ if and only if $T v_{k}=\lambda_{k}v_{k}$ for each $k$ . Thus (a) and (b) are equivalent.  

Suppose (b) holds; thus $V$ has a basis consisting of eigenvectors of $T.$ . Hence every vector in $V$ is a linear combination of eigenvectors of $T$ , which implies that  

$$
V=E(\lambda_{1},T)+\cdots+E(\lambda_{m},T).
$$  

Now 5.54 shows that (c) holds, proving that (b) implies (c).  

That (c) implies (d) follows immediately from 3.94. Finally, suppose (d) holds; thus  

5.56  

$$
\dim V=\dim E(\lambda_{1},T)+\cdots+\dim E(\lambda_{m},T).
$$  

Choose a basis of each $E(\lambda_{k},T)$ ; put all these bases together to form a list $v_{1},...,v_{n}$ of eigenvectors of $T$ , where $n=\dim V$ (by 5.56). To show that this list is linearly independent, suppose  

$$
a_{1}v_{1}+\cdots+a_{n}v_{n}=0,
$$  

where $\textstyle{a_{1},...,a_{n}}\in\mathbf{F}$ . For each $k=1,...,m$ , let $u_{k}$ denote the sum of all the terms $a_{j}v_{j}$ such that $v_{j}\in E(\lambda_{k},T)$ . Thus each $u_{k}$ is in $E(\lambda_{k},T)$ , and  

$$
u_{1}+\cdots+u_{m}=0.
$$  

Because eigenvectors corresponding to distinct eigenvalues are linearly independent (see 5.11), this implies that each $u_{k}$ equals 0. Because each $u_{k}$ is a sum of terms $a_{j}v_{j}$ , where the $v_{j}$ ’s were chosen to be a basis of $E(\lambda_{k},T)$ , this implies that all $a_{j}$ ’s equal 0. Thus $v_{1},...,v_{n}$ is linearly independent and hence is a basis of $V$ (by 2.38). Thus (d) implies (b), completing the proof.  

For additional conditions equivalent to diagonalizability, see 5.62, Exercises 5 and 15 in this section, Exercise 24 in Section 7B, and Exercise 15 in Section 8A.  

As we know, every operator on a finite-dimensional complex vector space has an eigenvalue. However, not every operator on a finite-dimensional complex vector space has enough eigenvectors to be diagonalizable, as shown by the next example.  

## 5.57 example: an operator that is not diagonalizable  

Define an operator $T\in\mathcal{L}(\mathbf{F}^{3})$ by $T(a,b,c)=(b,c,0)$ . The matrix of $T$ with respect to the standard basis of $\mathbf{F}^{3}$ is  

$$
{\left(\begin{array}{l l l}{0}&{1}&{0}\\ {0}&{0}&{1}\\ {0}&{0}&{0}\end{array}\right)},
$$  

which is an upper-triangular matrix but is not a diagonal matrix.  

As you should verify, 0 is the only eigenvalue of $T$ and furthermore  

$$
E(0,T)=\big\{(a,0,0)\in\mathbf{F}^{3}:a\in\mathbf{F}\big\}.
$$  

Hence conditions (b), (c), and (d) of 5.55 fail (of course, because these conditions are equivalent, it is sufficient to check that only one of them fails). Thus condition (a) of 5.55 also fails. Hence $T$ is not diagonalizable, regardless of whether $\mathbf{F}=\mathbf{R}$ or $\mathbf{F}=\mathbf{C}$ .  

The next result shows that if an operator has as many distinct eigenvalues as the dimension of its domain, then the operator is diagonalizable.  

5.58 enough eigenvalues implies diagonalizability  

Suppose $V$ is finite-dimensional and $T\in{\mathcal{L}}(V)$ has dim $V$ distinct eigenvalues.   
Then $T$ is diagonalizable.  

Proof Suppose $T$ has distinct eigenvalues $\lambda_{1},...,\lambda_{\dim V}$ . For each $k$ , let $v_{k}\in V$ be an eigenvector corresponding to the eigenvalue $\lambda_{k}$ . Because eigenvectors corresponding to distinct eigenvalues are linearly independent (see 5.11), $v_{1},...,v_{\mathrm{dim}\,V}$ is linearly independent.  

A linearly independent list of dim $V$ vectors in $V$ is a basis of $V\,(\sec2.38)$ ; thus $v_{1},...,v_{\dim V}$ is a basis of $V.$ With respect to this basis consisting of eigenvectors, $T$ has a diagonal matrix.  

In later chapters we will find additional conditions that imply that certain operators are diagonalizable. For example, see the real spectral theorem (7.29) and the complex spectral theorem (7.31).  

The result above gives a sufficient condition for an operator to be diagonalizable. However, this condition is not necessary. For example, the operator $T$ on $\mathbf{F}^{3}$ defined by $T(x,y,z)=(6x,6y,7z)$ has only two eigenvalues (6 and 7) and dim $\mathbf{\nabla}_{|}\mathbf{F}^{3}=3$ , but $T$ is diagonalizable (by the standard basis of $\mathbf{F}^{3}$ ).  

The next example illustrates the importance of diagonalization, which can be used to compute high powers of an operator, taking advantage of the equation $T^{k}v=\lambda^{k}v$ if $v$ is an eigenvector of $T$ with eigenvalue $\lambda$ .  

For a spectacular application of these techniques, see Exercise 21, which shows how to use diagonalization to find an exact formula for the $n^{t h}$ term of the Fibonacci sequence.  

5.59 example: using diagonalization to compute $T^{100}$  

Define $T\in{\mathcal{L}}(\mathbf{F}^{3})$ by $T(x,y,z)=(2x+y,5y+3z,8z)$ . With respect to the standard basis, the matrix of $T$ is  

$$
{\left(\begin{array}{l l l}{2}&{1}&{0}\\ {0}&{5}&{3}\\ {0}&{0}&{8}\end{array}\right)}.
$$  

The matrix above is an upper-triangular matrix but it is not a diagonal matrix. By 5.41, the eigenvalues of $T$ are 2, 5, and 8. Because $T$ is an operator on a vector space of dimension three and $T$ has three distinct eigenvalues, 5.58 assures us that there exists a basis of $\mathbf{F}^{3}$ with respect to which $T$ has a diagonal matrix.  

To find this basis, we only have to find an eigenvector for each eigenvalue. In other words, we have to find a nonzero solution to the equation  

$$
T(x,y,z)=\lambda(x,y,z)
$$  

for $\lambda=2$ , then for $\lambda=5$ , and then for $\lambda=8$ . Solving these simple equations shows that for $\lambda\,=\,2$ we have an eigenvector $(1,0,0)$ , for $\lambda\,=\,5$ we have an eigenvector (1, 3, 0), and for $\lambda=8$ we have an eigenvector (1, 6, 6).  

Thus $(1,0,0)$ , (1, 3, 0), (1, 6, 6) is a basis of $\mathbf{F}^{3}$ consisting of eigenvectors of $T$ , and with respect to this basis the matrix of $T$ is the diagonal matrix  

$$
{\left(\begin{array}{l l l}{2}&{0}&{0}\\ {0}&{5}&{0}\\ {0}&{0}&{8}\end{array}\right)}.
$$  

To compute $T^{100}(0,0,1)$ , for example, write $(0,0,1)$ as a linear combination of our basis of eigenvectors:  

$$
\begin{array}{r}{(0,0,1)=\frac{1}{6}(1,0,0)-\frac{1}{3}(1,3,0)+\frac{1}{6}(1,6,6).}\end{array}
$$  

Now apply $T^{100}$ to both sides of the equation above, getting  

$$
\begin{array}{r l}&{T^{100}(0,0,1)=\frac{1}{6}\Big(T^{100}(1,0,0)\Big)-\frac{1}{3}\Big(T^{100}(1,3,0)\Big)+\frac{1}{6}\Big(T^{100}(1,6,6)\Big)}\\ &{\qquad\qquad\qquad=\frac{1}{6}\Big(2^{100}(1,0,0)-2\cdot5^{100}(1,3,0)+8^{100}(1,6,6)\Big)}\\ &{\qquad\qquad\qquad=\frac{1}{6}\Big(2^{100}-2\cdot5^{100}+8^{100},\,6\cdot8^{100}-6\cdot5^{100},\,6\cdot8^{100}\Big).}\end{array}
$$  

We saw earlier that an operator $T$ on a finite-dimensional vector space $V$ has an upper-triangular matrix with respect to some basis of $V$ if and only if the minimal polynomial of $T$ equals $(z-\lambda_{1})\cdots(z-\lambda_{m})$ for some $\lambda_{1},...,\lambda_{m}\in\mathbf{F}$ (see 5.44). As we previously noted (see 5.47), this condition is always satisfied if $\mathbf{F}=\mathbf{C}$ .  

Our next result 5.62 states that an operator $T\in{\mathcal{L}}(V)$ has a diagonal matrix with respect to some basis of $V$ if and only if the minimal polynomial of $T$ equals $(z-\lambda_{1})\cdots(z-\lambda_{m})$ for some distinct $\lambda_{1},...,\lambda_{m}\in\mathbf{F}$ . Before formally stating this result, we give two examples of using it.  

5.60 example: diagonalizable, but with no known exact eigenvalues  

Define $T\in{\mathcal{L}}(\mathbf{C}^{5})$ by  

$$
T(z_{1},z_{2},z_{3},z_{4},z_{5})=(-3z_{5},z_{1}+6z_{5},z_{2},z_{3},z_{4}).
$$  

The matrix of $T$ is shown in Example 5.26, where we showed that the minimal polynomial of $T$ is $3-6z+z^{5}$ .  

As mentioned in Example 5.28, no exact expression is known for any of the zeros of this polynomial, but numeric techniques show that the zeros of this polynomial are approximately $-1.67$ , 0.51, 1.40, $-0.12+1.59i$ , $-0.12-1.59i$ .  

The software that produces these approximations is accurate to more than three digits. Thus these approximations are good enough to show that the five numbers above are distinct. The minimal polynomial of $T$ equals the fifth degree monic polynomial with these zeros. Now 5.62 shows that $T$ is diagonalizable.  

5.61 example: showing that an operator is not diagonalizable  

Define $T\in\mathcal{L}(\mathbf{F}^{3})$ by  

$$
T(z_{1},z_{2},z_{3})=(6z_{1}+3z_{2}+4z_{3},6z_{2}+2z_{3},7z_{3}).
$$  

The matrix of $T$ with respect to the standard basis of $\mathbf{F}^{3}$ is  

$$
{\left(\begin{array}{l l l}{6}&{3}&{4}\\ {0}&{6}&{2}\\ {0}&{0}&{7}\end{array}\right)}.
$$  

The matrix above is an upper-triangular matrix but is not a diagonal matrix. Might $T$ have a diagonal matrix with respect to some other basis of $\mathbf{F}^{3}$ ?  

To answer this question, we will find the minimal polynomial of $T.$ . First note that the eigenvalues of $T$ are the diagonal entries of the matrix above (by 5.41). Thus the zeros of the minimal polynomial of $T$ are $6,7\left[{\bf b y}\,5.27({\bf a})\right]$ . The diagonal of the matrix above tells us that $(T-6I)^{2}(T-7I)=0$ (by 5.40). The minimal polynomial of $T$ has degree at most 3 (by 5.22). Putting all this together, we see that the minimal polynomial of $T$ is either $(z-6)(z-7)$ or $(z-6)^{2}(z-7)$ .  

A simple computation shows that $(T-6I)(T-7I)\neq0$ . Thus the minimal polynomial of $T$ is $(z-6)^{2}(z-7)$ .  

Now 5.62 shows that $T$ is not diagonalizable.  

Suppose $V$ is finite-dimensional and $T\in{\mathcal{L}}(V)$ . Then $T$ is diagonalizable if and only if the minimal polynomial of $T$ equals $(z-\lambda_{1})\cdots(z-\lambda_{m})$ for some list of distinct numbers $\lambda_{1},...,\lambda_{m}\in\mathbf{F}$ .  

Proof First suppose $T$ is diagonalizable. Thus there is a basis $v_{1},...,v_{n}$ of $V$ consisting of eigenvectors of $T$ . Let $\lambda_{1},...,\lambda_{m}$ be the distinct eigenvalues of $T.$ . Then for each $v_{j}$ , there exists $\lambda_{k}$ with $(T-\lambda_{k}I)v_{j}=0$ . Thus  

$$
(T-\lambda_{1}I)\cdots(T-\lambda_{m}I)v_{j}=0,
$$  

which implies that the minimal polynomial of $T$ equals $(z-\lambda_{1})\cdots(z-\lambda_{m})$ .  

To prove the implication in the other direction, now suppose the minimal polynomial of $T$ equals $(z-\lambda_{1})\cdots(z-\lambda_{m})$ for some list of distinct numbers $\lambda_{1},...,\lambda_{m}\in\mathbf{F}$ . Thus  

5.63  

$$
(T-\lambda_{1}I)\cdots(T-\lambda_{m}I)=0.
$$  

We will prove that $T$ is diagonalizable by induction on $m$ . To get started, suppose $m=1$ . Then $T-\lambda_{1}I=0$ , which means that $T$ is a scalar multiple of the identity operator, which implies that $T$ is diagonalizable.  

Now suppose that $m>1$ and the desired result holds for all smaller values of $m$ . The subspace range $(T-\lambda_{m}I)$ is invariant under $T$ [this is a special case of 5.18 with $p(z)=z-\lambda_{m}]$ . Thus $T$ restricted to range $(T-\lambda_{m}I)$ is an operator on range $(T-\lambda_{m}I)$ .  

If $u\in$ range $(T-\lambda_{m}I)$ , then $u=(T\!-\!\lambda_{m}I)v$ for some $v\in V,$ , and 5.63 implies  

$$
(T-\lambda_{1}I)\cdots(T-\lambda_{m-1}I)u=(T-\lambda_{1}I)\cdots(T-\lambda_{m}I)v=0.
$$  

Hence $(z-\lambda_{1})\cdots(z-\lambda_{m-1})$ is a polynomial multiple of the minimal polynomial of $T$ restricted to range $(T-\lambda_{m}I)$ [by 5.29]. Thus by our induction hypothesis, there is a basis of range $(T-\lambda_{m}I)$ consisting of eigenvectors of $T$ .  

Suppose that $u\in$ range $(T-\lambda_{m}I)$ $\cap$ null $(T-\lambda_{m}I)$ . Then $T u=\lambda_{m}u$ . Now 5.64 implies that  

$$
\begin{array}{r l}&{0=(T-\lambda_{1}I)\cdots(T-\lambda_{m-1}I)u}\\ &{\quad=(\lambda_{m}-\lambda_{1})\cdots(\lambda_{m}-\lambda_{m-1})u.}\end{array}
$$  

Because $\lambda_{1},...,\lambda_{m}$ are distinct, the equation above implies that $u\,=\,0$ . Hence range $(T-\lambda_{m}I)\mid$ ∩null $(T-\lambda_{m}I)=\{0\}$ .  

Thus range $(T\!-\!\lambda_{m}I)\!+\!\mathrm{null}(T\!-\!\lambda_{m}I)$ is a direct sum (by 1.46) whose dimension is dim $V$ (by 3.94 and 3.21). Hence range $(T-\lambda_{m}I)\oplus\mathrm{null}(T-\lambda_{m}I)=V.$ Every vector in null $(T-\lambda_{m}I)$ is an eigenvector of $T$ with eigenvalue $\lambda_{m}$ . Earlier in this proof we saw that there is a basis of range $(T-\lambda_{m}I)$ consisting of eigenvectors of $T.$ . Adjoining to that basis a basis of null $(T-\lambda_{m}I)$ gives a basis of $V$ consisting of eigenvectors of $T.$ . The matrix of $T$ with respect to this basis is a diagonal matrix, as desired.  

No formula exists for the zeros of polynomials of degree 5 or greater. However, the previous result can be used to determine whether an operator on a complex vector space is diagonalizable without even finding approximations of the zeros of the minimal polynomial—see Exercise 15.  

The next result will be a key tool when we prove a result about the simultaneous diagonalization of two operators; see 5.76. Note how the use of the characterization of diagonalizable operators in terms of the minimal polynomial (see 5.62) leads to a short proof of the next result.  

5.65 restriction of diagonalizable operator to invariant subspace  

Suppose $T\in{\mathcal{L}}(V)$ is diagonalizable and $U$ is a subspace of $V$ that is invariant under $T.$ Then $T|_{U}$ is a diagonalizable operator on $U$ .  

Proof Because the operator $T$ is diagonalizable, the minimal polynomial of $T$ equals $(z-\lambda_{1})\cdots(z-\lambda_{m})$ for some list of distinct numbers $\lambda_{1},...,\lambda_{m}\in\mathbf{F}$ (by 5.62). The minimal polynomial of $T$ is a polynomial multiple of the minimal polynomial of $T|_{U}$ (by 5.31). Hence the minimal polynomial of $T|_{U}$ has the form required by 5.62, which shows that $T|_{U}$ is diagonalizable.  

## Gershgorin Disk Theorem  

## 5.66 definition: Gershgorin disks  

Suppose $T\in{\mathcal{L}}(V)$ and $v_{1},...,v_{n}$ is a basis of $V.$ . Let $A$ denote the matrix of $T$ with respect to this basis. A Gershgorin disk of $T$ with respect to the basis $v_{1},...,v_{n}$ is a set of the form  

$$
\left\{z\in\mathbf{F}:|z-A_{j,j}|\leq\sum_{\stackrel{k=1}{k\neq j}}^{n}|A_{j,k}|\right\},
$$  

where $j\in\{1,...,n\}$ .  

Because there are $n$ choices for $j$ in the definition above, $T$ has $n$ Gershgorin disks. If $\mathbf{F}=\mathbf{C}$ , then for each $j\in\{1,...,n\}$ , the corresponding Gershgorin disk is a closed disk in $\mathbf{C}$ centered at $A_{j,j}$ , which is the $j^{\mathrm{th}}$ entry on the diagonal of $A$ . The radius of this closed disk is the sum of the absolute values of the entries in row $j$ of $A$ , excluding the diagonal entry. If $\mathbf{F}=\mathbf{R}$ , then the Gershgorin disks are closed intervals in $\mathbf{R}$ .  

In the special case that the square matrix $A$ above is a diagonal matrix, each Gershgorin disk consists of a single point that is a diagonal entry of $A$ (and each eigenvalue of $T$ is one of those points, as required by the next result). One consequence of our next result is that if the nondiagonal entries of $A$ are small, then each eigenvalue of $T$ is near a diagonal entry of $A$ .  

Suppose $T\in{\mathcal{L}}(V)$ and $v_{1},...,v_{n}$ is a basis of $V$ . Then each eigenvalue of $T$ is contained in some Gershgorin disk of $T$ with respect to the basis $v_{1},...,v_{n}.$  

Proof Suppose $\lambda\in\mathbf{F}$ is an eigenvalue of $T$ . Let $w\in V$ be a corresponding eigenvector. There exist $c_{1},...,c_{n}\in\mathbf{F}$ such that  

5.68  

$$
w=c_{1}v_{1}+\cdots+c_{n}v_{n}.
$$  

Let $A$ denote the matrix of $T$ with respect to the basis $v_{1},...,v_{n}$ . Applying $T$ to both sides of the equation above gives  

5.69  

$$
\begin{array}{l}{\displaystyle\lambda w=\sum_{k=1}^{n}\displaystyle c_{k}T v_{k}}\\ {\displaystyle\qquad=\sum_{k=1}^{n}\displaystyle c_{k}\sum_{j=1}^{n}\displaystyle A_{j,k}v_{j}}\\ {\displaystyle\qquad=\sum_{j=1}^{n}\biggl(\sum_{k=1}^{n}A_{j,k}c_{k}\biggr)v_{j}.}\end{array}
$$  

5.70  

Let $j\in\{1,...,n\}$ be such that  

$$
|c_{j}|=\operatorname*{max}\{|c_{1}|,...,|c_{n}|\}.
$$  

Using 5.68, we see that the coefficient of $v_{j}$ on the left side of 5.69 equals $\lambda c_{j}$ , which must equal the coefficient of $v_{j}$ on the right side of 5.70. In other words,  

$$
\lambda c_{j}=\sum_{k\,=\,1}^{n}A_{j,k}\,c_{k}.
$$  

Subtract $A_{j,j}\,c_{j}$ from each side of the equation above and then divide both sides by $c_{j}$ to get  

$$
\begin{array}{r l r}{\lefteqn{|\lambda-A_{j,j}|=\bigg|\sum_{\stackrel{k=1}{k\neq j}}^{n}A_{j,k}\frac{c_{k}}{c_{j}}\bigg|}}\\ &{}&{\leq\displaystyle\sum_{\stackrel{k=1}{k\neq j}}^{n}|A_{j,k}|.}\end{array}
$$  

Thus $\lambda$ is in the $j^{\mathrm{th}}$ Gershgorin disk with respect to the basis $v_{1},...,v_{n}$ .  

Exercise 22 gives a nice application of the Gershgorin disk theorem.  

Exercise 23 states that the radius of each Gershgorin disk could be changed  

The Gershgorin disk theorem is named for Semyon Aronovich Gershgorin, who published this result in 1931.  

to the sum of the absolute values of corresponding column entries (instead of row entries), excluding the diagonal entry, and the theorem above would still hold.  

1 Suppose $V$ is a finite-dimensional complex vector space and $T\in{\mathcal{L}}(V)$ .  

(a) Prove that if $T^{4}=I$ , then $T$ is diagonalizable.   
(b) Prove that if $T^{4}=T.$ , then $T$ is diagonalizable.   
(c) Give an example of an operator $T\in{\mathcal{L}}(\mathbf{C}^{2})$ such that $T^{4}=T^{2}$ and $T$ is not diagonalizable.  

2 Suppose $T\,\in\,{\mathcal{L}}(V)$ has a diagonal matrix $A$ with respect to some basis of $V.$ . Prove that if $\lambda\in\mathbf{F}$ , then $\lambda$ appears on the diagonal of $A$ precisely dim $E(\lambda,T)$ times.  

3 Suppose $V$ is finite-dimensional and $T\in{\mathcal{L}}(V)$ . Prove that if the operator $T$ is diagonalizable, then $V=\mathrm{null}\,T\oplus$ range $T$ .  

4 Suppose $V$ is finite-dimensional and $T\in{\mathcal{L}}(V)$ . Prove that the following are equivalent.  

(a) $V=\mathrm{null}\,T\oplus$ range $T.$ . (b) $V=\mathrm{null}\,T+$ range $T.$ . (c) null $T\cap$ range $T=\{0\}$  

5 Suppose $V$ is a finite-dimensional complex vector space and $T\,\in\,{\mathcal{L}}(V)$ . Prove that $T$ is diagonalizable if and only if  

$$
V=\mathrm{{null}}(T-\lambda I)\oplus\mathrm{{range}}(T-\lambda I)
$$  

for every $\lambda\in\mathbf{C}$ .  

6 Suppose $T\in{\mathcal{L}}(\mathbf{F}^{5})$ and dim $E(8,T)\,=\,4$ . Prove that $T-2I$ or $T-6I$ is invertible.  

7 Suppose $T\in{\mathcal{L}}(V)$ is invertible. Prove that  

$$
\begin{array}{r}{E(\lambda,T)=E\Big(\frac{1}{\lambda},T^{-1}\Big)}\end{array}
$$  

for every $\lambda\in\mathbf{F}$ with $\lambda\ne0$ .  

8 Suppose $V$ is finite-dimensional and $T\in{\mathcal{L}}(V)$ . Let $\lambda_{1},...,\lambda_{m}$ denote the distinct nonzero eigenvalues of $T.$ Prove that  

$$
\dim E(\lambda_{1},T)+\cdots+\dim E(\lambda_{m},T)\leq\dim\operatorname{range}T.
$$  

9 Suppose $R,T\in\mathcal{L}(\mathbf{F}^{3})$ each have 2, 6, 7 as eigenvalues. Prove that there exists an invertible operator $S\in\mathcal{L}(\mathbf{F}^{3})$ such that $R=S^{-1}T S$ .  

10 Find $R,T\in\mathcal{L}(\mathbf{F}^{4})$ such that $R$ and $T$ each have 2, 6, 7 as eigenvalues, $R$ and $T$ have no other eigenvalues, and there does not exist an invertible operator $S\in{\mathcal{L}}(\mathbf{F}^{4})$ such that $R=S^{-1}T S$ .  

11 Find $T\in{\mathcal{L}}(C^{3})$ such that 6 and 7 are eigenvalues of $T$ and such that $T$ does not have a diagonal matrix with respect to any basis of $\mathbf{C}^{3}.$ .  

12 Suppose $T\in{\mathcal{L}}(\mathbf{C}^{3})$ is such that 6 and 7 are eigenvalues of $T$ . Furthermore, suppose $T$ does not have a diagonal matrix with respect to any basis of $\mathbf{C}^{3}.$ . Prove that there exists $(z_{1},z_{2},z_{3})\in\mathbf{C}^{3}$ such that  

$$
T(z_{1},z_{2},z_{3})=(6+8z_{1},7+8z_{2},13+8z_{3}).
$$  

13 Suppose $A$ is a diagonal matrix with distinct entries on the diagonal and $B$ is a matrix of the same size as $A$ . Show that $A B=B A$ if and only if $B$ is a diagonal matrix.  

14 (a) Give an example of a finite-dimensional complex vector space and an operator $T$ on that vector space such that $T^{2}$ is diagonalizable but $T$ is not diagonalizable. (b) Suppose ${\textbf{F}}={\textbf{C}}$ , $k$ is a positive integer, and $T\,\in\,{\mathcal{L}}(V)$ is invertible. Prove that $T$ is diagonalizable if and only if $T^{k}$ is diagonalizable.  

15 Suppose $V$ is a finite-dimensional complex vector space, $T\in{\mathcal{L}}(V)$ , and $p$ is the minimal polynomial of $T.$ . Prove that the following are equivalent. (a) $T$ is diagonalizable.  

(b) There does not exist $\lambda\in\mathbf{C}$ such that $p$ is a polynomial multiple of $(z-\lambda)^{2}$ .  

(c) $p$ and its derivative $p^{\prime}$ have no zeros in common.   
(d) The greatest common divisor of $p$ and $p^{\prime}$ is the constant polynomial 1.  

The greatest common divisor of $p$ and $p^{\prime}$ is the monic polynomial 𝑞of largest degree such that $p$ and $p^{\prime}$ are both polynomial multiples of 𝑞. The Euclidean algorithm for polynomials (look it up) can quickly determine the greatest common divisor of two polynomials, without requiring any information about the zeros of the polynomials. Thus the equivalence of $(a)$ and $(d)$ above shows that we can determine whether $T$ is diagonalizable without knowing anything about the zeros of $p$ .  

16 Suppose that $T\in{\mathcal{L}}(V)$ is diagonalizable. Let $\lambda_{1},...,\lambda_{m}$ denote the distinct eigenvalues of $T.$ Prove that a subspace $U$ of $V$ is invariant under $T$ if and only if there exist subspaces $U_{1},...,U_{m}$ of $V$ such that $U_{k}\subseteq E(\lambda_{k},T)$ for each $k$ and $U=U_{1}\oplus\cdots\oplus U_{m}$ .  

17 Suppose $V$ is finite-dimensional. Prove that ${\mathcal{L}}(V)$ has a basis consisting of diagonalizable operators.  

18 Suppose that $T\in{\mathcal{L}}(V)$ is diagonalizable and $U$ is a subspace of $V$ that is invariant under $T.$ Prove that the quotient operator $T/U$ is a diagonalizable operator on $V/U$ .  

The quotient operator $T/U$ was defined in Exercise 38 in Section 5A.  

19 Prove or give a counterexample: If $T\in{\mathcal{L}}(V)$ and there exists a subspace $U$ of $V$ that is invariant under $T$ such that $T|_{U}$ and $T/U$ are both diagonalizable, then $T$ is diagonalizable.  

See Exercise 13 in Section $5C$ for an analogous statement about uppertriangular matrices.  

20 Suppose $V$ is finite-dimensional and $T\in{\mathcal{L}}(V)$ . Prove that $T$ is diagonalizable if and only if the dual operator $T^{\prime}$ is diagonalizable.  

21 The Fibonacci sequence $F_{0},F_{1},F_{2},\dots$ is defined by  

Define $T\in{\mathcal{L}}(\mathbb{R}^{2})$ by $T(x,y)=(y,x+y)$ .  

(a) Show that $T^{n}(0,1)=(F_{n},F_{n+1})$ for each nonnegative integer $n$ . (b) Find the eigenvalues of $T.$ . (c) Find a basis of $\mathbf{R}^{2}$ consisting of eigenvectors of $T$ . (d) Use the solution to (c) to compute $T^{n}(0,1)$ . Conclude that  

$$
F_{n}={\frac{1}{\sqrt{5}}}\Biggl[\left({\frac{1+{\sqrt{5}}}{2}}\right)^{n}-\left({\frac{1-{\sqrt{5}}}{2}}\right)^{n}\Biggr]
$$  

for each nonnegative integer $n$ .  

(e) Use (d) to conclude that if $n$ is a nonnegative integer, then the Fibonacci number $F_{n}$ is the integer that is closest to  

$$
{\frac{1}{\sqrt{5}}}\biggl({\frac{1+{\sqrt{5}}}{2}}\biggr)^{n}.
$$  

Each $F_{n}$ is a nonnegative integer, even though the right side of the formula in $(d)$ does not look like an integer. The number  

$$
\frac{1+{\sqrt{5}}}{2}
$$  

is called the golden ratio.  

22 Suppose $T\in{\mathcal{L}}(V)$ and $A$ is an $n$ -by- $\cdot n$ matrix that is the matrix of $T$ with respect to some basis of $V$ . Prove that if  

$$
|A_{j,j}|>\sum_{\stackrel{k\,=\,1}{k\,\neq\,j}}^{n}|A_{j,k}|
$$  

for each $j\in\{1,...,n\}$ , then $T$ is invertible.  

This exercise states that if the diagonal entries of the matrix of 𝑇are large compared to the nondiagonal entries, then $T$ is invertible.  

23 Suppose the definition of the Gershgorin disks is changed so that the radius of the $k^{\mathrm{{th}}}$ disk is the sum of the absolute values of the entries in column (instead of row) $k$ of $A$ , excluding the diagonal entry. Show that the Gershgorin disk theorem (5.67) still holds with this changed definition.  

## 5.71 definition: commute  

• Two operators $S$ and $T$ on the same vector space commute if $S T=T S$ .  

• Two square matrices $A$ and $B$ of the same size commute if $A B=B A$ .  

For example, if $T$ is an operator and $p,q\in\mathcal{P}(\mathbf{F})$ , then $p(T)$ and $q(T)$ commute [see 5.17(b)].  

As another example, if $I$ is the identity operator on $V,$ , then $I$ commutes with every operator on $V.$ .  

5.72 example: partial differentiation operators commute  

Suppose 𝑚is a nonnegative integer. Let $\mathcal{P}_{m}(\mathbf{R}^{2})$ denote the real vector space of polynomials (with real coefficients) in two real variables and of degree at most $m$ , with the usual operations of addition and scalar multiplication of real-valued functions. Thus the elements of $\mathcal{P}_{m}(\mathbf{R}^{2})$ are functions $p$ on $\mathbf{R}^{2}$ of the form  

$$
p=\sum_{j\,+\,k\,\leq\,m}a_{j,k}x^{j}y^{k},
$$  

where the indices $j$ and $k$ take on all nonnegative integer values such that $j+k\leq m$ , each $a_{j,k}$ is in $\mathbf{R}$ , and $x^{j}y^{k}$ denotes the function on $\mathbf{R}^{2}$ defined by $(x,y)\mapsto x^{j}y^{k}$ .  

Define operators $D_{x},D_{y}\in\mathcal{L}(\mathcal{P}_{m}(\mathbb{R}^{2}))$ by  

$$
D_{x}p=\frac{\partial p}{\partial x}=\sum_{j+k\leq m}j a_{j,k}x^{j-1}y^{k}\quad{\mathrm{and}}\quad D_{y}p=\frac{\partial p}{\partial y}=\sum_{j+k\leq m}k a_{j,k}x^{j}y^{k-1}
$$  

where $p$ is as in 5.73. The operators $D_{x}$ and $D_{y}$ are called partial differentiation operators because each of these operators differentiates with respect to one of the variables while pretending that the other variable is a constant.  

The operators $D_{x}$ and $D_{y}$ commute because if $p$ is as in 5.73, then  

$$
(D_{x}D_{y})p=\sum_{j+k\leq m}j k a_{j,k}x^{j-1}y^{k-1}=(D_{y}D_{x})p.
$$  

The equation $D_{x}D_{y}=D_{y}D_{x}$ on $\mathcal{P}_{m}(\mathbf{R}^{2})$ illustrates a more general result that the order of partial differentiation does not matter for nice functions.  

Commuting matrices are unusual. For example, there are 214,358,881 pairs of 2-by-2 matrices all of whose entries are integers in the interval [−5, 5]. Only about $0.3\%$ of these pairs of matrices commute.  

All 214,358,881 (which equals 118) pairs of the 2-by-2 matrices under consideration were checked by a computer to discover that only 674,609 of these pairs of matrices commute.  

The next result shows that two operators commute if and only if their matrices (with respect to the same basis) commute.  

## 5.74 commuting operators correspond to commuting matrices  

Suppose $S,T\in{\mathcal{L}}(V)$ and $v_{1},...,v_{n}$ is a basis of $V.$ . Then $S$ and $T$ commute if and only if $\mathcal{M}(S,(v_{1},...,v_{n}))$ and $\mathcal{M}(T,(v_{1},...,v_{n}))$ commute.  

Proof We have  

$$
\begin{array}{r l}&{\mathrm{\re\iff}S T=T S}\\ &{\iff\mathcal{M}(S T)=\mathcal{M}(T S)}\\ &{\iff\mathcal{M}(S)\mathcal{M}(T)=\mathcal{M}(T)\mathcal{M}(S)}\\ &{\iff\mathcal{M}(S)\mathrm{\and~}\mathcal{M}(T)\mathrm{\commute},}\end{array}
$$  

as desired.  

The next result shows that if two operators commute, then every eigenspace for one operator is invariant under the other operator. This result, which we will use several times, is one of the main reasons why a pair of commuting operators behaves better than a pair of operators that does not commute.  

5.75 eigenspace is invariant under commuting operator  

Suppose $S,T\in{\mathcal{L}}(V)$ commute and $\lambda\in\mathbf{F}$ . Then $E(\lambda,S)$ is invariant under $T.$ .  

Proof Suppose $v\in E(\lambda,S)$ . Then  

$$
S(T v)=(S T)v=(T S)v=T(S v)=T(\lambda v)=\lambda T v.
$$  

The equation above shows that $T v\in E(\lambda,S)$ . Thus $E(\lambda,S)$ is invariant under $T.$ .  

Suppose we have two operators, each of which is diagonalizable. If we want to do computations involving both operators (for example, involving their sum), then we want the two operators to be diagonalizable by the same basis, which according to the next result is possible when the two operators commute.  

5.76 simultaneous diagonalizablity $\Longleftrightarrow$ commutativity  

Two diagonalizable operators on the same vector space have diagonal matrices with respect to the same basis if and only if the two operators commute.  

Proof First suppose $S,T\in{\mathcal{L}}(V)$ have diagonal matrices with respect to the same basis. The product of two diagonal matrices of the same size is the diagonal matrix obtained by multiplying the corresponding elements of the two diagonals. Thus any two diagonal matrices of the same size commute. Thus $S$ and $T$ commute, by 5.74.  

To prove the implication in the other direction, now suppose that $S,T\in{\mathcal{L}}(V)$ are diagonalizable operators that commute. Let $\lambda_{1},...,\lambda_{m}$ denote the distinct eigenvalues of $S$ . Because $S$ is diagonalizable, 5.55(c) shows that  

$$
V=E(\lambda_{1},S)\oplus\cdots\oplus E(\lambda_{m},S).
$$  

For each $k=1,...,m$ , the subspace $E(\lambda_{k},S)$ is invariant under $T$ (by 5.75). Because $T$ is diagonalizable, 5.65 implies that $T|_{E(\lambda_{k},S)}$ is diagonalizable for each $k$ . Hence for each $k\,=\,1,...,m$ , there is a basis of $E(\lambda_{k},S)$ consisting of eigenvectors of $T.$ Putting these bases together gives a basis of $V$ (because of 5.77), with each vector in this basis being an eigenvector of both $S$ and $T.$ . Thus $S$ and $T$ both have diagonal matrices with respect to this basis, as desired.  

See Exercise 2 for an extension of the result above to more than two operators.  

Suppose $V$ is a finite-dimensional nonzero complex vector space. Then every operator on $V$ has an eigenvector (see 5.19). The next result shows that if two operators on $V$ commute, then there is a vector in $V$ that is an eigenvector for both operators (but the two commuting operators might not have a common eigenvalue). For an extension of the next result to more than two operators, see Exercise 9(a).  

5.78 common eigenvector for commuting operators  

Every pair of commuting operators on a finite-dimensional nonzero complex vector space has a common eigenvector.  

Proof Suppose $V$ is a finite-dimensional nonzero complex vector space and $S,T\in{\mathcal{L}}(V)$ commute. Let $\lambda$ be an eigenvalue of $S$ (5.19 tells us that $S$ does indeed have an eigenvalue). Thus $E(\lambda,S)\;\neq\;\{0\}$ . Also, $E(\lambda,S)$ is invariant under $T$ (by 5.75).  

Thus $T|_{E(\lambda,S)}$ has an eigenvector (again using 5.19), which is an eigenvector for both $S$ and $T$ , completing the proof.  

5.79 example: common eigenvector for partial differentiation operators  

Let $\mathcal{P}_{m}(\mathbf{R}^{2})$ be as in Example 5.72 and let $D_{x},D_{y}\;\in\;\mathcal{L}\Big(\mathcal{P}_{m}(\mathbf{R}^{2})\Big)$ be the commuting partial differentiation operators in that example. As you can verify, 0 is the only eigenvalue of each of these operators. Also  

$$
\begin{array}{l}{E(0,D_{x})=\Big\{\displaystyle\sum_{k\,=\,0}^{m}a_{k}y^{k}:a_{0},...,a_{m}\in\mathbb{R}\Big\},}\\ {E(0,D_{y})=\Big\{\displaystyle\sum_{j\,=\,0}^{m}c_{j}x^{j}:c_{0},...,c_{m}\in\mathbb{R}\Big\}.}\end{array}
$$  

The intersection of these two eigenspaces is the set of common eigenvectors of the two operators. Because $E(0,D_{x})\cap E(0,D_{y})$ is the set of constant functions, we see that $D_{x}$ and $D_{y}$ indeed have a common eigenvector, as promised by 5.78.  

The next result extends 5.47 (the existence of a basis that gives an uppertriangular matrix) to two commuting operators.  

## 5.80 commuting operators are simultaneously upper triangularizable  

Suppose $V$ is a finite-dimensional complex vector space and $S,T$ are commuting operators on $V.$ Then there is a basis of $V$ with respect to which both $S$ and $T$ have upper-triangular matrices.  

Proof Let $n=\dim V.$ . We will use induction on $n$ . The desired result holds if $n=1$ because all 1-by-1 matrices are upper triangular. Now suppose $n>1$ and the desired result holds for all complex vector spaces whose dimension is $n-1$ .  

Let $v_{1}$ be any common eigenvector of $S$ and $T$ (using 5.78). Hence $S v_{1}\in$ span $(v_{1})$ and $T v_{1}\in\mathrm{span}(v_{1})$ . Let $W$ be a subspace of $V$ such that  

$$
V=\operatorname{span}(v_{1})\oplus W;
$$  

see 2.33 for the existence of $W.$ . Define a linear map $P\colon V\to W$ by  

$$
P(a v_{1}+w)=w
$$  

for each $a\in\mathbf{C}$ and each $w\in W.$ . Define $\hat{S},\hat{T}\in\mathcal{L}(W)$ by  

$$
{\hat{S}}w=P(S w)\quad{\mathrm{and}}\quad{\hat{T}}w=P(T w)
$$  

for each $w\in W.$ To apply our induction hypothesis to $\hat{S}$ and $\hat{T}.$ , we must first show that these two operators on $W$ commute. To do this, suppose $w\in W.$ Then there exists $a\in\mathbf{C}$ such that  

$$
(\hat{S}\hat{T})w=\hat{S}\big(P(T w)\big)=\hat{S}(T w-a v_{1})=P\big(S(T w-a v_{1})\big)=P\big((S T w)w\big),
$$  

where the last equality holds because $v_{1}$ is an eigenvector of $S$ and $P v_{1}\,=\,0$ . Similarly,  

$$
(\hat{T}\hat{S})w=P\big((T S)w\big).
$$  

Because the operators $S$ and $T$ commute, the last two displayed equations show that $(\hat{S}\hat{T})w=(\hat{T}\hat{S})w$ . Hence $\hat{S}$ and𝑇̂commute.  

Thus we can use our induction hypothesis to state that there exists a basis $v_{2},...,v_{n}$ of $W$ such that 𝑆̂and𝑇̂both have upper-triangular matrices with respect to this basis. The list $v_{1},...,v_{n}$ is a basis of $V.$ .  

If $k\in\{2,...,n\}$ , then there exist $a_{k},b_{k}\in\mathbf{C}$ such that  

$$
S v_{k}=a_{k}v_{1}+\hat{S}v_{k}\quad\mathrm{and}\quad T v_{k}=b_{k}v_{1}+\hat{T}v_{k}.
$$  

Because $\hat{S}$ and $\hat{T}$ have upper-triangular matrices with respect to $v_{2},...,v_{n}$ , we know that $\hat{S}v_{k}\in\operatorname{span}(v_{2},...,v_{k})$ and $\hat{T}v_{k}\in\operatorname{span}(v_{2},...,v_{k})$ . Hence the equations above imply that  

$$
S v_{k}\in\operatorname{span}(v_{1},...,v_{k})\quad{\mathrm{and}}\quad T v_{k}\in\operatorname{span}(v_{1},...,v_{k}).
$$  

Thus $S$ and $T$ have upper-triangular matrices with respect to $v_{1},...,v_{n}$ , as desired.  

Exercise 9(b) extends the result above to more than two operators.  

In general, it is not possible to determine the eigenvalues of the sum or product of two operators from the eigenvalues of the two operators. However, the next result shows that something nice happens when the two operators commute.  

## 5.81 eigenvalues of sum and product of commuting operators  

Suppose $V$ is a finite-dimensional complex vector space and $S,T$ are commuting operators on $V.$ Then  

every eigenvalue of $S+T$ is an eigenvalue of $S$ plus an eigenvalue of $T$ ,  

every eigenvalue of $S T$ is an eigenvalue of $S$ times an eigenvalue of $T.$ .  

Proof There is a basis of $V$ with respect to which both $S$ and $T$ have uppertriangular matrices (by 5.80). With respect to that basis,  

$$
\begin{array}{r}{\mathcal{M}(S+T)=\mathcal{M}(S)+\mathcal{M}(T)\quad\mathrm{and}\quad\mathcal{M}(S T)=\mathcal{M}(S)\mathcal{M}(T),}\end{array}
$$  

as stated in 3.35 and 3.43.  

The definition of matrix addition shows that each entry on the diagonal of $\mathcal{M}(S+T)$ equals the sum of the corresponding entries on the diagonals of ${\mathcal{M}}(S)$ and ${\mathcal{M}}(T)$ . Similarly, because ${\mathcal{M}}(S)$ and ${\mathcal{M}}(T)$ are upper-triangular matrices, the definition of matrix multiplication shows that each entry on the diagonal of ${\mathcal{M}}(S T)$ equals the product of the corresponding entries on the diagonals of ${\mathcal{M}}(S)$ and ${\mathcal{M}}(T)$ . Furthermore, $\mathcal{M}(S+T)$ and ${\mathcal{M}}(S T)$ are upper-triangular matrices (see Exercise 2 in Section 5B).  

Every entry on the diagonal of ${\mathcal{M}}(S)$ is an eigenvalue of $S$ , and every entry on the diagonal of ${\mathcal{M}}(T)$ is an eigenvalue of $T$ (by 5.41). Every eigenvalue of $S+T$ is on the diagonal of $\mathcal{M}(S\,+\,T)$ , and every eigenvalue of $S T$ is on the diagonal of ${\mathcal{M}}(S T)$ (these assertions follow from 5.41). Putting all this together, we conclude that every eigenvalue of $S+T$ is an eigenvalue of $S$ plus an eigenvalue of $T$ , and every eigenvalue of $S T$ is an eigenvalue of $S$ times an eigenvalue of $T$ .  

## Exercises 5E  

1 Give an example of two commuting operators $S,T$ on $\mathbf{F}^{4}$ such that there is a subspace of $\mathbf{F}^{4}$ that is invariant under $S$ but not under $T$ and there is a subspace of $\mathbf{F}^{4}$ that is invariant under $T$ but not under $S$ .  

2 Suppose $\mathcal{E}$ is a subset of ${\mathcal{L}}(V)$ and every element of $\mathcal{E}$ is diagonalizable. Prove that there exists a basis of $V$ with respect to which every element of $\mathcal{E}$ has a diagonal matrix if and only if every pair of elements of $\mathcal{E}$ commutes.  

3 Suppose $S,T\in{\mathcal{L}}(V)$ are such that $S T=T S$ . Suppose $p\in\mathcal{P}(\mathbf{F})$ .  

(a) Prove that null $p(S)$ is invariant under $T$ .   
(b) Prove that range $p(S)$ is invariant under $T$ .  

See 5.18 for the special case $S=T.$ .  

4 Prove or give a counterexample: If $A$ is a diagonal matrix and $B$ is an upper-triangular matrix of the same size as $A$ , then $A$ and $B$ commute.  

5 Prove that a pair of operators on a finite-dimensional vector space commute if and only if their dual operators commute.  

See 3.118 for the definition of the dual of an operator.  

6 Suppose $V$ is a finite-dimensional complex vector space and $S,T\in{\mathcal{L}}(V)$ commute. Prove that there exist $\alpha,\lambda\in\mathbf{C}$ such that  

$$
{\mathrm{range}}(S-\alpha I)+{\mathrm{range}}(T-\lambda I)\neq V.
$$  

7 Suppose $V$ is a complex vector space, $S\,\in\,{\mathcal{L}}(V)$ is diagonalizable, and $T\in{\mathcal{L}}(V)$ commutes with 𝑆. Prove that there is a basis of $V$ such that $S$ has a diagonal matrix with respect to this basis and $T$ has an upper-triangular matrix with respect to this basis.  

8 Suppose $m\,=\,3$ in Example 5.72 and $D_{x},D_{y}$ are the commuting partial differentiation operators on $\mathcal{P}_{3}(\mathbf{R}^{2})$ from that example. Find a basis of $\mathcal{P}_{3}(\mathbb{R}^{2})$ with respect to which $D_{x}$ and $D_{y}$ each have an upper-triangular matrix.  

9 Suppose $V$ is a finite-dimensional nonzero complex vector space. Suppose that ${\mathcal{E}}\subseteq{\mathcal{L}}(V)$ is such that $S$ and $T$ commute for all $S,T\in{\mathcal{E}}$ .  

(a) Prove that there is a vector in $V$ that is an eigenvector for every element of $\mathcal{E}$ .   
(b) Prove that there is a basis of $V$ with respect to which every element of $\mathcal{E}$ has an upper-triangular matrix.  

This exercise extends 5.78 and 5.80, which consider the case in which $\mathcal{E}$ contains only two elements. For this exercise, $\mathcal{E}$ may contain any number of elements, and $\mathcal{E}$ may even be an infinite set.  

10 Give an example of two commuting operators $S,T$ on a finite-dimensional real vector space such that $S+T$ has a eigenvalue that does not equal an eigenvalue of 𝑆plus an eigenvalue of $T$ and $S T$ has a eigenvalue that does not equal an eigenvalue of $S$ times an eigenvalue of $T$ .  

This exercise shows that 5.81 does not hold on real vector spaces.  


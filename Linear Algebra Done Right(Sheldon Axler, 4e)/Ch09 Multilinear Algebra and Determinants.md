# Ch09 Multilinear Algebra and Determinants  

We begin this chapter by investigating bilinear forms and quadratic forms on a vector space. Then we will move on to multilinear forms. We will show that the vector space of alternating $n$ -linear forms has dimension one on a vector space of dimension $n$ . This result will allow us to give a clean basis-free definition of the determinant of an operator.  

This approach to the determinant via alternating multilinear forms leads to straightforward proofs of key properties of determinants. For example, we will see that the determinant is multiplicative, meaning that $\operatorname*{det}(S T)=(\operatorname*{det}S)(\operatorname*{det}T)$ for all operators $S$ and $T$ on the same vector space. We will also see that $T$ is invertible if and only if det $T\neq0$ . Another important result states that the determinant of an operator on a complex vector space equals the product of the eigenvalues of the operator, with each eigenvalue included as many times as its multiplicity.  

The chapter concludes with an introduction to tensor products.  

## standing assumptions for this chapter  

• 𝐅 denotes 𝐑 or 𝐂. 𝑉 and 𝑊 denote finite-dimensional nonzero vector spaces over 𝐅.  

## Bilinear Forms  

A bilinear form on $V$ is a function from $V\times V$ to $\mathbf{F}$ that is linear in each slot separately, meaning that if we hold either slot fixed then we have a linear function in the other slot. Here is the formal definition.  

## 9.1 definition: bilinear form  

A bilinear form on $V$ is a function $\beta\colon V\times V\rightarrow\mathbf{F}$ such that  

$$
v\mapsto\beta(v,u)\quad{\mathrm{and}}\quad v\mapsto\beta(u,v)
$$  

are both linear functionals on $V$ for every $u\in V.$  

For example, if $V$ is a real inner product space, then the function that takes an ordered pair $(u,v)\,\in\,V\times V$ to $\langle u,v\rangle$ is a bilinear form on $V.$ . If $V$ is a nonzero complex inner product space, then this function is not a bilinear form because the inner product is not linear in the second slot (complex scalars come out of the second slot as their complex conjugates).  

Recall that the term linear functional, used in the definition above, means a linear function that maps into the scalar field 𝐅. Thus the term bilinear functional would be more consistent terminology than bilinear form, which unfortunately has become standard.  

If $\mathbf{F}=\mathbf{R}$ , then a bilinear form differs from an inner product in that an inner product requires symmetry [meaning that $\beta(v,w)\,=\,\beta(w,v)$ for all $v,w\in V]$ and positive definiteness [meaning that $\beta(v,v)>0$ for all $v\in V\backslash\{0\}]$ , but these properties are not required for a bilinear form.  

9.2 example: bilinear forms • The function $\beta\colon\mathbf{F}^{3}\times\mathbf{F}^{3}\rightarrow\mathbf{F}$ defined by  

$$
\beta\big((x_{1},x_{2},x_{3}),(y_{1},y_{2},y_{3})\big)=x_{1}y_{2}-5x_{2}y_{3}+2x_{3}y_{1}
$$  

is a bilinear form on $\mathbf{F}^{3}$ .  

• Suppose $A$ is an $n$ -by- $_n$ matrix with $A_{j,k}\in\mathbf{F}$ in row $j$ , column $k$ . Define a bilinear form $\beta_{A}$ on $\mathbf{F}^{n}$ by  

$$
\beta_{A}\bigl((x_{1},...,x_{n}),(y_{1},...,y_{n})\bigr)=\sum_{k\,=\,1}^{n}\sum_{j\,=\,1}^{n}A_{j,k}x_{j}y_{k}.
$$  

The first bullet point is a special case of this bullet point with $n=3$ and  

$$
A={\left(\begin{array}{l l l}{0}&{1}&{0}\\ {0}&{0}&{-5}\\ {2}&{0}&{0}\end{array}\right)}.
$$  

• Suppose $V$ is a real inner product space and $T\in{\mathcal{L}}(V)$ . Then the function $\beta\colon V\times V\rightarrow\mathbb{R}$ defined by  

$$
\beta(u,v)=\langle u,T v\rangle
$$  

is a bilinear form on $V.$ .  

• If $n$ is a positive integer, then the function $\beta\colon\mathcal{P}_{n}(\mathbf{R})\times\mathcal{P}_{n}(\mathbf{R})\to\mathbf{R}$ defined by  

$$
\beta(p,q)=p(2)\cdot q^{\prime}(3)
$$  

is a bilinear form on ${\mathcal P}_{n}({\bf R})$ .  

• Suppose $\varphi$ $\rho,\tau\in V_{\cdot}^{\prime}$ . Then the function $\beta\colon V\times V\rightarrow\mathbf{F}$ defined by  

$$
\beta(u,v)=\varphi(u)\cdot\tau(v)
$$  

is a bilinear form on $V.$ .  

• More generally, suppose that $\varphi_{1},...,\varphi_{n},\tau_{1},...,\tau_{n}\,\in\,V^{\prime}$ . Then the function $\beta\colon V\times V\rightarrow\mathbf{F}$ defined by  

$$
\beta(u,v)=\varphi_{1}(u)\cdot\tau_{1}(v)+\cdots+\varphi_{n}(u)\cdot\tau_{n}(v)
$$  

is a bilinear form on $V.$  

A bilinear form on $V$ is a function from $V\times V$ to 𝐅. Because $V\times V$ is a vector space, this raises the question of whether a bilinear form can also be a linear map from $V\times V$ to 𝐅. Note that none of the bilinear forms in 9.2 are linear maps except in some special cases in which the bilinear form is the zero map. Exercise 3 shows that a bilinear form $\beta$ on $V$ is a linear map on $V\times V$ only if $\beta=0$ .  

9.3 definition: 𝑉(2)  

The set of bilinear forms on $V$ is denoted by $V^{(2)}.$  

With the usual operations of addition and scalar multiplication of functions, $V^{(2)}$ is a vector space.  

For $T$ an operator on an $n$ -dimensional vector space $V$ and a basis $e_{1},...,e_{n}$ of $V,$ we used an $n$ -by- $\cdot n$ matrix to provide information about $T.$ . We now do the same thing for bilinear forms on $V.$ .  

9.4 definition: matrix of a bilinear form, $\mathcal{M}(\beta)$  

Suppose $\beta$ is a bilinear form on $V$ and $e_{1},...,e_{n}$ is a basis of $V.$ The matrix of $\beta$ with respect to this basis is the $n$ -by- $_n$ matrix $\mathcal{M}(\beta)$ whose entry $\mathcal{M}(\beta)_{j,k}$ in row $j$ , column $k$ is given by  

$$
\mathcal{M}(\beta)_{j,k}=\beta(e_{j},e_{k}).
$$  

If the basis $e_{1},...,e_{n}$ is not clear from the context, then the notation $\mathcal{M}(\beta,(e_{1},...,e_{n}))$ is used.  

Recall that $\mathbf{F}^{n,n}$ denotes the vector space of $n$ -by- $_n$ matrices with entries in 𝐅 and that dim $\mathbf{F}^{n,n}=n^{2}$ (see 3.39 and 3.40).  

$$
\sqrt{9.5\quad\dim V^{(2)}=(\dim V)^{2}}
$$  

Suppose $e_{1},...,e_{n}$ is a basis of $V.$ Then the map $\beta\mapsto\mathcal{M}(\beta)$ is an isomorphism of $V^{(2)}$ onto $\mathbf{F}^{n,n}$ . Furthermore, $\dim V^{(2)}=(\dim V)^{2}$ .  

Proof The map $\beta\mapsto\mathcal{M}(\beta)$ is clearly a linear map of $V^{(2)}$ into $\mathbf{F}^{n,n}.$ . For $A\in\mathbf{F}^{n,n}.$ , define a bilinear form $\beta_{A}$ on $V$ by  

$$
\beta_{A}(x_{1}e_{1}+\cdots+x_{n}e_{n},y_{1}e_{1}+\cdots+y_{n}e_{n})=\sum_{k\,=\,1}^{n}\sum_{j\,=\,1}^{n}A_{j,k}x_{j}y_{k}
$$  

for $x_{1},...,x_{n},y_{1},...,y_{n}\in\mathbf{F}$ (if $V=\mathbf{F}^{n}$ and $e_{1},...,e_{n}$ is the standard basis of $\mathbf{F}^{n}$ , this $\beta_{A}$ is the same as the bilinear form $\beta_{A}$ in the second bullet point of Example 9.2).  

The linear map $\beta\mapsto\mathcal{M}(\beta)$ from $V^{(2)}$ to $\mathbf{F}^{n,n}$ and the linear map $A\mapsto\beta_{A}$ from $\mathbf{F}^{n,n}$ to $V^{(2)}$ are inverses of each other because $\beta_{\mathcal{M}(\beta)}=\beta$ for all $\beta\in V^{(2)}$ and $\mathcal{M}(\beta_{A})=A$ for all $A\in\mathbf{F}^{n,n};$ , as you should verify.  

Thus both maps are isomorphisms and the two spaces that they connect have the same dimension. Hence dim $V^{(2)}=\dim\mathbf{F}^{n,n}=n^{2}=(\dim V)^{2}$ .  

Recall that $C^{\mathfrak{t}}$ denotes the transpose of a matrix $C$ . The matrix $C^{\mathrm{t}}$ is obtained by interchanging the rows and the columns of $C$ .  

9.6 composition of a bilinear form and an operator  

Suppose $\beta$ is a bilinear form on $V$ and $T\in{\mathcal{L}}(V)$ . Define bilinear forms $\alpha$ and $\rho$ on $V$ by  

$$
\alpha(u,v)=\beta(u,T v)\quad\mathrm{and}\quad\rho(u,v)=\beta(T u,v).
$$  

Let $e_{1},...,e_{n}$ be a basis of $V.$ Then  

$$
\mathcal{M}(\alpha)=\mathcal{M}(\beta)\mathcal{M}(T)\quad\mathrm{and}\quad\mathcal{M}(\rho)=\mathcal{M}(T)^{\mathfrak{t}}\mathcal{M}(\beta).
$$  

Proof If $j,k\in\{1,...,n\}$ , then  

$$
\begin{array}{r l}{\mathcal{M}(\alpha)_{j,k}=\alpha(e_{j},e_{k})}&{}\\ {\quad=\beta(e_{j},T e_{k})}\\ {\quad=\beta\Big(e_{j},\displaystyle\sum_{m=1}^{n}\mathcal{M}(T)_{m,k}\,e_{m}\Big)}\\ {\quad=\displaystyle\sum_{m=1}^{n}\beta(e_{j},e_{m})\mathcal{M}(T)_{m,k}}\\ {\quad=\big(\mathcal{M}(\beta)\mathcal{M}(T)\big)_{j,k}.}\end{array}
$$  

Thus $\mathcal{M}(\alpha)=\mathcal{M}(\beta)\mathcal{M}(T)$ . The proof that $\mathcal{M}(\rho)=\mathcal{M}(T)^{\intercal}\mathcal{M}(\beta)$ is similar.  

The result below shows how the matrix of a bilinear form changes if we change the basis. The formula in the result below should be compared to the changeof-basis formula for the matrix of an operator (see 3.84). The two formulas are similar, except that the transpose $C^{\mathrm{t}}$ appears in the formula below and the inverse $C^{-1}$ appears in the change-of-basis formula for the matrix of an operator.  

9.7 change-of-basis formula  

Suppose $\beta\in V^{(2)}$ . Suppose $e_{1},...,e_{n}$ and $f_{1},...,f_{n}$ are bases of $V.$ . Let  

$$
\begin{array}{r}{A=\mathcal{M}\big(\beta,(e_{1},...,e_{n})\big)\quad\mathrm{and}\quad B=\mathcal{M}\big(\beta,(f_{1},...,f_{n})\big)}\end{array}
$$  

and $C=\mathcal{M}(I,(e_{1},...,e_{n}),(f_{1},...,f_{n}))$ . Then  

$$
A=C^{\mathrm{t}}B C.
$$  

Proof The linear map lemma (3.4) tells us that there exists an operator $T\in{\mathcal{L}}(V)$ such that $T f_{k}=e_{k}$ for each $k=1,...,n$ . The definition of the matrix of an operator with respect to a basis implies that  

$$
\mathcal{M}\big(T,(f_{1},...,f_{n})\big)=C.
$$  

Define bilinear forms $\alpha,\rho$ on $V$ by  

$$
\alpha(u,v)=\beta(u,T v)\quad{\mathrm{and}}\quad\rho(u,v)=\alpha(T u,v)=\beta(T u,T v).
$$  

Then $\beta(e_{j},e_{k})=\beta(T f_{j},T f_{k})=\rho(f_{j},f_{k})$ for all $j,k\in\{1,...,n\}$ . Thus  

$$
\begin{array}{r l}&{A=\mathcal{M}\big(\rho,(f_{1},...,f_{n})\big)}\\ &{\quad=C^{\dagger}\mathcal{M}\big(\alpha,f_{1},...,f_{n}\big)\big)}\\ &{\quad=C^{\dagger}B C,}\end{array}
$$  

where the second and third lines each follow from 9.6.  

9.8 example: the matrix of a bilinear form on ${\mathcal{P}}_{2}(\mathbf{R})$  

Define a bilinear form $\beta$ on ${\mathcal{P}}_{2}(\mathbf{R})$ by $\beta(p,q)=p(2)\cdot q^{\prime}(3)$ . Let  

$$
A=\mathcal{M}\big(\beta,(1,x-2,(x-3)^{2})\big)\quad\mathrm{and}\quad B=\mathcal{M}\big(\beta,(1,x,x^{2})\big)
$$  

and $C=\mathcal{M}\big(I,(1,x-2,(x-3)^{2}),(1,x,x^{2}$ ). Then  

$$
{\begin{array}{r l}{1}&{0}\\ {0}&{0}\\ {1}&{0}\end{array}}\,{\begin{array}{r l}{\operatorname{and}}&{B=\left({\begin{array}{c c c}{0}&{1}&{6}\\ {0}&{2}&{12}\\ {0}&{4}&{24}\end{array}}\right)}\quad{\mathrm{and}}\quad C=\left({\begin{array}{c c c}{1}&{-2}&{9}\\ {0}&{1}&{-6}\\ {0}&{0}&{1}\end{array}}\right).
$$  

Now the change-of-basis formula 9.7 asserts that $A=C^{\mathrm{t}}B C$ , which you can verify with matrix multiplication using the matrices above.  

9.9 definition: symmetric bilinear form, $V_{\mathrm{sym}}^{(2)}$ 1  

A bilinear form $\rho\in V^{(2)}$ is called symmetric if  

$$
\rho(u,w)=\rho(w,u)
$$  

for all $u,w\in V.$ The set of symmetric bilinear forms on $V$ is denoted by $V_{\mathrm{sym}}^{(2)}.$  

9.10 example: symmetric bilinear forms  

• If $V$ is a real inner product space and $\rho\in V^{(2)}$ is defined by  

$$
\rho(u,w)=\langle u,w\rangle,
$$  

then $\rho$ is a symmetric bilinear form on $V.$  

• Suppose $V$ is a real inner product space and $T\in{\mathcal{L}}(V)$ . Define $\rho\in V^{(2)}$ by  

$$
\rho(u,w)=\langle u,T w\rangle.
$$  

Then $\rho$ is a symmetric bilinear form on $V$ if and only if $T$ is a self-adjoint operator (the previous bullet point is the special case $T={\cal I},$ ).  

• Suppose $\rho\colon{\mathcal{L}}(V)\times{\mathcal{L}}(V)\to\mathbf{F}$ is defined by  

$$
\rho(S,T)=\operatorname{tr}(S T).
$$  

Then $\rho$ is a symmetric bilinear form on ${\mathcal{L}}(V)$ because trace is a linear functional on ${\mathcal{L}}(V)$ and $\mathbf{tr}(S T)=\mathbf{tr}(T S)$ for all $S,T\in{\mathcal{L}}(V)$ ; see 8.56.  

## 9.11 definition: symmetric matrix  

A square matrix $A$ is called symmetric if it equals its transpose.  

An operator on $V$ may have a symmetric matrix with respect to some but not all bases of $V.$ In contrast, the next result shows that a bilinear form on $V$ has a symmetric matrix with respect to either all bases of $V$ or with respect to no bases of $V.$  

9.12 symmetric bilinear forms are diagonalizable  

Suppose $\rho\in V^{(2)}$ . Then the following are equivalent.  

(a) $\rho$ is a symmetric bilinear form on $V.$ .  

(b) $\mathcal{M}(\rho,(e_{1},...,e_{n}))$ is a symmetric matrix for every basis $e_{1},...,e_{n}$ of $V.$ (c) $\mathcal{M}(\rho,(e_{1},...,e_{n}))$ is a symmetric matrix for some basis $e_{1},...,e_{n}$ of $V.$ . (d) $\mathcal{M}(\rho,(e_{1},...,e_{n}))$ is a diagonal matrix for some basis $e_{1},...,e_{n}$ of $V.$ .  

Proof First suppose (a) holds, so $\rho$ is a symmetric bilinear form. Suppose $e_{1},...,e_{n}$ is a basis of $V$ and $j,k\in\{1,...,n\}$ . Then $\rho(e_{j},e_{k})=\rho(e_{k},e_{j})$ because $\rho$ is symmetric. Thus $\mathcal{M}(\rho,(e_{1},...,e_{n}))$ is a symmetric matrix, showing that (a) implies (b).  

Clearly (b) implies (c).  

Now suppose (c) holds and $e_{1},...,e_{n}$ is a basis of $V$ such that $\mathcal{M}(\rho,(e_{1},...,e_{n}))$ is a symmetric matrix. Suppose $u,w\in V.$ . There exist $a_{1},...,a_{n},b_{1},...,b_{n}\in\mathbf{F}$ such that $u=a_{1}e_{1}+\cdots+a_{n}e_{n}$ and $w=b_{1}e_{1}+\cdots+b_{n}e_{n}$ . Now  

$$
\begin{array}{r l r}{\lefteqn{\rho(u,w)=\rho\Big(\sum_{j=1}^{n}a_{j}e_{j},\ \sum_{k=1}^{n}b_{k}e_{k}\Big)}}\\ &{}&\\ &{}&{=\sum_{j=1}^{n}\sum_{k=1}^{n}a_{j}b_{k}\rho(e_{j},e_{k})}\\ &{}&\\ &{}&{=\sum_{j=1}^{n}\sum_{k=1}^{n}a_{j}b_{k}\rho(e_{k},e_{j})}\\ &{}&\\ &{}&{=\rho\Big(\sum_{k=1}^{n}b_{k}e_{k},\ \sum_{i=1}^{n}a_{j}e_{j}\Big)}\\ &{}&\\ &{}&{=\rho(w,u),}\end{array}
$$  

where the third line holds because $\mathcal{M}(\boldsymbol{\rho})$ is a symmetric matrix. The equation above shows that $\rho$ is a symmetric bilinear form, proving that (c) implies (a).  

At this point, we have proved that (a), (b), (c) are equivalent. Because every diagonal matrix is symmetric, (d) implies (c). To complete the proof, we will show that (a) implies (d) by induction on $n=\dim V.$ .  

If $n=1$ , then (a) implies (d) because every 1-by-1 matrix is diagonal. Now suppose $n\,>\,1$ and the implication (a) $\Longrightarrow$ (d) holds for one less dimension. Suppose (a) holds, so $\rho$ is a symmetric bilinear form. If $\rho=0$ , then the matrix of $\rho$ with respect to every basis of $V$ is the zero matrix, which is a diagonal matrix. Hence we can assume that $\rho\neq0$ , which means there exist $u,w\in V$ such that $\rho(u,w)\neq0.$ . Now  

$$
2\rho(u,w)=\rho(u+w,u+w)-\rho(u,u)-\rho(w,w).
$$  

Because the left side of the equation above is nonzero, the three terms on the right cannot all equal 0. Hence there exists $v\in V$ such that $\rho(v,v)\neq0$ .  

Let $U\;=\;\{u\;\in\;V\;:\;\rho(u,v)\;=\;0\}$ . Thus $U$ is the null space of the linear functional $u\mapsto\rho(u,v)$ on $V.$ . This linear functional is not the zero linear functional because $v\not\in U$ . Thus dim $U=n-1$ . By our induction hypothesis, there is a basis $e_{1},...,e_{n-1}$ of $U$ such that the symmetric bilinear form $\rho|_{U\times U}$ has a diagonal matrix with respect to this basis.  

Because $v\not\in U$ , the list $e_{1},...,e_{n-1},\tau$ is a basis of $V.$ Suppose $k\in\{1,...,n\!-\!1\}$ . Then $\rho(e_{k},v)\,=\,0$ by the construction of $U$ . Because $\rho$ is symmetric, we also have $\rho(v,e_{k})=0$ . Thus the matrix of $\rho$ with respect to $e_{1},...,e_{n-1},v$ is a diagonal matrix, completing the proof that (a) implies (d).  

The previous result states that every symmetric bilinear form has a diagonal matrix with respect to some basis. If our vector space happens to be a real inner product space, then the next result shows that every symmetric bilinear form has a diagonal matrix with respect to some orthonormal basis. Note that the inner product here is unrelated to the bilinear form.  

## 9.13 diagonalization of a symmetric bilinear form by an orthonormal basis  

Suppose $V$ is a real inner product space and $\rho$ is a symmetric bilinear form on $V.$ Then $\rho$ has a diagonal matrix with respect to some orthonormal basis of $V.$  

Proof Let $f_{1},...,f_{n}$ be an orthonormal basis of $V.$ Let $B=\mathcal{M}(\rho,(f_{1},...,f_{n}))$ . Then $B$ is a symmetric matrix (by 9.12). Let $T\in{\mathcal{L}}(V)$ be the operator such that $\mathcal{M}(T,(f_{1},...,f_{n}))=B$ . Thus $T$ is self-adjoint.  

The real spectral theorem (7.29) states that $T$ has a diagonal matrix with respect to some orthonormal basis $e_{1},...,e_{n}$ of $V.$ Let $C=\mathcal{M}(I,(e_{1},...,e_{n})$ , $(f_{1},...,f_{n}))$ . Thus $C^{-1}T C$ is the matrix of $T$ with respect to the basis $e_{1},...,e_{n}$ (by 3.84). Hence $C^{-1}T C$ is a diagonal matrix. Now  

$$
M(\rho,(e_{1},...,e_{n}))=C^{\mathrm{t}}T C=C^{-1}T C,
$$  

where the first equality holds by 9.7 and the second equality holds because $C$ is a unitary matrix with real entries (which implies that $C^{-1}=C^{\dagger}$ ; see 7.57).  

Now we turn our attention to alternating bilinear forms. Alternating multilinear forms will play a major role in our approach to determinants later in this chapter.  

9.14 definition: alternating bilinear form, $V_{\mathrm{alt}}^{(2)}$  

A bilinear form $\alpha\in V^{(2)}$ is called alternating if  

$$
\alpha(v,v)=0
$$  

for all $v\in V.$ . The set of alternating bilinear forms on $V$ is denoted by $V_{\mathrm{alt}}^{(2)}$ .  

9.15 example: alternating bilinear forms  

• Suppose $n\geq3$ and $\alpha\colon\mathbf{F}^{n}\times\mathbf{F}^{n}\rightarrow\mathbf{F}$ is defined by  

$$
\alpha\big((x_{1},...,x_{n}),(y_{1},...,y_{n})\big)=x_{1}y_{2}-x_{2}y_{1}+x_{1}y_{3}-x_{3}y_{1}.
$$  

Then $\alpha$ is an alternating bilinear form on $\mathbf{F}^{n}.$ .  

• Suppose $\varphi,\tau\in V_{\cdot}^{\prime}$ . Then the bilinear form $\alpha$ on $V$ defined by  

$$
\alpha(u,w)=\varphi(u)\tau(w)-\varphi(w)\tau(u)
$$  

is alternating.  

The next result shows that a bilinear form is alternating if and only if switching the order of the two inputs multiplies the output by $-1$ .  

9.16 characterization of alternating bilinear forms  

A bilinear form $\alpha$ on $V$ is alternating if and only if  

$$
\alpha(u,w)=-\alpha(w,u)
$$  

for all $u,w\in V.$ .  

Proof First suppose that $\alpha$ is alternating. If $u,w\in V,$ then  

$$
\begin{array}{r l}&{0=\alpha(u+w,u+w)}\\ &{\;\;=\alpha(u,u)+\alpha(u,w)+\alpha(w,u)+\alpha(w,w)}\\ &{\;\;=\alpha(u,w)+\alpha(w,u).}\end{array}
$$  

Thus $\alpha(u,w)=-\alpha(w,u)$ , as desired.  

To prove the implication in the other direction, suppose $\alpha(u,w)=-\alpha(w,u)$ for all $u,w\;\in\;V.$ . Then $\alpha(v,v)\,=\,-\alpha(v,v)$ for all $v\,\in\,V,$ which implies that $\alpha(v,v)=0$ for all $v\in V.$ Thus $\alpha$ is alternating.  

Now we show that the vector space of bilinear forms on $V$ is the direct sum of the symmetric bilinear forms on $V$ and the alternating bilinear forms on $V.$ .  

9.17 𝑉(2) = 𝑉s(y2)m ⊕ 𝑉(2) alt  

The sets 𝑉s(y2)m and 𝑉(2) are subspaces of $V^{(2)}$ . Furthermore,  

$$
V^{(2)}=V_{\mathrm{sym}}^{(2)}\oplus V_{\mathrm{alt}}^{(2)}.
$$  

Proof The definition of symmetric bilinear form implies that the sum of any two symmetric bilinear forms on $V$ is a bilinear form on $V,$ and any scalar multiple of any bilinear form on $V$ is a bilinear form on $V.$ Thus $V_{\mathrm{sym}}^{(2)}$ is a subspace of $V^{(2)}$ Similarly, the verification that $V_{\mathrm{alt}}^{(2)}$ is a subspace of $V^{(2)}$ is straightforward.  

Next, we want to show that $\ddot{V^{(2)}}=V_{\mathrm{sym}}^{(2)}+V_{\mathrm{alt}}^{(2)}$ . To do this, suppose $\beta\in V^{(2)}$ . Define $\rho,\alpha\in V^{(2)}$ by  

$$
\rho(u,w)={\frac{\beta(u,w)+\beta(w,u)}{2}}\quad{\mathrm{and}}\quad\alpha(u,w)={\frac{\beta(u,w)-\beta(w,u)}{2}}.
$$  

Then 𝜌∈𝑉s(y2)m and 𝛼∈ 𝑉a(l2t) , and 𝛽= 𝜌+ 𝛼. Thus 𝑉(2) = 𝑉s(y2)m + 𝑉(2) .  

Finally, to show that the intersection of the two subspaces under consideration equals $\{0\}$ , suppose $\beta\in V_{\mathrm{sym}}^{(2)}\cap V_{\mathrm{alt}}^{(2)}$ . Then 9.16 implies that  

$$
\beta(u,w)=-\beta(w,u)=-\beta(u,w)
$$  

for all $u,w\in V,$ , which implies that $\beta=0$ . Thus $V^{(2)}=V_{\mathrm{{sym}}}^{(2)}\oplus V_{\mathrm{{alt}}}^{(2)}$ 𝑉a(l2t) , as implied by 1.46.  

Then $q=q_{\beta}$ , as desired.  

## 9.18 definition: quadratic form associated with a bilinear form, $q_{\beta}$  

For $\beta$ a bilinear form on $V,$ define a function $q_{\beta}\colon V\to\mathbf{F}$ by $q_{\beta}(v)=\beta(v,v)$ . A function $q\colon V\to\mathbf{F}$ is called a quadratic form on $V$ if there exists a bilinear form $\beta$ on $V$ such that $q=q_{\beta}$ .  

Note that if $\beta$ is a bilinear form, then $q_{\beta}=0$ if and only if $\beta$ is alternating.  

9.19 example: quadratic form  

Suppose $\beta$ is the bilinear form on $\mathbf{R}^{3}$ defined by  

$$
\beta\bigl((x_{1},x_{2},x_{3}),(y_{1},y_{2},y_{3})\bigr)=x_{1}y_{1}-4x_{1}y_{2}+8x_{1}y_{3}-3x_{3}y_{3}.
$$  

Then $q_{\beta}$ is the quadratic form on $\mathbf{R}^{3}$ given by the formula  

$$
q_{\beta}(x_{1},x_{2},x_{3})=x_{1}^{\,2}-4x_{1}x_{2}+8x_{1}x_{3}-3x_{3}^{\,2}.
$$  

The quadratic form in the example above is typical of quadratic forms on $\mathbf{F}^{n},$ as shown in the next result.  

## 9.20 quadratic forms on $\mathbf{F}^{n}$  

Suppose $n$ is a positive integer and $q$ is a function from $\mathbf{F}^{n}$ to $\mathbf{F}$ . Then $q$ is a quadratic form on $\mathbf{F}^{n}$ if and only if there exist numbers $A_{j,k}\in\mathbf{F}$ for $j,k\in\{1,...,n\}$ such that  

$$
q(x_{1},...,x_{n})=\sum_{k\,=\,1}^{n}\sum_{j\,=\,1}^{n}A_{j,k}x_{j}x_{k}
$$  

for all $(x_{1},...,x_{n})\in\mathbf{F}^{n}$ .  

Proof First suppose $q$ is a quadratic form on $\mathbf{F}^{n}.$ . Thus there exists a bilinear form $\beta$ on $\mathbf{F}^{n}$ such that $q=q_{\beta}$ . Let $A$ be the matrix of $\beta$ with respect to the standard basis of $\mathbf{F}^{n}.$ Then for all $(x_{1},...,x_{n})\in\mathbf{F}_{:}^{n}$ , we have the desired equation  

$$
q(x_{1},...,x_{n})=\beta{\big(}(x_{1},...,x_{n}),(x_{1},...,x_{n}){\big)}=\sum_{k\,=\,1}^{n}\sum_{j\,=\,1}^{n}A_{j,k}x_{j}x_{k}.
$$  

Conversely, suppose there exist numbers $A_{j,k}\in\mathbf{F}$ for $j,k\in\{1,...,n\}$ such that  

$$
q(x_{1},...,x_{n})=\sum_{k\mathop{=}1}^{n}\sum_{j\mathop{=}1}^{k}A_{j,k}x_{j}x_{k}
$$  

for all $(x_{1},...,x_{n})\in\mathbf{F}^{n}$ . Define a bilinear form $\beta$ on $\mathbf{F}^{n}$ by  

$$
\beta{\big(}(x_{1},...,x_{n}),(y_{1},...,y_{n}){\big)}=\sum_{k=1}^{n}\sum_{j=1}^{k}A_{j,k}x_{j}y_{k}.
$$  

Although quadratic forms are defined in terms of an arbitrary bilinear form, the equivalence of (a) and (b) in the result below shows that a symmetric bilinear form can always be used.  

Thus $q=q_{\rho}$ , completing the proof that (d) implies (a).  

## 9.21 characterization of quadratic forms  

Suppose $q\colon V\to\mathbf{F}$ is a function. The following are equivalent.   
(a) $q$ is a quadratic form.  

(b) There exists a unique symmetric bilinear form $\rho$ on $V$ such that $q=q_{\rho}$ .  

(c) $q(\lambda v)=\lambda^{2}q(v)$ for all $\lambda\in\mathbf{F}$ and all $v\in V,$ and the function  

$$
(u,w)\mapsto q(u+w)-q(u)-q(w)
$$  

is a symmetric bilinear form on $V.$ .  

(d) $q(2v)=4q(v)$ for all $v\in V,$ , and the function  

$$
(u,w)\mapsto q(u+w)-q(u)-q(w)
$$  

is a symmetric bilinear form on $V.$ .  

Proof First suppose (a) holds, so $q$ is a quadratic form. Hence there exists a bilinear form $\beta$ such that $q=q_{\beta}$ . By 9.17, there exist a symmetric bilinear form $\rho$ on $V$ and an alternating bilinear form $\alpha$ on $V$ such that $\beta=\rho+\alpha$ . Now  

$$
q=q_{\beta}=q_{\rho}+q_{\alpha}=q_{\rho}.
$$  

If $\rho^{\prime}\in V_{\mathrm{sym}}^{(2)}$ also satisfies $q_{\rho^{\prime}}=q$ , then $q_{\rho^{\prime}-\rho}=0$ ; thus $\rho^{\prime}-\rho\in V_{\mathrm{sym}}^{(2)}\cap V_{\mathrm{alt}}^{(2)}$ , which implies that $\rho^{\prime}=\rho$ (by 9.17). This completes the proof that (a) implies (b).  

Now suppose (b) holds, so there exists a symmetric bilinear form $\rho$ on $V$ such that $q=q_{\rho}$ . If $\lambda\in\mathbf{F}$ and $v\in V$ then  

$$
q(\lambda v)=\rho(\lambda v,\lambda v)=\lambda\rho(v,\lambda v)=\lambda^{2}\rho(v,v)=\lambda^{2}q(v),
$$  

showing that the first part of (c) holds.  

If $u,w\in V,$ then  

$$
\begin{array}{r}{\jmath(u+w)-q(u)-q(w)=\rho(u+w,u+w)-\rho(u,u)-\rho(w,w)=2\rho(w)\kappa_{w}.}\end{array}
$$  

Thus the function $(u,w)\mapsto q(u\!+\!w)\!-\!q(u)\!-\!q(w)$ equals $2\rho$ , which is a symmetric bilinear form on $V,$ completing the proof that (b) implies (c).  

Clearly (c) implies (d). Now suppose (d) holds. Let $\rho$ be the symmetric bilinear form on $V$ defined by  

$$
\rho(u,w)=\frac{q(u+w)-q(u)-q(w)}{2}.
$$  

If $v\in V,$ then  

$$
\spadesuit(v,v)=\frac{q(2v)-q(v)-q(v)}{2}=\frac{4q(v)-2q(v)}{2}=q(v).
$$  

9.22 example: symmetric bilinear form associated with a quadratic form Suppose $q$ is the quadratic form on $\mathbf{R}^{3}$ given by the formula  

$$
q(x_{1},x_{2},x_{3})=x_{1}^{\,2}-4x_{1}x_{2}+8x_{1}x_{3}-3x_{3}^{\,2}.
$$  

A bilinear form $\beta$ on $\mathbf{R}^{3}$ such that $q\,=\,q_{\beta}$ is given by Example 9.19, but this bilinear form is not symmetric, as promised by 9.21(b). However, the bilinear form $\rho$ on $\mathbf{R}^{3}$ defined by  

𝜌( $\langle x_{1},x_{2},x_{3}\rangle,(y_{1},y_{2},y_{3}))=x_{1}y_{1}-2x_{1}y_{2}-2x_{2}y_{1}+4x_{1}y_{3}+4x_{3}y_{1}-3x_{3}y_{3}$ 3𝑦3 is symmetric and satisfies 𝑞= 𝑞𝜌.  

The next result states that for each quadratic form we can choose a basis such that the quadratic form looks like a weighted sum of squares of the coordinates, meaning that there are no cross terms of the form $x_{j}x_{k}$ with $j\neq k$ .  

9.23 diagonalization of quadratic form  

Suppose $q$ is a quadratic form on $V.$  

(a) There exist a basis $e_{1},...,e_{n}$ of $V$ and $\lambda_{1},...,\lambda_{n}\in\mathbf{F}$ such that  

$$
q(x_{1}e_{1}+\cdots+x_{n}e_{n})=\lambda_{1}x_{1}^{2}+\cdots+\lambda_{n}x_{n}^{2}
$$  

for all $x_{1},...,x_{n}\in\mathbf{F}$ .  

(b) If $\mathbf{F}=\mathbf{R}$ and $V$ is an inner product space, then the basis in (a) can be chosen to be an orthonormal basis of $V.$  

## Proof  

(a) There exists a symmetric bilinear form $\rho$ on $V$ such that $q=q_{\rho}$ (by 9.21). Now there exists a basis $e_{1},...,e_{n}$ of $V$ such that $\mathcal{M}(\rho,(e_{1},...,e_{n}^{\phantom{\dagger}}))$ is a diagonal matrix (by 9.12). Let $\lambda_{1},...,\lambda_{n}$ denote the entries on the diagonal of this matrix. Thus  

$$
\rho(e_{j},e_{k})={\binom{\lambda_{j}}{0}}_{\mathrm{~}\mathrm{~if~}j\ne k}^{\mathrm{~}\mathrm{if~}j}=k,
$$  

for all $j,k\in\{1,...,n\}$ . If $x_{1},...,x_{n}\in\mathbf{F}$ , then  

$$
\begin{array}{l}{q(x_{1}e_{1}+\dots+x_{n}e_{n})=\rho(x_{1}e_{1}+\dots+x_{n}e_{n},x_{1}e_{1}+\dots+x_{n}e_{n})}\\ {\qquad\qquad\qquad=\displaystyle\sum_{k=1}^{n}\sum_{j=1}^{n}x_{j}x_{k}\rho(e_{j},e_{k})}\\ {\qquad\qquad\qquad=\lambda_{1}x_{1}^{2}+\dots+\lambda_{n}x_{n}^{2},}\end{array}
$$  

as desired.  

(b) Suppose $\mathbf{F}=\mathbf{R}$ and $V$ is an inner product space. Then 9.13 tells us that the basis in (a) can be chosen to be an orthonormal basis of $V.$  

1 Prove that if $\beta$ is a bilinear form on 𝐅, then there exists $c\in\mathbf{F}$ such that  

$$
\beta(x,y)=c x y
$$  

for all $x,y\in\mathbf{F}$ .  

2 Let $n\,=\,\dim V.$ . Suppose $\beta$ is a bilinear form on $V.$ Prove that there exist 𝜑1, …, 𝜑𝑛, 𝜏1, …, 𝜏𝑛∈𝑉′such that  

$$
\beta(u,v)=\varphi_{1}(u)\cdot\tau_{1}(v)+\cdots+\varphi_{n}(u)\cdot\tau_{n}(v)
$$  

for all $u,v\in V.$ .  

This exercise shows that if $n=\dim V,$ then every bilinear form on $V$ is of the form given by the last bullet point of Example 9.2.  

3 Suppose $\beta\colon V\times V\rightarrow\mathbf{F}$ is a bilinear form on $V$ and also is a linear functional on $V\times V.$ . Prove that $\beta=0$ .  

4 Suppose $V$ is a real inner product space and $\beta$ is a bilinear form on $V.$ Show that there exists a unique operator $T\in{\mathcal{L}}(V)$ such that  

$$
\beta(u,v)=\langle u,T v\rangle
$$  

for all $u,v\in V.$ .  

This exercise states that if $V$ is a real inner product space, then every bilinear form on $V$ is of the form given by the third bullet point in 9.2.  

5 Suppose $\beta$ is a bilinear form on a real inner product space $V$ and $T$ is the unique operator on $V$ such that $\beta(u,v)\;=\;\langle u,T v\rangle$ for all $u,v\in V$ (see Exercise 4). Show that $\beta$ is an inner product on $V$ if and only if $T$ is an invertible positive operator on $V_{\cdot}$ .  

6 Prove or give a counterexample: If $\rho$ is a symmetric bilinear form on $V.$ , then  

$$
\{v\in V:\rho(v,v)=0\}
$$  

is a subspace of $V.$  

7 Explain why the proof of 9.13 (diagonalization of a symmetric bilinear form by an orthonormal basis on a real inner product space) fails if the hypothesis that $\mathbf{F}=\mathbf{R}$ is dropped.  

8 Find formulas for dim $V_{\mathrm{sym}}^{(2)}$ and dim $V_{\mathrm{alt}}^{(2)}$ in terms of $\dim V.$  

9 Suppose that $n$ is a positive integer and $V=\{p\in{\mathcal{P}}_{n}(\mathbf{R}):p(0)=p(1)\}.$ . Define $\alpha\colon V\times V\rightarrow\mathbb{R}$ by  

$$
\alpha(p,q)=\int_{0}^{1}p q^{\prime}.
$$  

Show that $\alpha$ is an alternating bilinear form on $V.$  

$V=\{p\in{\mathcal{P}}_{n}(\mathbf{R}):p(0)=p(1)$  

Define $\rho\colon V\times V\rightarrow\mathbb{R}$ by  

$$
\rho(p,q)=\int_{0}^{1}p q^{\prime\prime}\!.
$$  

Show that $\rho$ is a symmetric bilinear form on $V.$  

from the copyright holder.  

## Multilinear Forms  

## 9.24 definition: 𝑉𝑚  

For 𝑚a positive integer, define $V^{m}$ by  

$$
V^{m}=\underbrace{V\times\cdots\times V}_{m\,{\mathrm{times}}}.
$$  

Now we can define $m$ -linear forms as a generalization of the bilinear forms that we discussed in the previous section.  

9.25 definition: 𝑚-linear form, $V^{(m)},$ multilinear form  

For 𝑚a positive integer, an $m$ -linear form on $V$ is a function $\beta\colon V^{m}\rightarrow\mathbf{F}$ that is linear in each slot when the other slots are held fixed. This means that for each $k\in\{1,...,m\}$ and all $u_{1},...,u_{m}\in V_{:}$ , the function  

$$
v\mapsto\beta(u_{1},...,u_{k-1},v,u_{k+1},...,u_{m})
$$  

is a linear map from $V$ to $\mathbf{F}$ .  

• The set of $m$ -linear forms on $V$ is denoted by $V^{(m)}.$ .  

• A function $\beta$ is called a multilinear form on $V$ if it is an $m$ -linear form on $V$ for some positive integer $m$ .  

In the definition above, the expression $\beta(u_{1},...,u_{k-1},v,u_{k+1},...,u_{m})$ means $\beta(v,u_{2},...,u_{m})$ if $k=1$ and means $\beta(u_{1},...,u_{m-1},v)$ if $k=m$ .  

A 1-linear form on $V$ is a linear functional on $V.$ A 2-linear form on $V$ is a bilinear form on $V.$ . You can verify that with the usual addition and scalar multiplication of functions, $V^{(m)}$ is a vector space.  

9.26 example: 𝑚-linear forms  

• Suppose $\alpha,\rho\in V^{(2)},$ . Define a function $\beta\colon V^{4}\rightarrow\mathbf{F}$ by  

$$
\beta(v_{1},v_{2},v_{3},v_{4})=\alpha(v_{1},v_{2})\,\rho(v_{3},v_{4}).
$$  

Then $\beta\in V^{(4)}$ .  

• Define $\beta\colon\left({\mathcal{L}}(V)\right)^{m}\to\mathbf{F}$ by  

$$
\beta(T_{1},...,T_{m})=\mathbf{tr}(T_{1}{\cdots}T_{m}).
$$  

Then $\beta$ is an $m$ -linear form on ${\mathcal{L}}(V)$ .  

Alternating multilinear forms, which we now define, play an important role as we head toward defining determinants.  

9.27 definition: alternating forms, $V_{\mathrm{alt}}^{(m)}$  

Suppose $m$ is a positive integer.  

• An $m$ -linear form $\alpha$ on $V$ is called alternating if $\alpha(v_{1},...,v_{m})=0$ whenever $v_{1},...,v_{m}$ is a list of vectors in $V$ with $v_{j}=v_{k}$ for some two distinct values of $j$ and $k$ in $\{1,...,m\}$ . $V_{\mathrm{alt}}^{(m)}=\big\{\alpha\in V^{(m)}:\alpha$ is an alternating $m$ -linear form on $V\}$ .  

You should verify that $V_{\mathrm{alt}}^{(m)}$ is a subspace of $V^{(m)}.$ . See Example 9.15 for examples of alternating 2-linear forms. See Exercise 2 for an example of an alternating 3-linear form.  

The next result tells us that if a linearly dependent list is input to an alternating multilinear form, then the output equals 0.  

9.28 alternating multilinear forms and linear dependence  

Suppose 𝑚is a positive integer and $\alpha$ is an alternating $m$ -linear form on $V.$ If $v_{1},...,v_{m}$ is a linearly dependent list in $V,$ , then  

$$
\alpha(v_{1},...,v_{m})=0.
$$  

Proof Suppose $v_{1},...,v_{m}$ is a linearly dependent list in $V.$ By the linear dependence lemma (2.19), some $v_{k}$ is a linear combination of $v_{1},...,v_{k-1}$ . Thus there exist $b_{1},...,b_{k-1}$ such that $v_{k}=b_{1}v_{1}+\cdots+b_{k-1}v_{k-1}$ . Now  

$$
\begin{array}{l}{\displaystyle\alpha(v_{1},...,v_{m})=\alpha\biggl(v_{1},...,v_{k-1},\sum_{j=1}^{k-1}b_{j}v_{j},v_{k+1},...,v_{m}\biggr)}\\ {\displaystyle=\sum_{j=1}^{k-1}b_{j}\,\alpha(v_{1},...,v_{k-1},v_{j},v_{k+1},...,v_{m})}\\ {\displaystyle=0.}\end{array}
$$  

The next result states that if $m>\dim V,$ , then there are no alternating $m$ -linear forms on $V$ other than the function on $V^{m}$ that is identically 0.  

9.29 no nonzero alternating 𝑚-linear forms for $m>\dim V$  

Suppose $m>\dim V.$ Then 0 is the only alternating $m$ -linear form on $V.$ .  

Proof Suppose that $\alpha$ is an alternating $m$ -linear form on $V$ and $v_{1},...,v_{m}\in V.$ Because $m\,>\,\dim V,$ , this list is not linearly independent (by 2.22). Thus 9.28 implies that $\alpha(v_{1},...,v_{m})=0$ . Hence $\alpha$ is the zero function from $V^{m}$ to $\mathbf{F}$ .  

## Alternating Multilinear Forms and Permutations  

## 9.30 swapping input vectors in an alternating multilinear form  

Suppose $m$ is a positive integer, $\alpha$ is an alternating $m$ -linear form on $V,$ and $v_{1},...,v_{m}$ is a list of vectors in $V.$ Then swapping the vectors in any two slots of $\alpha(v_{1},...,v_{m})$ changes the value of $\alpha$ by a factor of $-1$ .  

Proof Put $v_{1}+v_{2}$ in both the first two slots, getting  

$$
0=\alpha(v_{1}+v_{2},v_{1}+v_{2},v_{3},...,v_{m}).
$$  

Use the multilinear properties of $\alpha$ to expand the right side of the equation above (as in the proof of 9.16) to get  

$$
\alpha(v_{2},v_{1},v_{3},...,v_{m})=-\alpha(v_{1},v_{2},v_{3},...,v_{m}).
$$  

Similarly, swapping the vectors in any two slots of $\alpha(v_{1},...,v_{m})$ changes the value of $\alpha$ by a factor of $-1$ .  

To see what can happen with multiple swaps, suppose $\alpha$ is an alternating 3-linear form on $V$ and $v_{1},v_{2},v_{3}\;\in\;V.$ . To evaluate $\alpha(v_{3},v_{1},v_{2})$ in terms of $\alpha(v_{1},v_{2},v_{3})$ , start with $\alpha(v_{3},v_{1},v_{2})$ and swap the entries in the first and third slots, getting $\alpha(v_{3},v_{1},v_{2})=-\alpha(v_{2},v_{1},v_{3})$ . Now in the last expression, swap the entries in the first and second slots, getting  

$$
\alpha(v_{3},v_{1},v_{2})=-\alpha(v_{2},v_{1},v_{3})=\alpha(v_{1},v_{2},v_{3}).
$$  

More generally, we see that if we do an odd number of swaps, then the value of $\alpha$ changes by a factor of $-1$ , and if we do an even number of swaps, then the value of $\alpha$ does not change.  

To deal with arbitrary multiple swaps, we need a bit of information about permutations.  

## 9.31 definition: permutation, perm 𝑚  

Suppose 𝑚is a positive integer.  

• A permutation of $(1,...,m)$ is a list $(j_{1},...,j_{m})$ that contains each of the numbers $1,...,m$ exactly once.  

The set of all permutations of $(1,...,m)$ is denoted by perm 𝑚.  

For example, $(2,3,4,5,1)\,\in\,\mathrm{perm}\,5$ . You should think of an element of perm 𝑚as a rearrangement of the first $m$ positive integers.  

The number of swaps used to change a permutation $(j_{1},...,j_{m})$ to the standard order $(1,...,m)$ can depend on the specific swaps selected. The following definition has the advantage of assigning a well-defined sign to every permutation.  

The sign of a permutation $(j_{1},...,j_{m})$ is defined by  

$$
\mathrm{sign}(j_{1},...,j_{m})=(-1)^{N}\!,
$$  

where $N$ is the number of pairs of integers $(k,\ell)$ with $1\leq k<\ell\leq m$ such that $k$ appears after ℓin the list $(j_{1},...,j_{m})$ .  

Hence the sign of a permutation equals 1 if the natural order has been changed an even number of times and equals $-1$ if the natural order has been changed an odd number of times.  

## 9.33 example: signs  

• The permutation $(1,...,m)$ [no changes in the natural order] has sign 1.  

• The only pair of integers $(k,\ell)$ with $k<\ell$ such that $k$ appears after ℓin the list (2, 1, 3, 4) is (1, 2). Thus the permutation (2, 1, 3, 4) has sign $-1$ .  

• In the permutation $(2,3,...,m,1)$ , the only pairs $(k,\ell)$ with $k<\ell$ that appear with changed order are $(1,2),(1,3),...,(1,m)$ . Because we have $m-1$ such pairs, the sign of this permutation equals $(-1)^{m-1}$ .  

9.34 swapping two entries in a permutation  

Swapping two entries in a permutation multiplies the sign of the permutation by $-1$ .  

Proof Suppose we have two permutations, where the second permutation is obtained from the first by swapping two entries. The two swapped entries were in their natural order in the first permutation if and only if they are not in their natural order in the second permutation. Thus we have a net change (so far) of 1 or $-1$ (both odd numbers) in the number of pairs not in their natural order.  

Consider each entry between the two swapped entries. If an intermediate entry was originally in the natural order with respect to both swapped entries, then it is now in the natural order with respect to neither swapped entry. Similarly, if an intermediate entry was originally in the natural order with respect to neither of the swapped entries, then it is now in the natural order with respect to both swapped entries. If an intermediate entry was originally in the natural order with respect to exactly one of the swapped entries, then that is still true. Thus the net change (for each pair containing an entry between the two swapped entries) in the number of pairs not in their natural order is 2, $-2$ , or 0 (all even numbers).  

For all other pairs of entries, there is no change in whether or not they are in their natural order. Thus the total net change in the number of pairs not in their natural order is an odd number. Hence the sign of the second permutation equals $-1$ times the sign of the first permutation.  

Suppose $m$ is a positive integer and $\alpha\in V_{\mathrm{alt}}^{(m)}$ . Then  

$$
\alpha(v_{j_{1}},...,v_{j_{m}})=(\mathrm{sign}(j_{1},...,j_{m}))\alpha(v_{1},...,v_{m})
$$  

for every list $v_{1},...,v_{m}$ of vectors in $V$ and all $(j_{1},...,j_{m})\in\mathrm{perm}\,m.$ .  

Proof Suppose $v_{1},...,v_{m}\,\in\,V$ and $(j_{1},...,j_{m})\,\in\,\mathrm{perm}\,m$ . We can get from $(j_{1},...,j_{m})$ to $(1,...,m)$ by a series of swaps of entries in different slots. Each such swap changes the value of $\alpha$ by a factor of $-1$ (by 9.30) and also changes the sign of the remaining permutation by a factor of $-1$ (by 9.34). After an appropriate number of swaps, we reach the permutation $1,...,m$ , which has sign 1. Thus the value of $\alpha$ changed signs an even number of times if $\mathrm{sign}(j_{1},...,j_{m})=1$ and an odd number of times if sig $\mathfrak{n}(j_{1},...,j_{m})=-1$ , which gives the desired result.  

Our use of permutations now leads in a natural way to the following beautiful formula for alternating $n$ -linear forms on an $n$ -dimensional vector space.  

where the third line holds because $\alpha(e_{j_{1}},...,e_{j_{n}})\,=\,0$ if $j_{1},...,j_{n}$ are not distinct integers, and the last line holds by 9.35.  

## 9.36 formula for $(\dim V)$ -linear alternating forms on $V$  

Let $n=\dim V.$ Suppose $e_{1},...,e_{n}$ is a basis of $V$ and $v_{1},...,v_{n}\in V.$ For each $k\in\{1,...,n\}$ , let $b_{1,k},...,b_{n,k}\in\mathbf{F}$ be such that  

$$
\boldsymbol{v}_{k}=\sum_{j\mathop{=}1}^{n}b_{j,k}\boldsymbol{e}_{j}.
$$  

Then  

$$
\alpha(v_{1},...,v_{n})=\alpha(e_{1},...,e_{n})\sum_{(j_{1},...,j_{n})\in\mathrm{perm}n}(\mathrm{sign}(j_{1},...,j_{n}))b_{j_{1},1}...b_{j_{n},n}
$$  

for every alternating $n$ -linear form $\alpha$ on $V.$  

Proof Suppose $\alpha$ is an alternating $n$ -linear form $\alpha$ on $V.$ Then  

$$
\begin{array}{r l r}{\lefteqn{\alpha(\boldsymbol{v}_{1},...,\boldsymbol{v}_{n})=\alpha\biggl(\sum_{j_{1}=1}^{n}b_{j_{1},1}\boldsymbol{e}_{j_{1}},...,\underset{j_{n}=1}{\overset{n}{\prod}}b_{j_{n},n}\boldsymbol{e}_{j_{n}}\biggr)}}\\ &{}&{=\underset{j_{1}=1}{\overset{n}{\sum}}\cdots\underset{j_{n}=1}{\overset{n}{\sum}}b_{j_{1},1}\cdots b_{j_{n},n}\,\alpha(\boldsymbol{e}_{j_{1}},...,\boldsymbol{e}_{j_{n}})}\\ &{}&{=\underset{(j_{1},\ldots,j_{n})\in\mathrm{{perm}}}{\sum}b_{j_{1},1}\cdots b_{j_{n},n}\,\alpha(\boldsymbol{e}_{j_{1}},...,\boldsymbol{e}_{j_{n}})}\\ &{}&{=\alpha(\boldsymbol{e}_{1},...,\boldsymbol{e}_{n})}\underset{(j_{1},\ldots,j_{n})\in\mathrm{{perm}}}{\sum}(\mathrm{sign}(j_{1},...,j_{n}))b_{j_{1},1}\cdots b_{j_{n},n},}\end{array}
$$  

The following result will be the key to our definition of the determinant in the next section.  

## 9.37 dim 𝑉(dim𝑉) alt  

The vector space $V_{\mathrm{alt}}^{(\dim V)}$ has dimension one.  

Proof Let $n=\dim V.$ . Suppose $\alpha$ and $\alpha^{\prime}$ are alternating $n$ -linear forms on $V$ with $\alpha\neq0$ . Let $e_{1},...,e_{n}$ be such that $\alpha(e_{1},...,e_{n})\neq0$ . There exists $c\in\mathbf{F}$ such that  

$$
\alpha^{\prime}(e_{1},...,e_{n})=c\alpha(e_{1},...,e_{n}).
$$  

Furthermore, 9.28 implies that $e_{1},...,e_{n}$ is linearly independent and thus is a basis of $V.$  

Suppose $v_{1},...,v_{n}\in V.$ . Let $b_{j,k}$ be as in 9.36 for $j,k=1,...,n$ . Then  

$$
\begin{array}{l}{{\displaystyle\alpha^{\prime}(v_{1},...,v_{n})=\alpha^{\prime}(e_{1},...,e_{n})\sum_{(j_{1},...,j_{n})\in\mathrm{perm}\,n}(\mathrm{sign}(j_{1},...,j_{n}))b_{j_{1},1}{\cdots}b_{j_{n},n}}}\\ {{\displaystyle=c\alpha(e_{1},...,e_{n})\sum_{(j_{1},...,j_{n})\in\mathrm{perm}\,n}(\mathrm{sign}(j_{1},...,j_{n}))b_{j_{1},1}{\cdots}b_{j_{n},n}}}\\ {{\displaystyle=c\alpha(v_{1},...,v_{n}),}}\end{array}
$$  

where the first and last lines above come from 9.36. The equation above implies that $\alpha^{\prime}\,=\,c\alpha$ . Thus $\alpha_{}^{\prime},\alpha$ is not a linearly independent list, which implies that dim $V_{\mathrm{alt}}^{(n)}\leq1$ .  

To complete the proof, we only need to show that there exists a nonzero alternating $n$ -linear form $\alpha$ on $V$ (thus eliminating the possibility that dim $V_{\mathrm{alt}}^{(n)}$ equals 0). To do this, let $e_{1},...,e_{n}$ be any basis of $V,$ and let $\varphi_{1},...,\varphi_{n}\in V^{\prime}$ be the linear functionals on $V$ that allow us to express each element of $V$ as a linear combination of $e_{1},...,e_{n}$ . In other words,  

$$
v=\sum_{j\mathop{=}1}^{n}\varphi_{j}(v)e_{j}
$$  

for every $v\in V$ (see 3.114). Now for $v_{1},...,v_{n}\in V,$ define  

9.38  

$$
\alpha(v_{1},...,v_{n})=\sum_{(j_{1},...,j_{n})\in\mathrm{perm}n}(\mathrm{sign}(j_{1},...,j_{n}))\varphi_{j_{1}}(v_{1}){\cdots}\varphi_{j_{n}}(v_{n}).
$$  

The verification that $\alpha$ is an $n$ -linear form on $V$ is straightforward.  

To see that $\alpha$ is alternating, suppose $v_{1},...,v_{n}\in V$ with $v_{1}=v_{2}$ . For each $(j_{1},...,j_{n})\in\mathsf{p e r m}\,n$ , the permutation $(j_{2},j_{1},j_{3},...,j_{n})$ has the opposite sign. Because $v_{1}=v_{2}$ , the contributions from these two permutations to the sum in 9.38 cancel either other. Hence $\alpha(v_{1},v_{1},v_{3},...,v_{n})=0$ . Similarly, $\alpha(v_{1},...,v_{n})=0$ if any two vectors in the list $v_{1},...,v_{n}$ are equal. Thus $\alpha$ is alternating.  

Finally, consider 9.38 with each $v_{k}=e_{k}$ . Because $\varphi_{j}(e_{k})$ equals 0 if $j\neq k$ and equals 1 if $j=k$ , only the permutation $(1,...,n)$ makes a nonzero contribution to the right side of 9.38 in this case, giving the equation $\alpha(e_{1},...,e_{n})=1$ . Thus we have produced a nonzero alternating $n$ -linear form $\alpha$ on $V.$ , as desired.  

Earlier we showed that the value of an alternating multilinear form applied to a linearly dependent list is 0; see 9.28. The next result provides a converse of 9.28 for $n$ -linear multilinear forms when $n\,=\,\dim V.$ In the following result, the statement that $\alpha$ is nonzero means (as  

The formula 9.38 used in the last proof to construct a nonzero alternating 𝑛- linear form came from the formula in 9.36, and that formula arose naturally from the properties of an alternating multilinear form.  

usual for a function) that $\alpha$ is not the function on $V^{n}$ that is identically 0.  

9.39 alternating $\operatorname{dim}V)$ )-linear forms and linear independence  

Let $n=\dim V$ . Suppose $\alpha$ is a nonzero alternating $n$ -linear form on $V$ and $e_{1},...,e_{n}$ is a list of vectors in $V.$ Then  

$$
\alpha(e_{1},...,e_{n})\neq0
$$  

if and only if $e_{1},...,e_{n}$ is linearly independent.  

Proof First suppose $\alpha(e_{1},...,e_{n})\neq0$ . Then 9.28 implies that $e_{1},...,e_{n}$ is linearly independent.  

To prove the implication in the other direction, now suppose $e_{1},...,e_{n}$ is linearly independent. Because $n=\dim V,$ this implies that $e_{1},...,e_{n}$ is a basis of $V$ (see 2.38).  

Because $\alpha$ is not the zero $n$ -linear form, there exist $v_{1},...,v_{n}\in V$ such that $\alpha(v_{1},...,v_{n})\neq0$ . Now 9.36 implies that $\alpha(e_{1},...,e_{n})\neq0$ .  

## Exercises 9B  

1 Suppose $m$ is a positive integer. Show that dim $V^{(m)}=(\dim V)^{m}.$ .  

2 Suppose $n\geq3$ and $\alpha\colon\mathbf{F}^{n}\times\mathbf{F}^{n}\times\mathbf{F}^{n}\rightarrow\mathbf{F}$ is defined by  

$$
\begin{array}{r l r}{\lefteqn{\alpha\big((x_{1},...,x_{n}),(y_{1},...,y_{n}),(z_{1},...,z_{n})\big)}}\\ &{}&{=x_{1}y_{2}z_{3}-x_{2}y_{1}z_{3}-x_{3}y_{2}z_{1}-x_{1}y_{3}z_{2}+x_{3}y_{1}z_{2}+x_{2}y_{3}z_{1}.}\end{array}
$$  

Show that $\alpha$ is an alternating 3-linear form on $\mathbf{F}^{n}$  

3 Suppose $m$ is a positive integer and $\alpha$ is an $m$ -linear form on $V$ such that $\alpha(v_{1},...,v_{m})=0$ whenever $v_{1},...,v_{m}$ is a list of vectors in $V$ with $v_{j}=v_{j+1}$ for some $j\in\{1,...,m-1\}$ . Prove that $\alpha$ is an alternating $m$ -linear form on $V_{\cdot}$ .  

4 Prove or give a counterexample: If $\alpha\in V_{\mathrm{alt}}^{(4)}$ , then  

$$
\{(v_{1},v_{2},v_{3},v_{4})\in V^{4}:\alpha(v_{1},v_{2},v_{3},v_{4})=0\}
$$  

is a subspace of $V^{4}$ .  

5 Suppose $m$ is a positive integer and $\beta$ is an $m$ -linear form on $V.$ . Define an $m$ -linear form $\alpha$ on $V$ by  

$$
\alpha(v_{1},...,v_{m})=\sum_{(j_{1},...,j_{m})\in\mathrm{perm}m}(\mathrm{sign}(j_{1},...,j_{m}))\beta(v_{j_{1}},...,v_{j_{m}})
$$  

for $v_{1},...,v_{m}\in V.$ . Explain why $\alpha\in V_{\mathrm{alt}}^{(m)}$ .  

Suppose $m$ is a positive integer and $\beta$ is an $m$ -linear form on $V.$ . Define an $m$ -linear form $\alpha$ on $V$ by  

$$
\alpha(v_{1},...,v_{m})=\sum_{(j_{1},...,j_{m})\,\in\,\mathrm{perm}\,m}\beta(v_{j_{1}},...,v_{j_{m}})
$$  

for $v_{1},...,v_{m}\in V.$ . Explain why  

$$
\alpha(v_{k_{1}},...,v_{k_{m}})=\alpha(v_{1},...,v_{m})
$$  

for all $v_{1},...,v_{m}\in V$ and all $(k_{1},...,k_{m})\in$ perm 𝑚.  

7 Give an example of a nonzero alternating 2-linear form $\alpha$ on $\mathbf{R}^{3}$ and a linearly independent list $v_{1},v_{2}$ in $\mathbf{R}^{3}$ such that $\alpha(v_{1},v_{2})=0$ .  

This exercise shows that 9.39 can fail if the hypothesis that $n=\dim V$ is deleted.  

## Defining the Determinant  

The next definition will lead us to a clean, beautiful, basis-free definition of the determinant of an operator.  

9.40 definition: 𝛼𝑇  

Suppose that 𝑚is a positive integer and 𝑇 ∈ℒ(𝑉). For 𝛼∈𝑉a(lt𝑚 ), define $\alpha_{T}\in V_{\mathrm{alt}}^{(m)}$ by  

$$
\alpha_{T}(v_{1},...,v_{m})=\alpha(T v_{1},...,T v_{m})
$$  

for each list $v_{1},...,v_{m}$ of vectors in $V.$  

Suppose $T\in{\mathcal{L}}(V)$ . If $\alpha\in V_{\mathrm{alt}}^{(m)}$ and $v_{1},...,v_{m}$ is a list of vectors in $V$ with $v_{j}\,=\,v_{k}$ for some $j\neq k$ , then $T v_{j}\,=\,T v_{k}$ , which implies that $\alpha_{T}(v_{1},...,v_{m})\,=$ $\alpha(T v_{1},...,T v_{m})=0.$ . Thus the function $\alpha\mapsto\alpha_{T}$ is a linear map of $V_{\mathrm{alt}}^{(m)}$ to itself.  

We know that dim $V_{\mathrm{alt}}^{(\dim V)}\,=\,1$ (see 9.37). Every linear map from a onedimensional vector space to itself is multiplication by some unique scalar. For the linear map $\alpha\mapsto\alpha_{T}$ , we now define det $T$ to be that scalar.  

9.41 definition: determinant of an operator, det $T$  

Suppose $T\in{\mathcal{L}}(V)$ . The determinant of $T,$ , denoted by det $T,$ is defined to be the unique number in $\mathbf{F}$ such that  

$$
\alpha_{T}=(\operatorname*{det}T)\,\alpha
$$  

for all $\alpha\in V_{\mathrm{alt}}^{(\dim V)}$  

9.42 example: determinants of operators  

Let $n=\dim V.$  

• If $I$ is the identity operator on $V,$ then $\alpha_{I}=\alpha$ for all $\alpha\in V_{\mathrm{alt}}^{(n)}$ . Thus det $I=1$ .  

• More generally, if $\lambda\in\mathbf{F}$ , then $\alpha_{\lambda I}=\lambda^{n}\alpha$ for all $\alpha\in V_{\mathrm{alt}}^{(n)}$ . Thus det $(\lambda I)=\lambda^{n}$ .  

• Still more generally, if $T\in{\mathcal{L}}(V)$ and $\lambda\in\mathbf{F}$ , then $\alpha_{\lambda T}=\lambda^{n}\alpha_{T}=\lambda^{n}(\operatorname*{det}T)\alpha$ for all $\alpha\in V_{\mathrm{alt}}^{(n)}$ . Thus det $(\lambda T)=\lambda^{n}$ det $T$ .  

• Suppose $T\in{\mathcal{L}}(V)$ and there is a basis $e_{1},...,e_{n}$ of $V$ consisting of eigenvectors of $T,$ with corresponding eigenvalues $\lambda_{1},...,\lambda_{n}$ . If $\alpha\in V_{\mathrm{alt}}^{(n)}$ , then  

$$
\alpha_{T}(e_{1},...,e_{n})=\alpha(\lambda_{1}e_{1},...,\lambda_{n}e_{n})=(\lambda_{1}...\lambda_{n})\alpha(e_{1},...,e_{n}).
$$  

If $\alpha\neq0$ , then 9.39 implies $\alpha(e_{1},...,e_{n})\neq0.$ . Thus the equation above implies  

Our next task is to define and give a formula for the determinant of a square matrix. To do this, we associate with each square matrix an operator and then define the determinant of the matrix to be the determinant of the associated operator.  

## 9.43 definition: determinant of a matrix, det $A$  

Suppose that $n$ is a positive integer and $A$ is an $n$ -by- $^{\cdot n}$ square matrix with entries in 𝐅. Let $T\in{\mathcal{L}}(\mathbf{F}^{n})$ be the operator whose matrix with respect to the standard basis of $\mathbf{F}^{n}$ equals $A$ . The determinant of $A$ , denoted by det $A$ , is defined by det $A=\operatorname*{det}T$ .  

## 9.44 example: determinants of matrices  

• If $I$ is the $n$ -by- $_n$ identity matrix, then the corresponding operator on $\mathbf{F}^{n}$ is the identity operator $I$ on $\mathbf{F}^{n}$ Thus the first bullet point of 9.42 implies that the determinant of the identity matrix is 1.  

• Suppose $A$ is a diagonal matrix with $\lambda_{1},...,\lambda_{n}$ on the diagonal. Then the corresponding operator on $\mathbf{F}^{n}$ has the standard basis of $\mathbf{F}^{n}$ as eigenvectors, with eigenvalues $\lambda_{1},...,\lambda_{n}$ . Thus the last bullet point of 9.42 implies that det $A=\lambda_{1}{\cdots}\lambda_{n}$ .  

For the next result, think of each list $v_{1},...,v_{n}$ of $n$ vectors in $\mathbf{F}^{n}$ as a list of $n$ -by-1 column vectors. The notation $\left(\begin{array}{l l l}{v_{1}}&{\cdots}&{v_{n}}\end{array}\right)$ then denotes the $n$ -by- $\cdot n$ square matrix whose $k^{\mathrm{{th}}}$ column is $v_{k}$ for each $k=1,...,n$ .  

9.45 determinant is an alternating multilinear form  

Suppose that $n$ is a positive integer. The map that takes a list $v_{1},...,v_{n}$ of vectors in $\mathbf{F}^{n}$ to det $\left(\begin{array}{l l l}{v_{1}}&{\cdots}&{v_{n}}\end{array}\right)$ is an alternating $n$ -linear form on $\mathbf{F}^{n}$ .  

Proof Let $e_{1},...,e_{n}$ be the standard basis of $\mathbf{F}^{n}$ and suppose $v_{1},...,v_{n}$ is a list of vectors in $\mathbf{F}^{n}$ . Let $T\in{\mathcal{L}}(\mathbf{F}^{n})$ be the operator such that $T e_{k}=v_{k}$ for $k=1,...,n$ . Thus $T$ is the operator whose matrix with respect to $e_{1},...,e_{n}$ is $\left(\begin{array}{l l l}{v_{1}}&{\cdots}&{v_{n}}\end{array}\right)$ . Hence det ${\left(\begin{array}{l l l}{v_{1}}&{\cdots}&{v_{n}}\end{array}\right)}=\operatorname*{det}T_{\mathfrak{\tau}}$ , by definition of the determinant of a matrix. Let $\alpha$ be an alternating $n$ -linear form on $\mathbf{F}^{n}$ such that $\alpha(e_{1},...,e_{n})=1$ . Then  

$$
\begin{array}{r l}{\operatorname*{det}\left(\begin{array}{l l l}{v_{1}}&{\cdots}&{v_{n}}\end{array}\right)=\operatorname*{det}T}\\ &{\quad\quad}&{=(\operatorname*{det}T)\,\alpha(e_{1},...,e_{n})}\\ &{\quad\quad}&{=\alpha(T e_{1},...,T e_{n})}\\ &{\quad\quad}&{=\alpha(v_{1},...,v_{n}),}\end{array}
$$  

where the third line follows from the definition of the determinant of an operator. The equation above shows that the map that takes a list of vectors $v_{1},...,v_{n}$ in $\mathbf{F}^{n}$ to det $\left(\begin{array}{l l l}{v_{1}}&{\cdots}&{v_{n}}\end{array}\right)$ is the alternating $n$ -linear form $\alpha$ on $\mathbf{F}^{n}$ .  

The previous result has several important consequences. For example, it immediately implies that a matrix with two identical columns has determinant 0. We will come back to other consequences later, but for now we want to give a formula for the determinant of a square matrix. Recall that if $A$ is a matrix, then $A_{j,k}$ denotes the entry in row $j$ , column $k$ of $A$ .  

9.46 formula for determinant of a matrix  

Suppose that $n$ is a positive integer and $A$ is an $n$ -by- $^{\cdot n}$ square matrix. Then  

$$
\operatorname*{det}A=\sum_{(j_{1},\dots,j_{n})\in\operatorname{perm}n}(\operatorname{sign}(j_{1},...,j_{n}))A_{j_{1},1}\cdot\cdot\cdot A_{j_{n},n}.
$$  

Proof Apply 9.36 with $V=\mathbf{F}^{n}$ and $e_{1},...,e_{n}$ the standard basis of $\mathbf{F}^{n}$ and $\alpha$ the alternating $n$ -linear form on $\mathbf{F}^{n}$ that takes $v_{1},...,v_{n}$ to det $\left(\begin{array}{l l l}{v_{1}}&{\cdots}&{v_{n}}\end{array}\right)$ [see 9.45]. If each $v_{k}$ is the $k^{\mathrm{{th}}}$ column of $A$ , then each $b_{j,k}$ in 9.36 equals $A_{j,k}$ . Finally,  

$$
\alpha(e_{1},...,e_{n})=\operatorname*{det}\left(\begin{array}{l l l}{e_{1}}&{\cdots}&{e_{n}}\end{array}\right)=\operatorname*{det}I=1.
$$  

Thus the formula in 9.36 becomes the formula stated in this result.  

9.47 example: explicit formula for determinant  

• If $A$ is a 2-by-2 matrix, then the formula in 9.46 becomes  

$$
\operatorname*{det}A=A_{1,1}A_{2,2}-A_{2,1}A_{1,2}.
$$  

• If $A$ is a 3-by-3 matrix, then the formula in 9.46 becomes  

$$
\begin{array}{r l}&{\operatorname*{det}A=\!A_{1,1}A_{2,2}A_{3,3}-A_{2,1}A_{1,2}A_{3,3}-A_{3,1}A_{2,2}A_{1,3}}\\ &{\qquad\qquad-A_{1,1}A_{3,2}A_{2,3}+A_{3,1}A_{1,2}A_{2,3}+A_{2,1}A_{3,2}A_{1,3}.}\end{array}
$$  

The sum in the formula in 9.46 contains 𝑛! terms. Because 𝑛! grows rapidly as $n$ increases, the formula in 9.46 is not a viable method to evaluate determinants even for moderately sized $n$ . For example, 10! is over three million, and 100! is approximately $10^{158}$ , leading to a sum that the fastest computer cannot evaluate. We will soon see some results that lead to faster evaluations of determinants than direct use of the sum in 9.46.  

9.48 determinant of upper-triangular matrix  

Suppose that $A$ is an upper-triangular matrix with $\lambda_{1},...,\lambda_{n}$ on the diagonal.   
Then det $A=\lambda_{1}{\cdots}\lambda_{n}$ .  

Proof If $(j_{1},...,j_{n})\in\mathsf{p e r m}\,n$ with ${(j_{1},...,j_{n})\neq(1,...,n)}$ , then $j_{k}>k$ for some $k\,\in\,\{1,...,n\}$ , which implies that $A_{j_{k},k}\,=\,0$ . Thus the only permutation that can make a nonzero contribution to the sum in 9.46 is the permutation $(1,...,n)$ . Because $A_{k,k}=\lambda_{k}$ for each $k=1,...,n$ , this implies that det $A=\lambda_{1}{\cdots}\lambda_{n}$ .  

Our definition of the determinant leads to the following magical proof that the determinant is multiplicative.  

## 9.49 determinant is multiplicative  

(a) Suppose $S,T\in{\mathcal{L}}(V)$ . Then det(𝑆𝑇) = (det 𝑆)(det 𝑇).  

(b) Suppose $A$ and $B$ are square matrices of the same size. Then  

$$
\operatorname*{det}(A B)=(\operatorname*{det}A)(\operatorname*{det}B)
$$  

## Proof  

(a) Let $n=\dim V.$ Suppose $\alpha\in V_{\mathrm{alt}}^{(n)}$ and $v_{1},...,v_{n}\in V.$ Then  

$$
\begin{array}{r l}&{\alpha_{S T}(v_{1},...,v_{n})=\alpha(S T v_{1},...,S T v_{n})}\\ &{\qquad\qquad\qquad=(\operatorname*{det}S)\alpha(T v_{1},...,T v_{n})}\\ &{\qquad\qquad\qquad=(\operatorname*{det}S)(\operatorname*{det}T)\alpha(v_{1},...,v_{n}),}\end{array}
$$  

where the first equation follows from the definition of $\alpha_{S T}$ , the second equation follows from the definition of det $S$ , and the third equation follows from the definition of det $T.$ . The equation above implies that det $(S T)=(\operatorname*{det}S)(\operatorname*{det}T)$ .  

(b) Let $S,T\in{\mathcal{L}}(\mathbf{F}^{n})$ be such that ${\mathcal{M}}(S)=A$ and $\mathcal{M}(T)=B$ , where all matrices of operators in this proof are with respect to the standard basis of $\mathbf{F}^{n}$ . Then $\mathcal{M}(S T)=\mathcal{M}(S)\mathcal{M}(T)=A B$ (see 3.43). Thus  

$$
\operatorname*{det}(A B)=\operatorname*{det}(S T)=(\operatorname*{det}S)(\operatorname*{det}T)=(\operatorname*{det}A)(\operatorname*{det}B),
$$  

where the second equality comes from the result in (a).  

The determinant of an operator determines whether the operator is invertible.  

9.50 invertible $\Longleftrightarrow$ nonzero determinant  

An operator $T\in{\mathcal{L}}(V)$ is invertible if and only if det $T\neq0$ . Furthermore, if $T$ is invertible, then det $\begin{array}{r}{(T^{-1})=\frac{1}{\operatorname*{det}T}}\end{array}$  

Proof First suppose $T$ is invertible. Thus $T T^{-1}=I.$ Now 9.49 implies that  

$$
1=\operatorname*{det}I=\operatorname*{det}(T T^{-1})=(\operatorname*{det}T){\Big(}\operatorname*{det}(T^{-1}){\Big)}.
$$  

Hence det $T\neq0$ and de $\mathfrak{t}(T^{-1})$ is the multiplicative inverse of det $T$ .  

To prove the other direction, now suppose det $T\neq0$ . Suppose $v\in V$ and $v\neq0$ . Let $v,e_{2},...,e_{n}$ be a basis of $V$ and let $\alpha\in V_{\mathrm{alt}}^{(n)}$ be such that $\alpha\neq0$ . Then $\alpha(v,e_{2},...,e_{n})\neq0$ (by 9.39). Now  

$$
\alpha(T v,T e_{2},...,T e_{n})=(\operatorname*{det}T)\alpha(v,e_{2},...,e_{n})\neq0,
$$  

Thus $T v\neq0$ . Hence $T$ is invertible.  

An $n$ -by- $_n$ matrix $A$ is invertible (see 3.80 for the definition of an invertible matrix) if and only if the operator on $\mathbf{F}^{n}$ associated with $A$ (via the standard basis of $\mathbf{F}^{n}$ ) is invertible. Thus the previous result shows that a square matrix $A$ is invertible if and only if det $A\neq0$ .  

## 9.51 eigenvalues and determinants  

Suppose $T\in{\mathcal{L}}(V)$ and $\lambda\in\mathbf{F}$ . Then $\lambda$ is an eigenvalue of $T$ if and only if $\operatorname*{det}(\lambda I-T)=0.$ .  

Proof The number $\lambda$ is an eigenvalue of $T$ if and only if $T-\lambda I$ is not invertible (see 5.7), which happens if and only if $\lambda I-T$ is not invertible, which happens if and only if det $(\lambda I-T)=0$ (by 9.50).  

Suppose $T\in{\mathcal{L}}(V)$ and $S\colon W\to V$ is an invertible linear map. To prove that d $\mathbf{z}\mathbf{t}(S^{-1}T S)=\operatorname*{det}T,$ , we could try to use 9.49 and 9.50, writing  

$$
\begin{array}{r}{\operatorname*{det}(S^{-1}T S)=(\operatorname*{det}S^{-1})(\operatorname*{det}T)(\operatorname*{det}S)}\\ {=\operatorname*{det}T.\qquad\qquad\qquad\qquad\qquad}\end{array}
$$  

That proof works if $W=V,$ but if $W\neq V$ then it makes no sense because the determinant is defined only for linear maps from a vector space to itself, and $S$ maps $W$ to $V,$ making det $S$ undefined. The proof given below works around this issue and is valid when $W\neq V.$  

9.52 determinant is a similarity invariant  

Suppose $T\in{\mathcal{L}}(V)$ and $S\colon W\to V$ is an invertible linear map. Then  

$$
\operatorname*{det}(S^{-1}T S)=\operatorname*{det}T.
$$  

Proof Let $n=\dim W=\dim V.$ Suppose $\tau\in W_{\mathrm{alt}}^{(n)}$ . Define $\alpha\in V_{\mathrm{alt}}^{(n)}$ by  

$$
\alpha(v_{1},...,v_{n})=\tau(S^{-1}v_{1},...,S^{-1}v_{n})
$$  

for $v_{1},...,v_{n}\in V.$ Suppose $w_{1},...,w_{n}\in W_{}$ Then  

$$
\begin{array}{r l}{\tau_{S^{-1}T S}(w_{1},...,w_{n})=\tau(S^{-1}T S w_{1},...,S^{-1}T S w_{n})}&{}\\ {=\alpha(T S w_{1},...,T S w_{n})}\\ {=\alpha_{T}(S w_{1},...,S w_{n})}&{}\\ {=(\operatorname*{det}T)\alpha(S w_{1},...,S w_{n})}&{}\\ {=(\operatorname*{det}T)\tau(w_{1},...,w_{n}).}\end{array}
$$  

The equation above and the definition of the determinant of the operator $S^{-1}T S$ imply that de $\mathsf{t}(S^{-1}T S)=\operatorname*{det}T.$  

For the special case in which $V=\mathbf{F}^{n}$ and $e_{1},...,e_{n}$ is the standard basis of $\mathbf{F}^{n},$ the next result is true by the definition of the determinant of a matrix. The left side of the equation in the next result does not depend on a choice of basis, which means that the right side is independent of the choice of basis.  

9.53 determinant of operator equals determinant of its matrix  

Suppose $T\in{\mathcal{L}}(V)$ and $e_{1},...,e_{n}$ is a basis of $V.$ . Then  

$$
\operatorname*{det}T=\operatorname*{det}\mathcal{M}(T,(e_{1},...,e_{n})).
$$  

Proof Let $f_{1},...,f_{n}$ be the standard basis of $\mathbf{F}^{n}$ . Let $S\colon{\mathbf{F}}^{n}\,\to\,V$ be the linear map such that $S f_{k}=e_{k}$ for each $k=1,...,n$ . Thus $\mathcal{M}(S,(f_{1},...,f_{n})$ , $(e_{1},...,e_{n}))$ and $\mathcal{M}(S^{-1}$ , $(e_{1},...,e_{n})$ , $(f_{1},...,f_{n}))$ both equal the $n$ -by- $\cdot n$ identity matrix. Hence  

9.54  

$$
\mathcal{M}\big(S^{-1}T S,(f_{1},...,f_{n})\big)=\mathcal{M}\big(T,(e_{1},...,e_{n})\big),
$$  

as follows from two applications of 3.43. Thus  

$$
\begin{array}{r l}&{\operatorname*{det}T=\operatorname*{det}\bigl(S^{-1}T S\bigr)}\\ &{\qquad=\operatorname*{det}\mathcal{M}\bigl(S^{-1}T S,(f_{1},...,f_{n})\bigr)}\\ &{\qquad=\operatorname*{det}\mathcal{M}\bigl(T,(e_{1},...,e_{n})\bigr),}\end{array}
$$  

where the first line comes from 9.52, the second line comes from the definition of the determinant of a matrix, and the third line follows from 9.54.  

The next result gives a more intuitive way to think about determinants than the definition or the formula in 9.46. We could make the characterization in the result below the definition of the determinant of an operator on a finite-dimensional complex vector space, with the current definition then becoming a consequence of that definition.  

9.55 if $\mathbf{F}=\mathbf{C},$ , then determinant equals product of eigenvalues  

Suppose $\mathbf{F}=\mathbf{C}$ and $T\in{\mathcal{L}}(V)$ . Then det $T$ equals the product of the eigenvalues of $T.$ , with each eigenvalue included as many times as its multiplicity.  

Proof There is a basis of $V$ with respect to which $T$ has an upper-triangular matrix with the diagonal entries of the matrix consisting of the eigenvalues of $T,$ , with each eigenvalue included as many times as its multiplicity—see 8.37. Thus 9.53 and 9.48 imply that det $T$ equals the product of the eigenvalues of $T_{\mathbf{\delta}}$ , with each eigenvalue included as many times as its multiplicity.  

As the next result shows, the determinant interacts nicely with the transpose of a square matrix, with the dual of an operator, and with the adjoint of an operator on an inner product space.  

(a) Suppose $A$ is a square matrix. Then det $A^{\mathrm{t}}=\operatorname*{det}A$ .  

(b) Suppose $T\in{\mathcal{L}}(V)$ . Then det $T^{\prime}=\operatorname*{det}T$ (c) Suppose $V$ is an inner product space and $T\in{\mathcal{L}}(V)$ . Then  

$$
\operatorname*{det}(T^{*})={\overline{{\operatorname*{det}T}}}.
$$  

## Proof  

(a) Let $n$ be a positive integer. Define $\alpha\colon\left(\mathbf{F}^{n}\right)^{n}\rightarrow\mathbf{F}$ by  

$$
\alpha{\Big(}{\big(}\begin{array}{l l l}{v_{1}}&{\cdots}&{v_{n}}\end{array}\big){\Big)}=\operatorname*{det}\!{\Big(}{\big(}\begin{array}{l l l}{v_{1}}&{\cdots}&{v_{n}}\end{array}\big)^{\mathrm{\scriptscriptstylet}}{\Big)}
$$  

for all $v_{1},...,v_{n}\in\mathbf{F}^{n}$ . The formula in 9.46 for the determinant of a matrix shows that $\alpha$ is an $n$ -linear form on $\mathbf{F}^{n}$ .  

Suppose $v_{1},...,v_{n}\in\mathbf{F}^{n}$ and $v_{j}=v_{k}$ for some $j\neq k$ . If $B$ is an $n$ -by- $_n$ matrix, then ${\left(\begin{array}{l l l}{v_{1}}&{\cdots}&{v_{n}}\end{array}\right)}^{\ell}B$ cannot equal the identity matrix because row $j$ and row $k$ of ${\left(\begin{array}{l l l}{v_{1}}&{\cdots}&{v_{n}}\end{array}\right)}^{\ell}B$ are equal. Thus ${\left(\begin{array}{l l l}{v_{1}}&{\cdots}&{v_{n}}\end{array}\right)}^{\mathbf{t}}$ is not invertible, which implies that $\alpha\Big(\big(\begin{array}{l l l}{v_{1}}&{\cdots}&{v_{n}}\end{array}\big)\Big)\,=\,0$ . Hence $\alpha$ is an alternating $n$ - linear form on $\mathbf{F}^{n}$ .  

Note that $\alpha$ applied to the standard basis of $\mathbf{F}^{n}$ equals 1. Because the vector space of alternating $n$ -linear forms on $\mathbf{F}^{n}$ has dimension one (by 9.37), this implies that $\alpha$ is the determinant function. Thus (a) holds.  

(b) The equation det $T^{\prime}=\operatorname*{det}T$ follows from (a) and 9.53 and 3.132.  

(c) Pick an orthonormal basis of $V.$ . The matrix of $T^{*}$ with respect to that basis is the conjugate transpose of the matrix of $T$ with respect to that basis (by 7.9). Thus 9.53, 9.46, and (a) imply that $\operatorname*{det}(T^{*})={\overline{{\operatorname*{det}T}}}.$ .  

## 9.57 helpful results in evaluating determinants  

(a) If either two columns or two rows of a square matrix are equal, then the determinant of the matrix equals 0.   
(b) Suppose $A$ is a square matrix and $B$ is the matrix obtained from $A$ by swapping either two columns or two rows. Then det $A=-\operatorname*{det}B$ .   
(c) If one column or one row of a square matrix is multiplied by a scalar, then the value of the determinant is multiplied by the same scalar.   
(d) If a scalar multiple of one column of a square matrix to added to another column, then the value of the determinant is unchanged.   
(e) If a scalar multiple of one row of a square matrix to added to another row, then the value of the determinant is unchanged.  

Proof All the assertions in this result follow from the result that the maps $v_{1},...,v_{n}\,\mapsto\,\operatorname*{det}\left(\begin{array}{l l l}{v_{1}}&{\cdots}&{v_{n}}\end{array}\right)$ and $v_{1},...,v_{n}\,\mapsto\,\operatorname*{det}\left(\,\ v_{1}\,\quad\cdots\,\quad v_{n}\ \right)^{\dagger}$ are both alternating $n$ -linear forms on $\mathbf{F}^{n}$ [see 9.45 and 9.56(a)].  

For example, to prove (d) suppose $v_{1},...,v_{n}\in\mathbf{F}^{n}$ and $c\in\mathbf{F}$ . Then  

$$
\begin{array}{r l}&{\operatorname*{det}\bigl(\begin{array}{l l l l l}{v_{1}+c v_{2}}&{v_{2}}&{\cdots}&{v_{n}}\end{array}\bigr)}\\ &{\quad\quad=\operatorname*{det}\bigl(\begin{array}{l l l l l}{v_{1}}&{v_{2}}&{\cdots}&{v_{n}}\end{array}\bigr)+c\operatorname*{det}\bigl(\begin{array}{l l l l l}{v_{2}}&{v_{2}}&{v_{3}}&{\cdots}&{v_{n}}\end{array}\bigr)}\\ &{\quad\quad=\operatorname*{det}\bigl(\begin{array}{l l l l l}{v_{1}}&{v_{2}}&{\cdots}&{v_{n}}\end{array}\bigr),}\end{array}
$$  

where the first equation follows from the multilinearity property and the second equation follows from the alternating property. The equation above shows that adding a multiple of the second column to the first column does not change the value of the determinant. The same conclusion holds for any two columns. Thus (d) holds.  

The proof of (e) follows from (d) and from 9.56(a). The proofs of (a), (b), and (c) use similar tools and are left to the reader.  

For matrices whose entries are concrete numbers, the result above leads to a much faster way to evaluate the determinant than direct application of the formula in 9.46. Specifically, apply the Gaussian elimination procedure of swapping rows [by 9.48(b), this changes the determinant by a factor of −1], multiplying a row by a nonzero constant [by 9.48(c), this changes the determinant by the same constant], and adding a multiple of one row to another row [by 9.48(e), this does not change the determinant] to produce an upper-triangular matrix, whose determinant is the product of the diagonal entries (by 9.48). If your software keeps track of the number of row swaps and of the constants used when multiplying a row by a constant, then the determinant of the original matrix can be computed.  

Because a number $\lambda\in\mathbf{F}$ is an eigenvalue of an operator $T\in{\mathcal{L}}(V)$ if and only if $\operatorname*{det}(\lambda I-T)\,=\,0$ (by 9.51), you may be tempted to think that one way to find eigenvalues quickly is to choose a basis of $V,$ , let $A\,=\,{\mathcal{M}}(T)$ , evaluate d $\operatorname{let}(\lambda I-A)$ , and then solve the equation $\operatorname*{det}(\lambda I-A)=0$ for $\lambda$ . However, that procedure is rarely efficient, except when dim $V=2$ (or when $\dim V$ equals 3 or 4 if you are willing to use the cubic or quartic formulas). One problem is that the procedure described in the paragraph above for evaluating a determinant does not work when the matrix includes a symbol (such as the $\lambda$ in $\lambda I-A)$ . This problem arises because decisions need to be made in the Gaussian elimination procedure about whether certain quantities equal 0, and those decisions become complicated in expressions involving a symbol $\lambda$ .  

Recall that an operator on a finite-dimensional inner product space is unitary if it preserves norms (see 7.51 and the paragraph following it). Every eigenvalue of a unitary operator has absolute value 1 (by 7.54). Thus the product of the eigenvalues of a unitary operator has absolute value 1. Hence (at least in the case $\mathbf{F}=\mathbf{C}_{}^{},$ ) the determinant of a unitary operator has absolute value 1 (by 9.55). The next result gives a proof that works without the assumption that $\mathbf{F}=\mathbf{C}$ .  

Suppose $V$ is an inner product space and $S\,\in\,{\mathcal{L}}(V)$ is a unitary operator.   
Then |det $S|=1$ .  

Proof Because $S$ is unitary, $I=S^{*}S$ (see 7.53). Thus  

$$
1=\operatorname*{det}(S^{*}S)=(\operatorname*{det}S^{*})(\operatorname*{det}S)=\overline{{(\operatorname*{det}S)}}(\operatorname*{det}S)=|\operatorname*{det}S|^{2},
$$  

where the second equality comes from 9.49(a) and the third equality comes from 9.56(c). The equation above implies that |det $S|=1$ .  

The determinant of a positive operator on an inner product space meshes well with the analogy that such operators correspond to the nonnegative real numbers.  

9.59 every positive operator has nonnegative determinant  

Suppose $V$ is an inner product space and $T\in{\mathcal{L}}(V)$ is a positive operator.   
Then det $T\geq0$ .  

Proof By the spectral theorem (7.29 or 7.31), $V$ has an orthonormal basis consisting of eigenvectors of $T.$ Thus by the last bullet point of 9.42, det $T$ equals a product of the eigenvalues of $T.$ , possibly with repetitions. Each eigenvalue of $T$ is a nonnegative number (by 7.38). Thus we conclude that det $T\geq0$ .  

Suppose $V$ is an inner product space and $T\in{\mathcal{L}}(V)$ . Recall that the list of nonnegative square roots of the eigenvalues of $T^{*}T$ (each included as many times as its multiplicity) is called the list of singular values of $T$ (see Section 7E).  

9.60 |det 𝑇| = product of singular values of $T$  

Suppose $V$ is an inner product space and $T\in{\mathcal{L}}(V)$ . Then  

$$
|\!\operatorname*{det}T|={\sqrt{\operatorname*{det}(T^{*}T)}}=\operatorname{product\,of\,}\operatorname{singular\,values\,of\,}T.
$$  

## Proof We have  

$$
|\mathbf{det}\,T|^{2}={\overline{{(\operatorname*{det}T)}}}(\operatorname*{det}T)=\left(\operatorname*{det}(T^{*})\right)(\operatorname*{det}T)=\operatorname*{det}(T^{*}T),
$$  

where the middle equality comes from 9.56(c) and the last equality comes from 9.49(a). Taking square roots of both sides of the equation above shows that |det $T|=\sqrt{\operatorname*{det}(T^{*}T)}$ .  

Let $s_{1},...,s_{n}$ denote the list of singular values of $T.$ . Thus $s_{1}^{\,2},...,s_{n}^{\,2}$ is the list of eigenvalues of $T^{*}T$ (with appropriate repetitions), corresponding to an orthonormal basis of $V$ consisting of eigenvectors of $T^{*}T.$ Hence the last bullet point of 9.42 implies that  

Thus |det $T|=s_{1}{\cdots}s_{n}$ , as desired.  

$$
\operatorname*{det}(T^{*}T)=s_{1}^{2}{\cdots}s_{n}^{\,2}.
$$  

An operator $T$ on a real inner product space changes volume by a factor of the product of the singular values (by 7.111). Thus the next result follows immediately from 7.111 and 9.60. This result explains why the absolute value of a determinant appears in the change of variables formula in multivariable calculus.  

9.61 𝑇changes volume by factor of |det $T|$  

Suppose $T\in{\mathcal{L}}(\mathbf{R}^{n})$ and $\Omega\subseteq\mathbf{R}^{n}.$ Then  

$$
\mathrm{volume}\,T(\Omega)=|\mathrm{det}\,T|(\mathrm{volume}\,\Omega).
$$  

For operators on finite-dimensional complex vector spaces, we now connect the determinant to a polynomial that we have previously seen.  

9.62 if $\mathbf{F}=\mathbf{C},$ , then characteristic polynomial of $T$ equals det(𝑧𝐼−𝑇)  

Suppose $\mathbf{F}=\mathbf{C}$ and $T\in{\mathcal{L}}(V)$ . Let $\lambda_{1},...,\lambda_{m}$ denote the distinct eigenvalues of $T$ , and let $d_{1},...,d_{m}$ denote their multiplicities. Then  

$$
\operatorname*{det}(z I-T)=(z-\lambda_{1})^{d_{1}}\cdots(z-\lambda_{m})^{d_{m}}.
$$  

Proof There exists a basis of $V$ with respect to which $T$ has an upper-triangular matrix with each $\lambda_{k}$ appearing on the diagonal exactly $d_{k}$ times (by 8.37). With respect to this basis, $z I-T$ has an upper-triangular matrix with $z-\lambda_{k}$ appearing on the diagonal exactly $d_{k}$ times for each $k$ . Thus 9.48 gives the desired equation.  

Suppose $\mathbf{F}\,=\,\mathbf{C}$ and $T\,\in\,{\mathcal{L}}(V)$ . The characteristic polynomial of $T$ was defined in 8.26 as the polynomial on the right side of the equation in 9.62. We did not previously define the characteristic polynomial of an operator on a finitedimensional real vector space because such operators may have no eigenvalues, making a definition using the right side of the equation in 9.62 inappropriate.  

We now present a new definition of the characteristic polynomial, motivated by 9.62. This new definition is valid for both real and complex vector spaces. The equation in 9.62 shows that this new definition is equivalent to our previous definition when $\mathbf{F}=\mathbf{C}$ (8.26).  

## 9.63 definition: characteristic polynomial  

Suppose $T\in{\mathcal{L}}(V)$ . The polynomial defined by  

$$
z\mapsto\operatorname*{det}(z I-T)
$$  

is called the characteristic polynomial of $T$ .  

The formula in 9.46 shows that the characteristic polynomial of an operator $T\in{\mathcal{L}}(V)$ is a monic polynomial of degree $\dim V.$ . The zeros in 𝐅of the characteristic polynomial of $T$ are exactly the eigenvalues of $T$ (by 9.51).  

Previously we proved the Cayley–Hamilton theorem (8.29) in the complex case. Now we can extend that result to operators on real vector spaces.  

## 9.64 Cayley–Hamilton theorem  

Suppose $T\in{\mathcal{L}}(V)$ and $q$ is the characteristic polynomial of $T.$ . Then $q(T)=0.$ .  

Proof If $\mathbf{F}=\mathbf{C}$ , then the equation $q(T)=0$ follows from 9.62 and 8.29.  

Now suppose $\mathbf{F}\,=\,\mathbf{R}$ . Fix a basis of $V,$ and let $A$ be the matrix of $T$ with respect to this basis. Let $S$ be the operator on $C^{\dim V}$ such that the matrix of $S$ (with respect to the standard basis of $C^{\dim V}$ ) is $A$ . For all $z\in\mathbb{R}$ we have  

$$
q(z)=\operatorname*{det}(z I-T)=\operatorname*{det}(z I-A)=\operatorname*{det}(z I-S).
$$  

Thus $q$ is the characteristic polynomial of $S$ . The case $\mathbf{F}=\mathbf{C}$ (first sentence of this proof) now implies that $0=q(S)=q(A)=q(T)$ .  

The Cayley–Hamilton theorem (9.64) implies that the characteristic polynomial of an operator $T\in{\mathcal{L}}(V)$ is a polynomial multiple of the minimal polynomial of $T$ (by 5.29). Thus if the degree of the minimal polynomial of $T$ equals dim $V,$ then the characteristic polynomial of $T$ equals the minimal polynomial of $T.$ This happens for a very large percentage of operators, including over $99.999\%$ of 4-by-4 matrices with integer entries in $[-100,100]$ (see the paragraph following 5.25).  

The last sentence in our next result was previously proved in the complex case (see 8.54). Now we can give a proof that works on both real and complex vector spaces.  

9.65 characteristic polynomial, trace, and determinant  

Suppose $T\in{\mathcal{L}}(V)$ . Let $n=\dim V.$ Then the characteristic polynomial of $T$ can be written as  

$$
z^{n}-(\operatorname{tr}T)z^{n-1}+\cdots+(-1)^{n}(\operatorname*{det}T).
$$  

Proof The constant term of a polynomial function of $z$ is the value of the polynomial when $z=0$ . Thus the constant term of the characteristic polynomial of $T$ equals det $(-T)$ , which equals $(-1)^{n}$ det $T$ (by the third bullet point of 9.42).  

Fix a basis of $V,$ and let $A$ be the matrix of $T$ with respect to this basis. The matrix of $z I-T$ with respect to this basis is $z I-A$ . The term coming from the identity permutation $\{1,...,n\}$ in the formula 9.46 for de $:\!(z I-A)$ is  

$$
(z-A_{1,1})\cdots(z-A_{n,n}).
$$  

The coefficient of $z^{n-1}$ in the expression above is $-(A_{1,1}+\cdots+A_{n,n})$ , which equals −tr $T$ . The terms in the formula for de $\mathbf{t}(z I-A)$ coming from other elements of perm $n$ contain at most $n\!-\!2$ factors of the form $z\!-\!A_{k,k}$ and thus do not contribute to the coefficient of $z^{n-1}$ in the characteristic polynomial of $T$ .  

In the result below, think of the columns of the $n$ -by- $\cdot n$ matrix $A$ as elements of $\mathbf{F}^{n}.$ . The norms appearing below  

The next result was proved by Jacques Hadamard (1865–1963) in 1893.  

then arise from the standard inner product on $\mathbf{F}^{n}$ . Recall that the notation $R_{.,k}$ in the proof below means the $k^{\mathrm{th}}$ column of the matrix $R$ (as was defined in 3.44).  

9.66 Hadamard’s inequality   
Suppose $A$ is an $n$ -by- $_n$ matrix. Let $v_{1},...,v_{n}$ denote the columns of $A$ . Then $|\operatorname*{det}A|\leq\prod_{k\,=\,1}^{n}\|v_{k}\|.$  

Proof If $A$ is not invertible, then det $A=0$ and hence the desired inequality holds in this case.  

Thus assume that $A$ is invertible. The QR factorization (7.58) tells us that there exist a unitary matrix $Q$ and an upper-triangular matrix $R$ whose diagonal contains only positive numbers such that $A=Q R$ . We have  

$$
\begin{array}{r l}&{A|=\vert\ensuremath{\mathrm{det}}(Q|\ensuremath{\mathrm{det}}\,R)\,}\\ &{\phantom{\lambda}=\vert\ensuremath{\mathrm{det}}R\,\ensuremath{\mathrm{det}}}\\ &{\phantom{\lambda}=\prod_{i=1}^{n}R_{k,k}}\\ &{\phantom{\lambda}\leq\displaystyle\sum_{i=1}^{n}\|R_{i,k}\|}\\ &{\phantom{\lambda}=\displaystyle\sum_{k=1}^{n}\|Q R_{k,k}\|}\\ &{\phantom{\lambda}=\displaystyle\sum_{i=1}^{n}\|P_{k,k}\|,}\\ &{\phantom{\lambda}=\displaystyle\int_{\ensuremath{\mathrm{det}}}\|P_{k}\|,}\end{array}
$$  

where the first line comes from 9.49(b), the second line comes from 9.58, the third line comes from 9.48, and the fifth line holds because $Q$ is an isometry.  

To give a geometric interpretation to Hadamard’s inequality, suppose $\mathbf{F}=\mathbf{R}$ . Let $T\in{\mathcal{L}}(\mathbf{R}^{n})$ be the operator such that $T e_{k}=v_{k}$ for each $k=1,...,n$ , where $e_{1},...,e_{n}$ is the standard basis of $\mathbf{R}^{n}.$ . Then $T$ maps the box $P(e_{1},...,e_{n})$ onto the parallelepiped $P(v_{1},...,v_{n})$ [see 7.102 and 7.105 for a review of this notation and terminology]. Because the box $P(e_{1},...,e_{n})$ has volume 1, this implies (by 9.61) that the parallelepiped $P(v_{1},...,v_{n})$ has volume |det $T|$ , which equals $|\mathrm{det}A|$ . Thus Hadamard’s inequality above can be interpreted to say that among all parallelepipeds whose edges have lengths $\|v_{1}\|,...,\|v_{n}\|$ , the ones with largest volume have orthogonal edges (and thus have volume $\dot{\prod}_{k=1}^{n}\left\lVert v_{k}\right\rVert\right)$ .  

For a necessary and sufficient condition for Hadamard’s inequality to be an equality, see Exercise 18.  

The matrix in the next result is called the Vandermonde matrix. Vandermonde matrices have important applications in polynomial interpolation, the discrete Fourier transform, and other areas of mathematics. The proof of the next result is a nice illustration of the power of switching between matrices and linear maps.  

9.67 determinant of Vandermonde matrix  

Suppose $n>1$ and $\beta_{1},...,\beta_{n}\in\mathbf{F}$ . Then  

$$
\operatorname*{det}\left(\begin{array}{l l l l l}{{1}}&{{\beta_{1}}}&{{\beta_{1}^{\;2}}}&{{\cdots}}&{{\beta_{1}^{\;n\;-1}}}\\ {{1}}&{{\beta_{2}}}&{{\beta_{2}^{\;2}}}&{{\cdots}}&{{\beta_{2}^{\;n\;-1}}}\\ {{}}&{{}}&{{\ddots}}&{{}}\\ {{}}&{{}}&{{}}&{{}}&{{}}\\ {{1}}&{{\beta_{n}}}&{{\beta_{n}^{\;2}}}&{{\cdots}}&{{\beta_{n}^{\;n\;-1}}}\end{array}\right)=\prod_{1\leq j<k\leq n}(\beta_{k}-\beta_{j}).
$$  

Proof Let $1,z,...,z^{n-1}$ be the standard basis of ${\mathcal{P}}_{n-1}(\mathbf{F})$ and let $e_{1},...,e_{n}$ denote the standard basis of $\mathbf{F}^{n}$ . Define a linear map $S\colon{\mathcal{P}}_{n-1}(\mathbf{F})\to\mathbf{F}^{n}$ by  

$$
S p=(p(\beta_{1}),...,p(\beta_{n})).
$$  

Let $A$ denote the Vandermonde matrix shown in the statement of this result. Note that  

$$
A={\mathcal{M}}{\big(}S,(1,z,...,z^{n-1}),(e_{1},...,e_{n}){\big)}.
$$  

Let $T\colon{\mathcal{P}}_{n-1}(\mathbf{F})\,\to\,{\mathcal{P}}_{n-1}(\mathbf{F})$ be the operator on ${\mathcal{P}}_{n-1}(\mathbf{F})$ such that $T1=1$ and  

$$
T z^{k}=(z-\beta_{1})(z-\beta_{2})\cdots(z-\beta_{k})
$$  

for $k=1,...,n-1$ . Let $B=\mathcal{M}(T,(1,z,...,z^{n-1})$ , $(1,z,...,z^{n-1})\big)$ . Then $B$ is an upper-triangular matrix all of whose diagonal entries equal 1. Thus det $B=1$ (by 9.48).  

Let $C=\mathcal{M}(S T,(1,z,...,z^{n-1})$ , $(e_{1},...,e_{n}))$ . Thus $C=A B$ (by 3.81), which implies that  

$$
\operatorname*{det}A=(\operatorname*{det}A)(\operatorname*{det}B)=\operatorname*{det}C.
$$  

The definitions of $C,S$ , and $T$ show that $C$ equals  

$$
{\begin{array}{c c c c c}{0}&{0}&{\cdots}&{}&{0}\\ {\l_{3}}&{\l_{2}}&{0}&{\cdots}&{}&{0}\\ {\l_{3_{2}}-\beta_{1}}&{(\beta_{3}-\beta_{1})(\beta_{3}-\beta_{2})}&{\cdots}&{}&{0}\\ {\l_{3}}&{}&{}&{}&{\l_{\cdots}}\\ {\l_{2}}&{}&{}&{}&{\ddots}\\ {\l_{3_{2}}-\beta_{1}}&{(\beta_{3}-\beta_{1})(\beta_{3}-\beta_{2})}&{\cdots}&{(\beta_{n}-\beta_{1})(\beta_{n}-\beta_{2})\cdots(\beta_{n}-\beta_{n-1})}\end{array}}
$$  

Now det $\begin{array}{r l}{A=\operatorname*{det}C={}}&{{}\prod\quad(\beta_{k}-\beta_{j})}\end{array}$ , where we have used 9.56(a) and 9.48. $1\leq j<k\leq n$  

1 Prove or give a counterexample: $S,T\in{\mathcal{L}}(V)\implies\operatorname*{det}(S\!+\!T)=\operatorname*{det}S\!+\!\operatorname*{det}T.$  

2 Suppose the first column of a square matrix $A$ consists of all zeros except possibly the first entry $A_{1,1}$ . Let $B$ be the matrix obtained from $A$ by deleting the first row and the first column of $A$ . Show that det $A=A_{1,1}$ det $B$ .  

3 Suppose $T\in{\mathcal{L}}(V)$ is nilpotent. Prove that det $(I+T)=1$ .  

4 Suppose $S\in{\mathcal{L}}(V)$ . Prove that $S$ is unitary if and only if $|\operatorname*{det}S|=\|S\|=1$ .  

5 Suppose $A$ is a block upper-triangular matrix  

$$
A={\left(\begin{array}{l l l}{A_{1}}&&{}&{*}\\ &{\ddots}&\\ {0}&&{}&{A_{m}}\end{array}\right)},
$$  

where each $A_{k}$ along the diagonal is a square matrix. Prove that  

$$
\operatorname*{det}A=(\operatorname*{det}A_{1})\cdots(\operatorname*{det}A_{m}).
$$  

6 Suppose $A={\left(\begin{array}{l l l}{v_{1}}&{\cdots}&{v_{n}}\end{array}\right)}$ is an $n$ -by- $_n$ matrix, with $v_{k}$ denoting the $k^{\mathrm{th}}$ column of $A$ . Show that if $(m_{1},...,m_{n})\in$ perm $n$ , then  

$$
\operatorname*{det}{\left(\begin{array}{l l l}{v_{m_{1}}}&{\cdots}&{v_{m_{n}}}\end{array}\right)}=\left(\operatorname{sign}(m_{1},...,m_{n})\right)\operatorname*{det}A.
$$  

7 Suppose $T\in{\mathcal{L}}(V)$ is invertible. Let $p$ denote the characteristic polynomial of $T$ and let $q$ denote the characteristic polynomial of $T^{-1}$ . Prove that  

$$
q(z)=\frac{1}{p(0)}\,z^{\dim V}\,p\bigg(\frac{1}{z}\bigg)
$$  

for all nonzero $z\in\mathbf{F}$ .  

8 Suppose $T\in{\mathcal{L}}(V)$ is an operator with no eigenvalues (which implies that $\mathbf{F}=\mathbf{R}_{\alpha}$ ). Prove that det $T>0$ .  

9 Suppose that $V$ is a real vector space of even dimension, $T\in{\mathcal{L}}(V)$ , and det $T<0$ . Prove that $T$ has at least two distinct eigenvalues.  

10 Suppose $V$ is a real vector space of odd dimension and $T\in{\mathcal{L}}(V)$ . Without using the minimal polynomial, prove that $T$ has an eigenvalue.  

This result was previously proved without using determinants or the characteristic polynomial—see 5.34.  

11 Prove or give a counterexample: If $\mathbf{F}=\mathbf{R}$ , $T\in{\mathcal{L}}(V)$ , and det $T>0$ , then $T$ has a square root.  

If $\mathbf{F}=\mathbf{C}\,$ , $T\in{\mathcal{L}}(V)$ , and det $V\neq0$ , then $V$ has a square root (see 8.41).  

12 Suppose $S,T\in{\mathcal{L}}(V)$ and $S$ is invertible. Define $p\colon\mathbf{F}\rightarrow\mathbf{F}$ by  

$$
p(z)=\operatorname*{det}(z S-T).
$$  

Prove that $p$ is a polynomial of degree dim $V$ and that the coefficient of $z^{\dim V}$ in this polynomial is det $S$ .  

13 Suppose ${\textbf{F}}={\textbf{C}}$ , $T\,\in\,{\mathcal{L}}(V)$ , and $n\,=\,\dim V\,>\,2$ . Let $\lambda_{1},...,\lambda_{n}$ denote the eigenvalues of $T$ , with each eigenvalue included as many times as its multiplicity.  

(a) Find a formula for the coefficient of $z^{n-2}$ in the characteristic polynomial of $T$ in terms of $\lambda_{1},...,\lambda_{n}$ .   
(b) Find a formula for the coefficient of $z$ in the characteristic polynomial of $T$ in terms of $\lambda_{1},...,\lambda_{n}$ .  

14 Suppose $V$ is an inner product space and $T$ is a positive operator on $V.$ . Prove that  

$$
\operatorname*{det}{\sqrt{T}}={\sqrt{\operatorname*{det}T}}.
$$  

15 Suppose $V$ is an inner product space and $T\in{\mathcal{L}}(V)$ . Use the polar decomposition to give a proof that  

$$
|\mathbf{det}\,T|={\sqrt{\mathbf{det}(T^{*}T)}}
$$  

that is different from the proof given earlier (see 9.60).  

16 Suppose $T\in{\mathcal{L}}(V)$ . Define $g\colon\mathbf{F}\rightarrow\mathbf{F}$ by $g(x)=\operatorname*{det}(I+x T)$ . Show that $g^{\prime}(0)=\operatorname{tr}T.$ .  

Look for a clean solution to this exercise, without using the explicit but complicated formula for the determinant of a matrix.  

17 Suppose $a,b,c$ are positive numbers. Find the volume of the ellipsoid  

$$
\left\{(x,y,z)\in\mathbf{R}^{3}:{\frac{x^{2}}{a^{2}}}+{\frac{y^{2}}{b^{2}}}+{\frac{z^{2}}{c^{2}}}<1\right\}
$$  

by finding a set $\Omega\subseteq\mathbb{R}^{3}$ whose volume you know and an operator $T$ on $\mathbf{R}^{3}$ such that $T(\Omega)$ equals the ellipsoid above.  

18 Suppose that $A$ is an invertible square matrix. Prove that Hadamard’s inequality (9.66) is an equality if and only if each column of $A$ is orthogonal to the other columns.  

19 Suppose $V$ is an inner product space, $e_{1},...,e_{n}$ is an orthonormal basis of $V.$ , and $T\in{\mathcal{L}}(V)$ is a positive operator.  

(a) Prove that det $\begin{array}{r}{T\leq\prod_{k=1}^{n}\langle T e_{k},e_{k}\rangle}\end{array}$ . (b) Prove that if $T$ is invertible, then the inequality in (a) is an equality if and only if $e_{k}$ is an eigenvector of $T$ for each $k=1,...,n$ .  

20 Suppose $A$ is an $n$ -by- $_n$ matrix, and suppose $c$ is such that $|A_{j,k}|\leq c$ for all $j,k\in\{1,...,n\}$ . Prove that  

$$
|\operatorname*{det}A|\leq c^{n}n^{n/2}.
$$  

The formula for the determinant of a matrix (9.46) shows that |det $A|\leq c^{n}n!$ . However, the estimate given by this exercise is much better. For example, if $c=1$ and $n=100$ , then $c^{n}n!\approx10^{158},$ , but the estimate given by this exercise is the much smaller number $10^{100}.$ . If $n$ is an integer power of 2, then the inequality above is sharp and cannot be improved.  

21 Suppose $n$ is a positive integer and $\delta\colon\mathbf{C}^{n,n}\rightarrow\mathbf{C}$ is a function such that  

$$
\delta(A B)=\delta(A)\cdot\delta(B)
$$  

for all $A,B\in\mathbf{C}^{n,n}$ and $\delta(A)$ equals the product of the diagonal entries of $A$ for each diagonal matrix $A\in\mathbf{C}^{n,n}$ . Prove that  

$$
\delta(A)=\operatorname*{det}A
$$  

for all $A\in\mathbf{C}^{n,n}$ .  

Recall that $\mathbf{C}^{n,n}$ denotes set of $n$ -by- $_n$ matrices with entries in 𝐂. This exercise shows that the determinant is the unique function defined on square matrices that is multiplicative and has the desired behavior on diagonal matrices. This result is analogous to Exercise 10 in Section 8D, which shows that the trace is uniquely determined by its algebraic properties.  

I find that in my own elementary lectures, I have, for pedagogical reasons, pushed determinants more and more into the background. Too often I have had the experience that, while the students acquired facility with the formulas, which are so useful in abbreviating long expressions, they often failed to gain familiarity with their meaning, and skill in manipulation prevented the student from going into all the details of the subject and so gaining a mastery.  

## Tensor Product of Two Vector Spaces  

The motivation for our next topic comes from wanting to form the product of a vector $v\,\in\,V$ and a vector $w\in W.$ . This product will be denoted by $v\otimes w$ , pronounced $\mathrm{~\hat{~}{~v~}~}$ tensor $w$ ”, and will be an element of some new vector space called $V\otimes W$ (also pronounced $^{\bullet\bullet}V$ tensor 𝑊”).  

We already have a vector space $V\times W$ (see Section 3E), called the product of $V$ and 𝑊. However, $V\times W$ will not serve our purposes here because it does not provide a natural way to multiply an element of $V$ by an element of 𝑊. We would like our tensor product to satisfy some of the usual properties of multiplication. For example, we would like the distributive property to be satisfied, meaning that if $v_{1},v_{2},v\in V$ and $w_{1},w_{2},w\in W_{}$ , then  

$$
v_{2})\otimes w=v_{1}\otimes w+v_{2}\otimes w\quad\mathrm{and}\quad v\otimes(w_{1}+w_{2})=v\otimes w_{1}+v\otimes w_{2}
$$  

We would also like scalar multiplica- To produce $\otimes$ in TEX, type \otimes. tion to interact well with this new multiplication, meaning that  

$$
\lambda(v\otimes w)=(\lambda v)\otimes w=v\otimes(\lambda w)
$$  

for all $\lambda\in\mathbf{F},v\in V,$ , and $w\in W.$ .  

Furthermore, it would be nice if each basis of $V$ when combined with each basis of $W$ produced a basis of $V\otimes W.$ . Specifically, if $e_{1},...,e_{m}$ is a basis of $V$ and $f_{1},...,f_{n}$ is a basis of $W.$ , then we would like a list (in any order) consisting of $e_{j}\otimes f_{k}$ , as $j$ ranges from 1 to $m$ and $k$ ranges from 1 to $n$ , to be a basis of $V\otimes W.$ . This implies that $\dim(V\otimes W)$ should equal $(\dim V)(\dim W)$ . Recall that $\dim(V\times W)=\dim V+\dim W$ (see 3.92), which shows that the product $V\times W$ will not serve our purposes here.  

To produce a vector space whose dimension is $(\dim V)(\dim W)$ in a natural fashion from $V$ and $W$ , we look at the vector space of bilinear functionals, as defined below.  

9.68 definition: bilinear functional on $V\times W,$ , the vector space $\mathcal{B}(V,W)$  

A bilinear functional on $V\times W$ is a function $\beta\colon V\times W\,\to\,{\bf F}$ such that $v\mapsto\beta(v,w)$ is a linear functional on $V$ for each $w\in W$ and $w\mapsto\beta(v,w)$ is a linear functional on $W$ for each $v\in V.$ The vector space of bilinear functionals on $V\times W$ is denoted by $\mathcal{B}(V,W)$ .  

If $W=V$ , then a bilinear functional on $V\times W$ is a bilinear form; see 9.1.  

The operations of addition and scalar multiplication on $\mathcal{B}(V,W)$ are defined to be the usual operations of addition and scalar multiplication of functions. As you can verify, these operations make $\mathcal{B}(V,W)$ into a vector space whose additive identity is the zero function from $V\times W$ to $\mathbf{F}$ .  

• Suppose $\varphi\in V^{\prime}$ and $\tau\in W^{\prime}$ Define $\beta\colon V\times W\rightarrow\mathbf{F}$ by $\beta(v,w)=\varphi(v)\tau(w)$ . Then $\beta$ is a bilinear functional on $V\times W.$ .   
• Suppose $v\in V$ and $w\in W.$ Define $\beta\colon V^{\prime}\times W^{\prime}\to\mathbf{F}$ by $\beta(\varphi,\tau)=\varphi(v)\tau(w)$ . Then $\beta$ is a bilinear functional on $V^{\prime}\times W^{\prime}$ .   
• Define $\beta\colon V\times V^{\prime}\to\mathbf{F}$ by $\beta(v,\varphi)=\varphi(v)$ . Then $\beta$ is a bilinear functional on $V\times V^{\prime}$ .   
• Suppose $\varphi\in V^{\prime}$ . Define $\beta\colon V\times{\mathcal{L}}(V)\to\mathbf{F}$ by $\beta(v,T)=\varphi(T v)$ . Then $\beta$ is a bilinear functional on $V\times{\mathcal{L}}(V)$ .   
• Suppose $m$ and $n$ are positive integers. Define $\beta\colon\mathbf{F}^{m,n}\!\times\!\mathbf{F}^{n,m}\rightarrow\mathbf{F}$ by $\beta(A,B)=$ $\mathrm{tr}(A B)$ . Then $\beta$ is a bilinear functional on $\mathbf{F}^{m,n}\times\mathbf{F}^{n,m}.$ .  

9.70 dimension of the vector space of bilinear functionals  

$\dim{\mathcal{B}}(V,W)=(\dim V)(\dim W).$  

Proof Let $e_{1},...,e_{m}$ be a basis of $V$ and $f_{1},...,f_{n}$ be a basis of $W.$ For a bilinear functional $\beta\in{\mathcal{B}}(V,W)$ , let $\mathcal{M}(\beta)$ be the $m$ -by- $_n$ matrix whose entry in row $j$ , column $k$ is $\beta(e_{j},f_{k})$ . The map $\beta\mapsto\mathcal{M}(\beta)$ is a linear map of $\mathcal{B}(V,W)$ into $\mathbf{F}^{m,n}$ . For a matrix $C\in\mathbf{F}^{m,n}.$ define a bilinear functional $\beta_{C}$ on $V\times W$ by  

$$
\beta_{C}(a_{1}e_{1}+\cdots+a_{m}e_{m},b_{1}f_{1}+\cdots+b_{n}f_{n})=\sum_{k\,=\,1}^{n}\sum_{j\,=\,1}^{m}C_{j,k}a_{j}b_{k}
$$  

for $a_{1},...,a_{m},b_{1},...,b_{n}\in\mathbf{F}$ .  

The linear map $\beta\mapsto\mathcal{M}(\beta)$ from $\mathcal{B}(V,W)$ to $\mathbf{F}^{m,n}$ and the linear map $C\mapsto\beta_{C}$ from $\mathbf{F}^{m,n}$ to $\mathcal{B}(V,W)$ are inverses of each other because $\beta_{\mathcal{M}(\beta)}\;=\;\beta$ for all $\beta\in{\mathcal{B}}(V,W)$ and $\mathcal{M}(\beta_{C})=C$ for all $C\in\mathbf{F}^{m,n};$ , as you should verify.  

Thus both maps are isomorphisms and the two spaces that they connect have the same dimension. Hence dim $\mathcal{B}(V,W)=\dim\mathbf{F}^{m,n}=m n=(\dim V)$ (dim 𝑊).  

Several different definitions of $V\otimes W$ appear in the mathematical literature. These definitions are equivalent to each other, at least in the finite-dimensional context, because any two vector spaces of the same dimension are isomorphic.  

The result above states that $\mathcal{B}(V,W)$ has the dimension that we seek, as do $\mathcal{L}(V,W)$ and $\mathbf{F}^{\mathrm{dim}\,V,\,\mathrm{dim}\,W}.$ . Thus it may be tempting to define $V\otimes W$ to be $\mathcal{B}(V,W)$ or $\mathcal{L}(V,W)$ or $\mathbf{F}^{\mathrm{dim}\,V,\,\mathrm{dim}\,W}.$ . However, none of those definitions would lead to a basis-free definition of $v\otimes w$ for $v\in V$ and $w\in W$ .  

The following definition, while it may seem a bit strange and abstract at first, has the huge advantage that it defines $v\otimes w$ in a basis-free fashion. We define $V\otimes W$ to be the vector space of bilinear functionals on $V^{\prime}\times W^{\prime}$ instead of the more tempting choice of the vector space of bilinear functionals on $V\times W.$ .  

• The tensor product $V\otimes W$ is defined to be $\mathcal{B}(V^{\prime},W^{\prime})$ .  

For $v\in V$ and $w\in W_{\mathrm{s}}$ the tensor product $v\otimes w$ is the element of $V\otimes W$ defined by  

$$
(v\otimes w)(\varphi,\tau)=\varphi(v)\tau(w)
$$  

for all $(\varphi,\tau)\in V^{\prime}\times W_{\cdot}^{\prime}$ .  

We can quickly prove that the definition of $V\otimes W$ gives it the desired dimension.  

9.72 dimension of the tensor product of two vector spaces  

$\dim(V\otimes W)=(\dim V)(\dim W).$  

Proof Because a vector space and its dual have the same dimension (by 3.111), we have dim $V^{\prime}\;=\;\dim V$ and dim $W^{\prime}\;=\;\dim W.$ . Thus 9.70 tells us that the dimension of $\mathcal{B}(V^{\prime},W^{\prime})$ equals $\operatorname{dim}V$ )(dim 𝑊).  

To understand the definition of the tensor product $v\otimes w$ of two vectors $v\in V$ and $w\in W_{\mathrm{s}}$ focus on the kind of object it is. An element of $V\otimes W$ is a bilinear functional on $V^{\prime}\times W^{\prime},$ , and in particular it is a function from $V^{\prime}\times W^{\prime}$ to 𝐅. Thus for each element of $V^{\prime}\times W^{\prime},$ it should produce an element of 𝐅. The definition above has this behavior, because $v\otimes w$ applied to a typical element $(\varphi,\tau)$ of $V^{\prime}\times W^{\prime}$ produces the number $\varphi(v)\tau(w)$ .  

The somewhat abstract nature of $v\otimes w$ should not matter. The important point is the behavior of these objects. The next result shows that tensor products of vectors have the desired bilinearity properties.  

9.73 bilinearity of tensor product  

Suppose $v,v_{1},v_{2}\in V$ and $w,w_{1},w_{2}\in W$ and $\lambda\in\mathbf{F}$ . Then $v_{1}+v_{2})\otimes w=v_{1}\otimes w+v_{2}\otimes w\quad{\mathrm{and}}\quad v\otimes(w_{1}+w_{2})=v\otimes w_{1}+v$ and  

$$
\lambda(v\otimes w)=(\lambda v)\otimes w=v\otimes(\lambda w).
$$  

Proof Suppose $(\varphi,\tau)\in V^{\prime}\times W_{\cdot}^{\prime}$ . Then  

$$
\begin{array}{r l}&{\bigl((v_{1}+v_{2})\otimes w\bigr)(\varphi,\tau)=\varphi(v_{1}+v_{2})\tau(w)}\\ &{\qquad\qquad\qquad\qquad=\varphi(v_{1})\tau(w)+\varphi(v_{2})\tau(w)}\\ &{\qquad\qquad\qquad\qquad=(v_{1}\otimes w)(\varphi,\tau)+(v_{2}\otimes w)(\varphi,\tau)}\\ &{\qquad\qquad\qquad\qquad=(v_{1}\otimes w+v_{2}\otimes w)(\varphi,\tau).}\end{array}
$$  

Thus $(v_{1}+v_{2})\otimes w=v_{1}\otimes w+v_{2}\otimes w$ . The other two equalities are proved similarly.  

Lists are, by definition, ordered. The order matters when, for example, we form the matrix of an operator with respect to a basis. For lists in this section with two indices, such as $\{e_{j}\otimes f_{k}\}_{j=1,\dots,m;k=1,\dots,n}$ in the next result, the ordering does not matter and we do not specify it—just choose any convenient ordering.  

The linear independence of elements of $V\otimes W$ in (a) of the result below captures the idea that there are no relationships among vectors in $V\otimes W$ other than the relationships that come from bilinearity of the tensor product (see 9.73) and the relationships that may be present due to linear dependence of a list of vectors in $V$ or a list of vectors in $W.$ .  

## 9.74 basis of 𝑉⊗𝑊  

Suppose $e_{1},...,e_{m}$ is a list of vectors in $V$ and $f_{1},...,f_{n}$ is a list of vectors in 𝑊.  

(a) If $e_{1},...,e_{m}$ and $f_{1},...,f_{n}$ are both linearly independent lists, then  

$$
\{e_{j}\otimes f_{k}\}_{j=1,\dots,m;k=1,\dots,n}
$$  

is a linearly independent list in $V\otimes W.$ .  

(b) If $e_{1},...,e_{m}$ is a basis of $V$ and $f_{1},...,f_{n}$ is a basis of $W_{s}$ , then the list $\{e_{j}\otimes f_{k}\}_{j=1,\dots,m;k=1,\dots,n}$ is a basis of $V\otimes W$ .  

Proof To prove (a), suppose $e_{1},...,e_{m}$ and $f_{1},...,f_{n}$ are both linearly independent lists. This linear independence and the linear map lemma (3.4) imply that there exist $\varphi_{1},...,\varphi_{m}\in V^{\prime}$ and $\tau_{1},...,\tau_{n}\in W^{\prime}$ such that  

$$
\varphi_{j}(e_{k})={\left\{\begin{array}{l l}{1}&{{\mathrm{if~}}j=k,}\\ {0}&{{\mathrm{if~}}j\neq k}\end{array}\right.}{\mathrm{~and~}}\quad\tau_{j}(f_{k})={\left\{\begin{array}{l l}{1}&{{\mathrm{if~}}j=k,}\\ {0}&{{\mathrm{if~}}j\neq k,}\end{array}\right.}
$$  

where $j,k\,\in\,\{1,...,m\}$ in the first equation and $j,k\,\in\,\{1,...,n\}$ in the second equation.  

Suppose $\{a_{j,k}\}_{j=1,\ldots,m;k=1,\ldots,n}$ is a list of scalars such that  

$$
\sum_{k=1}^{n}\sum_{j=1}^{m}a_{j,k}(e_{j}\otimes f_{k})=0.
$$  

Note that $(e_{j}\otimes f_{k})(\varphi_{M},\tau_{N})$ equals 1 if $j=M$ and $k=N$ , and equals 0 otherwise. Thus applying both sides of 9.75 to $(\varphi_{M},\tau_{N})$ shows that $a_{M,N}=0$ , proving that $\{e_{j}\otimes f_{k}\}_{j=1,\dots,m;k=1,\dots,n}$ is linearly independent.  

Now (b) follows from (a), the equation d $\ m\,V\otimes W=(\dim V)(\dim W)$ ) [see 9.72], and the result that a linearly independent list of the right length is a basis (see 2.38).  

Every element of $V\times W$ is a finite sum of elements of the form $v\otimes w$ , where $v\in V$ and $w\in W_{\mathrm{s}}$ , as implied by (b) in the result above. However, if dim $V>1$ and dim $W>1$ , then Exercise 4 shows that  

$$
\{v\otimes w:(v,w)\in V\times W\}\neq V\otimes W.
$$  

Suppose $m$ and $n$ are positive integers. Let $e_{1},...,e_{m}$ denote the standard basis of $\mathbf{F}^{m}$ and let $f_{1},...,f_{n}$ denote the standard basis of $\mathbf{F}^{n}$ . Suppose  

$$
v=(v_{1},...,v_{m})\in\mathbf{F}^{m}\quad{\mathrm{and}}\quad w=(w_{1},...,w_{n})\in\mathbf{F}^{n}.
$$  

Then  

$$
\begin{array}{c}{{v\otimes w=\displaystyle\left(\sum_{j\mathop{=}1}^{m}v_{j}e_{j}\right)\otimes\displaystyle\left(\sum_{k\mathop{=}1}^{n}w_{k}f_{k}\right)}}\\ {{=\displaystyle\sum_{k\mathop{=}1}^{n}\sum_{j\mathop{=}1}^{m}(v_{j}w_{k})(e_{j}\otimes f_{k}).}}\end{array}
$$  

Thus with respect to the basis $\{e_{j}\,\otimes\,f_{k}\}_{j=1,\dots,m;k=1,\dots,n}$ of $\mathbf{F}^{m}\otimes\mathbf{F}^{n}$ provided by 9.74(b), the coefficients of $v\otimes w$ are the numbers $\{v_{j}w_{k}\}_{j=1,\ldots,m;k=1,\ldots,n}.$ . If instead of writing these numbers in a list, we write them in an $m$ -by- $_n$ matrix with $v_{j}w_{k}$ in row $j_{\cdot}$ , column $k$ , then we can identify $v\otimes w$ with the $m$ -by- $\cdot n$ matrix  

$$
{\left(\begin{array}{l l l}{v_{1}w_{1}}&{\cdots}&{v_{1}w_{n}}\\ &{\ddots}&\\ &&{\ddots}&\\ {v_{m}w_{1}}&{\cdots}&{v_{m}w_{n}}\end{array}\right)}.
$$  

See Exercises 5 and 6 for practice in using the identification from the example above.  

We now define bilinear maps, which differ from bilinear functionals in that the target space can be an arbitrary vector space rather than just the scalar field.  

9.77 definition: bilinear map  

A bilinear map from $V\times W$ to a vector space $U$ is a function $\Gamma\colon V\times W\rightarrow U$ such that $v\,\mapsto\,\Gamma(v,w)$ is a linear map from $V$ to $U$ for each $w\,\in\,W$ and $w\mapsto\Gamma(v,w)$ is a linear map from $W$ to $U$ for each $v\in V.$ .  

## 9.78 example: bilinear maps  

• Every bilinear functional on $V\times W$ is a bilinear map from $V\times W$ to $\mathbf{F}$ .  

• The function $\Gamma\colon V\times W\to V\otimes W$ defined by $\Gamma(v,w)=v\otimes w$ is a bilinear map from $V\times W$ to $V\otimes W\,({\bf b y}\,9.73)$ .   
• The function $\Gamma\colon{\mathcal{L}}(V)\times{\mathcal{L}}(V)\to{\mathcal{L}}(V)$ defined by $\Gamma(S,T)=S T$ is a bilinear map from $\mathcal{L}(V)\times\mathcal{L}(V)$ to ${\mathcal{L}}(V)$ .   
• The function $\Gamma\colon V\times\mathcal{L}(V,W)\to W$ defined by $\Gamma(v,T)=T v$ is a bilinear map from $V\times{\mathcal{L}}(V,W)$ to $W.$  

Tensor products allow us to convert bilinear maps on $V\times W$ into linear maps on $V\otimes W$ (and vice versa), as shown by the next result. In the mathematical literature, (a) of the result below is called the “universal property” of tensor products.  

## 9.79 converting bilinear maps to linear maps  

Suppose $U$ is a vector space.  

(a) Suppose $\Gamma\colon V\times W\rightarrow U$ is a bilinear map. Then there exists a unique linear map $\hat{\Gamma}\colon V\otimes W\rightarrow U$ such that  

$$
\hat{\Gamma}(v\otimes w)=\Gamma(v,w)
$$  

for all $(v,w)\in V\times W.$  

(b) Conversely, suppose $T\colon V\otimes W\to U$ is a linear map. There there exists a unique bilinear map $T^{\#}\colon V\times W\to U$ such that  

$$
T^{\#}(v,w)=T(v\otimes w)
$$  

for all $(v,w)\in V\times W.$  

Proof Let $e_{1},...,e_{m}$ be a basis of $V$ and let $f_{1},...,f_{n}$ be a basis of $W.$ By the linear map lemma (3.4) and 9.74(b), there exists a unique linear map $\hat{\Gamma}\colon V\otimes W\rightarrow U$ such that  

$$
\hat{\Gamma}(e_{j}\otimes f_{k})=\Gamma(e_{j},f_{k})
$$  

for all $j\in\{1,...,m\}$ and $k\in\{1,...,n\}$ .  

Now suppose $(v,w)\in V\times W.$ . There exist $a_{1},...,a_{m},b_{1},...,b_{n}\in\mathbf{F}$ such that $v=a_{1}e_{1}+\cdots+a_{m}e_{m}$ and $w=b_{1}f_{1}+\cdots+b_{n}f_{n}$ . Thus  

$$
\begin{array}{l}{\displaystyle\hat{\Gamma}(v\otimes w)=\hat{\Gamma}\biggl(\sum_{k=1}^{n}\sum_{j=1}^{m}(a_{j}b_{k})(e_{j}\otimes f_{k})\biggr)}\\ {\displaystyle}\\ {\displaystyle}\\ {\displaystyle}\\ {\displaystyle\qquad=\sum_{k=1}^{n}\sum_{j=1}^{m}a_{j}b_{k}\hat{\Gamma}(e_{j}\otimes f_{k})}\\ {\displaystyle}\\ {\displaystyle}\\ {\displaystyle}\\ {\displaystyle}\end{array}\biggr=\sum_{k=1}^{n}\sum_{j=1}^{m}a_{j}b_{k}\Gamma(e_{j},f_{k})}\\ {\displaystyle}\\ {\displaystyle}\\ {\displaystyle}\end{array}
$$  

as desired, where the second line holds because $\hat{\Gamma}$ is linear, the third line holds by the definition of $\hat{\Gamma}$ , and the fourth line holds because $\Gamma$ is bilinear.  

The uniqueness of the linear map $\hat{\Gamma}$ satisfying $\hat{\Gamma}(v\otimes w)\,=\,\Gamma(v,w)$ follows from 9.74(b), completing the proof of (a).  

To prove (b), define a function $T^{\#}\colon V\times W\to U$ by $T^{\#}(v,w)=T(v\otimes w)$ for all $(v,w)\in V\times W.$ . The bilinearity of the tensor product (see 9.73) and the linearity of $T$ imply that $T^{\#}$ is bilinear.  

Clearly the choice of $T^{\#}$ that satisfies the conditions is unique.  

To prove 9.79(a), we could not just define $\hat{\Gamma}(v\otimes w)=\Gamma(v,w)$ for all $v\in V$ and $w\in W$ (and then extendΓ̂ linearly to all of $V\otimes W$ ) because elements of $V\otimes W$ do not have unique representations as finite sums of elements of the form $v\otimes w$ . Our proof used a basis of $V$ and a basis of $W$ to get around this problem.  

Although our construction of $\hat{\Gamma}$ in the proof of 9.79(a) depended on a basis of $V$ and a basis of $W,$ the equation $\hat{\Gamma}(v\otimes w\big)=\Gamma(v,w)$ that holds for all $v\in V$ and $w\in W$ shows that Γ̂ does not depend on the choice of bases for $V$ and $W$ .  

## Tensor Product of Inner Product Spaces  

The result below features three inner products—one on $V\otimes W,$ one on $V_{v}$ , and one on $W,$ , although we use the same symbol $\langle\cdot,\cdot\rangle$ for all three inner products.  

9.80 inner product on tensor product of two inner product spaces  

Suppose $V$ and $W$ are inner product spaces. Then there is a unique inner product on $V\otimes W$ such that  

$$
\langle v\otimes w,u\otimes x\rangle=\langle v,u\rangle\langle w,x\rangle
$$  

for all $v,u\in V$ and $w,x\in W.$ .  

Proof Suppose $e_{1},...,e_{m}$ is an orthonormal basis of $V$ and $f_{1},...,f_{n}$ is an orthonormal basis of 𝑊. Define an inner product on $V\otimes W$ by  

$$
\left\langle\sum_{k=1}^{n}\sum_{j\,=\,1}^{m}b_{j,k}\,e_{j}\otimes f_{k},\sum_{\substack{k=1\,j\,=\,1}}^{n}\sum_{\substack{j\,=\,1}}^{m}c_{j,k}\,e_{j}\otimes f_{k}\right\rangle=\sum_{k=1}^{n}\sum_{j\,=\,1}^{m}b_{j,k}\overline{{c_{j,k}}}.
$$  

The straightforward verification that 9.81 defines an inner product on $V\times W$ is left to the reader [use 9.74(b)].  

Suppose that $v,u~\in~V$ and $w,x\ \in\ W.$ . Let $v_{1},...,v_{m}\;\in\;\mathbf{F}$ be such that $v=v_{1}e_{1}+\cdots+v_{m}e_{m}$ , with similar expressions for $u,w$ , and $x$ . Then  

$$
\begin{array}{r l}&{\langle v\otimes w,u\otimes x\rangle=\Bigg\langle\displaystyle\sum_{j=1}^{m}v_{j}e_{j}\otimes\displaystyle\sum_{k=1}^{n}w_{k}f_{k}\displaystyle\sum_{j=1}^{m}u_{j}e_{j}\otimes\displaystyle\sum_{k=1}^{n}x_{k}f_{k}\Bigg\rangle}\\ &{\qquad\qquad\qquad=\left\langle\displaystyle\sum_{k=1}^{m}\displaystyle\sum_{j=1}^{m}v_{j}w_{k}e_{j}\otimes f_{k},\displaystyle\sum_{k=1}^{n}\sum_{j=1}^{m}u_{j}x_{k}e_{j}\otimes f_{k}\right\rangle}\\ &{\qquad\qquad=\displaystyle\sum_{k=1}^{n}\displaystyle\sum_{j=1}^{m}v_{j}\overline{{u}}_{j}w_{k}\overline{{x}}_{k}}\\ &{\qquad\qquad=\left(\displaystyle\sum_{j=1}^{m}v_{j}\overline{{u}}_{j}\right)\left(\displaystyle\sum_{k=1}^{n}w_{k}\overline{{x}}_{k}\right)}\\ &{\qquad\qquad=\langle v,u\rangle\langle w,x\rangle.}\end{array}
$$  

There is only one inner product on $V\otimes W$ such that $\langle v\otimes w,u\otimes x\rangle=\langle v,u\rangle\langle w,x\rangle$ for all $v,u\in V$ and $w,x\in W$ because every element of $V\otimes W$ can be written as a linear combination of elements of the form $v\otimes w$ [by 9.74(b)].  

The definition below of a natural inner product on $V\otimes W$ is now justified by 9.80. We could not have simply defined $\langle v\otimes w,u\otimes x\rangle$ to be $\langle v,u\rangle\langle w,x\rangle$ (and then used additivity in each slot separately to extend the definition to $V\otimes W_{\times}$ ) without some proof because elements of $V\otimes W$ do not have unique representations as finite sums of elements of the form $v\otimes w$ .  

9.82 definition: inner product on tensor product of two inner product spaces  

Suppose $V$ and $W$ are inner product spaces. The inner product on $V\otimes W$ is the unique function $\langle\cdot,\cdot\rangle$ from $(V\otimes W)\times(V\otimes W)$ to $\mathbf{F}$ such that  

$$
\langle v\otimes w,u\otimes x\rangle=\langle v,u\rangle\langle w,x\rangle
$$  

for all $v,u\in V$ and $w,x\in W.$ .  

Take $u=v$ and $x=w$ in the equation above and then take square roots to show that  

$$
\|v\otimes w\|=\|v\|\,\|w\|
$$  

for all $v\in V$ and all $w\in W.$ .  

The construction of the inner product in the proof of 9.80 depended on an orthonormal basis $e_{1},...,e_{m}$ of $V$ and an orthonormal basis $f_{1},...,f_{n}$ of $W.$ Formula 9.81 implies that $\{e_{j}\otimes f_{k}\}_{j=1,\dots,m;k=1,\dots,n}$ is a doubly indexed orthonormal list in $V\otimes W$ and hence is an orthonormal basis of $V\otimes W\left[{\bf b y}\,9.74({\bf b})\right]$ . The importance of the next result arises because the orthonormal bases used there can be different from the orthonormal bases used to define the inner product in 9.80. Although the notation for the bases is the same in the proof of 9.80 and in the result below, think of them as two different sets of orthonormal bases.  

9.83 orthonormal basis of $V\otimes W$  

Suppose $V$ and $W$ are inner product spaces, and $e_{1},...,e_{m}$ is an orthonormal basis of $V$ and $f_{1},...,f_{n}$ is an orthonormal basis of $W.$ Then  

$$
\{e_{j}\otimes f_{k}\}_{j=1,\dots,m;k=1,\dots,n}
$$  

is an orthonormal basis of $V\otimes W$ .  

Proof We know that $\{e_{j}\otimes f_{k}\}_{j=1,\dots,m;k=1,\dots,n}$ is a basis of $V\otimes W\,[{\bf b y}\,9.74({\bf b})]$ . Thus we only need to verify orthonormality. To do this, suppose $j,M\in\{1,...,m\}$ and $k,N\in\{1,...,n\}$ . Then  

$$
\langle e_{j}\otimes f_{k},e_{N}\otimes f_{M}\rangle=\langle e_{j},e_{N}\rangle\langle f_{k},f_{M}\rangle={\left\{\begin{array}{l l}{1}&{{\mathrm{if}}\ j=N{\mathrm{~and}}\ k=M,}\\ {0}&{{\mathrm{otherwise}}.}\end{array}\right.}
$$  

Hence the doubly indexed list $\{e_{j}\otimes f_{k}\}_{j=1,\dots,m;k=1,\dots,n}$ is indeed an orthonormal basis of $V\otimes W.$ .  

See Exercise 11 for an example of how the inner product structure on $V\otimes W$ interacts with operators on $V$ and $W$ .  

We have been discussing properties of the tensor product of two finite-dimensional vector spaces. Now we turn our attention to the tensor product of multiple finitedimensional vector spaces. This generalization requires no new ideas, only some slightly more complicated notation. Readers with a good understanding of the tensor product of two vector spaces should be able to make the extension to the tensor product of more than two vector spaces.  

Thus in this subsection, no proofs will be provided. The definitions and the statements of results that will be provided should be enough information to enable readers to fill in the details, using what has already been learned about the tensor product of two vector spaces.  

We begin with the following notational assumption.  

## 9.84 notation: $V_{1},...,V_{m}$  

For the rest of this subsection, 𝑚denotes an integer greater than 1 and $V_{1},...,V_{m}$ denote finite-dimensional vector spaces.  

The notion of an $m$ -linear functional, which we are about to define, generalizes the notion of a bilinear functional (see 9.68). Recall that the use of the word “functional” indicates that we are mapping into the scalar field 𝐅. Recall also that the terminology $^{\bullet}m$ -linear form” is used in the special case $V_{1}=\cdots=V_{m}$ (see 9.25). The notation $\mathcal{B}(V_{1},...,V_{m})$ generalizes our previous notation $\mathcal{B}(V,W)$ .  

9.85 definition: 𝑚-linear functional, the vector space ℬ(𝑉1, …, 𝑉𝑚)  

• An 𝑚-linear functional on $V_{1}\times\cdots\times V_{m}$ is a function $\beta\colon V_{1}\times\cdots\times V_{m}\rightarrow\mathbf{F}$ that is a linear functional in each slot when the other slots are held fixed. The vector space of $m$ -linear functionals on $V_{1}\times\cdots\times V_{m}$ is denoted by $\mathcal{B}(V_{1},...,V_{m})$ .  

9.86 example: 𝑚-linear functional  

Suppose $\varphi_{k}\in(V_{k})^{\prime}$ for each $k\in\{1,...,m\}$ . Define $\beta\colon V_{1}\times\cdots\times V_{m}\rightarrow\mathbf{F}$ by  

$$
\beta(v_{1},...,v_{m})=\varphi_{1}(v_{1})\times\cdots\times\varphi_{m}(v_{m}).
$$  

Then $\beta$ is an $m$ -linear functional on $V_{1}\times\cdots\times V_{m}$  

The next result can be proved by imitating the proof of 9.70.  

9.87 dimension of the vector space of 𝑚-linear functionals  

$$
\dim{\mathcal{B}}(V_{1},...,V_{m})=(\dim V_{1})\times\cdots\times(\dim V_{m}).
$$  

Now we can define the tensor product of multiple vector spaces and the tensor product of elements of those vector spaces. The following definition is completely analogous to our previous definition (9.71) in the case $m=2$ .  

9.88 definition: tensor product, $V_{1}\otimes\cdots\otimes V_{m},\,v_{1}\otimes\cdots\otimes v_{m}$ The tensor product $V_{1}\otimes\cdots\otimes V_{m}$ is defined to be $\mathcal{B}(V_{1}^{\prime},...,V_{m}^{\;\;\prime})$ . For $v_{1}\in V_{1},...,v_{m}\in V_{m}$ , the tensor product $v_{1}\otimes\cdots\otimes v_{m}$ is the element of $V_{1}\otimes\cdots\otimes V_{m}$ defined by for al $\begin{array}{c}{{(v_{1}\otimes\cdots\otimes v_{m})(\varphi_{1},...,\varphi_{m})=\varphi_{1}(v_{1})...\varphi_{m}(v_{m})}}\\ {{{}}}\\ {{|\,(\varphi_{1}...,\varphi_{m})\in V_{1}^{\prime}\times\cdots\times V_{m}^{\prime}.}}\end{array}$  

The next result can be proved by following the pattern of the proof of the analogous result when $m=2$ (see 9.72).  

9.89 dimension of the tensor product  

$$
\dim(V_{1}\otimes\cdots\otimes V_{m})=(\dim V_{1}){\cdots}(\dim V_{m}).
$$  

Our next result generalizes 9.74.  

9.90 basis of $V_{1}\otimes\cdots\otimes V_{m}$  

Suppose dim $V_{k}=n_{k}$ and $e_{1}^{k},...,e_{n_{k}}^{k}$ is a basis of $V_{k}$ for $k=1,...,m$ . Then  

$$
\{e_{j_{1}}^{1}\otimes\cdots\otimes e_{j_{m}}^{m}\}_{j_{1}=1,\dots,n_{1};\cdots;j_{m}=1,\dots,n_{m}}
$$  

is a basis of $V_{1}\otimes\cdots\otimes V_{m}$ .  

Suppose $m=2$ and $e_{1}^{1},...,e_{n_{1}}^{1}$ is a basis of $V_{1}$ and $e_{1}^{2},...,e_{n_{2}}^{2}$ is a basis of $V_{2}$ . Then with respect to the basis $\{e_{j_{1}}^{1}\otimes e_{j_{2}}^{2}\}_{j_{1}=1,\dots,n_{1};j_{2}=1,\dots,n_{2}}$ in the result above, the coefficients of an element of $V_{1}\otimes V_{2}$ can be represented by an $n_{1}$ -by- $\cdot n_{2}$ matrix that contains the coefficient of $e_{j_{1}}^{1}\otimes e_{j_{2}}^{2}$ in row $j_{1}$ , column $j_{2}$ . Thus we need a matrix, which is an array specified by two indices, to represent an element of $V_{1}\otimes V_{2}$ .  

If $m>2$ , then the result above shows that we need an array specified by $m$ indices to represent an arbitrary element of $V_{1}\otimes\cdots\otimes V_{m}$ . Thus tensor products may appear when we deal with objects specified by arrays with multiple indices.  

The next definition generalizes the notion of a bilinear map (see 9.77). As with bilinear maps, the target space can be an arbitrary vector space.  

## 9.91 definition: 𝑚-linear map  

An 𝑚-linear map from $V_{1}\,\times\,\cdots\,\times\,V_{m}$ to a vector space $U$ is a function $\Gamma\colon V_{1}\times\cdots\times V_{m}\rightarrow U$ that is a linear map in each slot when the other slots are held fixed.  

9.92 converting 𝑚-linear maps to linear maps  

Suppose $U$ is a vector space.  

(a) Suppose that $\Gamma\colon V_{1}\times\cdots\times V_{m}\rightarrow U$ is an $m$ -linear map. Then there exists a unique linear map $\ddot{\Gamma}\colon V_{1}\otimes\cdots\otimes V_{m}\rightarrow U$ such that  

$$
\hat{\Gamma}(v_{1}\otimes\cdots\otimes v_{m})=\Gamma(v_{1},...,v_{m})
$$  

for all $(v_{1},...,v_{m})\in V_{1}\times\cdots\times V_{m}.$  

(b) Conversely, suppose $T\colon V_{1}\otimes\cdots\otimes V_{m}\rightarrow U$ is a linear map. There there exists a unique $m$ -linear map $T^{\#}\colon V_{1}\times\cdots\times V_{m}\to U$ such that  

$$
T^{\#}(v_{1},...,v_{m})=T(v_{1}\otimes\cdots\otimes v_{m})
$$  

for all $(v_{1},...,v_{m})\in V_{1}\times\cdots\times V_{m}.$ .  

See Exercises 12 and 13 for tensor products of multiple inner product spaces.  

## Exercises 9D  

1 Suppose $v\in V$ and $w\in W.$ . Prove that $v\otimes w=0$ if and only if $v=0$ or $w=0$ .  

2 Give an example of six distinct vectors $v_{1},v_{2},v_{3},w_{1},w_{2},w_{3}$ in $\mathbf{R}^{3}$ such that  

$$
v_{1}\otimes w_{1}+v_{2}\otimes w_{2}+v_{3}\otimes w_{3}=0
$$  

but none of $v_{1}\otimes w_{1},v_{2}\otimes w_{2},v_{3}\otimes w_{3}$ is a scalar multiple of another element of this list.  

3 Suppose that $v_{1},...,v_{m}$ is a linearly independent list in $V.$ Suppose also that $w_{1},...,w_{m}$ is a list in $W$ such that  

$$
v_{1}\otimes w_{1}+\cdots+v_{m}\otimes w_{m}=0.
$$  

Prove that $w_{1}=\cdots=w_{m}=0$ .  

4 Suppose dim $V>1$ and dim $W>1$ . Prove that  

$$
\left\{v\otimes w:(v,w)\in V\times W\right\}
$$  

is not a subspace of $V\otimes W_{\ast}$ .  

This exercise implies that if dim $V>1$ and dim $W>1$ , then  

$$
\{v\otimes w:(v,w)\in V\times W\}\neq V\otimes W.
$$  

5 Suppose $m$ and $n$ are positive integers. For $v\,\in\,\mathbf{F}^{m}$ and $w\in\mathbf{F}^{n}$ , identify $v\otimes w$ with an $m$ -by- $\cdot n$ matrix as in Example 9.76. With that identification, show that the set  

$$
\left\{v\otimes w:v\in\mathbf{F}^{m}\;{\mathrm{and}}\;w\in\mathbf{F}^{n}\right\}
$$  

is the set of $m$ -by- $\cdot n$ matrices (with entries in $\mathbf{F}$ ) that have rank at most one.  

6 Suppose $m$ and $n$ are positive integers. Give a description, analogous to Exercise 5, of the set of $m$ -by- $_n$ matrices (with entries in $\mathbf{F}$ ) that have rank at most two.  

7 Suppose dim $V>2$ and dim $W>2$ . Prove that  

$$
\{v_{1}\otimes w_{1}+v_{2}\otimes w_{2}:v_{1},v_{2}\in V\operatorname{and}w_{1},w_{2}\in W\}\neq V\otimes W.
$$  

8 Suppose $v_{1},...,v_{m}\in V$ and $w_{1},...,w_{m}\in W$ are such that  

$$
v_{1}\otimes w_{1}+\cdots+v_{m}\otimes w_{m}=0.
$$  

Suppose that $U$ is a vector space and $\Gamma\colon V\times W\rightarrow U$ is a bilinear map. Show that  

$$
\Gamma(v_{1},w_{1})+\cdots+\Gamma(v_{m},w_{m})=0.
$$  

9 Suppose $S\in{\mathcal{L}}(V)$ and $T\in{\mathcal{L}}(W)$ . Prove that there exists a unique operator on $V\otimes W$ that takes $v\otimes w$ to $S v\otimes T w$ for all $v\in V$ and $w\in W$ .  

In an abuse of notation, the operator on $V\otimes$ 𝑊given by this exercise is often called $S\otimes T.$ .  

10 Suppose $S\in{\mathcal{L}}(V)$ and $T\in{\mathcal{L}}(W)$ . Prove that $S\otimes T$ is an invertible operator on $V\otimes W$ if and only if both $S$ and $T$ are invertible operators. Also, prove that if both $S$ and $T$ are invertible operators, then $(S\otimes T)^{-1}=S^{-1}\otimes T^{-1}$ , where we are using the notation from the comment after Exercise 9.  

11 Suppose $V$ and $W$ are inner product spaces. Prove that if $S\in{\mathcal{L}}(V)$ and $T\in{\mathcal{L}}(W)$ , then $(S\otimes T)^{*}=S^{*}\otimes T^{*}$ , where we are using the notation from the comment after Exercise 9.  

12 Suppose that $V_{1},...,V_{m}$ are finite-dimensional inner product spaces. Prove that there is a unique inner product on $V_{1}\otimes\cdots\otimes V_{m}$ such that  

$$
\langle v_{1}\otimes\cdots\otimes v_{m},u_{1}\otimes\cdots\otimes u_{m}\rangle=\langle v_{1},u_{1}\rangle\cdots\langle v_{m},u_{m}\rangle
$$  

for all $(v_{1},...,v_{m})$ and $(u_{1},...,u_{m})$ in $V_{1}\times\cdots\times V_{m}$ .  

Note that the equation above implies that  

$$
\|v_{1}\otimes\cdots\otimes v_{m}\|=\|v_{1}\|\times\cdots\times\|v_{m}\|
$$  

for all $(v_{1},...,v_{m})\in V_{1}\times\cdots\times V_{m}.$  

13 Suppose that $V_{1},...,V_{m}$ are finite-dimensional inner product spaces and $V_{1}\otimes\cdots\otimes V_{m}$ is made into an inner product space using the inner product from Exercise 12. Suppose 𝑒1𝑘, …, 𝑒𝑛𝑘 is an orthonormal basis of $V_{k}$ for each $k=1,...,m$ . Show that the list  

$$
\{e_{j_{1}}^{1}\otimes\cdots\otimes e_{j_{m}}^{m}\}_{j_{1}=1,\dots,n_{1};\cdots;j_{m}=1,\dots,n_{m}}
$$  

is an orthonormal basis of $V_{1}\otimes\cdots\otimes V_{m}$ .  
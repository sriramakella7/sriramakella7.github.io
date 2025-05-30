---
layout: post
title: Chern Simons Theory and IRF Models
comments: true
categories: hep-th
---
## 1. Introduction 

In today's post, I want to revisit an old paper from 1989 by Edward Witten titled [*Gauge theories and integrable lattice models*](https://doi.org/10.1016/0550-3213(89)90232-0) whose title and abstract I've taken the liberty to display below.
![[assets/gauge theories and integrable lattice models.png]]
This paper followed Witten's famous Jones Polynomial paper[^1] which showed that $(2+1)$-dimensional Chern-Simons theory was exactly solvable. The Jones polynomial paper (at the time of writing this post) is Witten's fourth most cited paper with around 3,900 citations (on [INSPIRE-HEP](https://inspirehep.net/literature/264818)). The integrable lattice models paper, however, has around 162 citations at the time of writing this post. Although it hasn't attracted the attention of the community, I think it's a beautiful and very interesting paper. 

What Witten shows (as you can read from the abstract above if you squint a little) is that expectation values of Wilson lines in Chern-Simons theory can equivalently be interpreted as partition functions of IRF (interactions round a face) models. 

### 1.1 IRF Models
IRF models are simple lattice models that are variants of vertex-models[^2] which were historically first developed to understand thermodynamic properties of ice[^3]! To define their partition function, we first consider a square lattice sketched below. 
<p align="center"> <img src="assets/square-lattice.png"></p>

The edges of the lattice carry indices that take values from $i = 1, \dots, N$. Each face of the lattice carries a weight $W_{ijkl}$: 

<p align="center"> <img width ="350px" src="assets/IRF.png"></p>

where we go around the face clockwise to define the ordering of the labels $i$, $j$, $k$, and $l$. The partition function of the model is defined as 
$$
\begin{equation}\tag{1.1}
\mathcal{Z} = \sum_{\text{edges}} \prod_{\text{faces}} W_{ijkl}.
\end{equation}
$$
We first assign labels $i$, $j$, $k$, etc. to all the edges of the lattice. Then we take a product of the weights $W_{ijkl}$ for all the faces, and then sum over all the edge labels to get the partition function.

IRF models are simple lattice models. For specific choices of the weights $W_{ijkl}$, the above partition function can be exactly computed. 

To understand Witten's paper, we will need to review some basic facts about Chern-Simons theory.
### 1.2 Chern-Simons Theory 
Chern-Simons theory is a $(2+1)$-dimensional *topological* quantum field theory defined as follows. First, we pick a compact $3$-manifold, say $M$. Typical choices of $M$ include $S^3$ and $S^2 \times S^1$. Next, we pick a compact semisimple Lie group $G$ which we assume is connected and simply connected for convenience. Typical choices include $U(1)$, $SU(2)$, $SU(3)$, etc. We can then define $E$ to be the $G$-bundle of $M$, and define a Lie-algebra valued connection $A$ which defines parallel transport in $E$. Explicitly, $A$ is a Lie-algebra valued one-form which looks like 
$$
\begin{equation}\tag{1.2}
A(x) = \sum_{a=1}^{\dim(G)} \sum_{i=1}^{3} A_i^{a}(x) t^a dx^i  
\end{equation}
$$
where $\{t^a\}$ is the set of generators of the Lie algebra $\mathfrak{g}$ of $G$. 

Armed with this connection, the action of Chern-Simons theory is
$$
\begin{equation}\tag{1.3}
S[A] = \frac{k}{4\pi} \int_{M} \text{Tr} \left(A \wedge dA + \frac{2}{3} A \wedge A \wedge A\right),
\end{equation}
$$
where the $\text{Tr}$ is defined using the Killing form of the group $G$. The co-efficient $k$ is an integer called the *level* of the theory. The Chern-Simons action has the following properties: 
- **Gauge invariant:** The action is invariant under gauge transformations of the form $A \to g^{-1} A g + g^{-1} d g$. 
- **Diffeomorphism invariant:** Being the integral of a 3-form on $M$, the action is independent of the metric. 

The path integral 
$$
\begin{equation}\tag{1.4}
Z(M) = \int [\mathcal{D}A] e^{i S[A]}
\end{equation}
$$
over gauge-inequivalent connections is a natural topological invariant of the 3-manifold $M$. More generally, we can insert operators into the path integral to compute expectation values. But due to the topological and gauge invariance of the theory, the class of allowed operator insertions is limited. 
#### Wilson Loops
One class of operator insertions, called *Wilson loops* are defined as follows. First, we embed an oriented circle $C: S^1 \to M$ in $M$. We then consider an irreducible representation $R$ of the gauge group $G$ and compute the *holonomy* of the connection in the representation $R$ around the circle $C$. Mathematically, the Wilson loop operators are
$$
\begin{equation}\tag{1.5}
W_{R}(C) = \text{Tr}_R\left( P \exp\left[\oint_C A\right]  \right).
\end{equation}
$$
By construction, these are gauge-invariant (because of the trace), and they are also topological because the holonomy is invariant under diffeomorphisms. 

If the *knot* $C$ is contractible in $M$, then the above Wilson loop operator is also trivial because we can shrink the knot in $M$ with a diffeomorphism. Wilson loops can only be defined for non-contractible cycles in the manifold $M$. An example is a solid torus with the Wilson loop threaded as shown below: 
<p align="center"> <img width = 250px src="assets/toru.png"></p>
The blue loop is contractible in the solid torus but the red loop is not. We get a nontrivial Wilson loop if we thread a representation $R$ through the red line, but the WIlson loop is trivial if we thread a representation through the blue line. 

With the Wilson loop insertion, we can compute expectation values of the form: 
$$
\begin{equation}\tag{1.6}
\langle W_R(C) \rangle = \frac{1}{Z(M)} \int [\mathcal D A] e^{i S[A]}\, W_R(C).
\end{equation}
$$
What Witten showed in the Jones Polynomial paper is how to compute these expectation values by using some cut and paste rules (called surgery) of the manifold $M$. We will not get into that in this post. What I want to discuss is an alternative way of calculating these Wilson loop expectation values. 

## 2. The IRF Model 
Suppose we want to calculate $\langle W_R(C)\rangle$, here's how we proceed. First, we project the knot $C$ to a plane so that it looks like 
<p align="center"> <img width = 300px src="assets/knot-projection.png"></p>

There are a bunch of crossings in the knot labeled in the above diagrams as $C_1$, $C_2$, and $C_3$. As we follow the arrows starting from $C_1$, we see that the knot splits into pieces labeled as $M_1, \dots, M_6$. The knot projection also separates the plane into various regions $R_0, \dots, R_4$ as shown below:
<p align="center"> <img width = 300px src="assets/knot-projection-2.png"></p>
To each region, we assign a "spin" which is an irreducible representation of the gauge group $G$ with the convention that $R_0$ is assigned the identity representation. This assignment is subject to the following constraint. Each $M_i$ separates two regions $R_k$ and $R_l$, and itself carries a representation $R$. These three representations must be *compatible* in the sense that $R \oplus R_k \oplus R_l$ must contain a $G$-invariant tensor $\epsilon$. 

Each crossing $C_i$ intersects four regions $R_i$, $R_j$, $R_k$, $R_l$, and contains two strands which carry some representations $R_n$ and $R_m$ (in the above example both $R_n$ and $R_m$ are equal to $R$). 
<p align="center"> <img width = 350px src="assets/path85.png"></p>
We assign a weight $W_{ijkl}^{nm}$ to each crossing. 

In addition to crossings, there are also the following *critical points* where the topology of the knot changes. 

Witten shows that 
$$
\begin{equation}\tag{2.1}
\langle W_R(C)\rangle = \sum_{\text{coloring}} \prod_{\text{crossings}} W_{ijkl}^{nm},
\end{equation}
$$
where the sum is over all allowed representations in the regions $R_i$ subject to the constraint discussed above. Given a *coloring* of the plane with these representations, we take a product of the weights above for each crossing $C_i$ and sum over all allowed colorings. 

This is the basic idea. Let us now get into more detail about what the specific choices of the weights are. 










[^1]: Witten, E., 1989. [Quantum field theory and the Jones polynomial.](https://doi.org/10.1007/BF01217730) _Communications in Mathematical Physics_, _121_(3), pp.351-399.
[^2]: Baxter, R.J., 2016. _Exactly solved models in statistical mechanics_. Elsevier.
[^3]:Lieb, E.H., 1967. [Residual entropy of square ice](https://doi.org/10.1103/PhysRev.162.162). _Physical Review_, _162_(1), p.162.
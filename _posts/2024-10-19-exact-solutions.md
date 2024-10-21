---
layout: post
title: "Resource theory of quantum entanglement" 
categories: quant-ph
comments: true
---

# Exact Solutions to Einstein's Field Equations

In this note, I want to revisit exact solutions to Einstein's field equations
$$
R_{ab} - \frac{1}{2} R g_{ab} + \Lambda g_{ab} = 8 \pi T_{ab}
$$
and discuss some well-known solutions in (3+1)-dimensions. There are many other exact solutions known in lower dimensions, but I won't be much concerned about them here. The treatment I'll follow will loosely be based on Chapter 5 of Hawking and Ellis [^1].

I want to make a few comments before proceeding. First, if we have a metric $g_{ab}$, then using Einstein's equations, it defines for us an energy-momentum tensor. For a general metric, this energy-momentum tensor cannot be thought of as coming from some underlying field theory. And it won't satisfy the sort of nice properties we'd want an energy-momentum to satisfy. 

## Constant Curvature Solutions
We'll first look for the simplest solutions; those that have a constant scalar curvature 
$$
R = R_{ab}g^{ab} = \text{const.},
$$
and no matter fields, i.e., 
$$
T_{ab} = 0. 
$$
Using the contracted Bianchi identities and some algebra, we can show that for metrics with constant curvature, the Riemann tensor is given by 
$$
R_{abcd} = \frac{R}{12}\left(g_{ac}g_{bd} - g_{ad}g_{bc}\right). 
$$
When we substitute this back in Einstein's equations with $T_{ab} = 0$, we get 
$$
\Lambda = \frac{R}{4}. 
$$



### Minkwoski Spacetime
The most familiar solution is Minkowski space where $\Lambda = R = 0$. In this case, the manifold is $\mathbb{R}^4$ metric takes the simple form
$$
ds^2 = -dt^2 + dx^2 + dy^2 + dz^2 
$$
where the range of each variable is from $-\infty$ to $\infty$. While locally this solution is trivial, it has some non-trivial global structure which we might be interested in understanding. These are rather important for understanding, say, holography in flat space [^2]. 

To understand the global structure of Minkowski space, we make a few co-ordinate changes. These ideas go back to Penrose [^3]. We first begin by using spherical polar co-ordinates defined via 
$$
z = r \cos\theta, \quad y = r \sin\theta \cos\phi, \quad x = r \sin\theta \sin\phi,
$$
in terms of which the line element becomes 
$$
ds^2 = -dt^2 + dr^2 + r^2\left(d\theta^2 + \sin^2\theta d\phi^2\right). 
$$
In spherical polar co-ordinates, the metric seems to be singular at $r = 0$ and $\sin\theta = 0$, but these are artifacts of the co-ordinate system we're using. We need more than one patch to cover all of Minkowski space. The range of the variables in spherical polar co-ordinates is 
$$
-\infty < t < \infty, \quad 0 \leq r < \infty, \quad 0 \leq \theta \leq \pi, \quad 0 \leq \phi \leq 2 \pi.
$$

The next co-ordinate change we make by introducing the retarded and advanced co-ordinates
$$
u = t + r, \quad v = t-r,
$$ 
in terms of which the metric becomes 
$$
ds^2 = - du\, dv + \frac{1}{4}(u-v)^2 \left(d\theta^2 + \sin^2 \theta d\phi^2\right). 
$$
The range of $u$ and $v$ is from $-\infty$ to $\infty$. The main idea of Penrose was to _compactify_ this infinite range by defining 
$$
u = \tan U, \quad v = \tan V,
$$
so that $U$ and $V$ run from $-\pi/2$ to $\pi/2$. In terms of these new variables, the metric becomes 
$$
ds^2 = \frac{1}{4}\sec^2 U \sec^2 V \left(-4\,dU dV + \sin^2(U-V) \left(d\theta^2 + \sin^2\theta d\phi^2\right)\right).
$$
The metric inside the parentheses looks very similar to the flat space metric in $(u, v, \theta, \phi)$ co-ordinates. To make the similarity more apparent, let's introduce the variables 
$$
T = U+V, \quad R = U-V,
$$
in terms of which the metric inside the parentheses becomes 
$$
d\tilde{s}^2 = -dT^2 + dR^2 + \sin^2 R \left(d\theta^2 + \sin^2\theta \,d\phi^2\right). 
$$
The range of these co-ordinates is 
$$
-\pi \leq T \leq \pi, \quad -\pi \leq R \leq \pi, \quad 0 \leq \theta \leq \pi, \quad 0 \leq \phi \leq 2\pi. 
$$
Note however that this is not the metric of Minkowksi spacetime, but rather of a spacetime that is _conformal_ to Minkowski. However, since this spacetime is compact, we can talk about its boundary. What we've essentially done is a conformal transformation to bring infinity to a finite distance to study the asymptotic structure of Minkowksi spacetime. Such a transformation distorts distances but preserves angles. Therefore it won't affect the causal structure of Minkowski spacetime. 

#### Causal structure of Minkowski spacetime 







### References
[^1]: Hawking, S.W. and Ellis, G.F., 1973. _The large scale structure of space-time_. Cambridge University Press.

[^2]: Raclariu, A.M., 2021. _Lectures on celestial holography._ [arXiv:2107.02075](https://arxiv.org/abs/2107.02075).

[^3]: Penrose, R., 1963. _Asymptotic properties of fields and space-times._ [Physical Review Letters, 10(2), p. 66](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.10.66).
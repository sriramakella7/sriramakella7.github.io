---
layout: post
title: Random Unitary Circuits
categories: quant-ph
comments: true
---
In this post, I want to discuss a beautiful paper[^1] by Tianci Zhou and Adam Nahum that came out in 2018. The problem they consider is simple, but has a very rich structure as we'll soon see. 

## Introduction
Realistic many-body problems that appear in physics are hard. In fact, sometimes they are so hard, that we might as well be completely agnostic about the details of the problem and assume the dynamics is completely random; subject to the laws of physics. 

Wigner put this idea to use when he wrote the following probability distribution for the spacing between the points in the spectra of the nuclei of heavy atoms: 
$$
p(s) = \frac{\pi s}{2} e^{-\pi s^2/4}.
$$
This is, in fact, the probability distribution followed by the difference between two eigenvalues $\lambda_1$ and $\lambda_2$ of a $2 \times 2$ matrix drawn from the so called Gaussian Orthogonal Ensemble (GOE)[^2]. 

The problem Zhou and Nahum consider is the following. Suppose we have an infinite linear chain of qudits (of local dimension $q \geq 2$) subject to a random quantum circuit. 

Each unitary gate $U$ that acts on two qudits is drawn from the Haar ensemble, and at a circuit depth $t$, this prepares for us a state $\ket{\psi(t)}$ at the dashed red line. The initial state $\ket{\psi(0)}$ is something we specify. Say a subset of the qudits at depth $t$ are labeled $A$ and $B$ is the set of all qudits not in $A$. Then we can construct the reduced density matrix 
$$
\rho_A(t) = \text{Tr}_{B}\left(\ket{\psi(t)} \bra{\psi(t)}\right), 
$$
and ask what is the time dependence of the entanglement entropy? Recall the entanglement entropy is defined as 
$$
S(A) = -\text{Tr}\, \rho_A \log \rho_A.
$$
This is implicitly a function of $t$ since $\rho_A$ is a function of $t$. More generally, we could ask what is the time dependence of the various Rényi entropies defined via
$$
S_n(A) = \frac{1}{1-n} \log \text{Tr} \, \rho_A^n. 
$$
This question has a beautiful answer in terms of a random walker 

### References
[^1]: Zhou, T. and Nahum, A., 2019. Emergent statistical mechanics of entanglement in random unitary circuits. _Physical Review B_, _99_(17), p.174205. [arXiv:1804.09737](https://arxiv.org/abs/1804.09737).
[^2]: Livan, G., Novaes, M. and Vivo, P., Introduction to Random Matrices Theory and Practice.[arXiv:1712.07903](https://arxiv.org/abs/1712.07903) [math-ph].

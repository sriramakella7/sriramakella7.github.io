---
layout: post
categories: quant-ph
comments: true
title: Entropic Inequalities and Separability
---
## Introduction
Quantum entanglement for mixed states is a mysterious and a complicated beast to tame[^1]. Pure states are easier to deal with; we know how to quantify pure state entanglement using measures like the Schmidt rank or the von Neumann entropy. At the heart of this discussion lies the concept of *separable* quantum states. 

A bipartite pure state $$\ket{\psi}_{AB} \in \mathcal{H}_A \otimes \mathcal{H}_B$$ is separable if it can be written as $$\ket{\psi}_{AB} = \ket{\psi}_A \otimes \ket{\chi}_B$$ for some $$\ket{\psi}_A$$ and $$\ket{\chi}_B$$ in $$\mathcal{H}_A$$ and $$\mathcal{H}_B$$. It is **entangled** if it is not separable. 

A bipartite mixed state $$\rho_{AB}$$ acting on $$\mathcal{H}_A \otimes \mathcal{H}_B$$, on the other hand, is separable if it can be decomposed as a convex combination of product density matrices: 
\begin{equation}\tag{1}
\rho_{AB} = \sum_{i = 1}^{r} p_i \, \rho_A^{(i)} \otimes \rho_B^{(i)},
\end{equation}
where the $$p_i$$'s are all positive and the $$\rho_A^{(i)}$$ and $$\rho_{B}^{(i)}$$ are density matrices on $$\mathcal{H}_A$$ and $$\mathcal{H}_B.$$ The mixed $$\rho_{AB}$$ is entangled if it is not separable. 

It is a non-trivial problem to check whether such a decomposition is possible or not, thereby making it difficult to quantify mixed state entanglement. This is where entropic inequalities can come to our rescue.

I will try to explain how in this short post. The main question I will address is 
> **Main Question.** Can we use entropic quantities to give necessary and sufficient conditions for the separability of a mixed state $$\rho_{AB}$$ ? 

## Conditional Entropy
Forget about Hilbert spaces and mixed states for a moment and think of probability distributions of two random variables $$X$$ and $$Y$$, drawn with some joint probability distribution $$p(x, y)$$. We can define the following quantity called the **conditional entropy**[^2]: 
\begin{equation}\tag{2}
S_{X|Y} := S_{X,Y} - S_Y 
\end{equation}
where $$S_{X,Y}$$ is the Shannon entropy of the joint probability distribution $$p(x, y)$$ and $$S_Y$$ is the Shannon entropy of the marginal $$p(y)$$ obtained via "summing" over $$x$$: 
\begin{equation}\tag{3}
p(y) = \sum_{x \in X} p(x, y). 
\end{equation}
The Shannon entropy, in case you forgot, is defined as 
\begin{equation}\tag{4}
S_X = -\sum_{x \in X} p(x) \log p(x).
\end{equation}

An alternative way of defining the conditional entropy is as follows. First, we fix the random variable $$Y$$ to take some value $$y$$, and consider the conditional probability on $$x$$ defined as 
\begin{equation}\tag{5}
p(x| Y = y) = \frac{p(x, y)}{p(y)}. 
\end{equation}
We then compute the Shannon entropy of this probability distribution on $$X$$ holding $$Y = y$$ fixed. This gives us the Shannon entropy of $$X$$ conditioned on $$Y = y$$ which I'll denote as $$S_{X|Y=y}$$. The conditional entropy is the $$Y$$-average of this quantity:
\begin{equation}\tag{6}
S_{X|Y} = \sum_{y \in Y} p(y) S_{X|Y = y}. 
\end{equation}
It follows that $$S_{X|Y} \geq 0$$ because it is an average of positive quantities. 

However, quantum mechanically, the conditional entropy can be negative. We no longer have joint probability distributions, but a mixed state $$\rho_{AB}$$. The conditional quantum entropy instead is defined as $$S_{A|B} = S_{AB} - S_{B}$$ where $$S_{AB}$$ and $$S_{B}$$ are the von Neumann entropies of $$\rho_{AB}$$ and $$\rho_B$$; the density matrix $$\rho_B$$ is defined by tracing over $$A$$ in $$\rho_{AB}$$. The von Neumann entropy of a mixed state $$\rho$$, in case you forgot, is 
\begin{equation}\tag{7}
S(\rho) = -\text{Tr} \rho \log \rho.
\end{equation}

The reason conditional entropy can be negative is due to quantum entanglement. If we consider an entangled pure state $$\ket{\psi}_{AB}$$, for example, then the corresponding density matrix $$\rho_{AB}$$ has zero von Neumann entropy while the reduced density matrices $$\rho_A$$ and $$\rho_B$$ have non-zero von Neumann entropy.

A natural question that pops up is: 
>**Question.** For what quantum states $$\rho_{AB}$$ is the conditional quantum entropy positive? 

An obvious answer would be separable states. As we just saw, entangled states are the ones which give negative conditional entropies. It is natural to expect that unentangled, i.e., separable, states have positive conditional quantum entropies.  This is indeed true[^3]. The conditional quantum entropy is non-negative for separable states. 

But the converse is not true. In other words, this only gives us a necessary condition for separability, not a sufficient one. If $$S_{A|B}$$ is positive, we are not guaranteed to have a separable state; the Werner state[^4] furnishes a nice example. We can etch this new-found wisdom of ours onto the below figure:
![](/assets/conditional-entropy.png)
The converse, as discussed above, is not true. This leads us to the next natural question: 
> **Question.** Can we do better? In other words, can we find an entropic quantity where the implication goes both ways?

This is indeed possible, and I'll now try to explain how.

## Mutual Information 
Let's begin with a simpler question. Suppose we have a density matrix of the form $$\rho_{AB} = \rho_A \otimes \rho_B$$; how do we know it is a product state? 

Translating this question to classical probability distributions: how do we know that a joint probability distribution is independent, i.e., $$p(x, y) = p(x) p(y)$$? An obvious entropic quantity which checks for statistical independence is the *mutual information* defined as 
\begin{equation}\tag{8}
\mathcal{I}(X, Y) = S_{X} + S_Y - S_{XY}.
\end{equation}

An operational meaning to the mutual information is the extra information contained in the joint probability distribution $$p(x,y)$$ after extracting the information contained in the marginals $$p(x)$$ and $$p(y)$$. If $$X$$ and $$Y$$ are independent, then the mutual information is zero, but positive otherwise. The vanishing of mutual information, however, is a necessary and sufficient condition for statistical independence[^C]. This piece of wisdom is sketched below: 
![](/assets/mutual-information.png)

The reason, as you might already know, is because the relative entropy of two distributions $$p(x)$$ and $$q(x)$$ over the sample space $$X$$, defined as 
\begin{equation}\tag{9}
S(p||q) = \sum_{x\in X,\, y \in Y} p(x) \log\left(\frac{p(x)}{q(y)}\right)
\end{equation}
is zero iff $$p(x) = q(x)$$. The mutual information is nothing but the relative entropy between the distributions $$p(x,y)$$ and $$p(x) p(y)$$ over the sample space $$X \times Y$$. 

There is a quantum version of the relative entropy defined between two density matrices $$\rho$$ and $$\sigma$$ as 
\begin{equation}\tag{10}
S(\rho||\sigma) = \text{Tr} \,\rho \log \rho - \text{Tr} \,\rho \log \sigma
\end{equation}
which is zero iff $$\rho = \sigma$$. The quantum mutual information is defined as the relative entropy between the density matrices $$\rho_{AB}$$ and $$\rho_A \otimes \rho_B$$:
\begin{equation}\tag{11}
\mathcal{I}(A, B) = S(\rho_{AB}|| \rho_A \otimes \rho_B) = S_A + S_B - S_{AB}.
\end{equation}
It is zero iff $$\rho_{AB} = \rho_A \otimes \rho_B$$. Let's put this important fact in a box.  
![](/assets/quantum-mutual-information.png)

What we want to do however, is talk about separable states and not product states. The above fact only features product states. We will need to come up with something better.


## Conditional Mutual Information
The idea is to generalize the notion of mutual information in such a way that it is zero for separable states. A separable state is a convex combination of product states: 
\begin{equation}\tag{12}
\rho_{AB} = \sum_{i = 1}^r p_i \, \rho_A^{(i)} \otimes \rho_B^{(i)},
\end{equation}
and each product state has zero mutual information. Therefore, the *average mutual information* is zero: 
\begin{equation}
\sum_{i=1}^{r} p_i \,\mathcal{I}(\rho_{AB}^{(i)}) = 0
\end{equation}
where $$\rho_{AB}^{(i)} = \rho_A^{(i)} \otimes \rho_B^{(i)}$$. 

More generally, we can split the density matrix $$\rho_{AB}$$ as a sum of $$\rho_{AB}^{(i)}$$ with probabilities $$p_i$$, and then define the above quantity. If $$\rho_{AB}$$ is separable, this quantity is zero as argued above, but more generally it is non-negative because it is a sum of positive quantities. 

The quantity defined is very similar to the conditional entropy, except we are now averaging over mutual information. I will call this quantity the **conditional mutual information**. Unlike the quantum conditional entropy, however, it is not a quantum object yet because of the presence of classical probabilities $$p_i$$. 

The way to make it quantum is by quantizing the index $$i$$ to a third party $$C$$ and defining the tripartite state 
\begin{equation}\tag{13}
\sigma_{ABC} = \sum_{i =1}^{r} p_i \,  \rho_A^{(i)} \otimes \rho_{B}^{(i)} \otimes \left(\ket{i}\otimes\bra{i}\right),
\end{equation}
such that $$\text{Tr}_C  \,\sigma_{ABC} = \rho_{AB}$$. The above quantity we defined is then
\begin{equation}\tag{14}
\mathcal{I}(A, B| C) = S_{AC} + S_{BC} - S_{ABC} - S_{C}. 
\end{equation}
This definition is quantum and makes no use of classical probabilities. We can define it for any $$\sigma_{ABC}$$ even if it is not of the form given in Eq. (13). From strong subadditivity of quantum entropy[^5], we also know that this quantity is always non-negative.

What's amazing about this construction is that the conditional mutual information is zero iff $$\rho_{AB}$$ is separable! The precise statement is if $$\rho_{AB}$$ is separable, then the $$\sigma_{ABC}$$ from Eq. (13) is such that it saturates strong subadditivity. Conversely if any $$\sigma_{ABC}$$ is such that it saturates strong subadditivity, then $$\rho_{AB} = \text{Tr}_C \, \sigma_{ABC}$$ is separable. 

This is going to be the final piece of wisdom we will etch into a Theorem[^6]. 
> **Theorem.** *For any state $$\sigma_{ABC}$$ that saturates strong subadditivity, i.e., $$S_{AC} + S_{BC} - S_{ABC} - S_C = 0$$, the marginal state $$\rho_{AB} = \text{Tr}_C \, \sigma_{ABC}$$ is separable. Conversely, for any separable $$\rho_{AB}$$ there exists an extension $$\sigma_{ABC}$$ that saturates strong subadditivity.*

This gives us a necessary and sufficient condition for separable $$\rho_{AB}$$ using strong subadditivity. Isn't that cool? 

### References

[^1]: Horodecki, R., Horodecki, P., Horodecki, M. and Horodecki, K., 2009. [Quantum entanglement.](https://doi.org/10.1103/RevModPhys.81.865) _Reviews of modern physics_, _81_(2), pp.865-942, available at [arXiv:quant-ph/0702225](https://arxiv.org/abs/quant-ph/0702225).
[^2]: Witten, E., 2020. [A mini-introduction to information theory.](https://doi.org/10.1007/s40766-020-00004-5) _La Rivista del Nuovo Cimento_, _43_(4), pp.187-227, available at [arXiv:1805.11965](https://arxiv.org/abs/1805.11965) [hep-th].
[^3]: Cerf, N.J., Adami, C. and Gingrich, R.M., 1997. Quantum conditional operator and a criterion for separability. [arXiv:quant-ph/9710001](https://arxiv.org/abs/quant-ph/9710001).
[^4]: Werner, R.F., 1989. [Quantum states with Einstein-Podolsky-Rosen correlations admitting a hidden-variable model.](https://doi.org/10.1103/PhysRevA.40.4277) _Physical Review A_, _40_(8), p.4277.
[^5]: Lieb, E.H. and Ruskai, M.B., 1973. [Proof of the strong subadditivity of quantum-mechanical entropy.](https://doi.org/10.1063/1.1666274) _Journal of Mathematical Physics_, _14_(12), pp.1938-1941.
[^6]: Hayden, P., Jozsa, R., Petz, D. and Winter, A., 2004. [Structure of states which satisfy strong subadditivity of quantum entropy with equality.](https://doi.org/10.1007/s00220-004-1049-z) _Communications in Mathematical Physics_, _246_, pp.359-374, available at [arXiv:quant-ph/0304007](https://arxiv.org/abs/quant-ph/0304007).
[^C]: Cover, T.M., 1999. _Elements of information theory_. John Wiley & Sons.
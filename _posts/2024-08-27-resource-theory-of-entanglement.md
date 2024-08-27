---
layout: post
title: "Resource theory of quantum entanglement" 
categories: quant-ph
---

### Quantum Teleportation and LOCC

When we think of entanglement as a physical resource in quantum theory, the idea of LOCC (local operations and classical communications) is natural. The setup we’d imagine is as follows. Alice is here on Earth and Bob is far off in the Andromeda galaxy, and they share a Bell pair
\begin{equation}
|\psi \rangle = \frac{1}{\sqrt{2}} |00\rangle + \frac{1}{\sqrt{2}} |11\rangle.
\end{equation}

Now, Alice is handed over another qubit which is in the state 
\begin{equation}
    |\phi\rangle = a |0\rangle + b |1\rangle,
\end{equation}
where $$|a|^2 + |b|^2 = 1$$, and she must send this state over to Bob. This is the famous quantum teleportation problem.

In this problem, Alice is allowed to perform operations on her two qubits, and she is allowed to establish a classical communication line with Bob (over e-mail or telephone). She can perform measurements on her qubits and relay the results to Bob via the classical communication channel. Bob can use these results and perform operations on his qubit. This allows Alice and Bob to establish classical correlations. This is the paradigm of LOCC.

LOCC operations come for "free" when we think of entanglement as a resource[^1]. They are operations that don't create entanglement. Therefore, any good measure of entanglement must be non-increasing under LOCC. 

### Nielsen's Majorization Theorem
For bipartite states of the form $$| \psi_{AB}\rangle \in H_A \otimes H_B,$$ Nielsen's majorization theorem[^2] states that
\begin{equation}
    | \psi_{AB} \rangle \xrightarrow{\text{LOCC}} | \phi_{AB}\rangle \iff \lambda_{\psi} \preccurlyeq \lambda_{\phi},
 \end{equation}
 where the \(\lambda\)'s are the Schmidt co-efficients. One immediate consequence of this theorem is the existence of a *maximally* entangled state which takes the form: 
 \begin{equation}
|\psi_{AB}\rangle = \frac{1}{\sqrt{d}}\sum_{i = 1}^{d} |i_A \rangle \otimes |i_B\rangle,
 \end{equation}
 
 where \(d\) is the dimension of the smaller Hilbert space between \(H_A\) and \(H_B\). Any other bipartite state belonging to \(H_A \otimes H_B\) majorizes the above state, and hence can be obtained from it via LOCC. In other words, starting from the maximally entangled state, we can reach every bipartite state via LOCC. 

 ### Zoo of Multipartite Entanglement
 However, for multipartite states, things are complicated. There is no analog of the majorization theorem. For three qubits held by Alice, Bob, and Charlie, there are two inequivalent LOCC classes[^3] given by the GHZ and the W states:
 $$
\begin{equation}
    |\text{GHZ}\rangle = \frac{1}{\sqrt{2}} | 000 \rangle + \frac{1}{\sqrt{2}} | 111 \rangle, \quad |\text{W}\rangle = \frac{1}{\sqrt{3}} | 001\rangle + \frac{1}{\sqrt{3}} | 010\rangle + \frac{1}{\sqrt{3}} | 1 0 0 \rangle. 
\end{equation}
$$
In other words, all three-qubit states can be obtained via LOCC starting with the GHZ and W states. However, there is no LOCC that takes the GHZ to W or vice versa. 

When we consider four qubits, there are nine inequivalent ways[^4], and infinitely many beyond four qubits. What's worse: as the number of parties increase, almost every state forms its own inequivalent LOCC class[^5]. Not only is there no maximally entangled state in the LOCC sense, but every state forms its own isolated island. 

Depending on how you look at it, this state of affairs may be both disappointing and intriguing. But we could take a different approach. Say we forget about all the Alices, Bobs and Charlies, and ask what should the transformations be that don't create entanglement? But before that, what is entanglement? 

### What is Entanglement? 
Just to make sure we're all on the same page. We say a pure state \(| \psi \rangle\) is entangled if it **cannot** be written as a tensor product of the form: 
$$
\begin{equation}
| \psi \rangle = |\psi_1 \rangle \otimes \dots | \psi_q \rangle. 
\end{equation}
$$
A mixed state \(\rho\) is entangled if it **cannot** be written as a convex combination of the form: 
$$
\begin{equation}
\rho = \sum_{i} p_i \, \rho_i^{(1)} \otimes \dots \rho_i^{(q)}. 
\end{equation}
$$

### Full Separability-Preserving maps (FSPs) 
What are the allowed transformations that don't create entanglement? Instead of LOCC, let's consider the set of transformations that map mixed states to mixed states, but send separable states to separable states. Such transformations can't create entanglement, and the LOCC transformations are a subset of all such transformations. Let's call these transformations full separability-preserving (FSP) transformations[^6]. 

Under this broader class of "free" operations, does the zoo of multipartite entanglement collapse and become something simple? Turns out it does, but not quite. The following three theorems have been proved[^6]: 

- **Theorem 1 (collapse of SLOCC classes)**: Any state \(|\psi\rangle\) can be converted to any other state \(|\phi \rangle\) *probabilistically* via an FSP map \(\Lambda\). 

- **Theorem 2 (no islands)**: Given any state \(|\psi_1\rangle\), there exists an *inequivalent* state \(|\psi_2 \rangle\) and an FSP map \(\Lambda\) such that \( \Lambda(\psi_1)) = \psi_2\). 

- **Theorem 3**: Even under the broader class of FSP transformations, there is no maximally entangled three-qubit state.  


For three qubits, the answer is no[^6]. And although there is no proof for higher number of qubits, it seems reasonable to expect that such a collapse does not occur. An immediate problem is to come up with such a proof. But until such a proof is found (and it hasn't been found to the best of my knowledge), there is a chance that for more number of qubits, the zoo collapses. 











### References
[^1]: Chitambar, E., & Gour, G. (2019). *Quantum resource theories.* Reviews of Modern Physics, **91**(2), 025001, available at [1806.06107](https://doi.org/10.48550/arXiv.1806.06107).

[^2]: Nielsen, M. A. (1999). *Conditions for a class of entanglement transformations.* Physical Review Letters, **83**(2), 436, available at [quant-ph/9811053](https://doi.org/10.48550/arXiv.quant-ph/9811053).

[^3]: Dür, W., Vidal, G., & Cirac, J. I. (2000). *Three qubits can be entangled in two inequivalent ways.* Physical Review A, **62**(6), 062314, available at [quant-ph/0005115](https://doi.org/10.48550/arXiv.quant-ph/0005115). 

[^4]: Verstraete, F., Dehaene, J., De Moor, B., & Verschelde, H. (2002). *Four qubits can be entangled in nine different ways.* Physical Review A, **65**(5), 052112, available at [quant-ph/0109033](https://doi.org/10.48550/arXiv.quant-ph/0109033).

[^5]: Sauerwein, D., Wallach, N. R., Gour, G., & Kraus, B. (2018). *Transformations among pure multipartite entangled states via local operations are almost never possible.* Physical Review X, **8**(3), 031020, available at [1711.11056](https://doi.org/10.48550/arXiv.1711.11056). 

[^6]: Contreras-Tejada, P., Palazuelos, C., & De Vicente, J. I. (2019). *Resource theory of entanglement with a unique multipartite maximally entangled state.* Physical Review Letters, **122**(12), 120503, available at [1807.11395](https://doi.org/10.48550/arXiv.1807.11395)
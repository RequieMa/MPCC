# Dirac Notation

[reference](https://www.physics.umd.edu/courses/Phys374/fall05/files/DiracNotation.pdf)

The Dirac notation for states in a linear space is a way of representing a state in a linear space in a way that is free of the choice of coordinate but allows us to insert a particular choice of coordinates easily and to convert from one choice of coordinates to another conveniently. 

Furthermore, it is oriented in a way (bra v.s. ket) that allows us to keep track of whether we need to take comlext conjugates or not. This is particularly useful if we are in an inner-product space. The orientation of the Dirac representation allows us to nicely represent the inner product in a way that keeps careful track of complex conjugation. 

## Compare with Ordinary Vectors
If the basis vectors are orthonormal, then we can obtain each components of a vector by dot product with the relevant basis vectors:
$$
\vec a = (\vec a \cdot \hat i) \hat i + (\vec a \cdot \hat j) \hat j + (\vec a \cdot \hat k) \hat k\\
$$

If you choose a different basis, the components of any given vector will change. However the value of $\vec a \cdot \vec b$ is independent of the basis.

In an $n$-dimensional 'Hilbert Space', we can write any Ket in terms of just $n$ othere kets, e.g.) in 3 dimensions
$$
\ket{a} = \alpha \ket p + \beta \ket q + \gamma \ket r\\
\ket{a} = a_x \ket i + a_y \ket j + a_z \ket k\\
$$

The choice of $\{ \ket p, \ket q, \ket r \}$ is a particular '**basis**', the numbers $\alpha, \beta, \gamma$ are the '**components**' of $\ket a$ in this basis (normally called 'amplitudes' in QM). If the Hilbert Space has an **infinite number of dimensions**, we get an infinite set of components. Such a set is called a **wavefunction**.  

## Inner Product
Let 
$$
\vec a =  \left| a \right \rangle\\
\vec a^{*} =  \left \langle a \right|\\
\vec a^{*} \cdot \vec a = \braket{a|a}
$$
where
$$
\braket{a|b} = \vec a^{*} \cdot \vec b = \begin{bmatrix} a_1^* & a_2^* \end{bmatrix} \begin{bmatrix} b_1 \\ b_2 \end{bmatrix} = a_1^*b_1 + a_2^*b_2
$$

## Outer Product
Consider 
```{math}
\begin{eqnarray*}
    \vec a (\vec b \cdot \vec c)\\
    \, =& \mathbf a (\mathbf b^T \mathbf c)\\ 
    \, =& (\mathbf a \mathbf b^T) \mathbf c\\
    \, =& (\vec a \otimes \vec b) \vec c\\
\end{eqnarray*}
```
where
$$
\vec a \otimes \vec b
$$
is called the **outer product** of the vectors.

It takes a vector in the $\vec c$ direction and gives back one in the $\vec a$ direction. ($\vec b$ serves as a measurement tool such that $\vec c$ project on)

$$
\vec a \otimes \vec b = \vec a \cdot \vec b^{*} = \begin{bmatrix} a_1 \\ a_2 \end{bmatrix} \begin{bmatrix} b_1^* & b_2^* \end{bmatrix} = \begin{bmatrix} a_1b_1^* & a_1b_2^* \\ a_2b_1^* & a_2b_2^*\end{bmatrix}
$$

In general, we can multiply an $(n \times k)$ matrix and a $(k \times m)$ matrix to get an $(n \times m)$ matrix
$$
(\mathbf A \mathbf B)_{ij} = \sum_{l=1}^k A_{il}B_{lj}\\
$$
where $i = 1...n$, $j = 1...m$

To see what is really going on here, it is useful to see the outer product of two orthonormal basis vectors $\hat e_i$ and $\hat e_j$
$$
(\hat e_i \otimes \hat e_j)\vec v = \hat e_i (\hat e_j \cdot \vec v) = \vec v_j \hat e_i
$$

The matrix that does this job is the one with 1 in the j-th row and i-th column and elsewhere. We can therefore write any matrix as an outer product operator
$$
\mathbf A = \sum_{i, j = 1}^N A_{ij} \hat e_i \otimes \hat e_j
$$
The outer product expansion reveals that the same matrix can be expressed in totally different forms, depending on the basis you choose. 

With Dirac notation
$$
\vec a \otimes \vec b = \ket{a} \bra{b}
$$

Then the previous relation can be expressed as 
$$
(\vec a \otimes \vec b) \vec c = \vec a (\vec b \cdot \vec c)\\
\Rightarrow (\ket{a} \bra{b}) \ket{c} = \ket{a} \braket{b|c}
$$

The rule about the matrices and the outer product produces a pair of useful results
$$
\mathbf A = \sum_{i, j = 1}^N A_{ij} \ket{e_i} \bra{e_j} = \sum_{i, j = 1}^N  \ket{e_i} A_{ij} \bra{e_j}\\
\mathbf I = \sum_{i, j = 1}^N  \ket{e_i} \delta_{ij} \bra{e_j} = \sum_{i = 1}^N  \ket{e_i} \bra{e_i}\\
$$

## Origin
[reference](https://chem.libretexts.org/Bookshelves/Physical_and_Theoretical_Chemistry_Textbook_Maps/Quantum_Tutorials_%28Rioux%29/01%3A_Quantum_Fundamentals/1.26%3A_Elements_of_Dirac_Notation)

Two major mathematical traditions emerged in quantum mechanics: **Heisenberg’s matrix mechanics** and **Schrödinger’s wave mechanics**. These distinctly different computational approaches to quantum theory are formally equivalent, each with its particular strengths in certain applications. Heisenberg’s variation, as its name suggests, is based matrix and vector algebra, while Schrödinger’s approach requires integral and differential calculus. Dirac’s notation can be used in a first step in which the quantum mechanical calculation is described or set up. After this is done, one chooses either matrix or wave mechanics to complete the calculation, depending on which method is computationally the most expedient.

## Integral Form
Consider the linear superposition
$$
\ket{\psi} = \int \ket{x} \braket{x | \psi} dx\\
\bra{\phi} = \int \braket{\phi | x'} \bra{x'} dx'
$$

Combining these yields,
$$
\braket{\phi | \psi} = \int_x \int_{x'} \braket{\phi | x'} \braket{x'|x} \braket{x | \psi} dx' dx = \int_x \braket{\phi | x} \braket{x | \psi} dx 
$$
The $x'$ disappears because the position eigenstates are an orthogonal basis set and $\braket{x'|x} = 0$ unless $x' = x$ in which case it equals 1.

## Summary
J. L. Martin (see references below) has identified four virtues of Dirac notation.

1. It is concise. There are a small number of basic elements to Dirac’s notation: bras, kets, bra-ket pairs, ket-bra products, and the completeness relation (continuous and discreet). With these few building blocks you can construct all of quantum theory.
2. It is flexible. You can use it to say the same thing in several ways; translate with ease from one language to another. Perhaps the insight that the Dirac notation offers to the Fourier transform is the best example of this virtue.
3. It is general. It is a syntax for describing what you want to do without committing yourself to a particular computational approach. In other words, you use it to set up a problem and then choose the most expeditious way to execute the calculation.
4. While it is not exactly the industry standard, it should be for the reasons listed in 1-3 above. It is widely used, so if you want to read the literature in quantum chemistry and physics, you need to learn Dirac notation. In addition most of the best quantum textbooks in chemistry and physics use it.
5. I would like to add a 5th virtue. Once you get the “hang of it” you will find that it is simple to use and very enlightening. It facilitates the understanding of all the fundamental quantum concepts.

+++
date = '2025-06-19'
title = "I don't understand Hilbert's thesis"
+++

Kripke has this argument he renders in favor of the Church-Turing Thesis that relies on what’s called Hilbert’s thesis. Hilbert’s thesis is “the idea that the steps of any mathematical argument can be expressed in a language based on first-order logic (with identity).”

Now, this thesis seems obviously wrong to me. For example, you cannot define a predicate for reachability on a graph in first-order logic. Suppose we attempt to create a first-order formula \(\phi(x, y)\) such that \(\phi(x, y)\) is true if and only if \(y\) is reachable from \(x\). Then, let’s define a certain class of graphs:

\[
\begin{align}
    \psi_1 &:= (\forall x)(\forall y) \phi(x, y) \\
    \psi_2 &:= (\forall x)(\exists y) (E(x, y) \land (\forall z) (E(x, z) \to y = z)) \\
    \psi_3 &:= (\forall x)(\exists y) (E(y, x) \land (\forall z)(E(z, x) \to y = z))
\end{align}
\]

\(\psi_1\) denotes the graph is strongly connected, \(\psi_2\) that each node in the graph has an out-degree of 1, and \(\psi_3\) that each node has an in-degree of 1. These sentences together characterize a cyclic graph. Additionally, we define a set of formulas \(I_k\), as follows:

\[I_k := (\forall x_1)(\forall x_2) \ldots (\forall x_{k-1})(\exists x_k)(x_k \neq x_1 \land x_k \neq x_2 \land \ldots \land x_k \neq x_{k-1})\]

That is, each \(I_k\) is true only if there are at least \(k\) domain elements, with \(x_k\) being distinct from \(x_1\) through \(x_{k-1}\).

Consider the first three axioms, alongside the requirement that there be at least three domain elements: \(\{\psi_1, \psi_2, \psi_3, I_3\}\). This theory clearly has a model; for instance, the directed cycle with three nodes satisfies it.

Likewise, there are models with 4, 5, 6, 7, etc., domain elements.

It’s evident that our theory, which describes a cyclic graph \(\{\psi_1, \psi_2, \psi_3\}\), has arbitrarily large finite models. By the overspill principle, it also has an infinite model. This result follows from the compactness theorem: if we add, for every natural number \(n\), a sentence stating that there are at least \(n\) domain elements, we know that there are arbitrarily large models. Hence, every finite subset of these sentences is satisfiable, and by the compactness theorem, there exists a model of the entire theory, which must have infinite cardinality.

\(\{\psi_1, \psi_2, \psi_3, I_1, I_2, \ldots\}\) thus has a model, an "infinite cycle", which leads to a contradiction. Using \(\phi\) in this concrete example, we would describe an infinite cycle. However, since the graph is strongly connected, if we start at some node and follow all out-degrees, we must eventually visit all nodes. Given that each node has an in-degree of 1, we must return to the starting node, implying that the graph must be finite.

Thus, we must reject one of our assumptions, and the only assumption we made was that \(\phi\) exists. Therefore, we conclude that \(\phi\) does not exist in first-order logic.

Since such predicates cannot be defined in first-order logic, how could the steps of any mathematical argument be expressed within first-order logic? An obvious counterexample would be any mathematical argument that requires a reachability predicate no?

But here’s the thing, I’m skeptical that Kripke’s argument assumes such an obvious falsehood, given Kripke was undoubtably more competent and intelligent than me in this domain. This leads me to believe I’m missing something obvious and/or misunderstanding Hilbert’s thesis. 

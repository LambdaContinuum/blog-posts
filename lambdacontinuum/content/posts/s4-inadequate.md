+++
title = 'S4 is Inadequate as a Logic of Formal Provability'
date = '2025-06-07'
+++

Provability logics are modal logics used to investigate, surprise, surprise, various features of provability operators or predicates. The first candidate for a provability logic was the modal system S4.

S4 is characterized by the following axioms:

  * (K) □(φ → ψ) → (□φ → □ψ)

  * (M) □φ → φ

  * (4) □φ → □□φ




and is closed under the following rules of inference:

  * Modus Ponens: From ⊢ φ and ⊢ φ → ψ, infer ⊢ ψ

  * Necessitation: If ⊢ φ, then ⊢ □φ




The interpretation that modal connectives take within modal logic depends on the modal system we’re attempting to analyze. ‘□’ can be interpreted as logical necessity, nomic necessity, moral obligation, and more. The interpretation we’re interested in is ‘□φ’ as ‘It is provable that φ.’

On its face, S4 might seem like a decent candidate for a modal logic that correctly analyzes provability. (K) holds because if a conditional is provable, then if the antecedent of the conditional is provable, the consequent of the conditional is obviously provable as well. (M) holds because if something is provable, it’s true. (4) holds because there’s a proof, then you can prove there is a proof.

This intuitive work is valuable, but more needs to be done. We need to ensure that there are no principles that hold for provability but are not provable in S4. To determine this, we require a precise explication of the notion of provability, and we must check whether the principles of S4 hold up in light of this explication.

Let’s provide an explication of provability. A natural candidate for the interpretation of □ is a formal provability predicate within a standard axiomatized mathematical theory. In fact, formal provability predicates are typically developed in the context of arithmetic. This is for a few reasons. For one, via Gödel coding, we can discuss numbers instead of expressions. Conveniently, arithmetic has many established results that can be borrowed and applied to syntax.

We’ll use Peano Arithmetic (PA). The language of PA, denoted 𝓛PA, is a first-order language with identity and the symbols 0, S, +, and *. Each natural number _n_ has a corresponding numeral, ⟨ _n_ ⟩, in PA with the form S(…S(0)) with _n_ occurrences of _S_. Formulas in 𝓛PA can be classified by their complexity. Consider the formulas ∀x < t φ(x) and ∃x < t φ(x), the quantifiers in such formulas are are called _bounded_. Formulas with only bounded quantifiers are called Δ0​-formulas. The complexity hierarchy is as follows: Π0 = Σ0 =Δ0. Σn+1-formulas have the form ∃x1…∃xk(φ(x1, …, xk)), where φ(x1,…,xk) is Πn​. Πn+1​-formulas have the form ∀x1…∀xk(φ(x1, …, xk)), where φ(x1,…,xk) is Σn​.

All sentences in 𝓛PA are logically equivalent to, for some _n_ and _m_ , a Σn​ or Πm​ formula. However, the class of Σ1-formulas is particularly interesting, as a function is Turing-recognizable if it is Σ1​-definable. This means an axiomatic arithmetic that can handle Σ1​ sentences is expressive enough to prove statements concerning the syntax of a formal language within it.

We say a theory of arithmetic, T, is Σ1-sound if, for any Σ1-formula, T ⊢ φ implies that φ is true in the standard model of arithmetic. Correspondingly, T is Σ1-complete if, for any sentence φ ∈ Σ1, φ is true in the standard model of arithmetic, then T ⊢ φ. Peano Arithmetic is Σ1-complete.

We also map syntactic objects to natural numbers so that each syntactic object τ of 𝓛PA is represented by a Gödel code ⌜τ⌝. Now, consider an arbitrary theory T of 𝓛PA that extends Peano Arithmetic. We call such a theory elementary presented if there’s an arithmetic ∆0-formula, 𝙰𝚡T(x), which is true of a natural number if it codes an axiom of T. We can use 𝙰𝚡T(x) to construct a ∆0-formula 𝙿𝚛𝚏T(y, x), a binary proof predicate of T that is true of natural numbers _m_ and _n_ if _m_ is the code of a sequence of formulas that constitute a proof of the formula whose code is _n_.

Now consider Binumeration, which consists of two propositions:

  1. If in the standard model 𝙿𝚛𝚏T( _m_ , _n_ ), then PA ⊢ 𝙿𝚛𝚏T(⟨ _m_ ⟩, ⟨ _n_ ⟩)

  2. If in the standard model ¬𝙿𝚛𝚏T( _m_ , _n_ ), then PA ⊢ ¬𝙿𝚛𝚏T(⟨ _m_ ⟩, ⟨ _n_ ⟩). 




We can obtain a monadic standard provability predicate, 𝙿𝚛𝚘𝚟T(x) := ∃y 𝙿𝚛𝚏T(y, x), and a consistency statement, 𝙲𝚘𝚗(x) := ¬𝙿𝚛𝚘𝚟T(⌜⊥⌝).

Since 𝙿𝚛𝚘𝚟T(x) is obtained by appending an existential quantifier to a ∆0-formula, it’s a ΣI-formula. It follows from Σ1-completeness that the first conjunct of Binumeration is true. The second conjunct of Binumeration fails, but this is no problem. 𝙿𝚛𝚘𝚟T(x) still succeeds in defining provability since 𝙿𝚛𝚘𝚟T(⟨⌜φ⌝⟩) is true in the standard model just in case T ⊢ φ.

In fact, our 𝙿𝚛𝚘𝚟T(x) formula satisfies what are known as the Hilbert-Bernays conditions for formal provability predicates, this is of future relevance.

Now that we have provided a precise explication of the notion of formal provability as the formal provability predicate 𝙿𝚛𝚘𝚟T(⟨⌜φ⌝⟩), we can finally ask whether we can interpret □ in S4 as this predicate.

To answer this, consider the Diagonal Lemma. For any formula φ(x) ∈ 𝓛PA, there is a sentence λ ∈ 𝓛PA such that PA ⊢ λ ≡ φ(⌜λ⌝). If we take φ(x) to be ¬𝙿𝚛𝚘𝚟PA( _x_ ), the diagonal lemma entails the existence of a sentence that provably satisfies the condition G ≡ ¬𝙿𝚛𝚘𝚟PA(⌜G⌝). G is thus independent of PA. You may recognize this is Gödel’s incompleteness theorem: if an elementary presented theory T extends PA and is consistent, then there is a sentence G ∈ 𝓛PA such that T ⊬ G and T ⊬ ¬G. Moreover, T ⊬ 𝙲𝚘𝚗(T).

Years later, Henkin would ask what would happen with sentences such as H ≡ 𝙿𝚛𝚘𝚟T(⌜H⌝). Löb answered this question with Löb’s theorem: if the Diagonal Lemma applies to T and the provability predicate of a theory T satisfies the Hilbert-Bernays provability conditions , T ⊢ 𝙿𝚛𝚘𝚟T(⌜φ⌝) → φ. For any given sentence φ, we call the formula 𝙿𝚛𝚘𝚟T(⌜φ⌝) → φ reflection for φ (over T), and Löb’s theorem asserts that reflection is provable in T but only for all theorems of T. The theorem follows from an application of 𝙿𝚛𝚘𝚟T(⌜x⌝) → φ to the Diagonal Lemma. Since, if the Diagonal Lemma applies to T, the lemma entails a ψ such that T ⊢ ψ ≡ (𝙿𝚛𝚘𝚟T(⌜ψ⌝) → φ). 

Now, with background laid down, can □ of S4 be reasonably interpreted as the formal provability predicate? Let us take T = PA. From here, there are a few ways to show the inadequacy of S4 with respect to formal provability. One such approach is to note that, since S4 ⊢ □φ → φ for any φ, interpreting □φ as 𝙿𝚛𝚘𝚟T(⌜φ⌝) would require that for all φ ∈ 𝓛PA, PA ⊢ 𝙿𝚛𝚘𝚟T(⌜φ⌝) → φ. This in conjunction with Löb’s theorem entails that for all φ ∈ 𝓛PA, PA ⊢ φ. So, if PA is consistent, S4 cannot be the logic of the formal provability predicate of PA.

Another approach is to recall that 𝙲𝚘𝚗(x) is ¬𝙿𝚛𝚘𝚟T(⌜⊥⌝), which is logically equivalent to 𝙿𝚛𝚘𝚟T(⌜⊥⌝) → ⊥. This is an axiom of S4 since □⊥ → ⊥ is an instance of (M). Therefore, if S4 is adequate, it follows that PA ⊢ 𝙲𝚘𝚗(PA). This contradicts Gödel’s second incompleteness theorem. Moreover, necessitation yields □(□⊥ → ⊥), allowing us, in S4, to derive the claim that the consistency statement is derivable, which again contradicts Gödel’s second incompleteness theorem.

This argument assumes that T = PA, but the point generalizes to any consistent, recursively axiomatizable extension of PA. Given this, it’s clear that S4 is inadequate as a modal logic of formal provability.

Here’s one ramification of this. S4 was initially proposed as a logic of provability in light of Brouwer’s intuitionistic logic, which was formalized by Heyting as Intuitionistic Propositional Calculus (IPC). On this approach we say a mathematical claim is true if it has a proof and false if there is a proof that it leads to contradiction. This idea inspired Brouwer-Heyting-Kolmogorov semantics, which identifies true with provability. A proof of φ ∧ ψ is a proof of φ and a proof of ψ; a proof of φ ∨ ψ is a proof of φ or a proof of ψ; a proof of φ → ψ is a construction of proofs of ψ from proofs of φ; and since contradictions have no proof, a proof ¬φ is a proof of φ → ⊥, where ⊥ is a contradiction. Gödel would later provide a translation function, _t_ , that converts formulas in IPC into modal formulas and would prove that if IPC ⊢ φ, then S4 ⊢ t(φ). McKinsey and Tarski subsequently proved that if S4 ⊢ t(φ), then IPC ⊢ φ. Thus, IPC can be interpreted to be about classical provability if and only if S4 is the logic of classical provability. We’ve shown that S4 cannot be the logic of classical provability, and so IPC cannot be taken to be about classical provability.

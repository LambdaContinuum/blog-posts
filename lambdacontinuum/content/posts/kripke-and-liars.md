+++
title = 'Kripke and Liars'
date = '2025-07-15'
+++

The Liar paradox is a paradox that arises when one is able to construct sentences that assert their own untruth. Consider the sentence "This sentence is not true." Abbreviating this sentence as 'L', one can see that 'L' is equivalent to ~True(L), that is: L ↔ ~True(L). Assuming that a truth predicate abides by the Tarski schema, True(A) ↔ A, it follows that True(L) ↔ ~True(L). This is a contradiction.

There are four routes one can take from here. One could grant that truth abides by the Tarski schema and so entirely abandon the notion of truth, keep the notion of truth but prevent the construction of any such Liar sentences, reject or restrict the Tarski schema, or restrict classical logic so one cannot infer a contradiction (or prohibit explosion while allowing contradictions).

Most find preventing the construction of Liar sentences the most plausible solution to the problem of the Liar. This seems plausible, but it isn't as easy as it sounds. Liar sentences seem to naturally arise if one allows self-reference and there are a variety of ways to achieve such self-reference. The most suspicious form of self-reference, what we'll call Artificial Self Reference, arises when we consider languages within which it's permissible to have names for sentences that contain those very names. For example, if we let 'L' be the name of the sentence 'L isn't true'. You may reasonably doubt that such a language is even intelligible, but importantly, this isn't the only way to achieve self-reference. For example, one could achieve self-reference through Gödel Self-Reference.

The core insight behind Gödel Self-Reference is that once languages hit a certain level of expressive power, they can express their own syntax. Famously, one can achieve this by setting up a correlation between letters in the alphabet of a language with certain numbers, and between some concatenation relation and a relation among numbers. The result is that for each expression _e_ of the language, we have a singular term ⟨ _e_ ⟩ that denotes the number correlated with _e_. Using Gödel numbering, from here on out we'll describe the liar as L ↔ ~True(⟨L⟩).

It turns out that for any property you can express in some language, one could construct a sentence in the language that predicates that property to its own Gödel number. Formally, for any formula C(v) in the language of arithmetic with v as its only free variable, there is a sentence F in that language such that F ↔ C(⟨F⟩) is provable in the arithmetic theory. This is known as the Gödel-Tarski Fixed Point Lemma. And so this allows us to indirectly but legitimately achieve self-reference.

Now, just because self-reference is permitted doesn't mean the construction of Liars is permitted. Applying the Fixed-Point Lemma to any formula ~B(v) gives us, for some sentence F, F ↔ ~B(⟨F⟩). It follows from F ↔ ~B(⟨F⟩) that ~(F ↔ B(⟨F⟩)). Now if truth abides by the Tarski schema, A ↔ True(⟨A⟩), then (arithmetic) truth must be undefinable since for any predicate, P, you define there will be a sentence of the form, ~(A ↔ P(⟨A⟩)), contradicting the Tarski schema. This is known as Tarski's "Undefinability Theorem".

This theorem generalizes to theories in classical logic in which our theory of arithmetic can be embedded. Consider an extension we'll call L1 that results from adding to our language of arithmetic, which we'll call L0, a primitive truth predicate, which we'll call Truth0, meaning 'is a true sentence of the language of L1'. The generalized proof of Tarski's theorem tells us that in the extended language there's the sentence Q such that it's provable that ~(Q ↔ Truth0(⟨Q⟩)), but this is no problem, we're able to consistently add into our extended language as axioms instances of the Tarski schema for all formulas in our non-extended arithmetic language L0 which enables us to define truth for our language L0 without having to deal with our sentence Q serving as a counter-example.

So we can define truth for sentences of a language, but only within an extended language. Of course, the undefinability theorem still shows we cannot extend our interpretation of the truth predicate to the extended language, since our extended language cannot consistently contain its own truth predicate any more than our non-extended language can. We need a second extension to consistently construct a truth predicate for the first extension. This second extension may look similar to the first, we obtain it by adding to arithmetic not only the predicate 'Truth0' but also a new predicate 'Truth1'. This process of extension will proceed indefinitely, giving us what we call the Tarski hierarchy over arithmetic.

This isn't limited to arithmetic; each of the truth predicates in the Tarski hierarchy over arithmetic can be defined within standard set theory, of course our undefinability theorem still implies that the notion of set-theoretic truth cannot be defined within set theory.

What does this tell us about truth _tout court_? If we were to add truth _tout court_ to a language, Tarski's theorem tells us there's a liar sentence in that language. And so if we want to restrict the formation of Liars in our language, it seems we need to reject full truth. This isn't to entirely abandon the notion of truth, we still have the variety of formal truth predicates as given by our extended languages, rather this is to reject the coherence of "full" truth to prevent the formation of Liars. This is the classical Tarskian picture of a never-ending increasing hierarchy of truth predicates.

This solution to the Liar seems fine enough, so what is there to be said about Kripke's thoughts? It's important to note that the standard Tarskian picture works by avoiding to venture into a domain that is extremely easy to enter, and this may indicate the Tarskian hierarchy as an insufficient solution. Consider Kripke's famous example of Jones who says:

  1. Most of Nixon’s assertions about Watergate are untrue.




This seems like the sort of mundane thing people are willing to say in our day-to-day lives. But, suppose one of the things Nixon said was:

  2. Everything Jones says about Watergate is true.




and that everything else Nixon said about Watergate is evenly divided between the false and the true. This would mean that Jones' assertion (1) is true if and only if Nixon's assertion (2) is untrue, and Nixon's assertion (2) is untrue if and only if Jones' assertion (1) is untrue. So Jones' assertion is true if and only if it's untrue, a contradiction.

Maybe to protect against paradox, Jones asserts with the usage of Tarskian truth predicates:

  1. Most of Nixon’s assertions about Watergate are not true0.




For reasons discussed previously this would obviously block the paradox, but it wouldn't be true to what Jones wanted to say. Jones needs to choose a subscript higher than all the subscripts on 'true' employed in Nixon's utterances. Sadly, Jones probably doesn't know which subscripts Nixon employed, and if he chooses one that's too low his statement won't have the content he wants it to have.

The general problem this indicates is that speaking in line with Tarskian theory places an immense pressure on us to choose incredibly high subscripts, otherwise we're at risk of falling short of what we hope to say, but in doing so we make it harder for others to fulfill their own intentions. Imagine if you and a friend each attempted to say that nothing the other said is true, you'd both be trying to include the other's assertions within the scope of your own. At most only one of you can succeed since success requires the use of a higher subscript than the other.

How do we go about dealing with this problem? Let's add a single non-indexical truth predicate to a language L0, presume that Tarskian truth in such a theory can be defined in standard set theory and also presume that L0 is expressive enough such that self-referential formulas are permitted. Since truth in L0 can be defined in standard set theory, quantifiers in such a language must be restricted so as to range only over the members of some set, we cannot permit the ability to speak of arbitrary sets.

We’ll extend L0, a first-order language with names, predicates, and function symbols, to a language L0\+ by adding a new 1-place predicate ‘True’. Variables in such a language will range over the members of some domain of discourse, D. Every n-place predicate in our original language has a set of n-tuples of members of D as its extension. For our ‘True’ predicate we won’t assign a permanent extension yet, first we’ll consider various temporary quasi-extensions. Each temporary quasi-extension X is a subset of our domain of discourse D satisfying the following conditions:

  1. All of the members of X are Gödel numbers of sentences

  2. No sentence and it’s negation are both in X.




Let Xneg consist of everything in D that is either not a sentence or the negation of a member of X. From (2) Xneg must be disjoint with X. From this one can give an inductive definition that assigns values to a formula of L0\+ relative to an assignment function and a temporary quasi-extension X for ‘True’. I'll avoid explicitly giving te full inductive definition here to avoid unnecessarily increasing the length of this article. Here, the main point is True(t) is true (which here is a term in some set-theoretic meta-language whose purpose is to describe L0+) relative to some assignment function and temporary quasi-extension X if and only if there is an object o denoted by t and o is in X. Likewise, True(t) is false if and only if there is an object o denoted by t and o isn’t in X.

Since X and Xneg need not be exhaustive, some formulas won’t be either true or false relative to a given assignment function and temporary quasi-extension X. Since we’ll be focusing on formulas with no free variables, we can drop talk of assignment functions and just focus on semantic value relative to a temporary quasi-extension X.

Now when it comes to our choice of a permanent quasi-extension, we can start with the simplest case. What we take to be the minimal fixed point. Let X0 be the empty set. Let X1 be the set of sentences that are true relative to the quasi-extension X0. For any ordinal α, let Xα+1 be the set of sentences that are true relative to the quasi-extension Xα. For a limit ordinal λ, let Xλ be the set of sentences that are true relative to some Xβ where β < λ. Now as it turns out, if a sentence is in Xα, it must also be in Xβ for any β > α. This is clear to see once you note our construction has the Monotonicity property. If X is a subset of Y, then every sentence with value 1 relative to X has value 1 relative to Y, and every sentence with value 0 relative to X has value 0 relative to Y. It follows that if Xα is a subset of Xα+1 then Xα+1 must be a subset of Xα+2 and by induction it follows that if Xα is a subset of Xα+1 then for all γ > β ≥ α, Xβ is a subset of Xγ. Since X0 is the empty set, X0 is a subset of X1, so whenever γ > β, Xβ is a subset of Xγ. Since Xα cannot grow indefinitely because of the fixed cardinality of sentences in the language, there must be an ordinal β for which Xβ = Xβ+1. This is the minimal fixed point.

We can say a sentence is true _tout court_ if it’s true in the minimal fixed point, false _tout court_ if it’s false in the minimal fixed point, or neither true nor false if it’s neither true nor false in the minimal fixed point. 

As it turns out, on this construction, any Liar sentence will be assigned neither true nor false and we're given a single non-indexical truth predicate allowing us to avoid the woes of competing for higher subscripts.

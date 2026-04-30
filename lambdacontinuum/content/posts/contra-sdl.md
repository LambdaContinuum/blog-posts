+++
date = '2025-01-23T17:57:25-05:00'
title = 'Contra Standard Deontic Logic'
+++

Bengt Hansson introduced the term Standard Deontic Logic (referred to as SDL from here on) to denote deontic logics characterized by the semantic principle of Ideal Worlds Intersection. This principle posits that there is a subset \(\mathcal{I}\) of the set \(\mathcal{W}\) of possible worlds, such that for all p, \(Op\) holds if and only if \(\forall w \in \mathcal{I}, p \in w\).

\(\mathcal{I}\) represents the set of deontically perfect worlds. Sentences valid in such a model coincide with the sentences derivable from the following axioms:

  1. \(Op \implies \neg O \neg p\),

  2. \(Op \land Oq \iff O(p \land q)\),

  3. \(O(p \lor q)\).

The second axiom is equivalent to the combination of:

  1. \(Op \land Oq \implies O(p \land q)\), i.e. agglomeration.

  2. If \(Op\) and \(p\) logically implies \(q\), then \(Oq\), i.e. necessitation.


Now that we’ve characterized SDL, why do I think it fails to properly model obligation? Consider the following issues.

First is the problem of free choice permission. Imagine your neighbor asked to borrow a crowbar. You showed him your crowbars and said, "You may borrow either the big or the small crowbar." You offer him a choice between two tools. Now imagine the tools belonged to someone else who authorized you to lend one of them, but you had forgotten which of the two could be lent. You might say, "You may borrow either the big or the small crowbar, but I do not know which." In this latter case, only one of the crowbars is permitted to be borrowed. However, the former case illustrates an instance of free choice permission: you are permitted to take the small crowbar, and you are permitted to take the large crowbar (but not both). To represent this in SDL, we want a permission operator that satisfies the postulate \(P(a \lor b) \implies Pa \land Pb\).

Such a principle doesn’t hold in SDL. An obvious solution might be to simply add the principle to the list of SDL axioms. However, this leads to implausible results. Consider the following inference:

\[
    \begin{array}{rll}
        1. & O(\neg a \land \neg b) \implies O \neg a & \text{Holds in SDL} \\
        2. & O \neg (a \lor b) \implies O \neg a & \text{1, Equiv} \\
        3. & \neg O \neg a \implies \neg O \neg (a \lor b) & \text{2, Contrapos} \\
        4. & Pa \implies P(a \lor b) & \text{3, Def. of P} \\
        5. & P(a \lor b) \implies Pa \land Pb & \text{Hyp.} \\
        6. & Pa \implies Pb & \text{4, 5, HS} \\
    \end{array}
\]


The axiom combined with the original postulates entails that if something is permitted, then everything else is permitted. This is intolerable, so we cannot solve the issue of free choice by turning the SDL permission operator into an operator of free choice permission.

Some deontic logicians attempt to fix this by introducing a second permission operator Pc into SDL. One such definition is \(P_c(a \lor b) \iff Pa \land Pb\). This definition is implausible, see the following derivation:

\[
    \begin{array}{rll}
        1. & Pa \implies (P a \lor b) & \text{Holds in SDL} \\
        2. & Pa \implies (Pa \land P(a \lor b)) & \text{1, Adjunction}\\
        3. & Pa \implies P_c(a \lor (a \lor b))& \text{2, Def. of }P_c \\
        3. & Pa \implies P_c(a \lor b) & \text{3, Idempotence} \\
    \end{array}
\]

So, if you’re permitted to borrow a screwdriver, it follows that you have free choice to either borrow or steal the screwdriver. Other attempts to construct free choice operators have similarly absurd consequences. This is because such constructions rely on the _single sentence assumption_; the idea that free choice between a and b can be represented as a property of a single sentence, namely a∨b.

Under this assumption, logically equivalent sentences are interchangeable. Thus, if \(a \lor b\) is equivalent to \(c \lor d\), then there is a free choice permission between a and b if and only if there is a free choice permission between c and d. This entails implausible results. Consider the case of the vegetarian’s free lunch. In a restaurant, I may have a meal with meat or a meal without meat. Therefore, I may either have a meal and pay for it or have a meal and not pay for it. This follows because: Let m denote having a meal with meat, v a meal without meat, and p paying: 

\[
    P(m \lor v) \equiv P(((m \lor v) \land p) \lor ((m \lor v) \land \neg p)).
\]

Free choice permission illustrates an intuitive deontic principle that doesn’t hold in SDL. Conversely, SDL sometimes validates principles that are not plausible. We call such cases deontic paradoxes. Consider Åqvist's knower paradox: If a police officer ought to know that Smith robbed Jones, then Smith ought to rob Jones. This counterexample challenges the principle of necessitation. Von Wright correctly points out that all major deontic paradoxes rely on necessitation. However, necessitation follows from SDL’s semantic construction of possible worlds, so these paradoxes challenge SDL’s semantics itself.

SDL also fails to model certain important kinds of obligations commonly discussed—namely, obligations of compensation, reparation, and prevention. Recall that under SDL’s semantics, obligatory acts in the actual world consist of actions that would occur in ideal worlds. Suppose there’s a drowning child in front of you. In a deontically ideal world, no child would drown, so you wouldn’t save a child from drowning in an ideal world because no drowning child would exist. It follows that you are not obligated to save the drowning child.

Obligations of compensation, reparation, and prevention require the existence of actions that need be compensated, reparated, and prevented. But these are actions that are unideal and wouldn’t occur in an ideal world. Consequently, SDL’s semantics cannot model such obligations. This is a significant problem, as such obligations are central not only to everyday moral discourse but also to moral philosophy as a whole. As Holly Goldman puts it, SDL "ignores the fact that particular obligations flow from abstract principles together with contingent features of the world," and such features "do not appear in all the morally best worlds."

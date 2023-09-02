# Propositions are types, proofs are terms.

This is where the world of type theory seriously diverges from the way things are set up in set theory, and also the way things were set up in my brain up until three years ago. In trying to understand what was going on here, I even realised that mathematicians take some liberties with their language here. Before we start, consider this. The [Bolzano-Weierstrass theorem](https://en.wikipedia.org/wiki/Bolzano%E2%80%93Weierstrass_theorem) is some statement in analysis about a bounded sequence having a convergent subsequence. I want to talk a little bit about how mathematicians use the phrase “Bolzano-Weierstrass theorem” in practice. A mathematician would say that the Bolzano-Weierstrass theorem is this statement about sequences having convergent subsequences. But if they are in the middle of a proof and need to apply it in order to continue with their proof, they say “by the Bolzano-Weierstrass theorem we deduce that there’s a convergent subsequence”. Nothing seems at all funny about any of this. But what I want to point out is that mathematicians are using the phrase “the Bolzano-Weierstrass theorem” in two different ways. When they say what it is, they are referring to the statement of the theorem. But when they say they’re using the Bolzano Weierstrass theorem, what they are actually using is its proof. The Birch and Swinnerton-Dyer conjecture is a perfectly well-formed true/false statement, you can certainly [say what it is](https://www.claymath.org/millennium-problems/birch-and-swinnerton-dyer-conjecture). But you can’t use the Birch and Swinnerton-Dyer conjecture in the middle of a proof of something else if you want your proof to be complete, because at the time of writing the conjecture is an unsolved problem. Making a clear distinction between the statement of a theorem, and the proof of a theorem, is important here. A mathematician might use the phrase “the Bolzano-Weierstrass theorem” to mean either concept. This informal abuse of notation can confuse beginners, because in the below it’s really important to be able to distinguish between a theorem statement, and a theorem proof; they are two very different things.

In the [natural number game](http://wwwf.imperial.ac.uk/~buzzard/xena/natural_number_game/), I use this abuse of notation because I am trying to communicate to mathematicians. The statement `∀ x : ℕ, x + 0 = x` is a true statement, and I say things like “this is called `add_zero` in Lean”. In the natural number game I write statements such as `add_zero : ∀ x : ℕ, x + 0 = x`. But what this means is that the term called `add_zero` in Lean is a proof of `∀ x : ℕ, x + 0 = x`! The colon is being used in the type theory way. I am intentionally vague about this concept in the natural number game. I let mathematicians believe that `add_zero` is somehow equal to the “idea” that $x+0=x$ for all $x$. But what is going on under the hood is that `∀ x : ℕ, x + 0 = x` is a Proposition, which is a type, and `add_zero` is its proof, which is a term. Making a clear distinction between the statement of a theorem, and its proof, is important here. The statements are the types, the proofs are the terms.

* Universe: `Prop`
* Examples of types: `2 + 2 = 4`, `2 + 2 = 37`, the statement of Fermat’s Last Theorem — `∀ x y z : ℕ, n > 2 ∧ x^n + y^n = z^n → x*y = 0`.
* Examples of terms: the proof that `2 + 2 = 4` (a term of type `2 + 2 = 4`), the proof of Fermat’s Last Theorem (a term of type `∀ x y z : ℕ, n > 2 ∧ x^n + y^n = z^n → x*y = 0`)
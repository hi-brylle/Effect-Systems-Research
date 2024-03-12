#paper
Pretnar, Matija. “An Introduction to Algebraic Effects and Handlers. Invited Tutorial Paper.” Electronic Notes in Theoretical Computer Science, vol. 319, Dec. 2015, pp. 19–35. DOI.org (Crossref), https://doi.org/10.1016/j.entcs.2015.12.003.
[https://www.eff-lang.org/handlers-tutorial.pdf](https://www.eff-lang.org/handlers-tutorial.pdf)
- - -
## First-pass summary:
This paper introduces *Eff*, a language with user-defined [effects and handlers](<Effect Systems>). The paper informally shows examples of how effects are given their semantics using handlers. As is typical of programming language research paper, it presents a [type system](<Type Systems>) extended with effect types that provides typing rules for effects and handlers. It also provides a denotational semantics for the underlying theory behind effect handlers (which I don't fully understand yet; I understand operational semantics more in terms of imperative languages). The effect system is powerful and general enough to subsume constructs that are otherwise specialized in present-day mainstream languages. Examples include async-await and lazy evaluation. In the async-await example, an effect is made that yields the execution to some other scheduler to allow for concurrency. In lazy evaluation, computations are wrapped in something called "thunks", which, in lazy languages like Haskell is the norm and is built-in. The generality of effects can emulate all these. The paper also claims that it can emulate monads, the canonical way of doing side-effects in functional languages for the longest time since their inception, but it didn't give examples (which is understandable, just use the effects and the handlers).
- - -
## NSDB:
### Needs:
* A programming language that uses an effect system for reasoning about side-effects.
### Solution:
* An implementation of a programming language with effects and handlers that give meaning to those effects.
* A powerful effect system that can generalize over specialized constructs in other languages such as async-await and lazy evaluation.
### Differentiation:
* A programming language that doesn't use monads for doing side-effects (although it mentions that the language can emulate them, too).
* Needs a runtime interpreter (which is the language it is written in: OCaml).
### Gaps:
* [I find the composability of effect handlers to be convoluted](<Effect composition is messy>).
#paper
Bauer, Andrej, and Matija Pretnar. “Programming with Algebraic Effects and Handlers.” _Journal of Logical and Algebraic Methods in Programming_, vol. 84, no. 1, Jan. 2015, pp. 108–23. _DOI.org (Crossref)_, https://doi.org/10.1016/j.jlamp.2014.02.001.
https://arxiv.org/pdf/1203.1539.pdf
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
- - -
## Further notes:
* Eff features default handlers that it calls resources. This definitely puts my problem statement in question now that default handlers exist anyway (and that I find user-defined handlers to be difficult to read). The paper, however, doesn't expound on resources and that might be worth looking into.
* The Eff compiler distinguishes expressions from computations. Constants, booleans, variables, instantiations of sum types, function declarations are considered as expressions. On the other hand, computations encompass a lot more cases. For example, an integer expression added to another integer expression is still considered a computation despite both expressions possibly being 'pure computations' in the functional programming sense, i.e., they don't have side effects. For me, this consideration of otherwise pure computations as "side-effectful computation" feels too fine-grained but the paper claims it helps to treat such computations uniformly.
* Eff effect types are types. Standard types have values or instantiations, for example, for the `boolean` type, there is `true` or `false` as value. Similarly, effect types have instances and in Eff, they are instantiated with `new E` for whatever effect type `E`.
* Resources are default handlers for effects. Effect instances still need to associate themselves with resources and if they don't, a runtime error occurs, similar to when a program crashes when `Exception`-throwing functions aren't put inside `try`/`catch` blocks in mainstream languages.
* Resources are a way for Eff programs to interact with the real world, e.g., state management (working with heap memory is pretty much well understood, and it's just a few operations of allocating, reading and writing to RAM anyway).
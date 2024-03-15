#paper
Leijen, Daan. “Type Directed Compilation of Row-Typed Algebraic Effects.” ACM SIGPLAN Notices, vol. 52, no. 1, May 2017, pp. 486–99. DOI.org (Crossref), https://doi.org/10.1145/3093333.3009872.
[https://www.microsoft.com/en-us/research/wp-content/uploads/2016/08/algeff-tr-2016-1.pdf](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/08/algeff-tr-2016-1.pdf)
- - -
## First-pass summary:
This paper introduces *Koka*, a compiled language with [user-defined effects and handlers](<Effect Systems>). As usual with these effect systems research PLs, this paper provides examples of how specialized control-flow constructs in other languages can be generalized using effect handlers. What is not mentioned in the [Eff paper](<Programming with Algebraic Effects and Handlers>), however, is this paper's example of how handlers can generalize iterators (but internally, it uses the same concept of 'yielding' computation). Also, something new compared to the Eff paper is the choice of compiling the language (and the techniques it entails) to some other runtime, e.g., NodeJS, .NET, JVM, etc., as Eff is implemented as a language that is interpreted by OCaml. Another difference is that the paper chose to define Koka's operational semantics than denotational semantics. The only similarity with the Eff paper is the extension of a type system with effects. It then proved a soundness theorem to make sure that any syntactically valid Koka program can never go wrong (semantically speaking) in the perspective of its type and effect system. 
- - -
## NSDB:
### Needs:
* Yet another programming language that uses an effect system for reasoning about side-effects.
### Solution:
* An implementation of a programming language with effects and handlers that give meaning to those effects.
* A powerful effect system that can generalize over specialized constructs in other languages.
* A type-and-effect system that is proven to be sound.
### Differentiation:
* Another programming language that doesn't use monads for doing side-effects.
* Unlike the [Eff paper](<Programming with Algebraic Effects and Handlers>), this paper mentions how its effects can subsume a special construct called iterators.
* This paper details a compilation strategy to existing runtime environments, e.g., .NET, NodeJS, etc.
### Gaps:
* [I find the composability of effect handlers to be convoluted](<Effect composition is messy>).
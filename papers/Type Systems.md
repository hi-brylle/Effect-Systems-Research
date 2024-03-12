---

---
#paper
Cardelli, Luca. “Type Systems.” _ACM Computing Surveys_, vol. 28, no. 1, Mar. 1996, pp. 263–64. _[DOI.org](http://DOI.org) (Crossref)_, [https://doi.org/10.1145/234313.234418](https://doi.org/10.1145/234313.234418).
[http://lucacardelli.name/papers/typesystems.pdf](http://lucacardelli.name/papers/typesystems.pdf)
- - - 
## First-pass summary:
This paper categorizes the different kinds of type systems: static (compile-time type checking), dynamic (run-time type checking), strong (no type coercions allowed), weak (type coercions allowed). The rest of the paper introduces how programming language features such as record types, polymorphism, subtyping, type inference are formalized through the language of inference rules. Finally, the paper introduces the point of all these formalizations of type systems: to prove a soundness theorem for every type system so it is able to guarantee that well-typed programs cannot go wrong.
- - - 
## NSDB:
### Needs:
* A good starting resource on the practical applications of and theory behind type systems.
### Solution:
* A categorization of programming languages in terms of type safety and when type-checking is down (either compile-time or run-time).
* An introduction and explanation to the notation of inference rules.
* Fundamental examples of various basic (but extendable) type systems.
* Points to resources for further reading about soundness theorems.
### Differentiation:
* Paper purposely omits type-checking algorithms (I don't consider this a gap).
### Benefits:
* Good introductory resource on how to read type system notation.
* It has a glossary of common type systems terminology as well.
- - -
## Further notes:
* $\Gamma$ (gamma) is the typing environment. Think of it as a set of ordered pairs $\Braket{x: \tau}$ where x is a variable and $\tau$ (tau) is its type. The paper mentions a judgment $\Gamma \vdash A$ which reads as “type A is a valid type in $\Gamma$”. I used to think that this means that $A$ exists in the set $\Gamma$ but this is wrong. The correct interpretation is that $A$ is constructed properly in whatever type system currently being studied. The construction can be of some ‘base’ case where $A$ is already some basic type or $A$ is inductively constructed using type constructors (think struct types, product types, sum types, etc.).

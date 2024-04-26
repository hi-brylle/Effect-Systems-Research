#paper 
Madsen, Magnus. “The Principles of the Flix Programming Language.” _Proceedings of the 2022 ACM SIGPLAN International Symposium on New Ideas, New Paradigms, and Reflections on Programming and Software_, ACM, 2022, pp. 112–27. _DOI.org (Crossref)_, https://doi.org/10.1145/3563835.3567661.
https://dl.acm.org/doi/pdf/10.1145/3563835.3567661
- - -
## First-pass summary
This paper documents the design principles of the Flix programming language, a functional-first programming language with a [polymorphic](<Polymorphism>) type-and-effect system. It is unlike the other languages seen so far because its effect system is purely syntactic, i.e., functions with effect annotations must be side-effectful and functions with no effect annotations must be side-effect-free and that's it; it doesn't user-defined handlers for the effect system to work because it behaves like a syntax-only extension of the typechecking. The paper is an innovation itself and it recognizes that most other papers in PL research start with the abstract syntax tree grammar, followed by the corresponding extended lambda calculus, its semantics and proof of soundness. The paper is much more accessible for programmers by first laying out the vision of the creators for the language instead of going straight into implementation detail (which is found in another paper). The paper acknowledges other languages with effect systems with user-defined handlers and distinguishes Flix from the rest of them.
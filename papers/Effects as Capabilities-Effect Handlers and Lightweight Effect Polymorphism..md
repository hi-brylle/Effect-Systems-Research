#paper
Brachthäuser, Jonathan Immanuel, et al. “Effects as Capabilities: Effect Handlers and Lightweight Effect Polymorphism.” _Proceedings of the ACM on Programming Languages_, vol. 4, no. OOPSLA, Nov. 2020, pp. 1–30. _DOI.org (Crossref)_, https://doi.org/10.1145/3428194.
https://dl.acm.org/doi/pdf/10.1145/3428194
- - -
## First-pass summary:
This paper introduces *Effekt*, another language with an [effect system](<Effect Systems>) but with a new perspective on effects: instead of the usual "effects express side-effects of computation", it re-interprets effects as "the capabilities a computation requires from its context". In this interpretation of effects, they become some explicit dependency that the function needs from its caller. A function with no effects is what the paper calls *contextually pure*, i.e., the function is standalone and doesn't need further context. It notes, however that contextual purity is not the same as function purity in the traditional sense. In this interpretation, if a function handles its own side-effects, its signature doesn't need to contain effect types. I find this novelty a relief, because in my time reading the [Eff](<Programming with Algebraic Effects and Handlers>) and [Koka](<Koka-Programming with Row-polymorphic Effect Types>) [papers](<Type Directed Compilation of Row-typed Algebraic Effects>), from a programmer perspective, the readability of the code suffers when there's too much composition happening. Eff and Koka mitigates this somehow using [effect inference](<Type Inference>) but comprehending examples is still too difficult and the control flow is lost on me. This paper, however, has a downside: it purposely set its functions to be second-class. The paper claims making functions second-class helped simplify the implementation as they no longer had to worry about implementing polymorphism (and I do believe them) but first-class functions is something I can no longer live without in modern software development. There's also the usual showcase of a type-and-effect system with a corresponding soundness theorem.
- - -
## NSDB:
### Needs:
* Yet another programming language that uses an effect system for reasoning about side-effects but views it from a radically different viewpoint: effects become requirements for the callers of functions.
### Solution:
* An implementation of a programming language with effects but it re-interprets effects in a different way compared to [Eff](<Programming with Algebraic Effects and Handlers>) and [Koka](<Koka-Programming with Row-polymorphic Effect Types>).
### Differentiation:
* The programming language now has two notions of purity: function purity ($A \rightarrow B$) and contextual purity ($A \rightarrow B /\{\}$). Contextual purity doesn't mean the function doesn't do side-effects, it still can, but it essentially means 'yes as a function I do side-effects but I can handle it', e.g., local mutable state.
* Unlike Eff and Koka, the creators of Effekt didn't need to implement complex solutions to do effect inference and effect polymorphism.
### Gap:
* To simplify the implementation of the programming language, the creators had to downgrade functions to be second-class.
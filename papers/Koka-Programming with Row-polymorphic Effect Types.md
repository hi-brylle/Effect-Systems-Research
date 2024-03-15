#paper
Leijen, Daan. “Koka: Programming with Row Polymorphic Effect Types.” Electronic Proceedings in Theoretical Computer Science, vol. 153, June 2014, pp. 100–26. arXiv.org, https://doi.org/10.4204/EPTCS.153.8.
[https://arxiv.org/pdf/1406.2061.pdf](https://arxiv.org/pdf/1406.2061.pdf)
- - - 
## First-pass summary:
This paper starts with a gentler and more informal introduction to [effect systems](<Effect Systems>) with the language *Koka*. It doesn't put an emphasis on possible user-defined effects but rather provides an analog to basic types in typical programming languages (int, bool, char, etc.) in the form of basis effects (exceptions, divergence, i/o, etc.); these basis effects can be extended later on. The pattern is apparent now with these effect systems PL papers: (1) craft the syntax of the core language separating effect-free values from effectful computations, (2) mention a [polymorphic](<Polymorphism>) [type system](<Type Systems>), and extend it with effect types, (3) prove a soundness theorem of the type system extended with effects so programs don't go wrong. This paper goes beyond and also implements [effect inference](<Type Inference>) on top of type inference. Type and effect polymorphism is what the paper claims to be a major source of complication for the implementation of the language. For this cause, it mentions how other languages with effect systems have tackled the difficulty of implementing polymorphism in an effect system. This paper is unique among the others I have seen because it mentions a practical application of the language it showcases: [Madoko](<Madoko-Scholarly Documents for the Web>) is a Markdown processor for scholarly publications written in Koka itself.
- - -
## NSDB:
### Needs:
* Yet another programming language that uses an effect system for reasoning about side-effects.
### Solution:
* An implementation of a programming language with effects and handlers that give meaning to those effects.
* A powerful effect system that can generalize over specialized constructs in other languages.
* A type-and-effect system that is proven to be sound.
### Differentiation:
* An actual application was made in this language (but when I looked up its repo in GitHub, most side-effects are just I/O and exceptions; I didn't see complex effect types like in the paper).
### Gaps:
* While there is an actual application written in this programming language, the application doesn't fully exercise the capabilities of the effect system the language has.
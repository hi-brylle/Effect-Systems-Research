#gaps
Function composition is clean and concise. Imagine the following functions:
$$
f: A \rightarrow B
$$
$$
g: B \rightarrow C
$$
$$
h: C \rightarrow D
$$
Composing the following functions in some `main` program that takes input of type `A` to type `D` would be as simple as (with `x` having a type of `A` as input to `f`):
$$
main: A \rightarrow D = h(g(f(x: A)))
$$
Look at the final type signature of `main`: $A \rightarrow D$. This is short and concise.

Effect composition is a much harder problem to solve, because effect types 'bubble' up the call stack. In a function that throws an exception (in a typical programming language), the error must be caught somewhere in the chain of functions that called the throwing function. In languages with effect systems, a handler must be provided to handle the error thrown.

Other handlers must also be implemented for the many other effect types. A question here is: how do you properly assign a type to a complex function that contains smaller functions that themselves do side-effects?

In [Koka](<Koka-Programming with Row-polymorphic Effect Types>), the language simply piles up all the effect types as a list on the topmost function. Consider a fibonacci function that memoizes its results, its type signature would be:
$$
fib: (n: int) \rightarrow \langle alloc \langle h \rangle, read \langle h \rangle, write \langle h \rangle \rangle \ int
$$
It has all the effect types for working with heap memory as it allocates, reads, and writes to memory when it is doing memoizations and computations.

In [Eff](<Programming with Algebraic Effects and Handlers>), the language only needs the programmer to add type and effect annotations to the handlers but a cursory glances on the examples give the feeling that control flow becomes obscured. This is an example taken from the paper for the async-await effect:
![[Pasted image 20240312232444.png]]

In [Effekt](<Effects as Capabilities-Effect Handlers and Lightweight Effect Polymorphism.>), the piling up of effect types in the signature is mitigated because in Effekt, effects are considered as requirements for the calling context of a function. Imagine an outer function that contains one side-effectful function and another pure function. If the side-effectful function can handle its own side-effects, the outer function need not show an effect type in its signature (but since it is not pure by virtue of having ran a side-effectful function inside it, the effect type would simply be `{}`).
#concept
Effects represent computations with side-effects. In a language or library with effects, syntactically, effects are tags to functions that do side-effects in them. While types annotate values and pure functions, effects annotate side-effectful (or impure) functions (alongside the return type).

Effects are just syntax. What gives them semantics are called algebraic effect handlers or simply, [handlers](Handlers.md). A good starting example would be typical exceptions. The information of possibly throwing errors inside functions doesn't manifest itself in the function signature in mainstream languages. Effect types do manifest this information. Also in typical languages, throwing an error must be caught in some `try`/`catch` block. Effect handlers are like `try`/`catch`, except, they don't just catch exceptions; they do so much more and can be user-defined.

Here's a non-exhaustive list of effects:
* Input-output
* State
* Non-determinism
* Exceptions
* Async-await
* Iterators
#concept
The [Type Systems paper](<Type Systems>) defines polymorphism as "the ability of a program fragment to have multiple types". In the context of our research, this refers to parametric type polymorphism (and by extension, effect polymorphism). Parametric type polymorphism refers to the use of a generic type in functions that are meant to be generic among any type.

Consider the following code in some hypothetical language:

```
\\ a' is a symbol that says "any type can be put here"
let sort = (items: Array<a'>, compare_fn: (item_a: a', item_b: a') -> int) -> Array<a'> { ... }
```
This `sort` function takes in an array of whatever `a'` type and a binary `compare_fn` function that compares two items of the same `a'` type so that the `sort` function can figure out the total ordering of the items by the end. It returns an array of `a'` type (that is now sorted, whether done in-place or as a persistent data structure, it doesn't matter).

An example of effect polymorphism in Koka is a map function whose function parameter might do a side-effect.
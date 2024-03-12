#concept
Handlers are constructs that provide meaning to the effects.

In Eff, handlers look like the following exception handler example:
```
let optionalize e = handler
| e#raise _ _ -> None
| val x -> Some x
```
In Eff, this means to catch the error `e` and either
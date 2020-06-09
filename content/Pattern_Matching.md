# Pattern Matching

the following function trys to get the first value from a supplied list.
it protects your code from failing with errors by always returning an option
type that contains either the first value in the list or none.

```fs
// tryFirst     - takes a list of strings, and returns the first value as an option
//
// Some value   - returns just the value.
// None         - returns the default value
//
// note the use of the :: cons keyword
let tryFirst (items:string list) =
    match items with
    | [] -> None
    | f :: _ -> Some f


// testing
> tryFirst [];;
val it : string option = None

> tryFirst ["apples"];;
val it : string option = Some "apples"

> tryFirst ["apples", "oranges"];;
val it : string option = Some "apples"
```

## How to handle a value of Option type

the following function unwraps an option type to return just the value
or return a default value when the option equals none.

```fs
// firstOrDefault   - takes a default value, and a list of strings
//                    then matches on the first item in the list
//
// Some value       - returns just the value.
// None             - returns the default value
let firstOrDefault def (items:string list) =
    match tryFirst items with
    | Some v -> v
    | None -> def


// testing
> firstOrDefault "nothing!" [];;
val it : string = "nothing!"

> firstOrDefault "nothing!" ["apples"];;
val it : string = "apples"
```

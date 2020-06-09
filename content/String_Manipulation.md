# String Manipulation

The list of function is available at above mentioned MSDN link. But here we’ll try to play a little with those function to understand what those functions actually do.

```
collect     : (char -> string) -> string -> string
concat      : string ->seq<string> -> string
exists      : (char -> bool) -> string -> bool
forall      : (char -> bool) -> string -> bool
init        : int -> (int -> string) -> string
iter        : (char -> unit) -> string -> unit
iteri       : (int -> char -> unit) -> string -> unit
length      : string ->int
map         : (char -> char) -> string -> string
mapi        : (int -> char -> char) -> string -> string
replicate   : int -> string -> string
```


# collect

Builds a new string whose characters are the results of applying a specified function to each of the characters of the input string and concatenating the resulting strings.
```fsharp

let collectTesting inputS = String.collect(fun c -> sprintf "%c# " c) inputS  

printfn "%s" (collectTesting"CFJ") 

// Output:

C# F# J#
```

# concat

Returns a new string made by concatenating the given strings with a separator.
```fsharp

let arr = [| "Sunday"; "Monday"; "Tuesday"; |]  
  
let concatPlay = String.concat " comes after " arr  

// Output:

val concatPlay : string = "Sunday comes after Monday comes after Tuesday"

```


# exists

Tests if any character of the string satisfies the given predicate.
```fsharp

let containsUppercase string1 =  
    if ( String.exists(fun c -> System.Char.IsUpper(c)) string1 ) then  
        printfn"The string \"%s\" contains uppercase characters." string1  
    else  
        printfn"The string \"%s\" does not contain uppercase characters." string1  
        containsUppercase "Hello World!"  
        containsUppercase "no"  

// Output:

The string "Hello World!" contains uppercase characters.
The string "no" does not contain uppercase characters.

```


# forall

```fsharp

let isValidName string1 =  
    if (String.forall (fun c ->System.Char.IsLetter(c)) string1) then  
        printfn "The string \"%s\" is a valid name." string1  
    else  
        printfn "The string \"%s\" is not a valid name." string1  
        isValidName "Amit"  
        isValidName "Amit25"  

// Output:

The string "Amit" is a valid name.
The string "Amit25" is not a valid name.

```


# Init

Creates a new string whose characters are the results of applying a specified function to each index and concatenating the resulting strings.
```fsharp

let string1 = String.init 10 (fun i -> i.ToString())  
printfn"%s" string1 

let string2 = String.init 26 (fun i -> sprintf "%c" (char (i + int'A')))  
printfn"%s" string2  

// Output:

0123456789
ABCDEFGHIJKLMNOPQRSTUVWXYZ

```


# iter

Applies a specified function to each character in a string.
```fsharp

letprintCharacterssourceString = String.iter(fun c ->printfn"%c" c) sourceString  
printCharacters "Happy New Year!!"  

// Output:

H
a
p
p
y

N
e
w

Y
e
a
r
!
!

```

Similarly there are below functions which takes lambda expressions(anonymous function) and applies on each character of given input.


# map:

Creates a new string whose characters are the results of applying a specified function to each of the characters of the input string.


# iteri and mapi

iteri function applies a specified function to the index of each character in the string and the character itself and returns unit.

mapi function creates a new string whose characters are the results of applying a specified function to each character and index of the input string.

e.g.
```fsharp

let enumerateCharactersinputString =   
String.iteri (funi c ->printfn"%d %c"i c) inputString  

enumerateCharacters "TIME"  
enumerateCharacters "SPACE" 

// Output:

Index Unit

0 T
1 I
2 M
3 E

0 S
1 P
2 A
3 C
4 E

```

# replicate

```fsharp

printfn "%s" <| String.replicate 10 "<>"  

// Output:

<><><><><><><><><><>

```

# length

Returns the length of the string.

The sample included with each string library function are simplified as it’s a beginner level post. In upcoming posts we’ll see more complex examples with function piping, pattern matching etc.
 
Read more articles on F#:

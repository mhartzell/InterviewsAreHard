[<< Back to F#](index.md)

# Quick Syntax
A quick overview of the F# syntax.

| Token | Description |
| ----- | ----------- |
| (indent) | Determines block scoping (there are no curly braces) |
| (space) | Used to separate parameters (there are no commas) |
| `//` | Single-line comment |
| `let` | Binds an immutable value, expression or function to an identifier (types are inferred) |
| `[]` | Creates a new list |
| `;` | Delimits values (i.e. `let myList = [1;2;3]`), and does not end statements! |
| `..` | Creates a range (i.e. `let myList = [1..100]`) |
| `@` | Concats two lists together |
| `::` | Separates a list into its first element and everything else |
| `( )` | Clarify precedence of execution |
| `|>` | Pipe the result of one operation to the input of another |
| `fun` | Define lambdas, or use for verbose function declaration syntax |
| `rec` | Specifies a function as recursive |
| `->` | Lambda operator |
| (Implicit returns) | Functions always return the last expression specified |
| `match..with` | Pattern matching, similar to case statements |
| `|` | Specifies a case / match in a pattern matching expression |
| `_` | Matches anything |
| `Some(x)` | Analogous to a nullable wrapper |
| `None` | A null value |
| `1,2,"A string"` | A tuple |
| `type` | Defines a new type |
| `printf` | Simliar to `Console.Write` |
| `printfn` | Similar to `Console.WriteLine` |
| `open` | Same as the C# `using` statement |

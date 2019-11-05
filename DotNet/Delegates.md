[<< Back to .NET](index.md)

# Delegates
Delegates define a type that specifies a specific method signature.  Any method with the same signature can be assigned to the delegate and executed when the delegate is invoked.  There are three short-hand delegate types provided by .NET:

- `Action<>` - used when there is a need to perform an action using delegate arguments
- `Func<>` - used when you need to transform delegate arguments into a different result set
- `Predicate<>` - used to determine if the argument satisfies the condition of the delegate (also `Func<T, bool>`)

You do not always need to strictly define a delegate.  Anonymous delegates allow delegates to be defined and used “inline”.   This syntax is refined even further with lambda functions, which declare a signature and a method body in quick syntax. 

`=>` is the lambda operator, which is read as “goes to”.  Lambdas allow you to write local functions that can be passed as arguments or returned as the value of function calls.

- Expression lambda - (input-parameters) => expression
- Statement lambda - (input-parameters) => { statement; }

Statement lambdas do not create expression trees.

When writing lambdas, you often do not have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter’s delegate type, and other factors.  However, you can also explicitly declare the type of input parameters in the lambda function declaration.

Lambdas create delegates or expression trees, depending on how they are used.  When a lambda expression is assigned to a variable, field, or parameter whose type is delegate, the compiler emits IL that is identical to that of an anonymous method.  When the lambda is assigned a type of Expression<T>, the compiler emits an expression tree.
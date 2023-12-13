1 = 1 (Casting)
For this.. the important part is I modified classC definition. It now stores all the parent classes including #'Object, this way I don't have to traverse the whole tree to see if an object is an instance of particular class (or subclass).

2 = 2 (Covariant and Contravariant)
When a subclass overrides a method in a superclass, the compiler must check that the overriding method has the right type. While some languages require that the type exactly matches the type in the superclass (invariance), it is also type safe to allow the overriding method to have a "better" type. By the usual subtyping rule for function types, this means that the overriding method should return a more specific type (return type covariance), and accept a more general argument (parameter type contravariance).

The checkoverride function was currently checking if the return types and method arguments match exactly. So, I got rid of them and allowed subclass method to override the return type and also allowed subclass method to override the method argument types.

3 = 2 (If statement)


4 = 2 (private)

8 = 2 (null)

7 = 2 (Functional update test.. don't have)

9 = 2 (Constructors)
For this, I again modified classC definition. My constructor doesn't take any arguments but it can process a list of expressions which I implemented by implementing begin. 
-----
5 = 13
-----

1 = 1 (Casting)
For this.. the important part is I modified classC definition. It now stores (how this happens? When I flatten_class.. the list grows) all the parent classes including #'Object, this way I don't have to traverse the whole tree to see if an object is an instance of particular class (or subclass).

2 = 2 (Covariant and Contravariant)
When a subclass overrides a method in a superclass, the compiler must check that the overriding method has the right type. While some languages require that the type exactly matches the type in the superclass (invariance), it is also type safe to allow the overriding method to have a "better" type. By the usual subtyping rule for function types, this means that the overriding method should return a more specific type (return type covariance), and accept a more general argument (parameter type contravariance).

The checkoverride function was currently checking if the return types and method arguments match exactly. So, for each method argument and result I created a supertype and checked if that supertype is a subtype of argument and result of the method that we are currently dealing with.

3 = 2 (If statement)
So, for this.. checking if the test part is integer was easy. For the then and else part.. I created a helper function that took t1 and t2 and decided that would give me supertype. And I checked whether the supertype I got is subtype of the then and else branches. 

4 = 2 (private).. my private methods can't be inherited and/or overridden (did nothing for this.. :D)
For this.. I changed the class definition now to include the word private infront of method. To make sure, the function is only exectued from this expression, I passed obj_exp along the call_method function which checked before function invocation.. if the obj_exp has this.. if it has.. then the call_method looked for all the methods (private and public) otherwise.. it only searches for the public ones.

7 = 2 (SET... Functional update test.. don't have)
Added a setE expression for this. And modified vield value implementation as Listof(Boxof(Value)) type now. Also, my constructor leverage this too to initialize fields with certain thing at first and update it later on. I've also made sure the setting is only done by checking if the value is the subtype of the field where we are trying to add the value. 

8 = 2 (null)
The getI and sendI already only accepted the field access and method access when the expression it received was a valid object (nothing like null would work in this instance). But I modified is_subtype to allow null to be added as non-integer method argument. 

9 = 2 (Constructors)
For this, I again modified classC definition. My constructor doesn't take any arguments (when I realized.. I can do this too.. it was 1PM already) but it can process a list of expressions which I implemented by implementing begin. 
-----
5 = 13
-----

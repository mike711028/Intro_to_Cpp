# Function Parameters
**A function can accept values that will be used in the statements in the function body**.  
These values are known as **arguments** when passed to a function.  The arguments are passed 
into parameters.  Parameters are the placeholders that are found inside the parentheses of 
a function declaration, as shown in the following example where a and b are the parameters. 
Note that the data types for these are specified and that the parameters are separated by a comma.
```cpp
int Sum(int a, int b)
{
     return a + b;
}
```
Your function can specify as many parameters as necessary for the function to complete
its work but for obvious reasons, you don't want to create a function signature that is so long,
your code line wraps.  If your function takes that many parameters, it's worth refactoring it
to reduce the number of parameters.

When calling the function, you use the function name, followed by an open parenthesis,
the arguments that will be passed into the parameters, and then a closing parenthesis, as shown here:
```cpp
int result = Sum(2, 3);
```
Note that you don't have to include the data type specifiers for the arguments
being passed in **but you must know the data type the function expects.  This is one of
the reasons for declaring a function prototype prior to using it in code.**

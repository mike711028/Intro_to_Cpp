# Function Prototypes

When declaring a function, you specify its storage class, return type, name, and parameters.
Some refer to this as the function signature.  In C++ it is also called a function prototype. 

In C++, function prototypes belong in header files.  Recall that the header file is what gets
imported into other source code files so that the compiler can track proper use of functions 
and other aspects of the included files.  The function prototype only contains the function's signature
with no implementation details.  The implementation details along with the function signature,
define the function.  The function definition exists in the source code file (.cpp).

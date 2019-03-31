# Inline Functions
One of the goals for using functions in your code is to create discrete pieces of functionality
in your code that is easier to test and maintain.  **However, functions also have an impact
on application performance.  The reason for this impact results from the operations that must
be performed when a function is called**.  For example, registers in the CPU need to be reset,
stack pointers are created, memory is consumed for these pointers and the values that are 
passed into and out of the function.    **For simple functions that may perform only a single 
operation or have only a single, simple statement, you might wonder why creating a function 
for it is worth the effort.**

You can still make use of a function to perform the necessary computation but it makes more 
sense to create the function as an inline function.  **Inline functions avoid _the overhead_
associated with traditional function calls.**  You create an inline function by prefixing 
it with the inline keyword.  A common function found in applications for a sorting algorithm
such as bubble sort, is a swap function.  Swap takes two variables and swaps their values as shown here:
```cpp
inline void swap(int & a, int & b)
{
     int temp = a;
     a = b;
     b = temp;
}
```
**Using this mechanism, each time that a call to the swap() method is encountered in your code, 
the compiler will _insert_ the body of the function in that location as opposed to making a function call.**
This example demonstrates what that would look like.
```cpp
// Traditional method that results in a function call
swap(5, 6);

// Using an inline function call, the compiler converts the previous line to this
int temp = a;
a = b;
b = temp;
```
**This avoids the overhead of making a function call because the contents of the function body 
_are now located at the point_ where the functionality is required.**  
Note a couple of points about inline functions:
   + the inline keyword is a compiler directive that is a recommendation only.  The compiler may ignore 
     your request and compile the function normally resulting in function calls anyway.
   + if you are using inline functions and change the function in anyway, the code needs to be recompiled
     because the code for that function will need to be updated in each location it was used.
   + use inline functions only for small functions that are used frequently, not for large functions.

# Introduction to Functions

Functions are a component of a programming language that permit you to break down 
the behavior of an application into discreet pieces of functionality, hence the name function. 
A function is essentially a block of C++ code that you give a name and then call from other 
locations in your application, when you want the computer to perform the instructions contained in that function.

You create a function by defining it.  The function definition may contain a return type,
a function name, parameters to accept incoming arguments, and finally a body which contains 
the code that will execute as part of that function.  **Functions may or may not return a value
back to the caller and they may or may not accept arguments passed in to the function**.
```cpp
int Sum(int x, int y)
{
     return x + y;
}

int Sum(int x, int y, int z)
{
     return x + y + z;
}
```
The compiler will know which function to call, based on the number of arguments passed in.

   + "Don't repeat yourself"
   + Twenty line of code with a name makes more sense
   + Even better if you don't have to write it
   + Function are strongly typed too
      + Parameters
      + Return type
   + Can be overloaded
      + Different parameters
   + Compiler must know about a function before you call it

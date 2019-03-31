# Storage Classes and Scope
MSDN defines *storage class(儲存類別)* as, "A storage class in the context of C++ variable declarations is 
a type specifier that **governs the lifetime, linkage, and memory location of objects**."

**Lifetime** refers to how long the variable "hangs around" in memory from the point at which it is declared 
and the point at which it is destroyed (the memory it used is released).  For the most part, once a variable
goes out of scope, its memory will be released back to the operating system for reuse.

**Linkage** refers to the visibility of a variable **outside of the file that contains it**. 

**Memory location** refers to the place in which the variable is found in memory.  This doesn't refer to
the physical memory address as you might expect but more to the logical division of memory that applies to 
a running application.  **There are two logical memory areas known as the stack and the heap**.  **The stack** is 
a location in memory where intrinsic data is stored as well as memory addresses (pointers).  It operates in 
the form of data structure known as a stack.  Like a cafeteria stack of plates, items are pushed on top 
of the stack and other items are pushed further down.  To remove an item from the stack, it is popped off,
used, and discarded.

**The heap**, or free store, is **a pool of memory** that is used to store objects that dynamically allocated 
at run time by your application.  An object is what you will learn about in the next topic on object-oriented programming.
You create and destroy objects on the heap by using specific instructions in your program code.

**Scope** is the term used describe where an identifier is visible in a program.  **An identifier is a variable, 
constant, class, etc**.  Your identifier is visible from the point in which you have declared it until 
the end of its scope.  The following code sample displays different scope for the identifiers used.
```cpp
1.#include <iostream>
2. int main()
3. {
4.     int total = 0;
5.     for(int i = 1; i <= 10; i++)
6.     {
7.          total += i;
8.     }
9.     std::cout << "The sum of the numbers 1 to 10 is " << total << std::endl;
10.    std::cout << "Current value of i is " << i << std::cout;
11. return 0;
12. }
```
In the previous code, the variable ```total``` is declared inside ```main()``` but outside of the for loop. 
This means that ```total``` is **visible (in scope)** for the entire ```main()``` method, which also includes
inside the for loop.  However, the variable ```i``` is declared inside the for loop's initialization
section and is therefore constrained to the scope of the for loop.   **The code at line 10 will result in
an error in C++ that indicates the variable is undefined**.    Anyplace other than inside the for loop 
is out of scope for the variable ```i```.

C++ makes use of the following keywords that apply to storage classes:
   + **static** - identifiers declared with static are allocated when the program starts and deallocated
     when the program execution ends.  Declaring a variable as static in a function means that 
     the variable will retain its value between calls to the function.
   + **extern** - used to declare an object that is defined in another translation unit of within 
     the enclosing scope but has an external linkage.
   + **thread_local** - declares that the identifier is only accessible on the thread in which it is created. 
     This prevents sharing of the identifier across multiple threads in the same application. This is part of the C++11 standard.

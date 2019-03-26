# Lesson 4 : Const
* const tells the compiler you won't try to change something
   * And the compiler will enfore this
* Using const correctly improves correctness
   * Save you from errors of thought
   * Allow optimizations at **compile time**
* Get const right from the beginning - very hard to add later
* Use const everywhere you can


```c++
#include <iostream>

int main()
{

	int i = 4;
	// both declarations are available
	const int j = 6;
	int const k = 6;

	// because j can not be modify, the compiler shows error message
	j = j + 2;
	// i is fine
	i = j + 2;
	
	// **because k can not be modify, the compiler shows error message**
	k = 7;
	// i is fine
	i = 7;

	return 0;
}


```

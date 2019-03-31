# Class Initialization
Initialization is an important part of working with your classes in C++. 
Even when using intrinsic data types, **if you do not initialize the variable for that type
and you access it in your code, you will end up with whatever values are stored in the memory location
that the variable refers to**.  This is something you want to avoid doing.  
You should always initialize your types in C++;

C++ offers a couple of options for initializing your classes.  You can initialize the member
variables by using the dot operator and setting the values explicitly or you can include
a constructor in your class that is responsible for initialization the member variables.  
You'll see this in the demo video next as well as more information in the topic on encapsulation.
```cpp
#include <iostream>

class rectangle
{
public:
	int width;
	int height;
};

	int main()
	{ 
		// don't uninitialize, please make sure you initialize all of your local variables
		rectangle small_rec; // uninitialized variable, may have garbage value in it

		rectangle big_rec = { 3, 4 }; // initialize big_rec with 3 for width, 4 for height

		small_rec.width = 3;      // initialize individually
		small_rec.height = 4;     // initialize individually

		rectangle mid_rec = {}  // initialize with all 0  ( width = 0, height = 0;

	}
  ```
constructor 在後面會講到

# Lesson 1 : types

+ C++ is strongly typed
+ Fundamental types
+ Casting (changing type)

```cpp
#include <iostream>

int main()
{
	// i = 3434458490; random variable
	// before assigning i, there would be some random variable in memory
	// int can only store integer
	int i = 2;
	// it will be truncated, if you store decimal
	// 3.2 > 3
	i = 3.2;
	// 2.9 > 2
	i = 2.9;
	// you won't get any error messenge for truncation
	i = -1;

	// most situations should avoid using unsigned int
	// should use integer
	unsigned int u = 0;
	// it will not store -2 rather than other thing
	// still won't get any error messenge
	u = -2;

	// we all use double instead of float
	double d = 2.7;
	// i is integer, d is double, integer can't present decimal
	// d assigns to i, and i will happen truncation
	i = d;
	// i = 2;   
	d = i;
	// d can present i 
	// d = 2; 


	// bool presents true or false
	bool flag = true;
	flag = false;
	// you can assign integer or other numeric values to a Boolean
	// 0 is false, the others is true
	flag = 7;

	return 0;

}
```

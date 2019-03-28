# Type Conversions
**Casting** refers to converting one data type to another. Some data conversions are not possible
while some are possible but result in data loss. **C++ can perform many conversions automatically**, 
what is known as **implicit casting** or **implicit conversion**. For example,
attempting to convert a smaller data type to larger data type as shown here:
```cpp
int myInt = 12;
long myLong;
myLong = myInt;
```

In the first line, we declare an integer data type and assign it a value of 12.
The next line declares a long data type and in the third line,
we assign the integer data type value to the long data type. C++ automatically converts the data type for you. 
This is known as a **widening conversion**. Some programmers also call this an __expanding assignment__.
We are expanding or widening the data type to a larger one. In this case, there is no loss in data. 
The following table highlights some potential data conversion problems.

|**Conversion**|**Potential Issues**|
|---|---|
|Large floating point type to small floating point type|Loss of precision and/or the starting value might be out of range for the new type|
|Floating point type to integer type|	Loss of the fractional component of the floating point type and/or out of range|
|Bigger integer type to smaller integer type|Starting value may be out of range for the new type|

This table **only deals with numeric data type conversions**.
There are other conversion types such as from character to numeric or numeric to character, 
or among character types. C++ also uses the boolean type that represents true or false. 
If you assign a zero value to a bool variable, it will be converted to false. Any non-zero value is converted to true.

When you want to **explicitly perform a conversion or cast**, you can use the type cast features of C++.
For example, the previous widening conversion in the int to long cast was implicit but **you can also
tell the compiler that you know what you are doing** by using the type cast statement as in:
```cpp
long myLong = (long)myInt;
// or you can use this version as well
long myLong = long(myInt);
```
**C++ also provides a cast operator that is more restrictive in its usage**. 
This in the form static_cast (type). This static cast operator can be used for 
converting numeric values or to numeric values. As an example:
```cpp
char ch;
int i = 65;
float f = 2.5;
double dbl;
ch = static_cast<char>(i);   // int to char
dbl = static_cast<double>(f);   // float to double
```

```cpp
#include <iostream>
int main()
{
	int i = 2;
	i = static_cast<int>(3.2);
  // the result is 3
	i = static_cast<int>(2.9);
  // the result is 2

	i = -1;

	std::cout << i << std::endl;

	double d = 2.7;
	std::cout << d << std::endl;
	i = static_cast<int>(d);
  // the result is 2
	d = i;

	bool flag = true;
	flag = false;
	flag = static_cast<bool>(7);
	std::cout << flag << std::endl;
}
```


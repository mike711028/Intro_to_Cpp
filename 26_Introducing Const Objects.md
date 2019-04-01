# Introducing Const Objects
Recall that the keyword **const** was used to indicate that a data type you use in your code 
is a constant and cannot have its value changed during application runtime.  Objects in
your code can also make use of the const keyword to indicate that **the objects are immutable**.
Immutable simply means that **they cannot change**.
   + you can **not** change variables in const class 
   + if the **member functions** inside of class don't change variables, you can call them 
     as long as **adding "const" behind declaration**
   + thinking about "const" from the very beginning in order to avoid modifying later
## header file
```cpp
// rectangle.h
class rectangle
{
public:
	rectangle() : width{}, height{}
	{}
	rectangle(int initial_width, int initial_height) : width{ initial_width }, height{ initial_height }
	{}
	void resize(int new_width, int new_height)
	{
		width = new_width;
		height = new_height;
	}

	//***** we tell compiler this function doesn't change variable by adding const behind declaration*****
	int area() const
	{
		return width * height;
	}
  
private:
	int width;
	int height;
};
```
## main function
```cpp
#include <iostream>
#include "rectangle.h"
// thinking about "const" at very beginning 

int main()
{ 
	//***the variables in "const class" (width, height) can not be modify after declared***
	rectangle mutable_rec{ 3, 4 };
	// if you change variables in const class, error will pop out
	rectangle const immutable_rec(3, 4);

	// work
	int new_area1 = mutable_rec.area();
	//*****can't work, coz compiler doesn't know "area()" doesn't change variables(width, height)*****
	// we have to tell it ( back to "area" function in the header file)
	int new_area2 = immutable_rec.area();   
	
	//*****can't work, coz "resize" will change variables even if you add "const" behind "resize"*****
	//immutable_rec.resize(4, 5);
  
	return 0;
}
```

# Introducing Encapsulation
Often considered the first pillar of object-oriented programming, **encapsulation can be used
to describe the accessibility of the members belonging to a class**.  C++ provides access modifiers 
and properties to help implement encapsulation in your classes.  While some consider this 
accessibility configuration to be the only aspect of encapsulation, others also define encapsulation
as the act of including all data and behavior required of the class, within the class definition.

**We use encapsulation to prevent changing the member variables directly**.  This is considered 
a poor practice because it presents the opportunity for potentially incorrect values to be 
assigned to these member variables.  This can result in unexpected behavior or more serious 
problems with your executing code.  It also helps with debugging of your code.

   + We want to restrict how we use types as much as possible.
   + we want to make it easy to use them correctly which means providing as few operations as are required.
   + we don't want to make them hard to use, we want to make them easy to use correctly.

## member function
```cpp
#include <iostream>
class rectangle
{
	// "public" means you can use these from outside of the class, like main function
	public:
	int width;
	int height;

	// "member function" can directly operate variables in this class
	// don't need input coz the variables are already in class
	int compute_area()
	{
		return height * width;
	}
};

int main()
{ 
	rectangle small_rec = { 6, 100 };		// customize your rectangle form	
	int area = small_rec.compute_area();   // Call "member function" and don't need input

	std::cout << "width is " << small_rec.width << std::endl
		<< "height is " << small_rec.height << std::endl
		<< "area is " << area << std::endl;

	return 0;
}
```
## the differences between "public" and "private"
```cpp
#include <iostream>
class rectangle
{
	// "public" means you can use these from outsie of the class, like in main function
	public:
	// member function can directly operate variables in this class
	// don't need input coz the variables are already in class
	int compute_area()
	{
		return height * width;
	}
	int get_width()
	{
		return width;
	}
	int get_height()
	{
		return height;
	}
	// "private" can not use these from outside of the class, like main function
	private:
		int width;
		int height;
};

int main()
{ 
	rectangle small_rec = {};		

	// these won't work
	int the_width = small_rec.width;
	int the_height = small_rec.height;

	// these will work
	int the_width = small_rec.get_width;
	int the_height = small_rec.get_height;
	int the_area = small_rec.compute_area;

	return 0;
}
```
## initialize variables in "private" content
we can't access variables in "private", but we can initialize them in the class by member function "resize"
```cpp
#include <iostream>
class rectangle
{
	// "public" means you can use these from outsie of the class, like in main function
	public:
	// initialize the variables in "private" content coz we can't access them
	void resize(int new_width, int new_height)
	{
		width = new_width;
		height = new_height;
	}	
	private:
		int width;
		int height;
};

int main()
{ 
	// initialize class as 0/NULL;
	rectangle small_rec = {};
	// initialze private variables by resize function
	small_rec.resize(3, 4);

	return 0;
}
```
## methods of defaulting variables (constructor)
```cpp
#include <iostream>
class rectangle
{
	public:
		// default constructor
		rectangle() : width{}, height{}
		{}
		// initialize rectangle with equal value
		explicit rectangle(int i) : width{ i }, height{ i }
		{}
		// initialze rectangle with custom values
		rectangle(int initial_width, int initial_height) : width{ initial_width }, height{ initial_height }
		{}
	// use member function to customize values
	void resize(int new_width, int new_height)
	{
		width = new_width;
		height = new_height;
	}	
	private:
		int width;
		int height;
};

int main()
{ 
	// 1
	rectangle rec1;
	rectangle rec1_2{};   // prefer to use this syntax coz it let reader know you default it
	// 2  (), {} are available
	rectangle rec2(66);
	rectangle rec2_2{ 32 };
	//3   (), {} are available
	rectangle rec3(10, 23);
	rectangle rec3_2{24, 64};
	//4
	rectangle rec4{};
	rec4.resize(60, 87);
	
	return 0;
}
```
## make class as header file and seperate functionality into some piece file
we don't need to implement all functionality inside the header file
### header file
```
// rectangle.h
class rectangle
{
public:
	// default constructor
	rectangle() : width{}, height{}
	{}
	// initialize rectangle with equal value
	explicit rectangle(int i) : width{ i }, height{ i }
	{}
	// initialze rectangle with custom values
	rectangle(int initial_width, int initial_height) : width{ initial_width }, height{ initial_height }
	{}
	// use member function to customize values
	// the body remove to resize.cpp, so just declare it here
	void resize(int new_width, int new_height);
	~~{
		width = new_width;
		height = new_height;
	}~~	
private:
	int width;
	int height;
};
```


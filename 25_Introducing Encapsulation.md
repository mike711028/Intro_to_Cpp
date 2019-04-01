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
# the differences between "public" and "private"
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
	// "private" can not use these from outside of the class, like in main function
	private:
		int width;
		int height;
};

int main()
{ 
	rectangle small_rec = {3, 4};		

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


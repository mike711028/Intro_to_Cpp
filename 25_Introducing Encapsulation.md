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
public:
	int width;
	int height;

	// member function can directly operate variables in this class
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


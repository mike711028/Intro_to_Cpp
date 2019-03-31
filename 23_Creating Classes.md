# Creating Classes
## Creating Classes and Members
In C++, a class is a programming construct that you can use to define your own custom types. 
When you create a class, you are effectively creating a blueprint for the type. The **class** 
defines the behaviors and characteristics, or **class members**, which are shared by all instances
of the class. You represent these behaviors and characteristics by defining methods and fields within your class.

Suppose you create a class to represent a rectangle shape in your program.  
You use the class keyword to declare a class, as shown in the following example:
```cpp
//Declaring a Class
class Rectangle
{
public:
    int _width;
    int _height;
};
```
Here we have declared a class called Rectangle and given it two public member variables 
called _ width and _ height, that will be used to represent the width and height of our rectangle. 
**Note that they are accessible directly because they are public, as a result of the public: modifier**.
## Using a Class
Now that we have a class created to represent a rectangle, **we can use that in our code to create
instances of a rectangle in our program**.  When we create a new rectangle from this class, it is known 
as a rectangle object and will be given a **unique name**.  That way ,we can refer to it in our program
directly and distinguish it from other rectangle instances that we might create, should our program
require more than one.
```cpp
void main()
{
     Rectangle outer;
     Rectangle inner;     

     outer._width = 10;
     outer._height = 10;

     inner._width = 5;
     inner._height = 5;
}
```
In this sample code, we have created **two rectangle objects** called outer and inner.  
Then, using what is known as "dot notation" or the dot operator, we provide values 
for the width and height of each rectangle.  The outer rectangle is 10 x 10 and the inner rectangle is 5x5.


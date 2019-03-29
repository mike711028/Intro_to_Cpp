# Enumerations
In the topics on variables and constants, it was noted that anytime you want to create a value 
for use in a program, where the value should never change, you used a constant. **An enumeration 
can be considered a way to create what are known as symbolic constants**. The most common example is
to use an enum to define the day of the week. There are only seven possible values for days of the week, 
and you can be reasonably certain that these values will never change.

To create an enum, you declare it in your code file with the following syntax,
which demonstrates creating an enum called ```Day```, that contains the days of the week:
```cpp
enum Day { Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday };
```
By default enum values start at 0 and each successive member is increased by 
a value of 1. As a result, the previous enum 'Day' would contain the values:
   + Sunday = 0
   + Monday = 1
   + Tuesday = 2
   + etc.

You can change the default by specifying a starting value for your enum as in the following example.
```cpp
enum Day { Sunday = 1, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday };
```
In this example, Sunday is given the value 1 instead of the default 0. Now Monday is 2, Tuesday is 3, etc.

The keyword enum is used to specify the "type" that the variable Day will be. In this case, 
an enumeration type. Consider the following code sample:
```cpp
enum Day { Sunday = 1, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday }; 
Day payDay; 
payDay = Thursday; 
cout << payDay << endl;
```
The first line defines the enumeration ```Day``` and assigns seven values to the enum. 
Sunday is listed as the first day of the week and is initialized with the value one.

The second line declares a new variable called ```payDay``` which is of the ```Day``` enum type.
In the third line, ```payDay``` is assigned a value from the list of values, in this case Thursday.
Finally, the last line outputs the value of ```payDay``` to the console window. If you run this code, 
you will notice that the last line outputs ```5 ```and not ```Thursday```. Internally, the constants in the
enum are used as numbers and not as the textual representation you assign to them.



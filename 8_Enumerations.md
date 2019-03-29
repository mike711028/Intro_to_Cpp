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




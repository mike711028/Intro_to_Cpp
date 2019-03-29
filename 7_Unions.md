# Unions

A union, in C++, **is similar to a structure** in that it can store multiple, disparate data types. 
**The differentiation is that a union can only store one piece of data at a time**. What does that signify? 
It's best represented using an example.
```cpp
union numericUnion 
{ 
     int intValue; 
     long longValue; 
     double doubleValue; 
}; 
numericUnion myUnion; 
myUnion.intValue = 3; 
cout << myUnion.intValue << endl; 
myUnion.doubleValue = 4.5; 
cout << myUnion.doubleValue << endl; 
cout << myUnion.intValue; cout << endl;
```
In this example, we define a union called ```numericUnion``` and then create a variable of that 
type, called ```myUnion```. We first assign the value 3 to the ```intValue``` field and then output it. 
Next we assign the value 4.5 to the ```doubleValue``` field and output that. The example shows how
the union works when on the second to last line, we try to output the value for intValue again.
In the output, it results in 0 rather than 3. **The reason is that once we assign a value to doubleValue,
what was contained in intValue is lost. The union can only store a value in one of its fields at a time**.

Why use a union over a struct if it can only hold one piece of data at a time? Consider a situation 
where you are programming an application that will run on a device with limited memory. You would like 
to use a data type that can support multiple types internally like a struct, but not necessarily all 
at the same time. **For example, part numbers for components in manufacturing where the part number may be 
a number or perhaps a string, depending on the manufacturer of the part. In this case, you could use the union 
to represent a numeric and a string data type internally but only assign the proper data type based on the part number**.


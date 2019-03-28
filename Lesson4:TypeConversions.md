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
|Large floating point type to small floating point type|Loss of precision and/or the starting value might be out of range for the new type|

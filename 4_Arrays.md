# Arrays
## Complex Data Types (Arrays)

So far you have been introduced to the intrinsic data types that C++ supports.
These are types that contain the data literals directly. 
The int type directly stores the literal integer value, for example.

C++ also provides support for complex data types. These are also referred to as compound data types.
Mostly because they store more than one piece of data or potentially more than one data type.

An array is a set of objects that are grouped together and managed as a unit. 
You can think of an array as a sequence of elements, all of which are the same type.
You can build simple arrays that have one dimension (a list), two dimensions (a table),
three dimensions (a cube), and so on. Arrays in C++ have the following features:

   +Every element in the array contains a value.
   +Arrays are zero-indexed, that is, the first item in the array is element 0.
   +**The size** of an array is the total number of elements that it can contain.
   +Arrays can be single-dimensional, multidimensional, or jagged.
   +**The rank** of an array is the number of dimensions in the array.

Arrays of a particular type can only hold elements of that type.
**This means that you cannot store integers, longs, and character data types in the same array.**

## Creating and Using Arrays

When you declare an array, you specify the type of data that it contains and a name for the array.
To declare a single-dimensional array, you specify the type of elements in the array and use brackets,
[] to indicate that a variable is an array. The following code example shows how to create
a single-dimensional array of integers with elements zero through nine.
```cpp
int arrayName[10];
```
You can also choose to create an array and initialize it with values at the same time
as in the following example that declares and integer array and assigns values to it.
The compiler knows how large to make the array by the number of values in the curly braces:
```cpp
int arrayName[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
```
You can also declare an array and only initialize some of the elements:
```cpp
int arrayName[10] = {1, 2, 3};
```
In this case, we have declared an array of size 10 but have only assigned values
to the first three elements. **The compiler will initialize the remaining elements to 
the default value for the data type the array holds.** In this case, 
int data type, the remaining values are initialized to 0.

### Accessing Data in an Array

You can access data in an array in several ways, such as by specifying the index of a specific
element that you require or by iterating through the entire array and returning each element in sequence.
The following code example uses an index to access the element at index two.
```cpp
//Accessing Data by Index 
int oldNumbers[] = { 1, 2, 3, 4, 5 }; 

//number will contain the value 3 
int number = oldNumbers[2];
```
Note: **Arrays are zero-indexed, so the first element in any dimension in an array is at index zero.**
The last element in a dimension is at index N-1, where **N is the size of the dimension**. 
If you are using some other languages, such as C#, and you attempt to access an element outside this range,
the C# runtime will throw an exception (error). **C++ doesn't offer such protection. 
If you attempt to access an element that is outside the bounds of your array,
you will still return data, but you have no idea what that data is.**

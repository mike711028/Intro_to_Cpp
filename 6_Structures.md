# Structures 
Arrays can store multiple pieces of data in one compound data type but recall,
the data types must all be of the same type. If that is the case, how might you store multiple
pieces of data in one type, where the individual pieces are of **different data types**? 
For example, let's say that we want to store information about a coffee bean. We might want to
store information about the bean type, its strength, and perhaps which country it originated
from. In this case, we could use all strings to store that information but what if the
strength was intended to be a number from 1 to 10. In this case, we would want to store two
strings and one integer in our coffee bean data type.

We haven't covered classes yet, which is another data type we could use, but instead, we will
use a **structure (struct)** to store this information. **Structures are known as user-defined types. 
You define the struct by giving it a name and then adding the member data types** as in the following example:
```cpp
// the structure's name > coffeeBean
struct coffeeBean 
{ 
     string name; 
     string country; 
     int strength; 
};
```
**Recall that in order to use the string data type in our struct, the C++ file that contains the struct must
include the string header file**. This code snippet also assumes that using namespace std; has also been included.

Once we have defined the structure, we can then use it in our code the same as any other data type. 
**To use the coffeeBean struct in your code, you simply declare a new variable of that type** as shown in this example.
```cpp
// declare a new variable of struct
coffeeBean myBean = { "Strata", "Colombia", 10 }; 
coffeeBean newBean; 
newBean.name = "Flora"; 
newBean.country = "Mexico"; 
newBean.strength = 9; 
cout << "Coffee bean " + newBean.name + " is from " + newBean.country << endl;
```
You can assign values to a struct using one of the methods seen here. For myBean, we assign values in 
the curly braces while for newBean, we use the dot notation. You can also access the values of the the struct
members using the dot notation as well, shown in the cout statement at the end.



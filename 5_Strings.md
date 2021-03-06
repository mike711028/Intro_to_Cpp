# Strings

**Strings are a series of characters**. C++ represents strings in one of two ways. 
The first maintains backward compatibility with the C language and represents **the string as an array of characters**.
There is one aspect to a C-style string that is important to note. **The last character of every string you 
store is the null character string, typically represented by the ASCII code for 0 which is \0.
This is necessary so that the compiler knows when the string ends**. An example demonstrates
a C-style string stored in a character array:
```cpp
char isAString[6] = { 'H', 'e', 'l', 'l', 'o', '\0'}; 
char isNotAString[5] = { 'H', 'e', 'l', 'l', 'o'}; 
cout << isAString << endl; 
cout << isNotAString << endl;
```
The most common mistake made by users of the C-style string is to 
**forget to make the char array large enough to accommodate the \0 character,
but also forgetting include the \0**. In the previous example, a programmer might think that an array
of size 5 would be large enough to contain Hello because that's how many characters are in the word.
However, the null character would not be included in the second array, which could result in errors 
in code that uses this array. **The reason is that C++ does not consider the isNotAString array to be a string**.

Consider the output displayed below. Note that the first output 
correctly terminates because C++ encountered the null (\0) character. 
The second did not terminate and output the contents of adjacent memory.
![alt text](https://github.com/mike711028/Intro_to_Cpp/blob/master/StringOutput.PNG)

**An alternative method of declaring a character array for use as a string** is
to simply initialize it with a string literal. A string literal is a sequence of characters 
enclosed in the double quotes ("). For example:
```cpp
char isAString[6] = "Hello"; 
char isAnotherString[] = "Array size is inferred";
```
In the previous example, the first line creates an array of size 6 and assigns the string
literal Hello to the array. The second example lets the compiler infer the size from the string literal itself.
Note that neither of these two string literals specifies a \0 character. The compiler will implicitly
add that for you. However, **caution is advised in the first line to ensure that you allow enough room in the 
array size specified for the null character**. If you create an array that is larger than required
for the string literal along with the null character, then C++ simply fills the remaining
elements of the array with null characters.

**The string Class** If the use of character arrays, single quoted characters, and null termination 
characters are making you think that strings aren't worth the hassle, consider the string class instead.
The ISO/ANSI standard helped to expand the string handling capabilities of C++ by adding the string class.

In order to use the string class, you have to include the string header file. We have not covered
namespaces yet but to make typing much easier, you would add a using statement as in the following example.
```cpp
#include <iostream>
// must to include header
#include <string>
int main()
{
	using namespace std;
	std::string newstring = "world";
	std::cout << "Hello, " << newstring << std::endl;
	// don't need to add std::
	cout << "test: Hello, " << newstring << endl;
}
```
Without the using directive, you would have to type std::string every time you wanted to use the string class
in your code, as in the second line above.

As you can see from the code example, you use string in the same manner in which you would use any other 
data type in C++. You also do not need to add a null character to terminate your string.

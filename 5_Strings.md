# Strings

Strings are a series of characters. C++ represents strings in one of two ways. 
The first maintains backward compatibility with the C language and represents the string as a character array.
There is one aspect to a C-style string that is important to note. The last character of every string you 
store is the null character string, typically represented by the ASCII code for 0 which is \0.
This is necessary so that the compiler knows when the string ends. An example demonstrates
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

Consider the output displayed in Figure 2.1. Note that the first output 
correctly terminates because C++ encountered the null (\0) character. 
The second did not terminate and output the contents of adjacent memory.
![Alt text](Intro_to_Cpp/StringOutput.PNG)
      

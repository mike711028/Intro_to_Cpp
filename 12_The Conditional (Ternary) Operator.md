# The Condition(Ternary) Operator

The C++ conditional operator is also known as a ternary operator because it takes three operands.
How this operator functions is somewhat similar to an if statement or a switch statement, **but
in a more compact form and for one single Boolean value with one of two possible outputs**.   
That is to say, the first operand is evaluated as a Boolean result.  If the result is true,
then the second operand will be the one evaluated.  Otherwise, the third operand will be evaluated. 
A sample helps amplify this.
```cpp
#include <iostream> 
using namespace std; 
int main() 
{ 
     int i = 1, j = 2; 
     cout << ( i > j ? i : j ) << " is greater." << endl; 
}
```
In this example, we have two integer variables, i and j which are initialized to 1 and 2 respectively. 
The ternary operator is embedded inside the cout statement and essentially follows this pattern:

   1. it checks whether i is greater than j
   2. it outputs the proper numeric value along with is greater.
   
In the code example here, j is greater than i so the condition evaluates to false and the value for j (2), 
is output to the console along with the text is greater.  In other words, the output is "2 is greater." 
If i was 5 and j was 2, the output would be, "5 is greater." 
```
i > j ? i : j where i is greater than j then the bold value is selected

i > j ? i : j where j is greater than i, then the bold value is selected
```

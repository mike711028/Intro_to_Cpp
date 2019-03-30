# switch Statements
If there are **too many** ```else if``` statements, code can become messy and difficult to follow.
In this scenario, a better solution is to use a ```switch``` statement. The ```switch``` statement simply
replaces multiple ```else if``` statements. The following sample shows how you can use a ```switch```
statement to replace a collection of else if clauses.

**switch Statement**
```cpp
char response = 'y';
switch (response)
{
   case 'y':
      // Block of code executes if the value of response is y.
      break;
   case 'Y':
      // Block of code executes if the value of response is Y.
      break;
   case 'n':
      // Block of code executes if the value of response is n.
      break;
   default:
      // Block executes if none of the above conditions are met.
      break;
}
```
Notice that there is a block labeled ```default```:. **This block of code will execute when none of 
the other blocks match**.  The default block is optional.

In each ```case``` statement, notice the ```break``` keyword. This causes control to jump to the end of
the ```switch``` after processing the block of code. If you omit the ```break``` keyword, the application 
may not perform as you anticipate.  In other languages, such as C#, omitting the break;
keyword will cause the code to no longer compile.

Without the break statement, the code will "**fall through**" to the remaining cases until it encounters
a break statement.   Be very careful in using fall through logic in your switch statements.  

(如果switch裡的case都不符合 那必須要有個default break 讓程式可以跳出)

The most common use for a fall through scenario is when you want to handle multiple cases with
a single statement or set of statements.

If you are coming from another programming language, such as C#, that also uses the switch statement,
you might notice that in the C# language, you can use string values in your switch statements and
don't have to use integers or enumerated types.  C++ switch statements support the following 
data types as expressions:

   +intrinsic data types such as int or char
   +enumerations

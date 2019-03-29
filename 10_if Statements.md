# if Statements

In C++, ```if``` statements are concerned with Boolean logic. If the statement is **true**, the block 
of code associated with the ```if``` statement is executed.  If the statement is **false**, control
either falls through to the line after the ```if``` statement, or after the closing curly brace of an ```if``` statement block.

The following code sample demonstrates an ```if``` statement to determine if a response contains a value of **y** or **Y**.
```cpp
char response = 'y';
if (response == 'y' || response == 'Y')
{
    cout << "Positive response received" << endl;
}
```
Note the use of curly braces in the code sample.  You can eliminate the curly braces 
if your statement to execute is a single line statement.  C++ understands that if no curly braces
are used, the line immediately after the if(condition) will be executed if the condition is true.
Otherwise that line of code is not executed and the code resumes after that line.  If you need to
have multiple statements execute if the condition is true, then you must use curly braces to 
surround the body of the if structure as in the code sample.  

TIP: To avoid confusion as to which lines will execute for a true condition, a recommended practice
is to always use curly braces for your if statement.

In C++, ```if``` statements can also have associated ```else``` clauses. The ```else``` clause executes when the ```if``` statement is **false**.

The following code example shows how to use an ```if else``` statement to execute code when a condition is **false**.

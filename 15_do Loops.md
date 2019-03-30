# do Loops
A ```do``` loop, sometimes also referred to as a ```do```...```while``` loop, is very similar to a ```while``` loop,
with the exception that **a do loop will always execute the body of the loop at least once**.
**In a while loop, if the condition is false from the start, the body of the loop will never execute**. 

You might want to use a ```do``` loop if you know that the code will only execute in response to a user prompt for data.
In this scenario, you know that the application will need to process at least one piece of data, 
and can therefore use a ```do``` loop.

The following code example shows the use of a ```do``` loop.

**do Loop**
```cpp
string response;

do
{        
     cout << "Enter menu choice " << endl << "More" << endl << "Quit" << endl;
     cin >> response;

     // Process the data.

} while (response != "Quit");
```
A couple of aspects to note about this loop.  First of all, the  response variable is declared outside of the loop. 
This is important due to **scope resolution requirements**.  **If you declare the variable inside the loop, 
then the while(response != "Quit") portion will not "see" the response variable**.

Second, note that in comparison with the while loop, the prompt only needs to be placed inside
the loop body and is not required ahead of the loop.  This is possible because the do loop executes
the contents of the loop at least once due to **the condition check being at the end of the loop**.

Third, **notice the semicolon at the end of the loop**.  This is required in the do loop and not in the while or for loop.


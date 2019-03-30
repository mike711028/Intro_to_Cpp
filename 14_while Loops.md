# while Loops

A ```while``` loop enables you to execute a block of code while a given condition is **true**.
For example, you can use a ```while``` loop to process user input until the user indicates
that they have no more data to enter.  The loop can continue to prompt the user until 
they decide to end the interaction by entering a sentinel value.   
The sentinel value is responsible for ending the loop.

The following code example shows how to use a ```while``` loop.

**while Loop**
```cpp
string response;
cout << "Enter menu choice " << endl << "More" << endl << "Quit" << endl;
cin >> response;

    while (response != "Quit")
    {
        // Code to execute if Quit is not entered

        // Prompt user again with menu choices until Quit is entered
        cout << "Enter menu choice " << endl << "More" << endl << "Quit" << endl;
        cin >> response;
    }
 ```
 It's imperative to include the prompt again, inside the loop braces.  Failure to put this 
 into the loop body will result in an infinite loop because the sentinel value can never be changed.


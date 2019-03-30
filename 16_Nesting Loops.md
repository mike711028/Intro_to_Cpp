# Nesting Loops

Nesting of loops is possible in C++.  The most common is to nest for loops. 
An example of nesting a for loop might be used for games, such as dealing four hands to
card players from a deck of 52.  Your outer loop would count from 0 to 51 for the total
number of cards in the deck and the inner loop would count from 0 to 3 to represent 
the 4 hands being dealt.   Of course, if you aren't dealing the entire 52 cards, you can change 
the outer loop counter to represent that fact.

The following code example shows nesting for loops to output a chess or
checkerboard representation using the characters X and O.
```cpp
bool alternate = true;

for (int x = 0; x < 8; x++)
{
    for (int y = 0; y < 4; y++)
    {
        if (alternate)
        {
            cout << "X ";
            cout << "O ";

        }
        else
        {
            cout << "O ";
            cout << "X ";

        }
    }
    alternate = !alternate;

    cout << endl;
}
```

# for Loops
```cpp
for ([initializer(s)]; [condition]; [iterator]) 
{
   // code to repeat goes here
}
```
The ```[initializer(s)]``` portion is used to initialize a value, or values, as a counter for the loop.
On each iteration, the loop checks that the value of the counter is within the range to execute 
the for loop, specified in the ```[condition]``` portion., and if so, execute the body of the loop.  
At then end of each loop iteration, the ```[iterator]``` section is responsible for incrementing the loop counter.

The following code example shows how to use a ```for``` loop to execute a code block 10 times.
```cpp
for (int i = 0 ; i < 10; i++) 
{
    // Code to execute.
}
```
In this example, ```i = 0```; is the initializer, ```i < 10```; is the condition, and ```i++``` is the iterator. 

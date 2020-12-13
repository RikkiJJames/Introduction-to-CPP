# Introduction to C++

A introductory guide into C++

## Contents

* Variables & Constants
* Characters & Strings
* Arrays & Vectors
* Statements & Operators
* Controlling Programme Flow
* Functions
* Pointers & References
* OOP - Classes & Objects
* Operator Overloading
* Inheritance
* Polymorphism
* Smart Pointers
* Exception Handling
* I/O & Streams
* The STL


### Variables & Constants

A variable is a name allocated to a value in memory. It is called a variable as the value can change throughout the programme.
In C++ the variable must be declared before use and are derived from the primative datatypes listed below:
* int - used for integer type data and values range from -2147483648 to 2147483647
* char - used for storing character data 
* bool - used for storing Boolean values which can be  true or false 
* float - used for storing floating point/decimal values  

#### Declaring Variables
To declare a variable the syntax is in the order datatype -> variable name -> value;
A variable can start with both upper and lowercase letters or an underscore "_". However, it cannot start with a number.
```c++
//Declaring a integer variable 
int x = 5;
```
Multiple variables of the same datatype can be declared in a single line
```c++
//Declaring multiple variables
int a = 5,b = 10,c = 15;
```
#### Scope
There are three types of variables based on scope

* Local Variables
* Instance Variables
* Static Variables

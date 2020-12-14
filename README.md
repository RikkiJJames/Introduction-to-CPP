# Introduction to C++

My introductory guide into C++

## Contents

* [Variables & Constants](###variables-&-constants)
  * [Datatypes](####datatypes)
  * [Declaring Variables](####declaring-variables)
  * [Variable Scope](####variable-scope)
  * [Constants](####constants)
  * [Section Challenge](####section-challenge)
* Characters & Strings
* Arrays & Vectors
* Statements & Operators
* Controlling Program Flow
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

#### Datatypes
A variable is a name allocated to a value in memory. It is called a variable as the value can change throughout the program.
In C++ the variable must be declared before use and are derived from the primitive datatypes listed below:
* int - used for integer type data.
* char - used for storing character data 
* bool - used for storing Boolean values which can be  true or false 
* float - used for storing floating point/decimal values  

##### Modifiers 
Most of the primitive datatypes can be modified using the following modifiers:
* signed
* unsigned
* short
* long

##### Signed/Unsigned
A signed variable is one that can store both positive and negative numbers. Whereas, an unsigned variable can only hold positive values, allowing it shift its range.

##### Short/Long

A short requires fewer bytes (typically 2 depending on the compiler), therefore saving space. However, it is important to know the maximum value being assigned to the variable otherwise overflow issues will occur.

The table below shows the value range and typical bit size for each datatype:

##### Value Range/Bit Size Table

| Datatype | Typical Bit Size (bytes) | Typical Value Range |
| :---: | :---: | :---: |
| int | 4 | -2147483648 to 2147483647 |
|signed int |	4 |	-2147483648 to 2147483647 |
|unsigned int |	4 |	0 to 4294967295 |
|short int |	2 |	-32768 to 32767 |
|signed short int	| 2 |	-32768 to 32767 |
|unsigned short int	| 2 |	0 to 65,535 |
|long int	| 8 |	-2,147,483,648 to 2,147,483,647 |
|signed long int|	8 |	-2,147,483,648 to 2,147,483,647 |
|unsigned long int |	8 |	0 to 4,294,967,295 |
|long long int | 8 |-(2^63) to (2^63)-1 |
|signed long long int	|8|-(2^63) to (2^63)-1|
|unsigned long long int	|8|0 to 18,446,744,073,709,551,615|
|float| 4 | 
|double|	8 |
|long double	|12| 

For a coded example click [here](Variables-&-Constants/Sizeof)

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

#### Variable Scope
There are three types of variables based on scope

* Local Variables
* Global Variables
* Static Variables

##### Local Variables

Local variables are those defined within a function or block and do not exist outside the block they are declared in.
```c++
include <iostream>

using namespace std;
//Demonstrating Local Variables
void func1(){

int age = 25;

}

int main(){

  cout << "My age is: " << age << endl;
  
}
```
If this is program is run, the following error will occur:

>Error: age was not declared in this scope

To fix this error the variable must be printed within the same scope.

```c++
include <iostream>

using namespace std;
//Correct Local Variable Method
void func1(){

int age = 25;
cout << "My age is: " << age << endl;
}

int main(){

  func1(){
  
}
```


##### Global Variables

Global variables can be accessed from any part of the program and are declared at the top of the program outside of any function blocks.
An example of a global variable being used can be seen below:

```c++
using namespace std;
//Demonstrating Local Variables

int age = 25;

int main(){

  cout << "My age is: " << age << endl;
  
}
```
If a local and global variable have the same, then the local variable will take precedence, take the example below:

```c++
#include <iostream>
 
using std::cout;
using std::endl;

int age {25}; // Global variable
 
int main() {
    
    int age {18};    // local variable
    
    cout << "My age is: " << age <<  endl;

    return 0;
}
```
The output will display :

> My age is: 18

To solve this problem the scope resolution operator :: can be used. An example of this can be seen [here](Variables-&-Constants/Local_&_Global_Variables)

#### Constants

Constants are defined using the const keyword and are variables which cannot change their value once defined.
The values assigned to a constant is known as a literal.

An example of defining a constant can be seen below:

```c++
include <iostream>

using namespace std;


int main(){

  const float pi {3.142};
  cout << "The value of pi is: " << pi << endl;
  
  return 0;
}
```
Trying to modify the value of a constant will result in an error stating:

> Error assignment of read-only variable

#### Section Challenge

Using all the information so far, a carpet cleaning service price estimator which determines the total cost of cleaning; depending on the size and number of rooms and including service tax to the total can be found [here](Variables-&-Constants/Challenge).

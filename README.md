# Introduction to C++

My introductory guide into C++

## Contents

* [Section 1 - Variables & Constants](#section-1---variables--constants)
  * [Datatypes](#datatypes)
  * [Declaring Variables](#declaring-variables)
  * [Variable Scope](#variable-scope)
  * [Constants](#constants)
  * [Section 1 Challenge](#section-1-challenge)
* [Section 2 - Arrays & Vectors](#section-2---arrays--vectors)
  * [Declaring Arrays](#declaring-arrays)
  * [Accessing Array Elements](#accessing-array-elements)
  * [Multidimensional Arrays](#multidimensional-arrays)
  * [Vectors](#vectors)
  * [Declaring Vectors](#declaring-vectors)
  * [Accessing Vector Elements](#accessing-vector-elements)
  * [Modifying Vectors](#modifying-vectors)
  * [Section Challenge](#section-2-challenge)
* [Characters & Strings](#section-3---characters--strings)
  * Testing Functions
  * Conversion Functions
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


### Section 1 - Variables & Constants

### Variables

#### Datatypes
A variable is a name allocated to a value in memory. It is called a variable as the value can change throughout the program.
In C++ the variable must be declared before use and are derived from the primitive datatypes listed below:
* int - used for integer type data.
* char - used for storing character data (primararly letters)
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

  cout << "My age is: " << age << endl; // Error: age was not declared in this scope
  
}
```
If this is program is run program will fail to compile.


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
    
    cout << "My age is: " << age <<  endl; // My age is: 18

    return 0;
}
```

To solve this problem the scope resolution operator :: can be used. An example of this can be seen [here](Variables-&-Constants/Local_&_Global_Variables)

### Constants

Constants are defined using the const keyword and are variables which cannot change their value once defined.
The values assigned to a constant is known as a literal.

An example of defining a constant can be seen below:

```c++
include <iostream>

using namespace std;


int main(){

  const float pi {3.142};
  cout << "The value of pi is: " << pi << endl; // Error assignment of read-only variable
  
  return 0;
}
```

### Section 1 Challenge

Using all the information so far, a carpet cleaning service price estimator which determines the total cost of cleaning; depending on the size and number of rooms and including service tax to the total can be found [here](Variables-&-Constants/Challenge).

### Section 2 - Arrays & Vectors

### Arrays

An array is a collection of items stored in contiguous memory locations, enabling the handling of large amounts of data.
All elements within an array must be of the same datatype and are static, which means their size is fixed and must be known at compile time.

#### Declaring Arrays

Arrays can be declared by defining their size, datatype of both:

Some examples are shown below:

```c++
//Declaring array of integers
int arr1 [3]; // Array with a size of three full or garbage data
int arr2 [3] = {1,2,3}; // Array of size three containing the numbers 1,2 & 3
int arr3 [6] = {1,2,3}; // Array of size three containing the numbers 1,2 & 3 followed by zeros for the remainder
int arr4 [] = {1,2,3}; // Array of size three containing the numbers 1,2 & 3
int arr5 [3] = {}; // Empty array with a size of three 
```
The outputs of the code above can be found [here](Arrays-&-Vectors/Declaring_Arrays)

#### Accessing Array Elements

Arrays are zero indexed which means the first element and last element have the an index of 0 and the size of the array minus one respectively.


```c++
//Accessing array elements
#include <iostream>

using namespace std;

int main(){

 int arr1 [] = {1,2,3};

 cout << arr[0] << endl; // returns 1
 cout << arr[1] << endl; // returns 2
 cout << arr[2] << endl; // returns 3

 return 0;
}
```
##### No Index Bounds Checking

C++ does not out of bounds index checking. This means that accessing an element that does not exist in the array will still compile:

```c++
//Accessing array elements
#include <iostream>

using namespace std;

int main(){
 int arr1 [] = {1,2,3};

 cout << arr[3] << endl; // Unexpected results
 cout << arr[-1] << endl; // Unexpected results

 return 0;

}
```

Earlier it was mentioned that elements in an array are stored in contiguous memory locations, meaning they are stored in consecutive blocks of memory. 
For instance if the size of an integer is 4 bytes then the difference between the first and second element in an array will differ by 4 bytes

```c++
//Accessing array elements
#include <iostream>

using namespace std;

int main(){
 int arr1 [] = {1,2,3};

 cout << &arr[0] << endl; // Returns 0x6ffe14
 cout << &arr[1] << endl; // Returns 0x6ffe18
 cout << &arr[2] << endl; // Returns 0x6ffe1c

return 0;
}
```
#### Multidimensional Arrays

In C++ a multidimensional array can be defined as an array of arrays.
Data in multidimensional arrays are stored in tabular form (in row major order).
Elements in two-dimensional arrays are commonly referred by x[i][j] where i is the row number and ‘j’ is the column number.

##### Declaring Multidimensional Arrays

```c++
// Two dimensional array:
int two_d[10][20];

// Three dimensional array:
int three_d[10][20][30];
```

##### Size Of A Multidimensional Array

The number of elements a multidimensional array can store can be calculated by muliplying the size of each dimension.
For example the array "two_d" in the previous example has a size of 10 x 20 = 200.

##### Initialising A Multidimensional Array

There are many different ways to initialise a multidimensional array.
But the best way is shown below:

```c++
int two_d[3][4] = {{0,1,2,3}, {4,5,6,7}, {8,9,10,11}};
```
This form uses nested curly brackets to indicate the number of columns.

##### Accessing Elements In A Multidimensional Array

Elements in 2D arrays are accessed using the row indexes and column indexes.
For example:

```c++
int two_d[3][4] = {{0,1,2,3}, {4,5,6,7}, {8,9,10,11}};

cout << two_d[1][0] // Returns 4;
```
The index refers to the  first element in the second row.

### Vectors

Vectors are very similar to arrays but are dynamic.
This means it can change its size automatically when an element is inserted or deleted.
The current size of the vector can be determined using:

Like arrays data is stored contiguously which means it can be accessed using iterators which will be discussed [later](#iterators). But generally iterators are objects that point to an element in a container.
To use vectors the <vectors> library must be included.
 
#### Declaring Vectors

Like arrays, vectors can be declared in multiple ways:

Some examples are shown below:

```c++
//Declaring vector of integers
#include <iostream>
#include <vector>

using namespace std;

int main(){
 vector<int> vect1;  // Empty vector
 vector<int> vect2(3, 10); // Creates a vector with a size of three with a value of 10 for all elements
 vector<int> vect3{ 10, 20, 30 }; // Creates an vector that contains the values 10, 20 & 30

 // Initialise from an array
 int arr1[] = {1,2,3,4};
 int n = sizeof(arr1) / sizeof(arr1[0]);
 vector<int> vect4 (arr1, arr1 + n ) // Creates a vector copy of arr1

 // Initialise from another vector
 vector<int> vect5 (vect3) // Creates copy of vect3
 vector<int> vect6(vect3.begin(), vect3.end()); // Creates copy of vect3

 return 0;
}
```

The size of a vector can be determined using;

```c++
#include <iostream>
#include <vector>

using namespace std;

int main(){
 vector <int> vect (5,100); // Creates a vector with a size of five with a value of 100 for all elements
 cout << vect.size(); // Returns 5

 return 0;
}
```
#### Accessing Vector Elements

As vectors can also use iterators there are different ways to access vector elements

| Function | Output |
| :-:| :-:|
|vect[a]| Returns element at position 'a' in the vector|
|vect.at(a)| Prefered element access method as it automatically executes a within bounds check. Returning element at position 'a' in the vector if within bounds. Throws an out_of_range exception if not.
|vect.front()| Returns first element in the vector|
|vect.back()| Returns last element in the vector|

For an example on how to access vector elements click [here](Arrays-&-Vectors/Accessing_Vector_Elements)

#### Modifying Vectors

| Function | Output |
| :-:| :-:|
|vect.assign(size,value)| Fills vect with 'value', 'size' number of times |
|vect.push_back(a)| Pushes element 'a' into the back of vect and increases vector size by 1|
|vect.pop_back()| Removes the element from back of the vector and decreases vector size by 1|
|vect.insert(\*position, value)| Inserts an element with 'value' at 'position' |
|vect.erase(\*position) or vect.erase(\*start, \*end) | Removes the element at 'position' or the range 'start' and 'end'. Includes 'start', does not include 'end' |
|vect.remove(\*start,\*end,value) | Defined in the <algorithm> library. Removes all elements which are equal to 'value' within the range of 'start' and 'end' and returns an iterator to the new end of that range |
|vect.remove_if(\*start, \*end, func) | Removes element within the range of'start' and 'end' if func is true |
|vect.swap(vect1)| Exchanges the content of vect with vect1 as long is it contains the same datatype, difference in sizes do not matter|
|vect.clear()| Removes all elements from vector, leaving it with a size of 0|
|vect.emplace(\*position, value)|Inserts an element with 'value' at 'position'. More efficient than insert |
|vect.emplace_back(value)| Pushes element 'a' into the back of vect and increases vector size by 1. More efficient than push_back|

\*parameter is an iterator e.g for the range of an entire vector start = vect.begin() and end = vect.end()

For an example on how to access vector elements click [here](Arrays-&-Vectors/Vector_Modifying_Functions)

### Section 2 Challenge

In this challenge two vectors are declared, initialised and push_back into another to form a 2d vector. The 2D vector is printed out and one of the orignal vector elements are modified to show that the 2D vector holds a copy of the original and so stays the same. The challenge can be found [here](Arrays-&-Vectors/Challenge).

### Section 3 - Characters & Strings

### Characters

There are various functions that can be used with characters contained within the <cctype> library which must be included.
They fit into two categories: Testing and Converting as shown below:
 
##### Testing Functions
| Function | Output |
| :-:| :-:|
|isalpha(c)| True if c is a letter|
|isalnum(c)| True if c is a letter or digit |
|isdigit(c)| True if c is a digit|
|isprint(c)| True if c is a printable character|
|ispunct(c)| True if c is a a punctuation character|
|isupper(c)| True if c is an uppercase letter |
|islower(c)| True if c is a lowercase letter|
|isspacea(c)| True if c is whitespace|

##### Conversion Functions

| Function | Output |
| :-:| :-:|
|tolower(c)| returns lowercase of c|
|toupper(c)| returns uppercase of c |

Examples of the use of these functions can be seen [here](Characters-&-Strings/Char_Functions)

### Strings
In C++ there are two types of strings: C-style strings and C++ strings. 

#### C-style Strings

C-style strings are simply arrays of characters with a null character '\0' being used to terminate it. They are natively, inherited from the C language.
The null character is automatically added. Therefore, even though a string may have 5 letters it must have a length of 6 at least.
It is alright if the array is larger than the length of the string as the string will end with the null terminator and the rest of the characters will be ignored.

A c-style array can be declared using the syntax below:
 
```c++
char string[50]; // declares a string of 49 letters and a null character
char string_name [] = "string"; //declares a string containing {"s","t","r","i","n","g","\0"}
char string_name []{ "string" }; //declares a string containing {"s","t","r","i","n","g","\0"}
```

When printing a C-style string, std::cout prints all characters until it encounters the null terminator. If the null terminator has been accidently overwritten( e.g. by assigning a value to string_name[7]), not only will all the characters get printed std::cout will  keep printing everything in adjacent memory slots until happens to hit null terminator 

##### C-style String Functions

There are various functions that can be used with c-style functions that are contained within the <cstring> libary. As shown below:
 
##### C-string Functions
| Function | Output |
| :-:| :-:|
|strlen(c)| Returns the length of 'c' not including the null character|
|strcpy(dest,source)| Copies and overwrite the contents of 'source' to 'dest' |
|strcat(dest,source)| Copy the contents of 'source' append it to the end of 'dest' starting with the null character|
|strrchr(string, c) | Returns a pointer to the last occurance of the character 'c'. If the character is not present in the string 'null' is returned|
|strcmp(s1, s2)|Returns 0 if s1 and s2 are the same; less than 0 if s1<s2; greater than 0 if s1>s2.|

Examples of their usage can be found [here](Characters-&-Strings/C-Style_Strings)

###### Usage
Although it is important to be aware of C-style strings and know how they work. It is recommended to avoid using them and stick with C++ strings which are covered next.

#### C++ Strings

C++ has it's own way of storing a sequence of characters. Using a class in the standard library 'std::string'.
In C++ strings the size of the array must be defined before compilation as it is allocated statically, this means that the size cannot be changed and any data not used is wasted. However, C++ strings allocate memory dynamically. Allowing memory to be allocated at run time depending on demand. Therefore no memory is wasted.

To use C++ strings the <string> library must be included. A C++ string can be declared using the syntax below:
 
```c++
#include <iostream>
#include <string>

using std::string

int main(){

 string s0; // Creates an empty string
 string s1 {"Rikki"}; // Create a string containing "Rikki"
 string s2 {s1}; // Creates a copy of 's1'
 string s3 {s1, 0, 3}; // Creates a string containing a substring of s1 starting at the zero index and ending and spans 3 letters "Rik"
 string s4 (10, 'X'); // Creates a string containing 'XXXXXXXXXX'
 
 return 0;
}
```

The std::string class has all the functionality of C-style strings. However, some operations such as copying contatination and comparing are simpler in syntax:

```c++
#include <iostream>
#include <string>
#include <iomanip> // Needed for boolalpha
using std::string;
using std::cout;
using std::endl;
using std::boolalpha;

int main(){

 string first_name {"Rikki"}; 
 string last_name {"James"};
 
 // Copying
 
  string copy {first_name}; // Copies the contents of 'first_name' into 'copy'
  
 // Concatination
 
 string full_name = first_name + " " + last_name; 
 cout << full_name << endl; // prints out"Rikki James"
 
 // Comparison
 cout << boolalpha; // Converts the 1 and 0 outputs of boolean functions to true and false;
 string name {"rikki"};
 cout << (name == first_name) << endl; // Returns false
 
 return 0;
}
```

C++ also has some added functionality as shown below:

##### C++ string Functions
| Function | Output |
| :-:| :-:|
|s0.length()| Returns the length of 's0'|
|s0.substr(a,n)| Returns a newly constructed string object containing a substring of 's0' starting at position 'a' and continuing for 'n' characters |
|s0.erase(a,n)| Erases characters in the string 's0' starting at position 'a' and continuing for 'n' characters|
|getline(cin, s0)| Extracts characters from the input stream and replaces the contents of the string object 's0'|
|s0.find(word)| Returns the index of the first occurrence of the substring 'word' in the string.  if the sub-string is not found it returns string::npos (the highest possible for a size_t structure) |

Examples of their usage can be found [here](Characters-&-Strings/CPP_Strings)

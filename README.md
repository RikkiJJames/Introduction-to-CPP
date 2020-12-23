 # Introduction to C++

 My introductory guide into C++

 ## Contents

 * [Section 1 - Variables & Constants](#section-1---variables--constants)
   * [Variables](#variables)
     * [Datatypes](#datatypes)
     * [Declaring Variables](#declaring-variables)
     * [Variable Scope](#variable-scope)
   * [Constants](#constants)
   * [Section 1 Challenge](#section-1-challenge)
 * [Section 2 - Operators](#section-2---operators)
   * [Arithmetic Operators](#arithmetic-operators)
   * [Assignment Operators](#assignment-operators)
   * [Comparison Operators](#comparison-operators)
   * [Logical Operators](#logical-operators)
   * [Section 2 Challenge](#section-2-challenge)
 * [Section 3 - Arrays & Vectors](#section-3---arrays--vectors)
   * [Arrays](#arrays)
     * [Declaring Arrays](#declaring-arrays)
     * [Accessing Array Elements](#accessing-array-elements)
     * [Multidimensional Arrays](#multidimensional-arrays)
   * [Vectors](#vectors)
     * [Declaring Vectors](#declaring-vectors)
     * [Accessing Vector Elements](#accessing-vector-elements)
     * [Modifying Vectors](#modifying-vectors)
   * [Section 3 Challenge](#section-3-challenge)
 * [Section 4 - Characters & Strings](#section-4---characters--strings)
   * [Characters](#characters)
   * [Strings](#strings)
     * [C-Style Strings](#c-style-strings)
     * [C++ Strings](#c-strings)
   * [Section 4 Challenge](#section-4-challenge)
 * [Section 5 - Controlling Program Flow](#section-5---controlling-program-flow)
   * [Conditional Statements](#conditional-statements)
     * [If Statements](#if-statements)
     * [Else Statements](#else-statements)
     * [Else If Statements](#else-if-statements)
     * [Switch Statements](#switch-statements)
     * [Conditional Operator](#conditional-operator)
   * [Loops](#loops)
     * [While Loops](#while-loops)
     * [Do/While Loops](#while-loops)
     * [For Loops](#for-loops)
     * [Break & Continue](#break--continue)
   * [Section 5 Challenge](#section-5-challenge)
 * [Section 6 - Functions](#section-6---functions)
   * [Function Declarations](#function-declarations)
   * [Function Declaration & Definition](#function-declaration--definition)
   * [Parameter Passing](#parameter-passing)
   * [Default Arguments](#default-arguments)
   * [Overloading Functions](#overloading-functions)
   * [Passing Arrays to Functions](#passing-arrays-to-functions)
   * [Recursive Functions](#recursive-functions)
   * [Section 6 Challenge](#section-6-challenge)
 * [Section 7 - Pointers & References](#section-7---pointers--references)
   * [Pointers](#pointers)
     * [Declaring Pointers](#declaring-pointers)
     * [Assigning Pointers](#assigning-pointers)
     * [Dereferencing Pointers](#dereferencing-pointers)
     * [Memory](#memory)
     * [Pointers & Arrays](#pointers--arrays)
     * [Pointer Arithmetic](#pointer-arithmetic)
     * [Const Pointers](#const-pointers)
     * [Passing Pointers To Functions](#passing-pointers-to-functions)
     * [Returning Pointers From Functions](#returning-pointers-from-functions)
   * [References](#references)
   * [Section 7 Challenge](#section-7-challenge)
 * [Section 8 - OOP (Classes & Objects)](#section-8---oop-classes--objects)
 * Operator Overloading
 * Inheritance
 * Polymorphism
 * Smart Pointers
 * Exception Handling
 * I/O & Streams
 * Useful Functions * Libraries
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

##### Static Variables

When a variable is declared as static, space for it gets allocated for the lifetime of the program. Even if the function is called multiple times, space for the static variable is allocated only once and the value of variable in the previous call gets carried through the next function call. This is useful for implementing coroutines in C/C++ or any other application where previous state of function needs to be stored.

```c++
void count(void){  
    static int num {0}; // Only declared once
    cout << num << endl;
    num++;    
    return;    
} 

int main(){
    for (int i {} ; i <= 5; i++){
        count(); // Prints 0,1,2,3,4,5
    } 
    
    return 0;
}

```

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

 ### Section 2 - Operators

 Operators are used to perform operations on variables and their are four types:
 * Arithmetic - used to perform common mathematical operations
 * Assignment
 * Comparison
 * Logical 

 #### Arithmetic Operators

 |Operator|Name| Operation|
 | :-:|:-:|:-:|
 |+| Addition| Adds two values|
 |-| Subtraction| Subtracts two values|
 |* | Multiplication| Multiplies two values|
 |/| Division | Divides one value by another|
 |%| Modulus | Returns the remainder of a division operation (only works with integers)| 
 |++| Increment| Increases the value of a variable by 1|
 |--| Decrement|Decreases the value of a variable by 1|

 Examples on how to use these operators can be seen [here](Operators/Arithmetic_Operators)

 #### Assignment Operators

 Assignment operators are used to assign values to variables:

 |Operator|Same as |
 | :-:|:-:|
 |=| x = 5|
 |+=| x = x + 5|
 |-=| x = x - 5|
 |/=| x = x / 5 |
 |%=|x = x % 5 |

 #### Comparison Operators

 Comparison operators are used to compare two values resulting in a 1 if the statement is true, or 0 if false.

 |Operator| Name |
 | :-:|:-:|
 |==| equal to |
 |!=| not equal to|
 |>| greater than|
 |<| less than|
 |>=| greater than or equal to |
 |<=| less than or equal to |


 #### Logical Operators

 Logical operators are used to determine logic between values:


 |Operator|Name| Description |
 | :-:|:-:|:-:|
 |&&| and |Returns true if both statements are true |
 |\|\||or|Returns true if either one of the statements is true |
 |!| not |Reverse the expected result. Returns true if the result is true|
 |<| less than| Returns true if the lhs statement is less than the rhs|
 |>| greater than |Returns true if the lhs statement is greater than the rhs|
 |<=| less than or equal to | Returns true if the lhs statement is less than or equal to the rhs|
 |>=| greater than or equal to |Returns true if the lhs statement is greater than or equal to the rhs|
 |^| xor| Returns true if either is true, but not both |

 ### Section 2 Challenge

 For this challenge a UK GBP change machine was made. Asking the user to input an amount of pennies and output its equivalent in Uk currency.
 The challange can be found [here](Operators/Challenge) 

 ### Section 3 - Arrays & Vectors

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

 ### Section 3 Challenge

 In this challenge two vectors are declared, initialised and push_back into another to form a 2d vector. The 2D vector is printed out and one of the orignal vector elements are modified to show that the 2D vector holds a copy of the original and so stays the same. The challenge can be found [here](Arrays-&-Vectors/Challenge).

 ### Section 4 - Characters & Strings

 ### Characters

 There are various functions that can be used with characters contained within the <cctype> library which must be included.
 They fit into two categories: Testing and Converting as shown below:

 ##### Character Testing Functions
 
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

 ##### Character Conversion Functions

 | Function | Output |
 | :-:| :-:|
 |tolower(c)| returns lowercase of c|
 |toupper(c)| returns uppercase of c |

 Examples of the use of these functions can be seen [here](Characters-&-Strings/Char_Functions)

 ### Strings
 
 In C++ there are two types of strings: C-style strings and C++ strings. 

 #### C-Style Strings

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

 ##### C-Style String Functions

 There are various functions that can be used with c-style functions that are contained within the <cstring> libary. As shown below:

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

 ##### C++ String Functions
 
 | Function | Output |
 | :-:| :-:|
 |s0.length()| Returns the length of 's0'|
 |s0.substr(a,n)| Returns a newly constructed string object containing a substring of 's0' starting at position 'a' and continuing for 'n' characters |
 |s0.erase(a,n)| Erases characters in the string 's0' starting at position 'a' and continuing for 'n' characters|
 |getline(cin, s0)| Extracts characters from the input stream and replaces the contents of the string object 's0'|
 |s0.find(word)| Returns the index of the first occurrence of the substring 'word' in the string.  if the sub-string is not found it returns string::npos (the highest possible for a size_t structure) |

 Examples of their usage can be found [here](Characters-&-Strings/CPP_Strings)

 ### Section 4 Challenge

 For this challenge I created a substitution cypher which can encrypt a message. Replacing the letters in the message with ones within a key. Only an individual in possession of the key and then decrypt the message. The challenge can be found [here](Characters-&-Strings/Challenge).

 ### Section 5 - Controlling Program Flow

 ### Conditional Statements

 Conditional statements are used to perform different actions depending on the situation.
 These can be determined using the logical operators discussed in the operators [section](#logical-operators)

 C++ has the following conditional statements:

 * if
 * else
 * else if
 * switch

 #### If Statements

 The 'if' statement is used to execute a block of code , if a condition is true. The 'if' must be lowercase to avoid throwing up an error.
 An example of an if statement can be seen below:

 ```c++

 int num {};
 const int max {50};

 cout << "Enter a number between " << min << " and " << max << ": ";
 cin >> num; // User enters a number which is stored in 'num'

 // Case 1
 if (num > max){
  cout << num << " is greater than: " << max << endl;
 }
 // Case 2
 if (num > max){
  cout << num << " is greater than: " << max << endl;
 }
 // Case 3
 if (num == max){
  cout << num << " is equal to: " << max << endl;
 }
 ```

 #### Else Statements

 The 'else' statement is used to execute a block of code , if the same condition as above if false.
 An example can be seen below:

 ```c++

 int num {};
 const int max {50};

 cout << "Enter a number between " << min << " and " << max << ": ";
 cin >> num; // User enters a number which is stored in 'num'

 if (num >= max){
  cout << num << " is greater than or equal to : " << max << endl;
 }
 else {
  cout << num << " is less than: " << max << endl;
 }
 ```

 #### Else If Statements

 The 'else if' operator used to specify a new condition to test, if the first condition is false.

 ```c++
 int num {2};

 if (num < 15){
  cout << num << " is small";
 }
 else if (num < 5) {
  cout << num << " is very small" << endl; // Prints this line
 }
 ```
 A more detailed example of if/else/elseif statements example can be found [here](Controlling-Program-Flow/Conditional_Statement)

 #### Switch Statements

 A 'switch' statement is used to specify many alternative blocks of code to be executed.
 It evaluates a statement once and compares the output of the expression against each 'case'.
 If the output matches a case then its corresponding code block will be run.
 An example can be seen below:

 ```c++
 int day {2};
 switch (day) {
   case 1:
     cout << "Monday";
     break; // used to signify end of case
   case 2:
     cout << "Tuesday"; // print Tuesday as the day number is 2
     break;
   case 3:
     cout << "Wednesday";
     break;
   case 4:
     cout << "Thursday";
     break;
   case 5:
     cout << "Friday";
     break;
   case 6:
     cout << "Saturday";
     break;
   case 7:
     cout << "Sunday";
     break;
   default: // triggers when the input doesn't match any case 
     cout << "Sorry that's not a valid input" << endl;
 ```

 #### Conditional Operator

 The conditional operator '?' is known as a ternary operator as requires three operands. 
 It can be used to replace if/else statements. For example, instead of writing the if/else statement below:

 ```c++
 if(condition) {
    var = X;
 } else {
    var = Y;
 }
 ```
 The conditional operator can be used:

 ```c++
 var = (y < 10) ? X : Y;
 ```

 More examples can be found [here](Controlling-Program-Flow/Conditional_Operator)
 ### Loops

 Loops execute a block of code as long as a specified condition is satisfied.
 Loops are powerful because they make code more readable, save time and reduce errors.

 #### While Loops

 A 'while' loop continuously loops through the block as code as long as the condition is true.
 Therefore it is important to modify the variable used in the condition, otherwise the loop will never end.

 ```c++
  int num {5};
  while (num > 0 ) {
      cout << num << endl;
      num--;
      }
 // Prints countdown 5,4,3,2,1
 ```

 #### Do/While Loops

 A 'do/while' loop a variant of the while loop. It will execute the code in the 'do' block once, before checking if the condition is true, then it will repeat the loop as long as the condition is true.

 ```c++
     char selection {};
     do {
         cout << "1. Option 1" << endl;
         cout << "2. Option 2" << endl;
         cout << "3. Option 3" << endl;
         cout << "Q" << endl;
         cout << "\nEnter your selection: ";
         cin >> selection;

         if (selection == '1')
             cout << "You chose: Option 1" << endl;
         else if (selection == '2') 
              cout << "You chose: Option 2 " << selection << endl;
         else if (selection == '3')
             cout << "You chose: Option 3 " << selection << endl;
         else if (selection == 'Q' || selection == 'q')
             cout << "Goodbye..." << endl;
         else
             cout << "Unknown option -- try again..." << endl;

     } while ( selection != 'q' && selection != 'Q'); // Menu keeps looping as long as the user does not press 'q' or 'Q' and quits

     cout  << endl;
 ```

 #### For Loops

 A for loop allows you to specify the number of times you want to repeat the same code block. It has three statements:

 ```c++

 for (statement 1;statement 2;statement 3){
 // code block
 }
 ```
 * statement 1 is executed once before the execution of the code block.
 * statement 2 defines the condition for executing the code block.
 * statement 3 is executed (every time) after the code block has been executed.

 Examples can be seen below:

 ```c++
  for (int i{} ; i <= 10 ; i++){
         cout << i << endl; // Prints out numbers 0 to 10 
  }       
  for (int i{} ; i <=10 ; i+=2){
         cout << i << endl; // Prints out even numbers between 0 and 10
  }
   for (int i{1}, j{5} ; i<=5 ; i++, j++){
       cout << i << " + " << j << " = " << (i+j) << endl; // Prints out sum of i and j increasing both variables by one each time
   }
 ```

 More examples can be founds [here](Controlling-Program-Flow/For_Loops)

 ##### Range Based For Loops

 A range based for loop automatically executes a for loop over a range. The syntax is as follows:

 ```c++
 for ( range_declaration : range_expression ){ 
     // code block
 }
 ```

 * range_declaration - a declaration of a named variable, whose has the same datatype as the range_expression. The the auto specifier is often used to automatically detect the type.
 * range_expression - any expression that represents a suitable data structure.

 An example can be seen below:

 ```c++

 vector <int> num {1,2,3,4,5,6,7,8,9,10}

 for (auto x : num){
 cout << x << endl; // Prints out the numbers contained within the vector
 ```
 
 ##### Nested Loops

 Loops can also be contained within each other. When loops are "nested" the inner loop does its full iterations for every repitition of the outer loop.
 An example can be seen below:

 ```c++
 for (int num1 {1}; num1 <=10 ; num1++) {
         for (int num2 {1}; num2 <=10; num2++) {
             cout << num1 << " * " << num2 << " = " << num1 * num2 << endl;
         }
         cout << "-----------" << endl; // Prints the multiplication table 
     }
 ```
 
 #### Break & Continue
 
 ##### Break

 The break statement can also be used to jump out of a loop. For example, the code below loops through the values of 1 and 10.
 However, if the value is a multiple of 4, it will break out of the loop.

 ```c++
 for (int i {1} ; i <= 10; i++) {
   if (i % 4 == 0 and i != 0) {
     break;
   }
   cout << i << "\n"; // Displays 0, 1, 2 & 3
 }
 ```
 
 ##### Continue

 The continue statement breaks out of a single iteration of the loop and continues with the next iteration in the loop. For example, the code below will skip multiples of 4.

 ```c++
 for (int i {1} ; i <= 10; i++) {
   if (i % 4 == 0 and i != 0) {
     continue;
   }
   cout << i << "\n"; // Displays 0, 1, 2, 3, 5, 6, 7, 9 & 10
 }
 ```
 
 ### Section 5 Challenge

 This challenge was about allowing the user to select options from a menu to perform operations on the list. Operations include adding a number to a vector, printing its contents, finding the mean of its contents and finding the largest and smallest number. The challenge can be found [here](Controlling-Program-Flow/Challenge)
 
 ### Section 6 - Functions

Functions are blocks of reusable and modular code which take an input, carry out some instructions and produce an output.
The main () function is the function at program startup and designates the start of the program. To call another function, it must be done within main().
Every function has a return type. If a function doesn’t return any value, then void is used as return type. Moreover, if the return type of the function is void, we still can use return statement in the body of function definition by not specifying any constant, variable, etc. with it, by only mentioning the ‘return;’ statement which would symbolise the termination of the function as shown below

 Functions have many advantages:

 * Redundancy - Prevents the need to rewrite code repeatedly to do the same task.
 * Maintenance - If changes need to be made, you only need to go to one place
 * Modularity - Functions make the code modular which improves the readablilty

#### Function Declarations

Before you can use a function you must declare it, else you'll get a compiler error stating that the function was not declared in this scope. 
The function declaration tells the compiler about the number of parameters function takes, datatypes of parameters and return type of function. Putting parameter names in function declaration is optional but it is good practice. 
By placing a function declaration at the top of the program file, you can call the function in the main() function regarless of when the definition of the function resides.

The format of a function declaration is shown below:

 ```c++
 return_datatype function_name(input_datatype input_name, ... );
 ```

An example can be seen below:

 ```c++
 double area(double length);
 ```
 
 #### Function Declaration & Definition

Function declaration and definition can be done at the same time.
The example below is a function that returns the area of a square can be seen below:

 ```c++
 double area(double length){
     return length*length;
 }

 int main(){
     cout << area (5); // Prints out 25 
     return 0;
 }
 ```

 To have the declaration and definition seperate would be done as follows:

 ```c++
 double area(double length);

 int main(){

 cout << area (5); // Prints out 25
 return 0;
 }

 double area(double length){
     return length * length;
 }
 ```

 #### Parameter Passing

 The parameters passed into a function are known as **actual** parameters. Whereas the parameters used by the function are known as **formal** parameters.
 There are two ways to pass parameters into a function:

 * Pass by value
 * Pass by reference

 ##### Pass By Value

In pass by value, the formal parameters are a copy of the actual parameters values Resulting in two types of parameters are stored in different memory locations. Therefore any changes made inside functions are not reflected in the actual parameters.

The function below is pass by value:

```c++
void pass_by_value1(int num) {
    num = 1000;
}
 int main(){

    int num {20};
 
    cout << "num before calling pass_by_value1: " << num << endl; // Prints 20
    pass_by_value1(num); // A copy of the parameter 'num' is made for the function, so the original remains unchanged
    cout << "num after calling pass_by_value1: " << num << endl; // Prints 20
 }
 ```
An example of a temperature conversion program using functions can be found [here](Functions/Temperature_Converter)

 ##### Pass By Reference

In pass by reference, the actual and formal parameters refer to same locations, so changes made to the parameter inside the function are reflected in actual parameter.


```c++
void pass_by_ref1(int &num){
    num = 1000;
}
 int main(){

    int num {20};
 
    cout << "num before calling pass_by_value1: " << num << endl; // Prints 20
    pass_by_ref1(num); // The memory location of the parameter 'num' is used, so the value is modified
    cout << "num after calling pass_by_value1: " << num << endl; // Prints 1000
 }
 ```

The same can also be done using pointers which will be covered later in the [guide]:

```c++
void pass_by_ref1(int *ptr){
    *ptr = 1000;
}
 int main(){

    int num {20};
 
    cout << "num before calling pass_by_value1: " << num << endl; // Prints 20
    pass_by_ref1(&num); // The memory location of the parameter 'num' is passed into the function, so the value is modified
    cout << "num after calling pass_by_value1: " << num << endl; // Prints 1000
 }
 ```

#### Default Arguments

A default argument is a value that is automatically used by the function if the user doesn't specify a value.

An example can be seen below:

```c++

int sum(int a, int b, int c = 0, int d = 0){
    return a + b + c + d;
}

int main(){
    cout << sum(10 + 20) // Prints 30 doesn't need all four arguments as c and d are automatically set to 0
}
```
An example of using default arguments to make a shopping list can be found [here](Functions/Default_Arguments)

#### Overloading Functions

Function overloading is a feature in C++ where two or more functions can have the same name but different parameters.
Function overloading can be considered as an example of polymorphism which will be covered later in the [guide].

An example can be seen below:

```c++
#include <iostream>
#include <string>

using std::string;
using std::cout;
using std::endl;

void print(int num) {
    cout << "Printing int: " << num << endl;
}

void print(string s) {
    cout << "Printing string: " << s << endl;
}

int main(){

int num {10};
string s {"This is a string"};

print(num); // Prints "Printing int: 10"
print(s) // Prints "Printing string: This is a string"

}
```
Another example of overloading functions can be found [here](Functions/Overloading_Functions)

#### Passing Arrays to Functions

Arrays are passed into functions as pointers. Therefore the size of the array must always be passed into the function as a parameter.
An example can be seen below:

```c++

void print_array(const int arr[], size_t size) {
    for (size_t i{0}; i < size; ++i)
        cout << arr[i] << " ";
    cout << endl;
}

int main() {
    int my_scores[] {100, 98, 90, 86, 84};
    
    print_array(my_scores, 5);
    
    return 0;
}
```

#### Recursive Functions

A recursive function is one which calls itself. Recursive algorithms can be used to solve certain problems quite easily.
Each recursive function can be split into two parts:

* Base Case - A easily solved situation that can be answered directly without using recursion. Each recursive algorithm must have at least one base case otherwise it will loop infinitely.

* Recursive Case - The recursive case is the more complicated case of the problem that isn't easy to answer directly, but can be expressed simply with recursion.

For instance the calculation of a factorial of a number can be seen below:

```c++
unsigned long long factorial(unsigned long long n) {
    if (n == 0)
        return 1;	             // base case
    return n * factorial(n-1); // recursive case
}

int main() {
    cout << factorial(3) << endl;       // 6
    cout << factorial(8) << endl;     // 40320
    cout << factorial(12) << endl;   // 479001600
    cout << factorial(20) << endl;   // 2432902008176640000
    return 0;
} 
```
Another example to find the Fibonacci value of a number using recursion can be found [here](Functions/Recursion)

### Section 6 Challenge

This challenge has the same purpose as the previous allowing the user to select options from a menu to perform operations on the list. However, all operations are now done within separate functions. The challenge can be found [here](Functions/Challenge)

### Section 7 - Pointers & References

### Pointers 

A pointer is a variable that can stores the memory address of a variable or function. They are used as they allow data to be access that lies outside the scope.
They also allow memory to allocated dynamically on the heap (will be discussed later). Variables allocated dynamically do not have a name, therefore the only way to access it is through a pointer.

#### Declaring Pointers

The datatype of the pointer must match the data you data you are storing in the address, otherwise you will get a compiler error.
The general declaration of a pointer has the following syntax:

```c++
datatype *ptr_name;
```
Some examples have been shown below:

```c++
int *int_ptr;
char *char_ptr;
string *string_ptr;
```

##### Null Pointers

Uninitialised pointers that aren't set to hold a value can be pointing to any memory address which could be dangerous.
A **null pointer** is the equivalent to initialising a variable to zero. A pointer can be initialised to null via the syntax shown below:

```c++
int *int_ptr{nullptr};
char *char_ptr{nullptr};
string *string_ptr{nullptr};
```

##### Pointer Size

The size of a pointer isn't defined by the datatype it points towards. All pointers in a program are the same size:

```c++
int *int_ptr{nullptr};
char *char_ptr{nullptr};
string *string_ptr{nullptr};

cout << "sizeof of int_ptr is: " << sizeof int_ptr << endl; // 8 bits
cout << "sizeof of char_ptr is: " << sizeof char_ptr << endl; // 8 bits
cout << "sizeof of string_ptr is: " << sizeof string_ptr << endl; // 8 bits
```

#### Assigning Pointers

##### Address Operator

The ampersand symbol '&'is the address operator and returns the address of a variable:

For instance, when used with an integer you get the following:

```c++
int num{5};
cout << "Value of num is: " << num << endl;	// 5	
cout << "sizeof of num is: " << sizeof num << endl; // 4 bits (depends on compiler)
cout << "Address of num is: " << &num << endl; // memory address 0x61fe1c
```

When done with a pointer to an integer you get the following:

```c++
int *p;
    cout << "\nValue of p is: " << p << endl;   // memory address the pointer is pointing to 0x7317a0
    cout << "Address of p is: " << &p << endl; // memory address of the pointer 0x61fe10
    cout << "sizeof of p is: " << sizeof p << endl; // 8 bits (depends on compiler)
    p = nullptr; // Points it nowhere
    cout << "\nValue of p is: " << p << endl; // Prints 0
```

##### Assigning Variables Addresses To Pointers

To assign a variable to a pointer the address operator must be used, as shown below:

```c++
    int val{10};
    double double_val{100.7};
    
    int *val_ptr {nullptr}; // Assigned to 0
    
    val_ptr = &val; // Points pointer to memory address of val
    cout << "Value of val is: " << val << endl; // Prints 10
    cout << "Address of val is: " << &val << endl; // Prints memory address of val e.g. 0x61fe0c
    cout << "Value of val_ptr is: " << val_ptr << endl; // Prints same address as above e.g. 0x61fe0c

    score_ptr = &high_temp;     // Compiler error is datatype doesn't match
```

#### Dereferencing Pointers

Dereferencing is the term used to get the value stored at the memory address of a pointer. 
This is done with the dereference operator '\*', enabling the value of the variable to be changed either by the pointer or by the variable itself.
An example is show below:

```c++
 int val {100};
    int *val_ptr {&val};

    cout << *val_ptr << endl;		// 100

    *val = 200;
    
    cout << *val_ptr << endl;		// 200
    cout << val << endl; 			// 200
```

#### Memory

The memory that a program uses typically uses can be divided into areas:

* Code Segment - This is where the compiled program sits in memory. This segment is typically read-only.
* Call Stack - Where function parameters, local variables, and other function-related information is stored.
* Heap - where dynamically allocated variables are allocated from

##### Call Stack

The call stack  supports the creation, maintenance and destruction of each called function's automatic variables in a last in first out (LIFO) behavior.
Therefore the first function called, is the last function to be popped from the stack. Whereas the last function called is the first to be popped of the stack.

##### The Heap

The heap has advantages and disadvantages:
* Allocating memory on the heap is slower than allocating memory on the stack.
* Allocated memory stays allocated until it is specifically deallocated (beware memory leaks) or the application ends (at which point the OS should clean it up).
* Dynamically allocated memory must be accessed through a pointer. Dereferencing a pointer is slower than accessing a variable directly.
* Because the heap is a big pool of memory, large arrays, structures, or classes can be allocated here.

#### Dynamic Memory Allocation

In the previous sections all memory allocated has been **static** and were determined at compile time residing in the call stack.
However, there are cases when you only know how much memory to allocate during runtime, such as depending on user input. 
On these cases, programs need to dynamically allocate memory which does not come from the program’s limited stack memory.
Instead, it is allocated from a much larger pool of memory managed by the operating system called the heap. On modern machines, the heap can be gigabytes in size.

##### Creating Dynamic Variables
Dynamic memory is allocated using 'new' keyword followed by the datatype of the variable you wish to create. If more than one variable of the same type is to be created the '[]' operator can be used.
The 'new' keyword returns pointer to the memory address of the variable. Or in the case of creating multiple variables, creates a pointer pointing the memory address of the first element.
An example can be seen below:

```c++
// Allocating single values
    int *int_ptr1 {new int}; // Allocate int on the heap
    *int_ptr1 = 7;
    cout << *int_ptr << endl; // Prints out 7, the value of the integer on the heap 
    
    int *int_ptr2 {new int{7}}; // Allocates int on the heap and sets it to 7
    cout << *int_ptr << endl; // Prints out 7, the value of the integer on the heap
    
 // Allocating multiple values   
    int size{0};
    int *value_ptr {nullptr};
    
    cout << "How many values? ";
    cin >> size;
    
    value_ptr = new int[size];    // Allocate the storage on the heap equal to the number the user entered
    cout << value_ptr << endl;       // Memory address of the first value
```

When the dynamically allocated variable is no longer needed, C++ must be told explicitly to free the memory for reuse. For single variables, this is done via 'delete' operator.

The delete operator does not actually delete anything. It simply returns the memory being pointed to back to the operating system. The operating system is then free to reassign that memory. Although it looks like the variable is being deleted this is not actually the case. The pointer variable still has the same scope as before, and can be assigned a new value just like any other variable.
Using the previous example:

```c++
    int *int_ptr {new int{7}}; // Allocate int on the heap
    cout << int_ptr << endl; // Prints out memory address e.g 0x1e18b0
    delete int_ptr; // Release memory
    
    int_ptr = new int; // Pointer can be reallocated with no issue
    cout << int_ptr << endl; // prints out memory address does not necessarily have to be the same address as before
    delete int_ptr; // Release memory again
```

**Note that deleting a pointer that is not pointing to dynamically allocated memory may cause bad things to happen.**

A pointer that is pointing to deallocated memory is called a dangling pointer. dereferencing or deleting a dangling pointer will lead to undefined behavior. Consider the following program:

```c++
    int *ptr{ new int }; // dynamically allocate an integer
    *ptr = 7; // put 7 in that memory location
 
    delete ptr; // return the memory to the operating system.  ptr is now a dangling pointer.
 
    std::cout << *ptr; // dereferencing deallocated dangling pointer will cause undefined behavior
    delete ptr; // trying to deallocate the memory again will also lead to undefined behavior.
```
There are cases where deallocating memory can produce multiple dangling pointers:

```c++
#include <iostream>
 
int main()
{
    int *ptr{ new int{} }; // dynamically allocate an integer
    int *otherPtr{ ptr }; // otherPtr is now pointed at that same memory location
 
    delete ptr; // return the memory to the operating system.  ptr and otherPtr are now dangling pointers.
    ptr = nullptr; // ptr is now a nullptr
 
    // however, otherPtr is still a dangling pointer!
 
    return 0;
}
```

There are a few best practices to prevent dangling pointers

Firstly, it is best to avoid having multiple pointers point at the same piece of dynamic memory. If this is not avoidable, it is best to be clear about which pointer “owns” the memory (and is responsible for deleting it) and which are just accessing it. How to do this will be discussed later

Second, a pointer is deleted, if that pointer is not going out of scope immediately, set the pointer to nullptr.

##### Memory Leaks

Dynamically allocated memory stays allocated until it is explicitly deallocated or until the program ends (Assuming your operating system does that). However, the pointers used to hold dynamically allocated memory addresses follow the normal scoping rules for local variables and will be destroyed when out of scope.

An example is shown below:

```c++
void function()
{
    int *ptr{ new int{} };
}
```
In this function an integer is allocated memory dynamically, but never frees it using delete. Because pointers variables are just normal variables, when the function ends the pointer will be delete. Because 'ptr' is the only variable holding the address of the dynamically allocated variable, there are ways to access the dynamically allocated memory. As a result, this dynamically allocated integer can not be deleted. This is called a **memory leak**.

Memory leaks happen when your program loses the address of some bit of dynamically allocated memory before giving it back to the operating system. When this happens, your program can’t delete the dynamically allocated memory, because it no longer knows where it is. The operating system also can’t use this memory, because that memory is considered to be still in use by your program.

Although forgetting to delete a pointer can cause a memory leak. There are other ways to achieve it:

```c++
int value = 5;
int *ptr{ new int{5} }; // Allocates memory dynamically
ptr = &value; // Address of new int lost - memory leak
```

This can be rectified by deleting the ptr before reusing, telling the OS that the memory address can be used.

```c++
int value{ 5 };
int *ptr{ new int{} }; // Allocates memory dynamically
delete ptr; // deallocates memory memory back to OS
ptr = &value; // reassign pointer to address of value
```

In summary, it is important to delete a pointer when it is no longer needed.

#### Pointers & Arrays

The value of an array is the address of the first element. Similarly, the value of a pointer is an address.
Therefore if a pointer is of the same datatype as the array and points to it. Then the pointer and the array name can be used interchangeably.

Here is an example using an array as a pointer:

```c++

int values [] {1,2,3}; // Declare an array of three elements

cout << values << endl; // Prints out address of first element e.g 0x6ffe14
cout << *values << endl; // Prints out element at first address '1'

int *val_ptr {values};

cout << val_ptr << endl; // Prints out same address as 'values' e.g 0x6ffe14
cout << *val_ptr << endl; // prints out same element '1'
```

As they are essentially interchangable the elements in an array can be accessed with subscript notation, either through the pointer or the array name as shown below:

```c++

int values [] {1,2,3}; // Declare an array of three elements
int *val_ptr {values};

cout << "\nArray subscript notation -------------------------" << endl;
    cout << values[0] << endl;
    cout << values[1] << endl;
    cout << values[2] << endl;
    
    cout << "\nPointer subscript notation -------------------------" << endl;
    cout << val_ptr[0] << endl;
    cout << val_ptr[1] << endl;
    cout << val_ptr[2] << endl;
```
More examples can be found [here](Pointers-&-References/Arrays_&_Pointers)

#### Pointer Arithmetic

In C++ pointers can also be used in arithmetic and comparison expressions. However they can only be done on a raw array.

##### Arithmetic Expressions

A limited set of arithmetic operations can be performed on pointers. A pointer may be:

* Incremented - Points to the next element in an array '++'
* Decremented - Points to the previous element in an array '—'
* Addition - Increments the integer by the size of the datatype of the pointer '+ or +='
* Subtraction - Decrements the integer by the size of the datatype of the pointer '– or -='

An example can be seen below:

```c++
// Incrementation
    int values[] {100, 95, 89, 68, -1};
    int *val_ptr {scores};
    
    while (*val_ptr != -1) { 
        cout << *val_ptr << endl; // Prints out 'values' until it reaches '-1' {100,95,89,68}
        val_ptr++; // Increments the address of the pointer by the size of an integer
    }
    
    // The example above could also be written as
    cout << "\n-------------------------" << endl;
    score_ptr = scores;
    while (*score_ptr != -1){
        cout << *score_ptr++ << endl; // Same as *(score_ptr++)
    }

// Addition

    while (*score_ptr != -1) {
        cout << *score_ptr << endl; // Prints out values until it reaches '-1' {100,89}
        score_ptr += 2; // Increments the pointer by the size of two integers
    }
````

###### Subtracting Pointers

Pointers can also be subtracted from each other provided they point to the same dataset. This gives the number of elements between the two pointers as shown below:

```c++
    char name[]  {"Rikki"};
    
    char *char_ptr1 {nullptr};
    char *char_ptr2{nullptr};
    
    char_ptr1 = &name[0];   // R
    char_ptr2 = &name[3];   // K

    cout << "In the string " << name << ",  " 
         << *char_ptr2 << " is " << (char_ptr2 - char_ptr1) 
         << " characters away from " <<  *char_ptr1  << endl;  // Prints that K is '3' characters away from R
```
##### Comparison Expressions

The equality operator '==' can be used to compare two pointers. However, this refers to the memory locations of the two pointers and not the values that the pointers reference. An example can be seen below:

```c++
    string s1 {"Rikki"};
    string s2 {"Rikki"};
    string s3 {"James"};

    string *p1 {&s1};		
    string *p2 {&s2}; // Different memory address as 'p1' but pointer references the same value
    string *p3 {&s1}; // Same memory address as 'p1'

    cout << p1 << "==" << p2 << ": " << (p1 == p2) << endl;		// Prints false
    cout << p1 << "==" << p3 << ": " << (p1 == p3) << endl;		// Prints true
```

The pointers must be dereferences in order to compare their values:

```c++
    string s1 {"Rikki"};
    string s2 {"Rikki"};
    string s3 {"James"};

    string *p1 {&s1};		
    string *p2 {&s2}; // Different memory address as 'p1' but pointer references the same value
    string *p3 {&s1}; // Same memory address as 'p1'

    cout << *p1 << "==" << *p2 << ": " << (*p1 == *p2) << endl;		// true
    cout << *p1 << "==" << *p3 << ": " << (*p1 == *p3) << endl;		// true
```

#### Const Pointers

The are multiple ways to use the 'const' keyword with pointers to make them read-only. In the example below, the data the pointer points to is constant and cannot be changed. However, the value of the pointer (address) can be changed.

```c++
int high_num {70};
int low_num {25};

const int *num_ptr {&high_num};

*num_ptr = 95; // Compiler error, value is read-only
num_ptr = &low_num; // Works fine
```

In the next example the data the pointer points to can by changed, but the address referenced by the pointer cannot change.

```c++
int high_num {70};
int low_num {25};

int const *num_ptr {&high_num};

*num_ptr = 95; // Works fine
num_ptr = &low_num; // Compiler error, value is read-only
```

Finally, in this example neither the data the pointer points to nor the address the pointer references can be changed.
```c++
int high_num {70};
int low_num {25};

const int const *num_ptr {&high_num};

*num_ptr = 95; // Compiler error, value is read-only
num_ptr = &low_num; // Compiler error, value is read-only
```

#### Passing Pointers To Functions

Pointers can also be used to pass by reference. The example below is used to double the value of the data passed in. The first asterix is used to dereference the pointer, while the second is used to multiply.

```c++
    void double_data(int *int_ptr) {
   *int_ptr *= 2;	
}

int main() {
    int value {10};
    int *int_ptr {nullptr};
    
    cout << "Value: " << value << endl; // Prints 10
    double_data(&value);
    cout << "Value: " << value << endl; // Prints 20
```
More examples on passing pointers into functions can be found [here](Pointers-&-References/Passing_Pointers_1) and [here](Pointers-&-References/Passing_Pointers_2)

#### Returning Pointers From Functions

In C++ functions can also return pointers by specifying the pointer type in the function declaration.

An example can be seen below:

```c++

int *largest_int (int *ptr1, int *ptr2){
    if (*ptr1 > *ptr2)
        return ptr1;
    else
        return ptr2;
}

int main(){

int a {10};
int b {20};

int *largest_ptr {nullptr};

largest_ptr = largest_int(&a, &b); // Sets the address of largest pointer to the memory location of 'b'.
cout<< *largest_ptr << endl; // Prints 200

return 0;
}
```
This can also be uses in conjunction with dynamic memory allocation. The  example [here](Pointers-&-References/Returning_Pointers) shows how to allocate memory dynamically within a function and returns its address.

Pointers pointing to local variables in a function should never be returned as they are deleting once out of scope. Here is an example of what not to do.

```c++
int *avoid_this(){

    int num {};
    
    return &num;
```

```c++
int *avoid_this_too(){

    int num {};
    int *num_ptr {&num};
    return num_ptr;
```

#### References

A reference is an alias for a variable, meaning itbecomes an alternative name for an existing variable. A variable can be declared as a reference by putting ‘&’ in the declaration. A benefit of using a reference if the variable is passed without reference, a new copy of it is created which causes wastage of CPU time and memory.

There are a few points that differentiate a pointer from a reference:

* A reference must be initialised to a variable when declared
* A reference cannot be nuk
* Once initialised it cannot be used to refer to another variable

Here is an example of a range based for loop that doesn't use references, during the loop a copy is made and therefore the original vector remains unchanged:

```c++
vector <string> colours {"Red", "Yellow" , "Blue"};

for (auto col : colours)
    col = "Purple"; // Only changes a copy of the vector
    
for (auto col : colours)
    cout << col << endl; // Prints "Red Yellow Blue"
```

To actually make changes in the vector, a reference can be used as shown below:

```c++
vector <string> colours {"Red", "Yellow" , "Blue"};

for (auto &col : colours)
    col = "Purple"; // Changes the actual values
    
for (auto const &col : colours)
    cout << col << endl; // Prints "Purple Purple Purple"
```
More examples on references can be found [here](Pointers-&-References/References)

### Section 7 Challenge

This challenge contains a function that two arrays of integers and their sizes and dynamically allocates a new array of integers whose size is the product of the 2 arrays.
The function also loops through the first and second arrays and multiplies each element, storing the product in the newly created array and returning a pointer to the newly allocated array. The challenge can be found [here](Pointers-&-References/Challenge)

### Section 8 - OOP (Classes & Objects)

OOP stands for Object-Oriented Programming.

Procedural programming is what has been covered until now; writing procedures or functions that perform operations on the data. However, object-oriented programming is about creating objects that contain both attributes and methods.

Object-oriented programming has several advantages over procedural programming:

* OOP is faster and easier to execute
* OOP provides a clear structure for the programs
* OOP helps to prevent code repition and makes the code easier to maintain, modify and debug
* OOP makes it possible to create full reusable applications with less code and shorter development time

The building block of C++ that leads to Object-Oriented programming is a 'class'. It is a user-defined data type that works as an object constructor, holding its own attributes and methods, accessible and useable by creating an instance of that class. A class is like a blueprint for an object and when an object is created, it inherits all the variables and functions from the class.

For example: in real life, a car is an object. The car has attributes, such as weight and color, and methods, such as drive and brake.
Attributes and methods are basically variables/data and functions that belongs to the class. These are often referred to as "class members".

### Classes

The syntax to create a class in C++ uses the 'class' keyword as shown below:

```c++
class Class_Name{

// delaration(s)

};
```
An example of a class can be seen below:

```c++
class Player{

// attributes

    std::string name;
    int health;
    int xp;

// methods

    void talk (std::string text){
         cout << name << " says " << text << endl;
    }
    bool is dead();
};
```
Once the class has been created, objects can be created using instances of that class.

#### Creating Objects

An object can be created using the regular method to create primitive datatypes

```c++
// Creating Instance of Player Class
Player hero;

// Creating Player Object on the heap
Player *enemy = new Player();
delete enemy;
```

#### Accessing Class Members

There are two ways to access class attributes and methods, either through the '.' operator or the '->' operator. Some class members may not be accessible since they can be hidden.

The example below shows how to access class members using the '.' and the '->' operator:

```c++
//
Player rikki
rikki.name = "Rikki";
rikki.health = 0;
rikki.xp = 12;
rikki.talk("Hi there"); // Prints "Rikki says Hi there"

Player *enemy = new Player;
// Pointer must be dereferenced before the member can be called
(*enemy).name = "Enemy";
(*enemy).health = 100;

// or the '->' operator can be used
enemy->xp = 15;
enemy->talk("Prepare to Meet Your Maker!");
delete enemy;
```
Another example on creating classes can be found [here](OOP/Accessing_Class_Members)

#### Class Access Specifier

C++ has three basic class member access specifiers:

* public - accessible everywhere
* private - only accessible by members or friends of the class
* protected - used with inheritance which will be covered later

They are declared in the body of the class and everything declared underneath the specified access modifier will have that access modifier applied to it. The syntax can be seen below:

```c++

class Class_Name
{
public:
// delarations

// Private is the default if no access modifier is specified
private:
// declarations

protected:
// declarations
};
```
An example of using the public and private specifiers are shown below:

```c++
class Player{

// Only accessible from other members and from friends of the class
private:
std::string name;
int health;
int xp;
// Accessible anywhere
public:
void talk(std:: string text);
bool is_dead();
};
```

Trying to directly access a private access member results in a compiler error 

#### Implementing Member Methods

Implimenting member methods is very similar to implementing functions. Also, as methods have access to member attributes, they do not need to be passed in arguments.

Member methods can be written inside or outside of the class declaration. If written inside, they are implicitly inline which speeds up the program. Although this is fine when the method is small, larger methods are best implemented outside of the class declaration. To do this the scope resolution operator '::' needs to be used as shown below:

```c++
Class_name::method_name
```
The implementation and delaration are normally stored seperately, to make it easier to manage. The declaration is stored in an include file/header file with the '.h' extension. While the implementation is in a '.cpp' file.

An example of class declaration and implementation being done together is shown below:

```c++
class Account{
private:
    double balance;
public:
    void set_balance(double bal){
        balance = bal;
    }
    double get_balance(){
        return balance;
    }
};
```

To implement the methods outside of the class declaration the scope resolution operator is used '::'.

```c++
// Account.h file
#pragma once // Ensures file is only included by only one cpp file 
class Account{
private:
    double balance;
public:
    void set_balance(double bal);
    double get_balange();
};

// Account.cpp file
#include "Account.h"

void Account::set_balance(double bal){
        balance = bal;
}

double Account::get_balance(){
        return balance;
}


// Main.cpp

#include <iostream>
#include "Account.h"

using namespace std;

int main(){

Account rikki_account;
rikki_account.set_balance(1000.00);
double bal = rikki_account.get_balance();

cout << bal << endl // Prints '1000'
return 0;
}
```

Some more examples of implementing class methods can be found [here](OOP/Implementing_Methods)

### Constructors and Destructors

#### Constructors

Constructors are special member methods that are invoked during object creation that have the same name as the class, are useful for initialisation and can be overloaded. An example can be seen below:

```c++

class Player{

private:
    std::string name;
    int health;
    in xp;
public:
// Overloaded Constructors
    Player();
    Player(std::string name);
    Player(std::string name, int health, int xp);
}; 
```

##### Overloading Constructors

Classes can have as many constructors as necessary. However, each must have its own unique signature so the compliler knows which one to use. A example is shown below:

```c++
Player::Player(){
    name = "None";
    health = 0;
    xp = 0;
}

Player::Player(std::string name_val){
    name = name_val;
    health = 0;
    xp = 0;
}
```

##### Initialisation Lists

Constructor initialisation lists are more efficient and initialises data members as soon as the object is created. An example is shown below:

```c++

// Previous method

Player::Player(){
    name = "None"; // assignment not initialisation
    health = 0;
    xp = 0;
}

// Better method
Player::Player()
    :name{"None"}, health {0}, xp {0} {
}
```

##### Delegating Constructors

The code for various constructors is often very similar and duplicated code often leads to errors. C++ allows deligating which allows one constructor to call another in the **initialisation** list. The sytanx is as follows:

```c++
Player::Player(std::string, int health_val, int xp_val)
    :name{name_val}, health {health_val}, xp {xp_val} {
}

Player::Player()
    :Player{"None",0,0}{ // Calls three args constructor with data needed
}

Player::Player(std::string name_val)
    :Player{name_val,0,0}{ // Calls three args constructor with data needed
}
```

##### Default Constructor

A default constructor also known as the 'no-args constructor' doesn't expect any arguments. If a no-args constructor has not been written then C++ will automatically generate one. However, a default constructor is no longer automatically generated once another constructor has been declared. It is best practice to define a default constructor otherwise the parameters will contain garbage data.

An example can be seen [here](OOP/Default_Constructors)

##### Default Constructor Parameters

Default value can also be used for class constructor and methods, often reducing the number of overloaded constructors needed. The three constructors shown in 'delegating constructors' example can be replaced by a single constructor, an example is shown below:

```c++

Player::Player(std::string = "None", int health_val = 0, int xp_val = 0){
 : name{name_val}, health{health_val}, xp{xp_val} {
}
```

#### Copy Constructors

When objects are copied, C++ must create an new object from an existing object. A copy is made due to the reasons below:

* Passing an object by value as a parameter
* Returning an object from a function by value
* Constructing one object based on another of the same class

An example of the passing by value use case can be seen below:

```c++
Player rikki {"Rikki",100,20};

void display_player(Player p){
// p is a copy of 'rikki' in this example
// p will be used
// A destructor will be called for p
}
```

An example of returning an object by value can be seen below:

```c++

Player enemy;

Player create_boss(){
    Player boss{"Boss",1000,1000};
    return boss; // A copy of boss is returned
}

enemy = create_boss();
```

Finally the use case example of constructing one object based on another can be seen below:

```c++
Player hero{"Hero",100,100};

Player another_hero {hero}; // A copy of hero is made
```

Copy constructors can be user defined or the C++ compiler will create a compiler generate a default one which does memberwise copy. Copying the attributes from the source object to the copy object, if a attribute is an object, then it's copy constructor will be called. This is fine for most use cases. However, if raw pointers are used then only the pointer will be copied - not what it's pointing to. This is referred to a shallow copy as opposed to a deep constructor

Below are a list of best practices:

* Always provide a copy constructor if the class has a raw pointer
* Provide the copy constructor with a const reference parameter
* Use STL classes as they already provide copy constructors
* Avoid using raw pointer data members if possible

##### Declaring Copy Constructors

The syntax for copy constructors can be seen below:

```c++

Player::Player(const Player &source);
Account::Account(const Account &source);
````
The syntax can be a bit confusing, but makes sense when you break it down.
Its a constructor, so it has the same name as the class, and in the parameter list is a single object passed in of the same type. It is passed in as a reference and constant. If it wasn't passed in by reference, then a copy would have to be made - which is the whole point of the copy constructor, this would defeat the purpose and end up with infinite recursive calls. The constant prevents any modification for the original object.

##### Implementing the Copy Constructor

The body of the copy constructor contains anything that is needed to initialise the new object. All members of it can be accessed as 'source' is an input. Initialisation lists can be used instead of assignment as shown below:


```c++
Player::Player (const Player &source)
: name {source.name}, health {source.health}, xp {source.xp} {
}

Account::Account (const Player &source)
: name {source.name}, balance {source.balance}{
}
```

An example of using copy constructors can be seen [here](OOP/Copy_Constructors)

##### Shallow Copying

A shallow copy is the default behaviour provided by the compiler generated copy constructor. If the object being copied has a raw pointer, this results in the original and copy object both pointing to the same memory address in the heap. When one of those objects are destroyed and its destructor is called, the dynamicalled allocated storage is released. However, the other area still points to the same address.

An example of the issues with shallow copies can be seen below:

```c++
class Shallow{

private:
    int *data; // Pointer 
public:
    Shallow (int d); // Constructor
    Shallow(const Shallow &source); // Copy constructor
};

Shallow::Shallow(int d){
data = new int; // allocate storage
*data = d
}

Shallow::~Shallow(){
delete data; // Free storage
}

Shallow::Shallow(const Shallow &source)
: data(source.data) 
// Only the pointer is copied - not what it is pointing too, 'source' and new object both point to same data area
{
}

int main(){

    Shallow obj1 {100};
    display_shallow(obj1); // A copy of obj1 has been made, at the end of the function, the data will be released. So obj1 will be pointing to invalid memory
```
##### Deep Copying

Deep copying creates a copy of the pointed-to data. This usually means data must be allocated and then perform the copy. You always want to perform a deep copy when using raw pointers. A example is shown below:


```c++
class Deep{

private:
    int *data;
public:
    Deep(int d);
    Deep(const Deep &source)
    ~Deep();
};

Deep::Deep(int d){
   data = new int;
   *data = d;
}

Deep::~Deep(){
delete data; // Free storage
}

Deep::Deep(const Deep &source){
deep = new int;
*data = *source.data;
// Creates new storage and copy values
}

// Delegating Constructor
Deep::Deep(const Deep &source){
: Deep {*source.data}{ // Delegating to constructor that expects an integer
}
```

More examples on deep copying can be found [here](OOP/Deep_Copying)

#### The 'this' Pointer

'this' is a reserved keyword that contains the address of the object - so its a pointer to the object that is currently being used. However, 'this' can only be used within the scope of the class. It's uses are listed below:

* Used to access data members and methods - all member access is actually done via the 'this' pointer
* Can be used to determine if two objects are the same
* Can be dereferenced '\*this' to yield the current object
* Can be used to disambiguate identifiers

An example to see if two objects are the same can be seen below:

```c++

int Account::compare_balance(const Account &other){
    if(this == &other)
        cout  << "These are the same objects" << endl;
}
```

An example of using the 'this' parameter to disambiguate an identifier is shown below:

```c++
void Account::set_balance (double balance){
    balance = balance; // Which balance? - ambiguous
}

void Account::set_balance (double balance){
    this->balance = balance; // unambiguous
}
```
#### Using const with Classes

C++ can also be used to create const objects, this means their attributes cannot change. But if member functions are called on 'const' objects you'll receive a compiler error as the function may be able to change some of the objects attributes. This can be corrected by using the 'const' keyword to tell the compiler that certain methods will not change any object attributes.

An example of trying to use member methods on const objects is shown below:

```c++
const Player villain {"Villain",100,55};
void display_name(const Player &p){
  cout << p.get_name() << endl;
}

display_name(villain); // Compiler Error - get_name could potentially change the object
```
An example of how to correct the error can be seen below:

```c++

class Player{

private:
// attributes
public:
   stf::string get)name () const;
// Other methods
};
```

More examples on const objects can be seen [here](OOP/Const_In_Classes)

#### Static Class Members

A C++ class can have static data members, this means that single data member belongs to the class, and not the objects. This is a useful way to store class-wide information. They are independent of any objects and can be called using the class name. An example showing how to determine the number of 'player' objects created from the 'Player' class is shown below:

```c++
class Player{
private:
    static int num_players;
public:
    static int get_num_players();
};
```

As the function 'get_num_players()' is static, it only has access to 


#### Friends of a Class

A friend is a function or class that has access to a private class member when the function or class is not a member of the class it is accessing.

* Friendship must be granted not taken
  * Friendship must be declared explicitly in the class that is granting friendship with the keyword 'friend'
* Friendship is not symmetric - A being a friend of B, does not make B a friend of A.
* Friendship is not transitive - A being and friend of B, while B is a friend of C, does not make A a friend of C.

The example below shows the syntax to grant friendship to a function:

```c++
class Player{
friend void display_player(Player &p);
std::string name;
int health;
int xp;

public:
// declarations
};

void display_player(Player &p){
    cout << p.name << endl; // Can directly access class members
    cout << p.health << endl;
    cout << p.xp << endl;
}
// The function can also change private data members
```
The example below shows a member function of another class being granted friendship: 

```c++
class Player{
friend void Other_class::display_player(Player &p);
std::string name;
int health;
int xp;

public:
// declarations
};

class Other_class{
public:
void display_player(Player &p){
    cout << p.name << endl; // Can directly access class members
    cout << p.health << endl;
    cout << p.xp << endl;
}
};
// The function can also change private data members
```

Finally an entire class can be granted friendship, as shown below:

```c++
class Player{
friend  Other_class; // All methods on 'Other_class' can access all attributes in 'Player' class
std::string name;
int health;
int xp;

public:
// declarations
};
```
#### Structs vs Class

In addition to declaring a 'class', you can also declare a 'struct'. They are near identical, however, struct members are **public** by default.

##### General Guidelines

* Use structs for passive objects with public access - just used to hold data
* Don't declare methods in struct

* Use classes for active objects with private acess
* Implement getters/setters as needed
* Implemenet member methods as needed
#### Destructors

Destructors also special member methods that have the same name as the class. However, descructors have a tilde '~' proceding their name. They are automatically invoked when an object is destroyed and only one is allowed per class. Therefore they cannot be overloaded, they are useful to release memory and other resources.

An example can be seen below:

```c++

class Player{

private:
    std::string name;
    int health;
    in xp;
public:
// Overloaded Constructors
    Player();
    Player(std::string name);
    Player(std::string name, int health, int xp);
// Destructor
~Player();
}; 
```

Therefore objects can be created using the example below:

```c++

Player rikki; // 0 arg constructor called


Player jocelyn("Jocelyn"); // 1 arg constructor called

Player james ("James",100,10); 

// After the objects are used and go out of scope - 3 destructors are called

// Constructors and Descructors can also be used with pointers and dynamic memory allocation

Player *enemy = new Player("Boss",1000,0); // 3 arg constructor called
delete enemy; // Destructor called
```

### Section 8 Challenge


---
day: 1
title: "Refresher to C programming"
description: "basic syntax, operators and expressions, Conditional Statements, Loops, Scope and Lifetime of Variables and Errors"
---

# Day 1 - Refresher to C Programming
<!-- Course content goes here -->
## Setting up the Environment
Installing a compiler: [GCC (MinGW)](https://sourceforge.net/projects/mingw/files/Installer/)

Install an IDE/Editor : [Visual Studio Code](https://code.visualstudio.com/download)

***Note:***: If `gcc` isn't recognized as a command, make sure that you've added its **bin** folder's path as an environment variable.

## Basic Syntax and Structure:  
1. **Preprocessor Directives:** Preprocessor directives are lines included in the code that are not program statements but instructions for the preprocessor. They begin with the # symbol. The most common preprocessor directive is `#include`. 

    *Example:* `#include<stdio.h>`, `#define PI 3.142`
2. **main() Function:**  Every C program must have a main function. This is the entry point of the program where execution begins.
```c
#include<stdio.h>
void main(){
    //your code here
}
``` 
3. **Statement Termination with `;`:** In C, each statement must end with a semicolon (`;`). This tells the compiler that the statement is complete.
```c
printf("Hello");
//semicolon marks the end of the statement
```
4. **Comments:** Comments are used to explain the code and are ignored by the compiler. They make the code more readable.
```c
//This is a single line comment
printf("Hello");
/*
This is a
multiline comment
*/
printf("There");
```
## Writing and running the first program ("Hello, World!")
```c
#include<stdio.h> //standard input-output header
void main(){
    printf("Hello World"); //simple print statement
}
```
##  Variables and Data Types: Integers, floats, characters, and basic I/O functions
Variables are used to store data. Each variable must be declared with a specific data type.  
`int`: Integer type  
`float`: Floating-point type  
`char`: Character type  
`double`: Long-floating-point type  
`void`: void type  
```c
int num = 10;        // Integer variable
float price = 9.99;  // Floating-point variable
char grade = 'A';    // Character variable
```
6. Input and Output  
C provides standard functions to take input and display output.  
`printf`: Used to print output to the screen.  
```c
printf("Hello, World!\n");
```
`scanf`: Used to take input from the user.  
```c
int n;
scanf("%d",&n);
```
Here `%d` is the format specifier used for integer datatype.
Some other format specifiers are
* `%f` -float
* `%c` -char
* `%lf` - long float/double
* `%s` - string/character_array

# Operators and Expressions

## Arithmetic Operators

Arithmetic operators are used to perform basic mathematical operations.

### Addition
```c
int a = 5;
int b = 3;
int sum = a + b;
printf("Sum: %d\n", sum);  // Output: Sum: 8
```

### Subtraction
```c
int a = 5;
int b = 3;
int difference = a - b;
printf("Difference: %d\n", difference);  // Output: Difference: 2
```

### Multiplication
```c
int a = 5;
int b = 3;
int product = a * b;
printf("Product: %d\n", product);  // Output: Product: 15
```

### Division
```c
int a = 6;
int b = 3;
int quotient = a / b;
printf("Quotient: %d\n", quotient);  // Output: Quotient: 2
```

### Modulus
```c
int a = 5;
int b = 3;
int remainder = a % b;
printf("Remainder: %d\n", remainder);  // Output: Remainder: 2
```

## Relational and Logical Operators

### Relational Operators

Relational operators are used to compare two values.

```c
int a = 5;
int b = 3;

printf("%d\n", a == b);  // Output: 0 (false)
printf("%d\n", a != b);  // Output: 1 (true)
printf("%d\n", a > b);   // Output: 1 (true)
printf("%d\n", a < b);   // Output: 0 (false)
printf("%d\n", a >= b);  // Output: 1 (true)
printf("%d\n", a <= b);  // Output: 0 (false)
```

### Logical Operators

Logical operators are used to combine multiple conditions.

```c
int a = 5;
int b = 3;
int c = 5;

printf("%d\n", (a > b) && (a == c));  // Output: 1 (true)
printf("%d\n", (a < b) || (a == c));  // Output: 1 (true)
printf("%d\n", !(a == c));            // Output: 0 (false)
```

## Increment and Decrement Operators

Increment and decrement operators are used to increase or decrease the value of a variable by one.

### Increment
```c
int a = 5;

a++;  // Postfix increment
printf("a: %d\n", a);  // Output: a: 6

++a;  // Prefix increment
printf("a: %d\n", a);  // Output: a: 7
```

### Decrement
```c
int a = 5;

a--;  // Postfix decrement
printf("a: %d\n", a);  // Output: a: 4

--a;  // Prefix decrement
printf("a: %d\n", a);  // Output: a: 3
```

## Assignment Operators

Assignment operators are used to assign values to variables.

### Basic Assignment
```c
int a = 5;
```

### Compound Assignment
```c
int a = 5;

a += 3;  // Equivalent to a = a + 3
printf("a: %d\n", a);  // Output: a: 8

a -= 2;  // Equivalent to a = a - 2
printf("a: %d\n", a);  // Output: a: 6

a *= 2;  // Equivalent to a = a * 2
printf("a: %d\n", a);  // Output: a: 12

a /= 3;  // Equivalent to a = a / 3
printf("a: %d\n", a);  // Output: a: 4

a %= 3;  // Equivalent to a = a % 3
printf("a: %d\n", a);  // Output: a: 1
```

## Type Casting and Type Conversion

Type casting and conversion allow you to change a variable's data type.

### Implicit Type Conversion
Automatically performed by the compiler when necessary.

```c
int a = 5;
float b = 2.5;
float result = a + b;  // a is implicitly converted to float
printf("Result: %.2f\n", result);  // Output: Result: 7.50
```

### Explicit Type Casting
Manually performed by the programmer.

```c
int a = 5;
int b = 2;
float result = (float)a / b;  // a is explicitly cast to float
printf("Result: %.2f\n", result);  // Output: Result: 2.50
```

## Conditional Statements

### if Statement
The `if` statement is used to execute a block of code if a condition is true.
```c
if (condition) {
    // code to be executed
}
```

### else-if Statement
The `else if` statement is used to check another condition if the initial condition is false.
```c
if (condition1) {
    // code to be executed if condition1 is true
} else if (condition2) {
    // code to be executed if condition1 is false and condition2 is true
}
```

### else Statement
The `else` statement is used to execute a block of code if all conditions are false.
```c
if (condition1) {
    // code to be executed if condition1 is true
} else if (condition2) {
    // code to be executed if condition1 is false and condition2 is true
} else {
    // code to be executed if all conditions are false
}
```

### switch Statement
The `switch` statement is used to execute a block of code based on the value of a variable.
```c
switch (variable) {
    case value1:
        // code to be executed if variable == value1
        break;
    case value2:
        // code to be executed if variable == value2
        break;
    default:
        // code to be executed if variable does not match any value
        break;
}
```

## Loops

### for Loop
The `for` loop is used to execute a block of code repeatedly for a specified number of times.

```c
for (initialization; condition; increment) {
    // code to be executed
}
```

### while Loop
The `while` loop is used to execute a block of code repeatedly while a condition is true.

```c
while (condition) {
    // code to be executed
}
```

### do-while Loop
The `do-while` loop is used to execute a block of code repeatedly while a condition is true.

```c
do {
    // code to be executed
} while (condition);
```

## Scope and Lifetime of Variables

### Scope
Scope refers to the region of the program where a variable is accessible.

- **Local Scope:** Variables declared inside a function are local to that function.
- **Global Scope:** Variables declared outside any function are global and accessible by any function.

### Lifetime
Lifetime refers to the duration for which a variable exists in memory.

- **Automatic (local) variables:** Exist only within the function they are defined.
- **Static variables:** Retain their value between function calls and exist for the lifetime of the program.

### Local Variables in Blocks
Local variables can be declared within blocks of code other than functions, such as if statements, while loops, and for loops. These variables are only accessible within the block they are declared in.

```c
if (condition) {
    int local_var = 10; // Local variable
    // code to be executed
}
```
```c
for (int i = 0; i < 10; i++) {
    int local_var = 20; // Local variable
    // code to be executed
}
```
Note that these local variables are created and destroyed each time the block is executed.
```c
#include <stdio.h>

int main() {
    for (int i = 0; i < 10; i++) {
        int local_var = 20; // Local variable
        printf("Local variable: %d\n", local_var);
    }
    return 0;
}
```

### Variable Overiding
If there exist 2 variables with the same name, one in local scope and the other in global scope. The local scope will always have higher priority.
```c
#include <stdio.h>
int i = 30;                         // Global variable

int main() {
    printf("global version of i: %d\n", i);
    for (int i = 0; i < 10; i++) {  // Local variable 1
        printf("\tfor loop's version of i: %d\n", i);
        if (i < 5) {
            int i = 0;              // Local variable 2
            printf("\t\tif blocks's version of i: %d\n", i);
        }
        printf("\tfor loop's version of i: %d\n", i);
    }
    printf("global version of i: %d\n", i);
    return 0;
}
```

## Errors - Types and Definitions
In programming, errors can be classified into several types. Understanding these types is crucial for effective debugging and error handling.

### Syntax Errors
Syntax errors occur when the code violates the programming language's syntax rules. These errors are typically detected by the compiler or interpreter.
```c
// Syntax error example: missing semicolon
int x = 5
```

### Semantic Errors
Semantic errors occur when the code is syntactically correct but does not make sense in the context of the program. These errors can be detected by the compiler or at runtime.
```c
// Semantic error example: assigning a string to an integer variable
int x = "hello";
```

### Logical Errors
Logical errors occur when the code is syntactically correct and semantically correct but does not produce the desired output. These errors can be difficult to detect and require thorough testing.
```c
// Logical error example: incorrect calculation
int x = 5;
int y = 3;
int result = x - y; // instead of x + y
```

### Runtime Errors
Runtime errors occur when the code encounters an error during execution. These errors can be caused by various factors such as division by zero, null pointer exceptions, or out-of-range values.
```c
// Runtime error example: division by zero
int x = 5;
int y = 0;
int result = x / y;
```
---
day: 2
title: "C- L2, CP - 2"
description: "C- L2, CP - 2
(Functions, Strings and arrays)"
---

## Function Basics: Definition, Declaration, and Calling Functions

### Definition
A function definition provides the actual body of the function. It includes the function's return type, name, parameters, and body.
```c
return_type function_name(parameter_list) {
    // function body
}
```

### Declaration
A function declaration, also known as a prototype, declares the function and its parameters without providing the body. This informs the compiler about the function's existence.
```c
return_type function_name(parameter_list);
```

### Calling Functions
To call a function, simply use its name followed by the argument list.
```c
function_name(argument_list);
```

### Example
```c
#include<stdio.h>

// Function declaration
int add(int a, int b);

int main() {
    int sum = add(5, 3);
    printf("Sum: %d
", sum);
    return 0;
}

// Function definition
int add(int a, int b) {
    return a + b;
}
```

## Parameters and Return Values

### Parameters
Parameters are variables listed as part of a function's declaration and definition.
- **Formal Parameters:** Parameters in the function definition.
- **Actual Parameters:** Parameters passed to the function when it is called.

### Return Values
A function can return a value back to the caller using the `return` statement.
```c
#include<stdio.h>

int multiply(int x, int y) {
    return x*y;
}

int main() {
    int result = multiply(4, 5);
    printf("Result: %d
", result);
    return 0;
}
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

### Example
```c
#include<stdio.h>

int global_var = 10; // Global variable

void demo() {
    int local_var = 20; // Local variable
    static int static_var = 30; // Static variable
    printf("Local: %d, Static: %d, Global: %d\n", local_var, static_var, global_var);
    local_var++;
    static_var++;
}

void main(){
    demo();
    demo();
}
```

## Recursive Functions

### Definition
A recursive function is a function that calls itself either directly or indirectly to solve a problem.

### Example
```c
#include<stdio.h>

// Function to calculate factorial of a number
int factorial(int n) {
   if(n==1||n==0) return 1; //base cases
   return n*factorial(n-1);
}

int main() {
    int num;
    scanf("%d",&num);
    printf("Factorial of %d is %d\n", num, factorial(num));
    return 0;
}
```

### Advantages and Disadvantages
**Advantages:**
- Simplifies the code for problems that can be broken down into similar sub-problems.

**Disadvantages:**
- Can lead to excessive memory usage and stack overflow if not implemented correctly.

---

## Time and Space Complexity with Efficiency Classes and Notations

### 1. Time Complexity
Time complexity is a measure of the amount of time an algorithm takes to complete as a function of the length of the input. It is typically expressed using Big O notation, which describes the upper bound of the algorithm's growth rate.

#### Efficiency Classes:
- **O(1) - Constant Time:** The algorithm takes a constant amount of time, regardless of the input size.
- **O(log n) - Logarithmic Time:** The algorithm's time complexity grows logarithmically as the input size increases.
- **O(n) - Linear Time:** The algorithm's time complexity grows linearly with the input size.
- **O(n log n) - Log-Linear Time:** The algorithm's time complexity grows in proportion to n log n.
- **O(n^2) - Quadratic Time:** The algorithm's time complexity grows quadratically as the input size increases.
- **O(2^n) - Exponential Time:** The algorithm's time complexity doubles with each additional input element.
- **O(n!) - Factorial Time:** The algorithm's time complexity grows factorially, which is highly inefficient for large inputs.

#### Example:
Consider a linear search algorithm:
```c
#include<stdio.h>

int linearSearch(int arr[], int n, int x) {
    for(int i = 0; i < n; i++) {
        if(arr[i] == x) {
            return i;
        }
    }
    return -1;
}

int main() {
    int arr[] = {2, 4, 0, 1, 9};
    int x = 1;
    int n = sizeof(arr)/sizeof(arr[0]);
    int result = linearSearch(arr, n, x);
    printf("Element found at index: %d\n", result);
    return 0;
}
```
In this example, the time complexity of the linear search is **O(n)** because, in the worst case, it may need to check each element in the array.

### 2. Space Complexity
Space complexity is a measure of the amount of memory an algorithm uses in relation to the size of the input data. Like time complexity, it is also expressed using Big O notation.

#### Efficiency Classes:
- **O(1) - Constant Space:** The algorithm uses a constant amount of space, regardless of the input size.
- **O(n) - Linear Space:** The algorithm's space usage grows linearly with the input size.
- **O(log n) - Logarithmic Space:** The algorithm's space usage grows logarithmically as the input size increases.
- **O(n^2) - Quadratic Space:** The algorithm's space usage grows quadratically with the input size.

#### Example:
Consider an example of calculating the Fibonacci sequence using recursion:
```c
#include<stdio.h>

int fibonacci(int n) {
    if(n <= 1) {
        return n;
    }
    return fibonacci(n-1) + fibonacci(n-2);
}

int main() {
    int n = 5;
    printf("Fibonacci number is: %d\n", fibonacci(n));
    return 0;
}
```
In this example, the space complexity is **O(n)** due to the depth of the recursion stack.

## Strings in C

### String Handling Functions
Strings in C are arrays of characters terminated by a null character (`\0`).

### Array of Characters
To declare and initialize a string:
```c
char str[] = "Hello, World!";
```
Or:
```c
char str[50] = "Hello, World!";
```

### Standard Library Functions

#### `strlen`
Calculates the length of a string.
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[] = "Hello, World!";
    printf("Length: %zu\n", strlen(str));
    return 0;
}
```

#### `strcpy`
Copies one string to another.
```c
#include <stdio.h>
#include <string.h>

int main() {
    char src[] = "Hello, World!";
    char dest[50];
    strcpy(dest, src);
    printf("Copied String: %s\n", dest);
    return 0;
}
```

#### `strcmp`
Compares two strings.
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str1[] = "Hello";
    char str2[] = "World";
    int result = strcmp(str1, str2);
    if(result == 0) {
        printf("Strings are equal\n");
    } else {
        printf("Strings are not equal\n");
    }
    return 0;
}
```

#### `strcat`
Concatenates two strings.
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str1[50] = "Hello";
    char str2[] = ", World!";
    strcat(str1, str2);
    printf("Concatenated String: %s\n", str1);
    return 0;
}
```

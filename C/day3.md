---
day: 3
title: "C- L3, CP - 2"
description: "C- L3, CP - 2
(Pointers and Dynamic Mem allocation)"
---

# Day 3 - C- L3, CP - 2

### 1. Introduction to Pointers

Pointers are variables that store the memory addresses of other variables. Learning pointers is essential to understand how memory works in C.

- **Memory Addresses:** Each variable in C is stored in memory at a specific address. Pointers help us access and manipulate that memory directly.
- **Declaration and Initialization:** You declare a pointer using the `*` symbol. Example: `int *ptr;`
- **Referencing and Dereferencing:**
  - `&` gives the address of a variable (reference)
  - `*` gives the value at the address (dereference)
- **Pointer Types:** Depending on what they point to, pointers are typed: `int*`, `char*`, `float*`, `void*`, etc.
- **Pointer Arithmetic:** You can perform operations like increment (`ptr++`) or decrement (`ptr--`) to move across memory.

---

### 2. Pointers and Arrays

Arrays and pointers are closely related in C, and understanding this helps in efficient memory and data handling.

- **Relationship:** The name of an array (`arr`) acts like a pointer to its first element.
- **Accessing Elements:** You can access elements using either `arr[i]` or `*(arr + i)`.
- **Pointer to Array vs Array of Pointers:**
  - Pointer to array: Single pointer pointing to a block of elements.
  - Array of pointers: Multiple pointers stored in an array, useful for strings.
- **Pointer Incrementing:** Moving from one array element to the next using pointer arithmetic.

---

### 3. Pointers and Functions

Pointers allow functions to directly modify the arguments passed to them, which is not possible by default in C.

- **Call by Value vs Call by Reference:**
  - Call by value: A copy of the variable is passed.
  - Call by reference (using pointers): The actual memory address is passed, allowing modification.
- **Passing Pointers to Functions:** Functions can receive pointers and work directly with memory addresses.
- **Returning Pointers:** Functions can return a pointer, but care must be taken not to return pointers to local variables.
- **Pointer to Function (optional):** A pointer that stores the address of a function, enabling dynamic function calls.

---

### 4. Dynamic Memory Allocation

Unlike arrays (which have a fixed size), dynamic memory allows memory to be allocated at runtime using the heap.

- **Why Dynamic Allocation?** Useful when you don’t know in advance how much memory you’ll need.
- **Functions:**
  - `malloc()`: Allocates a single block of memory.
  - `calloc()`: Allocates multiple blocks and initializes them to 0.
  - `realloc()`: Changes the size of an already allocated block.
  - `free()`: Deallocates memory to prevent leaks.
- **Memory Leaks:** Forgetting to `free()` memory leads to waste of memory.
- **Dangling Pointers:** Occur when memory is freed, but the pointer still points to it.

---

### 5. Pointers and Structures (Optional / Bonus)

Combining structures with pointers allows for dynamic creation and management of complex data types.

- **Pointer to Structure:** Allows accessing structure members dynamically.
  - Example: `struct Student *ptr;`
- **Arrow Operator (`->`):** Used to access structure members through pointers.
  - Example: `ptr->name`
- **Dynamic Struct Allocation:** Allocate memory for structures using `malloc()`.

---

## Practice/Hands-On Components

- **Swap Two Numbers Using Pointers:** Demonstrates how pointers allow direct manipulation of variables.
- **Reverse an Array Using Pointers:** A good example of array traversal using pointer arithmetic.
- **Dynamic Array Implementation:** Allocate space using `malloc()` and expand it with `realloc()` as needed.
- **Student Record System (Mini Project):**
  - Dynamically allocate an array of structures.
  - Store and display student details like name, ID, and marks.

---
day: 4
title: "C- L4, CP - 2"
description: "C- L4, CP - 2
(Structures and Unions)"
---

# Day 4 - Structures and Unions

## Structures

### Definition
A structure is a user-defined data type in C that allows combining data items of different kinds.

### Declaration
To declare a structure:
```c
struct Person {
    char name[50];
    int age;
    float height;
};
```
Alternate method using `typedef`
```c
typdef struct{
    char name[50];
    int age;
    float height;
}Person;
```
### Accessing Members
You can access structure members using the dot (`.`) operator.
```c
#include <stdio.h>

struct Person {
    char name[50];
    int age;
    float height;
};

int main() {
    struct Person person1;

    // Assigning values to members
    strcpy(person1.name, "Alice");
    person1.age = 25;
    person1.height = 5.5;

    // Accessing members
    printf("Name: %s\n", person1.name);
    printf("Age: %d\n", person1.age);
    printf("Height: %.1f\n", person1.height);

    return 0;
}
```

## Array of Structures
You can create an array of structures to store multiple records of the same type.
```c
#include <stdio.h>

struct Person {
    char name[50];
    int age;
    float height;
};

int main() {
    struct Person people[3];

    // Assigning values to array of structures
    strcpy(people[0].name, "Alice");
    people[0].age = 25;
    people[0].height = 5.5;

    strcpy(people[1].name, "Bob");
    people[1].age = 30;
    people[1].height = 6.0;

    strcpy(people[2].name, "Charlie");
    people[2].age = 35;
    people[2].height = 5.8;

    // Accessing array of structures
    for(int i = 0; i < 3; i++) {
        printf("Name: %s, Age: %d, Height: %.1f\n", people[i].name, people[i].age, people[i].height);
    }

    return 0;
}
```

## Nested Structures
A structure can contain other structures as members.
```c
#include <stdio.h>

struct Address {
    char city[50];
    char state[50];
};

struct Person {
    char name[50];
    int age;
    struct Address address;
};

int main() {
    struct Person person1;

    // Assigning values to nested structures
    strcpy(person1.name, "Alice");
    person1.age = 25;
    strcpy(person1.address.city, "New York");
    strcpy(person1.address.state, "NY");

    // Accessing nested structure members
    printf("Name: %s\n", person1.name);
    printf("Age: %d\n", person1.age);
    printf("City: %s\n", person1.address.city);
    printf("State: %s\n", person1.address.state);

    return 0;
}
```

## Unions

### Definition
A union is a user-defined data type similar to a structure, but it allows storing different data types in the same memory location.

### Declaration
To declare a union:
```c
union Data {
    int i;
    float f;
    char str[20];
};
```

### Accessing Members
You can access union members using the dot (`.`) operator.
```c
#include <stdio.h>

union Data {
    int i;
    float f;
    char str[20];
};

int main() {
    union Data data;

    // Assigning and accessing values
    data.i = 10;
    printf("data.i: %d\n", data.i);

    data.f = 220.5;
    printf("data.f: %.1f\n", data.f);

    strcpy(data.str, "C Programming");
    printf("data.str: %s\n", data.str);

    return 0;
}
```

## Difference between Structures and Unions

#### *Memory Allocation:*

 - **Structure**: Allocates separate memory for each member. The total memory required is the sum of the memory needed for all members.
 - **Union**: Allocates a single shared memory block for all members. The memory size of the union is equal to the size of its largest member.
#### *Member Access:*

- **Structure:** All members can be accessed and used simultaneously since each has its own memory.
- **Union:** Only one member can be accessed at a time because all members share the same memory location. Modifying one member will affect the values of others.
#### *Use Case:*  

- **Structure:** Suitable for grouping logically related data that need to be accessed independently. Example: A struct for a student that includes name, age, and GPA.
- **Union:** Suitable for situations where different types of data are stored in the same memory location, but only one type is used at a time. Example: A union for a variable that can store an integer, float, or string but only one at a time.
#### *Initialization:*
- **Structure:** All members can be initialized simultaneously at the time of declaration.
- **Union:** Only the first member can be initialized at the time of declaration. Initializing other members requires assignment after declaration.
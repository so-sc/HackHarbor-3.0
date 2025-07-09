---
day: 6
title: "C- L6, CP - 2"
description: "C- L6, CP - 2
(Data Structures
Stacks and Queues)"
---

# Day 6 - Data Structures

## Data Structures

### Definition
A `data structure` is a way of organizing and storing data in a computer so that it can be accessed and modified efficiently.

### Types
- **Primitive Data Structures:** Basic structures like int, float, char, etc.
- **Non-Primitive Data Structures:** More complex structures like arrays, linked lists, stacks, queues, trees, graphs, etc.

### Usage
Data structures are used to manage large amounts of data efficiently for various operations such as traversal, insertion, deletion, and searching.

## Stacks

### Definition
A `stack` is a linear data structure that follows the Last In First Out (LIFO) principle.

### Implementation using Arrays
```c
#include <stdio.h>
#define MAX 5

int stack[MAX], top = -1;

void push(int value) {
    if(top==MAX-1) {
        printf("Stack Overflow\n");
    }else{
        stack[++top] = value;
        printf("Inserted %d\n", value);
    }
}

void pop() {
    if(top==-1) {
        printf("Stack Underflow\n");
    }else{
        printf("Deleted %d\n",stack[top--]);
    }
}

void display() {
    if(top==-1) {
        printf("Stack is empty\n");
    }else{
        printf("Stack elements are:\n");
        for(int i=top;i>=0;i--) {
            printf("%d\n", stack[i]);
        }
    }
}

int main() {
    push(1);
    push(2);
    push(3);
    pop();
    pop();
    pop();
    pop();//underflow
    display();
    return 0;
}
```
### Push Operation
The push operation adds an element to the top of the stack.

### Pop Operation
The pop operation removes the top element from the stack.

## Queues

### Definition
A queue is a linear data structure that follows the First In First Out (FIFO) principle.

### Implementation using Arrays
```c
#include <stdio.h>
#define MAX 5

int queue[MAX], front=-1, rear=-1;

void enqueue(int value) {
    if(rear==MAX - 1) {
        printf("Queue Overflow\\n");
    } else {
        if(front==-1) front=0;
        queue[++rear]=value;
        printf("Inserted %d\\n", value);
    }
}

void dequeue() {
    if(front==-1 || front>rear) {
        printf("Queue Underflow\\n");
    } else {
        printf("Deleted %d\\n", queue[front++]);
        if(front > rear) front=rear=-1;//reset pointers
    }
}

void display() {
    if(front==-1) {
        printf("Queue is empty\\n");
    } else {
        printf("Queue elements are:\\n");
        for(int i=front; i<=rear;i++) {
            printf("%d\\n", queue[i]);
        }
    }
}

int main() {
    enqueue(1);
    enqueue(2);
    enqueue(3);
    dequeue();
    display();
    return 0;
}
```
### Enqueue Operation
The enqueue operation adds an element to the end of the queue.

### Dequeue Operation
The dequeue operation removes the front element from the queue.

## Circular Queue

### Definition
A circular queue is a linear data structure in which the last position is connected back to the first position to make a circle.

### Implementation
```c
#include <stdio.h>
#define MAX 5

int cqueue[MAX], front=-1, rear=-1;

void enqueue(int value) {
    if((front==0 && rear==MAX-1) || (rear+1)%MAX==front) {
        printf("Circular Queue Overflow\n");
    } else {
        if(front==-1) front=rear=0;
        else rear=(rear+1)%MAX;
        cqueue[rear]=value;
        printf("Inserted %d\n", value);
    }
}

void dequeue() {
    if(front==-1) {
        printf("Circular Queue Underflow\n");
    } else {
        printf("Deleted %d\n", cqueue[front]);
        if(front==rear) front=rear=-1;
        else front=(front+1) % MAX;
    }
}

void display() {
    if(front==-1) {
        printf("Circular Queue is empty\n");
    } else {
        printf("Circular Queue elements are:\n");
        int i=front;
        while(1) {
            printf("%d\n",cqueue[i]);
            if(i==rear) break;
            i=(i+1)%MAX;
        }
    }
}

int main() {
    enqueue(1);
    enqueue(2);
    enqueue(3);
    enqueue(4);
    dequeue();
    enqueue(5);
    display();
    return 0;
}
```
### Operations
- **Enqueue:** Adds an element to the rear of the circular queue.
- **Dequeue:** Removes an element from the front of the circular queue.

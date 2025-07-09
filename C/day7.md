---
day: 7
title: "C- L7, CP - 2"
description: "C- L7, CP - 2
(Linked list)"
---

# Day 7 - Linked Lists

## Singly Linked Lists

![SLL](https://media.geeksforgeeks.org/wp-content/uploads/20240726165319/Singly-Linked-List.webp "Singly Linked Lists")

### Implementation
A singly linked list consists of nodes, each containing data and a pointer to the next node.
```c
struct Node {
    int data;
    struct Node* next;
};
```

### Insertion
Insertion can be done at the beginning, end, or at a specific position.
```c
// Insert at the beginning
struct Node* insertAtBeginning(struct Node* head, int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = head;
    return newNode;
}
```

### Deletion
Deletion can be done from the beginning, end, or at a specific position.
```c
// Delete from the beginning
struct Node* deleteFromBeginning(struct Node* head) {
    if (head == NULL) return NULL;
    struct Node* temp = head;
    head = head->next;
    free(temp);
    return head;
}
```

### Traversal
Traversal involves visiting each node in the list.
```c
void traverse(struct Node* head) {
    struct Node* cursor = head;
    while (cursor != NULL) {
        printf("%d ", cursor->data);
        cursor = cursor->next;
    }
}
```

## Doubly Linked Lists

![DLL](https://res.cloudinary.com/practicaldev/image/fetch/s--QTk9XbRm--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/kvnpce96zqdxu73hp6oe.png "Doubly Linked Lists")

### Implementation
A doubly linked list has nodes with pointers to both the next and previous nodes.
```c
struct Node {
    int data;
    struct Node* next;
    struct Node* prev;
};
```

### Insertion
Insertion in a doubly linked list requires updating both next and prev pointers.
```c
// Insert at the beginning
struct Node* insertAtBeginning(struct Node* head, int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = head;
    if (head != NULL) head->prev = newNode;
    return newNode;
}
```

### Deletion
Deletion in a doubly linked list involves updating both next and prev pointers.
```c
// Delete from the beginning
struct Node* deleteFromBeginning(struct Node* head) {
    if (head == NULL) return NULL;
    struct Node* temp = head;
    head = head->next;
    if (head != NULL) head->prev = NULL;
    free(temp);
    return head;
}
```

### Traversal
Traversal can be done in both forward and backward directions.
```c
void traverseForward(struct Node* head) {
    struct Node* cursor = head;
    while (cursor != NULL) {
        printf("%d ", cursor->data);
        cursor = cursor->next;
    }
}

void traverseBackward(struct Node* tail) {
    struct Node* cursor = tail;
    while (cursor != NULL) {
        printf("%d ", cursor->data);
        cursor = cursor->prev;
    }
}
```

## Singly Linked Circular List:

![CSLL](https://examradar.com/wp-content/uploads/2016/10/Figure-3.6.1.-Circular-Single-Linked-List.png "Circular Linked Lists")

### Implementation
A circular linked list connects the last node back to the first node.
```c
struct Node {
    int data;
    struct Node* next;
};
```

### Insertion
Insertion in a circular linked list requires special handling for the last node.
```c
// Insert at the beginning
struct Node* insertAtBeginning(struct Node* head, int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    if (head == NULL) {
        newNode->next = newNode;
        return newNode;
    }
    newNode->next = head;
    struct Node* cursor = head;
    while (cursor->next != head) {
        cursor = cursor->next;
    }
    cursor->next = newNode;
    return newNode;
}
```

### Deletion
Deletion in a circular linked list requires updating the last node's next pointer.
```c
// Delete from the beginning
struct Node* deleteFromBeginning(struct Node* head) {
    if (head == NULL) return NULL;
    if (head->next == head) {
        free(head);
        return NULL;
    }
    struct Node* cursor = head;
    while (cursor->next != head) {
        cursor = cursor->next;
    }
    struct Node* temp = head;
    head = head->next;
    cursor->next = head;
    free(temp);
    return head;
}
```

### Traversal
Traversal in a circular linked list requires stopping when we reach the first node again.
```c
void traverse(struct Node* head) {
    if (head == NULL) return;
    struct Node* cursor = head;
    do {
        printf("%d ", cursor->data);
        cursor = cursor->next;
    } while (cursor != head);
}
```

### Example
```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

int main() {
    struct Node* head = createNode(1);
    head->next = createNode(2);
    head->next->next = createNode(3);
    
    struct Node* cursor = head;
    while (cursor != NULL) {
        printf("%d ", cursor->data);
        cursor = cursor->next;
    }
    
    return 0;
}
```

## Doubly Linked Circular List:
![CDLL](https://www.sanfoundry.com/wp-content/uploads/2013/05/circular-doubly-linked-list-example.png "Doubly Linked Lists")

### Implementation
```c
struct Node {
    struct Node* prev
    int data;
    struct Node* next;
};
```

### Insertion
Unlike in circular singly linked list, we don't have to traverse the whole list in order to get last position.  
Just do `lastNode = head->prev;`
```c
// Insert at the beginning
struct Node* insertAtBeginning(struct Node* head, int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    if (head == NULL) {
        newNode->prev = newNode->next = newNode;
        return newNode;
    }
    newNode->next = head;
    newNode->prev = head->prev;
    return newNode;
}
```

### Deletion
We can use that same advantage here as well.
```c
// Delete from the beginning
struct Node* deleteFromBeginning(struct Node* head) {
    if (head == NULL) return NULL;
    if (head->next == head) {
        free(head);
        return NULL;
    }
    struct Node* temp = head;
    head->prev->next = head->next;
    head->next->prev = head->prev;
    head = head->next;
    free(temp);
    return head;
}
```

### Traversal
Traversal in a circular doubly linked list is the same as circular singly linked list. Except you can now also traverse in reverse.
```c
void traverse(struct Node* head) {
    if (head == NULL) return;
    struct Node* cursor = head;
    do {
        printf("%d ", cursor->data);
        cursor = cursor->next;
    } while (cursor != head);
}

void traverseReverse(struct Node* head) {
    if (head == NULL) return;
    struct Node* cursor = head;
    do {
        printf("%d ", cursor->data);
        cursor = cursor->prev;
    } while (cursor != head);
}
```
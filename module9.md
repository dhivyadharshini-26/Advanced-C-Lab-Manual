# EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

## Aim:
To write a C program to display stack elements using an array.
## Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
## Program:
```c
#include <stdio.h>

#define MAX 100

int stack[MAX];
int top = -1;

void display() {
    if(top == -1) {
        printf("Stack is empty\n");
        return;
    }
    
    printf("Stack elements: ");
    for(int i = 0; i <= top; i++) {
        printf("%d ", stack[i]);
    }
    printf("\n");
}

int main() {
    int n, val;
    
    printf("Enter number of elements: ");
    scanf("%d", &n);
    
    for(int i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &val);
        stack[++top] = val;
    }
    
    display();
    
    return 0;
}
```
## Output:
<img width="506" height="303" alt="image" src="https://github.com/user-attachments/assets/f70f6f11-7c1e-4e1c-8c0a-26dda09438a5" />

## Result:
Thus, the program to display stack elements using an array is verified successfully.
 

# EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
## Aim:
To create a C program to push the given element in to a stack using array.
## Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
## Program:
```c
#include <stdio.h>

#define MAX 100

int stack[MAX];
int top = -1;

void push(int val) {
    if (top == MAX - 1) {
        printf("Stack Overflow! Cannot push %d\n", val);
        return;
    }
    stack[++top] = val;
    printf("Pushed %d into stack\n", val);
}

int main() {
    int n, val;

    printf("Enter number of elements to push: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &val);
        push(val);
    }

    return 0;
}
```
## Output:
<img width="437" height="295" alt="image" src="https://github.com/user-attachments/assets/f78c976f-8bee-4700-b3cc-f41dd12b1918" />

## Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
# EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
## Aim:
To write a C program to display queue elements using array

## Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
## Program:
```c
#include <stdio.h>

#define MAX 100

int queue[MAX];
int front = -1, rear = -1;

void display() {
    if (front == -1) {
        printf("Queue is empty\n");
        return;
    }

    printf("Queue elements: ");
    for (int i = front; i <= rear; i++) {
        printf("%d ", queue[i]);
    }
    printf("\n");
}

int main() {
    int n, val;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &val);

        if (rear == MAX - 1) {
            printf("Queue Overflow\n");
            break;
        }

        if (front == -1) front = 0;
        queue[++rear] = val;
    }

    display();

    return 0;
}
```
## Output:
<img width="893" height="653" alt="image" src="https://github.com/user-attachments/assets/368ef445-c862-469b-bc84-e5ac49960a05" />

## Result:
Thus, the program to display queue elements using array is verified successfully.


 
# EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
## Aim:
To write a C program to insert elements in queue using array.

## Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

## Program:
```c
#include <stdio.h>

#define MAX 100

int queue[MAX];
int front = -1, rear = -1;

void enqueue(int val) {
    if (rear == MAX - 1) {
        printf("Queue Overflow! Cannot insert %d\n", val);
        return;
    }

    if (front == -1)  // first element
        front = 0;

    queue[++rear] = val;
    printf("Inserted %d into queue\n", val);
}

int main() {
    int n, val;

    printf("Enter number of elements to insert: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &val);
        enqueue(val);
    }

    return 0;
}
```
## Output:

<img width="1070" height="678" alt="image" src="https://github.com/user-attachments/assets/b15affb1-0059-413e-8af1-2d9dae4f55ed" />

## Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
# EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY
## Aim:

To create a function in C that deletes an element from a queue implemented using an array.

## Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



## Program:
```c
#include <stdio.h>

#define MAX 100

int queue[MAX];
int front = -1, rear = -1;

void dequeue() {
    if (front == -1) {
        printf("Queue Underflow! Cannot delete\n");
        return;
    }

    printf("Deleted element: %d\n", queue[front]);

    if (front == rear) {
        front = rear = -1; // queue becomes empty
    } else {
        front++;
    }
}

int main() {
    int n, val;

    // Pre-inserting elements for deletion demonstration
    printf("Enter number of elements to insert first: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &val);

        if (rear == MAX - 1) {
            printf("Queue Overflow!\n");
            break;
        }

        if (front == -1)
            front = 0;

        queue[++rear] = val;
    }

    // Perform deletion
    dequeue();

    return 0;
}
```
## Output:
<img width="957" height="526" alt="image" src="https://github.com/user-attachments/assets/721688fb-86a7-4f1b-bec1-1295a86374ae" />

## Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.

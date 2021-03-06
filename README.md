# Data Structure

# Data Structure Concepts

1. Array
2. Linked List - Single, Doubly, Circular
3. Stack
4. Queue
5. PriorityQueue
6. Binary Search
7. Binary Search Tree
8. Hash Table and HashMap

# Sorting Algorithms
1. Bubble
2. Selection
3. Insertion
4. Merge
5. Quick Sort

# Path finding algorithms
1. Djkstra Algorithm
2. A* Allgorithm
3. Breadth First Search
4. Depth First Search




# Linked List
Like arrays, Linked List is a linear data structure. Unlike arrays, linked list elements are not stored at contiguous location; the elements are linked using pointers.
linkedlist

<b>Why Linked List?</b> <br>
Arrays can be used to store linear data of similar types, but arrays have following limitations.
1) The size of the arrays is fixed: So we must know the upper limit on the number of elements in advance. Also, generally, the allocated memory is equal to the upper limit irrespective of the usage.
2) Inserting a new element in an array of elements is expensive, because room has to be created for the new elements and to create room existing elements have to shifted.

For example, in a system if we maintain a sorted list of IDs in an array id[].

id[] = [1000, 1010, 1050, 2000, 2040].

![](https://www.geeksforgeeks.org/wp-content/uploads/gq/2013/03/Linkedlist.png)

And if we want to insert a new ID 1005, then to maintain the sorted order, we have to move all the elements after 1000 (excluding 1000).
Deletion is also expensive with arrays until unless some special techniques are used. For example, to delete 1010 in id[], everything after 1010 has to be moved.

<b> Advantages over arrays </b>
1) Dynamic size
2) Ease of insertion/deletion

<b> Drawbacks: </b>
1) Random access is not allowed. We have to access elements sequentially starting from the first node. So we cannot do binary search with linked lists efficiently with its default implementation. Read about it here.
2) Extra memory space for a pointer is required with each element of the list.
3) Not cache friendly. Since array elements are contiguous locations, there is locality of reference which is not there in case of linked lists.

<b> Representation: </b> <br>
A linked list is represented by a pointer to the first node of the linked list. The first node is called head. If the linked list is empty, then value of head is NULL.
Each node in a list consists of at least two parts:
1) data
2) Pointer (Or Reference) to the next node

```

class LinkedList 
{ 
    Node head;  // head of list 
  
    /* Linked list Node*/
    class Node 
    { 
        int data; 
        Node next; 
           
        // Constructor to create a new node 
        // Next is by default initialized 
        // as null 
        Node(int d) {data = d;} 
    } 
}
```

## Circular Linked List -
Circular linked list is a linked list where all nodes are connected to form a circle. There is no NULL at the end. A circular linked list can be a singly circular linked list or doubly circular linked list.

![](https://cdncontribute.geeksforgeeks.org/wp-content/uploads/CircularLinkeList.png)

Advantages of Circular Linked Lists: <br>
1) Any node can be a starting point. We can traverse the whole list by starting from any point. We just need to stop when the first visited node is visited again.

2) Useful for implementation of queue. Unlike this implementation, we don’t need to maintain two pointers for front and rear if we use circular linked list. We can maintain a pointer to the last inserted node and front can always be obtained as next of last.

3) Circular lists are useful in applications to repeatedly go around the list. For example, when multiple applications are running on a PC, it is common for the operating system to put the running applications on a list and then to cycle through them, giving each of them a slice of time to execute, and then making them wait while the CPU is given to another application. It is convenient for the operating system to use a circular list so that when it reaches the end of the list it can cycle around to the front of the list.

4) Circular Doubly Linked Lists are used for implementation of advanced data structures like Fibonacci Heap.

https://www.youtube.com/watch?time_continue=113&v=ANbJdUBIVRU

## Doubly Linked List -

A Doubly Linked List (DLL) contains an extra pointer, typically called previous pointer, together with next pointer and data which are there in singly linked list.

![](https://www.geeksforgeeks.org/wp-content/uploads/gq/2014/03/DLL1.png)

<b> Advantages </b> - <br>
1) A DLL can be traversed in both forward and backward direction.
2) The delete operation in DLL is more efficient if pointer to the node to be deleted is given.
3) We can quickly insert a new node before a given node.
In singly linked list, to delete a node, pointer to the previous node is needed. To get this previous node, sometimes the list is traversed. In DLL, we can get the previous node using previous pointer.<br>
<br>


```
// Class for Doubly Linked List 
public class DLL { 
    Node head; // head of list 
  
    /* Doubly Linked list Node*/
    class Node { 
        int data; 
        Node prev; 
        Node next; 
  
        // Constructor to create a new node 
        // next and prev is by default initialized as null 
        Node(int d) { data = d; } 
    } 
} 


```
<b>Time Complexity:</b><br>
Access: O(n)<br>
Search: O(n)<br>
Insert: O(1)<br>
Remove: O(1)<br>

# Stack

Stack is a linear data structure which follows a particular order in which the operations are performed. The order may be LIFO(Last In First Out) or FILO(First In Last Out).<br>


![](https://www.geeksforgeeks.org/wp-content/uploads/gq/2013/03/stack.png)<br>


<b> Mainly the following three basic operations are performed in the stack:</b><br>
<br>
<b>Push:</b> Adds an item in the stack. If the stack is full, then it is said to be an Overflow condition.<br>
<b>Pop:</b> Removes an item from the stack. The items are popped in the reversed order in which they are pushed. If the stack is empty, then it is said to be an Underflow condition.<br>
<b>Peek or Top:</b> Returns top element of stack.<br>
<b>isEmpty:</b> Returns true if stack is empty, else false.<br>

<b>How to understand a stack practically?</b> <br>
There are many real life examples of stack. Consider the simple example of plates stacked over one another in canteen. The plate which is at the top is the first one to be removed, i.e. the plate which has been placed at the bottommost position remains in the stack for the longest period of time. So, it can be simply seen to follow LIFO/FILO order.

<b>Time Complexities of operations on stack:</b> <br>

push(), pop(), isEmpty() and peek() all take O(1) time. We do not run any loop in any of these operations.


<b> Analysis of Stack Operations </b> <br>
Below mentioned are the time complexities for various operations that can be performed on the Stack data structure.<br>

1. Push Operation : O(1)
2. Pop Operation : O(1)
3. Top Operation : O(1)
4. Search Operation : O(n)

<b> Algorithm for PUSH operation </b> <br>
1. Check if the stack is full or not.
2. If the stack is full, then print error of overflow and exit the program.
3. If the stack is not full, then increment the top and add the element.


<b> Algorithm for POP operation </b> <br>
1. Check if the stack is empty or not.
2. If the stack is empty, then print error of underflow and exit the program.
3. If the stack is not empty, then print the element at the top and decrement the top.
    
```    
/*  Below program is written in C++ language  */

# include<iostream>

using namespace std;

class Stack
{
    int top;
    public:
    int a[10];  //Maximum size of Stack
    Stack()
    {
        top = -1;
    }
    
    // declaring all the function
    void push(int x);
    int pop();
    void isEmpty();
};

// function to insert data into stack
void Stack::push(int x)
{
    if(top >= 10)
    {
        cout << "Stack Overflow \n";
    }
    else
    {
        a[++top] = x;
        cout << "Element Inserted \n";
    }
}

// function to remove data from the top of the stack
int Stack::pop()
{
    if(top < 0)
    {
        cout << "Stack Underflow \n";
        return 0;
    }
    else
    {
        int d = a[top--];
        return d;
    }
}

// function to check if stack is empty
void Stack::isEmpty()
{
    if(top < 0)
    {
        cout << "Stack is empty \n";
    }
    else
    {
        cout << "Stack is not empty \n";
    }
}

// main function
int main() {

    Stack s1;
    s1.push(10);
    s1.push(100);
    /*
        preform whatever operation you want on the stack
    */
}
```

# Queue
Queue is also an abstract data type or a linear data structure, just like stack data structure, in which the first element is inserted from one end called the REAR(also called tail), and the removal of existing element takes place from the other end called as FRONT(also called head).

This makes queue as FIFO(First in First Out) data structure, which means that element inserted first will be removed first.

Which is exactly how queue system works in real world. If you go to a ticket counter to buy movie tickets, and are first in the queue, then you will be the first one to get the tickets. Right? Same is the case with Queue data structure. Data inserted first, will leave the queue first.

The process to add an element into queue is called Enqueue and the process of removal of an element from queue is called Dequeue.

https://www.studytonight.com/data-structures/images/introduction-to-queue.png

# Implementation of Queue Data Structure
Queue can be implemented using an Array, Stack or Linked List. The easiest way of implementing a queue is by using an Array.

Initially the head(FRONT) and the tail(REAR) of the queue points at the first index of the array (starting the index of array from 0). As we add elements to the queue, the tail keeps on moving ahead, always pointing to the position where the next element will be inserted, while the head remains at the first index.

https://www.studytonight.com/data-structures/images/implementation-of-queue.png

When we remove an element from Queue, we can follow two possible approaches (mentioned [A] and [B] in above diagram). In [A] approach, we remove the element at head position, and then one by one shift all the other elements in forward position.

In approach [B] we remove the element from head position and then move head to the next position.

In approach [A] there is an overhead of shifting the elements one position forward every time we remove the first element.

In approach [B] there is no such overhead, but whenever we move head one position ahead, after removal of first element, the size on Queue is reduced by one space each time.

<b> Algorithm for ENQUEUE operation </b>
Check if the queue is full or not.
If the queue is full, then print overflow error and exit the program.
If the queue is not full, then increment the tail and add the element.


<b> Algorithm for DEQUEUE operation </b>
Check if the queue is empty or not.
If the queue is empty, then print underflow error and exit the program.
If the queue is not empty, then print the element at the head and increment the head.

```
/* Below program is written in C++ language */

#include<iostream>

using namespace std;

#define SIZE 10

class Queue
{
    int a[SIZE];
    int rear;   //same as tail
    int front;  //same as head
  
    public:
    Queue()
    {
        rear = front = -1;
    }
    
    //declaring enqueue, dequeue and display functions
    void enqueue(int x);     
    int dequeue();
    void display();
};

// function enqueue - to add data to queue
void Queue :: enqueue(int x)
{
    if(front == -1) {
        front++;
    }
    if( rear == SIZE-1)
    {
        cout << "Queue is full";
    }
    else
    {
        a[++rear] = x;
    }
}

// function dequeue - to remove data from queue
int Queue :: dequeue()
{
    return a[++front];  // following approach [B], explained above
}

// function to display the queue elements
void Queue :: display()
{
    int i;
    for( i = front; i <= rear; i++)
    {
        cout << a[i] << endl;
    }
}

// the main function
int main()
{
    Queue q;
    q.enqueue(10);
    q.enqueue(100);
    q.enqueue(1000);
    q.enqueue(1001);
    q.enqueue(1002);
    q.dequeue();
    q.enqueue(1003);
    q.dequeue();
    q.dequeue();
    q.enqueue(1004);
    
    q.display();
    
    return 0;
}
```

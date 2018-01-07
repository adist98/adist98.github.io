## Files
* [Heaps.pdf](https://www.dropbox.com/s/30kq25klujxqyzs/Heaps.pdf?dl=0)

## To do list
- [ ] To write the explaination of Enqueue and Dequeue functions in circular array implementation of Queues.

## Important Links
* [Fredosaurus C++](http://www.fredosaurus.com/notes-cpp/)
* [cplusplus.com](http://www.cplusplus.com/)
* [cplusplus.com - Inline Function](http://www.cplusplus.com/articles/2LywvCM9/)
* [cppreference - Operators](http://en.cppreference.com/w/cpp/language/operator_incdec)
* [Dynamic Allocation of Arrays - Fredosaurus.com](http://www.fredosaurus.com/notes-cpp/newdelete/50dynamalloc.html)
* [Expansion of Arrays](http://www.fredosaurus.com/notes-cpp/newdelete/55dynexample.html)


## Reference Notes
1. A constructor is a special member function that has the **same name as class**. It's purpose is to ensure that each data member is set to sensible initial values.
`Source (Pg.431 -C++ Primer)`
2. Writing `std::cout` uses the **scope operator**(::) to say we want to use the name `cout` that is in the `namespace std`.
`Source (Pg.8 -C++ Primer)`
3. Each class defines an **interface** and **implementation**. The interface consists of the operations that we expect code that uses the class to execute. The implementationtypically consists the data needed by the class. The implementation also includes any functions needed to define the class but that are not intended for the general use.
`Source (Pg.63 -C++ Primer)`
4. A defintion must always end in semicolon, that is why a class definition also ends in semicolon.
5. `Pg.49 -C++ Primer`

## Class vs Struct
* CLASS
`class()
{
// if we have not used any access label, the default access label is private
};
`
* STRUCT
`struct()
{
// if we have not used any access label, the default access label is public
};
`

## Singly Linked List Implementation in c++

```c++
// Singly Linked List implementation in c++

#include <iostream>

using namespace std;

struct node
{
    int data;
    node *next;
};

class linked_list
{
private:
    node *head,*tail;
public:
    linked_list()
    {
        head = NULL;
        tail = NULL;
    }

    void add_node(int n)
    {
        node *tmp = new node;
        tmp->data = n;
        tmp->next = NULL;

        if(head == NULL)
        {
            head = tmp;
            tail = tmp;
        }
        else
        {
            tail->next = tmp;
            tail = tail->next;
        }
    }
};

int main()
{
    linked_list a;
    a.add_node(1);
    a.add_node(2);
    return 0;
}

/* Go to 
URL ="https://www.codesdope.com/blog/article/c-linked-lists-in-c-singly-linked-list/"
for a great explaination of singly linked list in c++
*/
```

## Stack implementation in c++ using Arrays

```c++
/* C++ program to implement basic stack
   operations */
#include<bits/stdc++.h>
using namespace std;
 
#define MAX 1000
 
class Stack
{
    int top;
public:
    int a[MAX];    //Maximum size of Stack
 
    Stack()  { top = -1; }
    bool push(int x);
    int pop();
    bool isEmpty();
};
 
bool Stack::push(int x)
{
    if (top >= MAX)
    {
        cout << "Stack Overflow";
        return false;
    }
    else
    {
        a[++top] = x;
        return true;
    }
}
 
int Stack::pop()
{
    if (top < 0)
    {
        cout << "Stack Underflow";
        return 0;
    }
    else
    {
        int x = a[top--];
        return x;
    }
}
 
bool Stack::isEmpty()
{
    return (top < 0);
}
 
// Driver program to test above functions
int main()
{
    struct Stack s;
    s.push(10);
    s.push(20);
    s.push(30);
 
    cout << s.pop() << " Popped from stack\n";
 
    return 0;
}
// Source for the above code :: "https://www.geeksforgeeks.org/stack-data-structure-introduction-program/" 
```
## Queue implementation using Circular Arrays
```c++
/* Queue - Circular Array implementation in C++*/
#include<iostream>
using namespace std; 
#define MAX_SIZE 101  //maximum size of the array that will store Queue. 

// Creating a class named Queue.
class Queue
{
private:
	int A[MAX_SIZE];
	int front, rear; 
public:
	// Constructor - set front and rear as -1. 
	// We are assuming that for an empty Queue, both front and rear will be -1.
	Queue()
	{
		front = -1; 
		rear = -1;
	}

	// To check wheter Queue is empty or not
	bool IsEmpty()
	{
		return (front == -1 && rear == -1); 
	}

	// To check whether Queue is full or not
	bool IsFull()
	{
		return (rear+1)%MAX_SIZE == front ? true : false;
	}

	// Inserts an element in queue at rear end
	void Enqueue(int x)
	{
		cout<<"Enqueuing "<<x<<" \n";
		if(IsFull())
		{
			cout<<"Error: Queue is Full\n";
			return;
		}
		if (IsEmpty())
		{ 
			front = rear = 0; 
		}
		else
		{
		    rear = (rear+1)%MAX_SIZE;
		    /* Remainder theorem is followed here implying
		    a = b.q+r
		    where r is the remainder and q is the quotient.
		    we know that remainder is returned by % operator
		    we also know that rear is smaller that MAX_SIZE 
		    and the % operator will return (rear+1) when the 
		    following operation is performed because
		    (rear+1) = MAX_SIZE*0 + (rear + 1)
		    a        =    b.q     +      r
		    The above thing happens because MAX_SIZE > rear
		    
		    When MAX_SIZE is equal to rear the remainder is 0
		    
		    TL:DR;
		    % == Modulo Operator
		    if a<b then a%b = a
		    */
		}
		A[rear] = x;
	}

	// Removes an element in Queue from front end. 
	void Dequeue()
	{
		cout<<"Dequeuing \n";
		if(IsEmpty())
		{
			cout<<"Error: Queue is Empty\n";
			return;
		}
		else if(front == rear ) 
		{
			rear = front = -1;
		}
		else
		{
			front = (front+1)%MAX_SIZE;
		}
	}
	// Returns element at front of queue. 
	int Front()
	{
		if(front == -1)
		{
			cout<<"Error: cannot return front from empty queue\n";
			return -1; 
		}
		return A[front];
	}
	/* 
	   Printing the elements in queue from front to rear. 
	   This function is only to test the code. 
	   This is not a standard function for Queue implementation. 
	*/
	void Print()
	{
		// Finding number of elements in queue  
		int count = (rear+MAX_SIZE-front)%MAX_SIZE + 1;
		cout<<"Queue       : ";
		for(int i = 0; i <count; i++)
		{
			int index = (front+i) % MAX_SIZE; // Index of element while travesing circularly from front
			cout<<A[index]<<" ";
		}
		cout<<"\n\n";
	}
};
int main()
{
	/*Driver Code to test the implementation
	  Printing the elements in Queue after each Enqueue or Dequeue 
	*/
   Queue Q; // creating an instance of Queue. 
   Q.Enqueue(2);  Q.Print();  
   Q.Enqueue(4);  Q.Print();  
   Q.Enqueue(6);  Q.Print();
   Q.Dequeue();	  Q.Print();
   Q.Enqueue(8);  Q.Print();
}
```

**My Github** [Link](https://github.com/adist98)

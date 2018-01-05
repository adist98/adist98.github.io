## Important Links
* [Fredosaurus C++](http://www.fredosaurus.com/notes-cpp/)
* [cplusplus.com](http://www.cplusplus.com/)
* [cplusplus.com - Inline Function](http://www.cplusplus.com/articles/2LywvCM9/)


## Reference Notes
1. A constructor is a special member function that has the **same name as class**. It's purpose is to ensure that each data member is set to sensible initial values.
`Source (Pg.431 -C++ Primer)`
2. Writing `std::cout` uses the **scope operator**(::) to say we want to use the name `cout` that is in the `namespace std`.
`Source (Pg.8 -C++ Primer)`
3. Each class defines an **interface** and **implementation**. The interface consists of the operations that we expect code that uses the class to execute. The implementationtypically consists the data needed by the class. The implementation also includes any functions needed to define the class but that are not intended for the general use.
`Source (Pg.63 -C++ Primer)`

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
**My Github** [Link](https://github.com/adist98)

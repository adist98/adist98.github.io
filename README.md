## Important Links
>> [Fredosaurus C++](http://www.fredosaurus.com/notes-cpp/)


## Go to codes to various Data Structures and Algorithms


### Singly Linked List Implementation in c++

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

### Stack implementation in c++ using Arrays

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
```
### Singly Linked List Implementation in c++
**My Github** [Link](https://github.com/adist98)

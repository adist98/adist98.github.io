## Important Links
>> [Fredosaurus C++](http://www.fredosaurus.com/notes-cpp/)


## Go to codes to various Data Structures and Algorithms


### Singly Linked List Implementation in c++

```
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
**My Github** [Link](https://github.com/adist98)

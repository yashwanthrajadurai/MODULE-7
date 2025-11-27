# Ex.No:1
# Ex.Name : Write a CPP Program to implement Queue using Linked List, insert integer elements in to Q and delete two items from Q. 

## Aim:
To write a CPP Program to implement Queue using Linked List, insert integer elements in to Q and delete two items from Q. 

## Algorithm:
1. Start
2. Create a Queue class with front and rear pointers
3. Insert elements using enqueue() (add to rear)
4. Delete elements using dequeue() (remove from front)
5. Display queue after insertion and deletion
6. Stop
   
## Program:
```
#include<iostream>
using namespace std;
struct node
{
    float data;
    node *next;
};
class Queue
{
    node *front,*back;
    public:
    Queue()
    {
        front=back=NULL;
    }
    void enqueue(float x)
    {
        node *newnode= new node;
        newnode->data=x;
        newnode->next=NULL;
        if(front==NULL)
        {
            front=back=newnode;
        }
        else
        {
            back->next=newnode;
            back=newnode;
        }
    }
    void dequeue()
    {
        node *newnode= new node;
        newnode=front;
        front=front->next;
        delete newnode;
    }
    void first()
    {
        cout<<front->data;
    }
    void last()
    {
        cout<<back->data;
    }
    void display()
    {
        if(front==NULL)
        {
            cout<<"Underflow.";
        }
        else
        {
            node *n=front;
            while(n!=NULL)
            {
                cout<<n->data<<" ";
                n=n->next;
            }
        }
    }
};
int main()
{
    Queue q;
    int n;
    cin>>n;
    q.display();
    for(int i=0;i<n;i++)
    {
        float a;
        cin>>a;
        q.enqueue(a);
    }
    cout<<endl<<"Queue :";
    q.display();
    q.dequeue();
    q.dequeue();
    cout<<endl<<"After DeQueue :";
    q.display();
    cout<<endl<<"Queue Front : ";
    q.first();
    cout<<endl<<"Queue Rear : ";
    q.last();
}
```

## Output:
<img width="830" height="481" alt="Screenshot 2025-10-11 135336" src="https://github.com/user-attachments/assets/8fca1a9f-3150-402d-b8bd-6b180f55da74" />

## Result:
The Program Executed Successfully.



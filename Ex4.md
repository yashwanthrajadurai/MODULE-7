# Ex.No:4
# Ex.Name : Write a CPP Program to insert five integer elements in to Stack using Linked LIst (use STL for Stack)

## Aim:
To write a CPP Program to insert five integer elements in to Stack using Linked LIst (use STL for Stack)

## Algorithm:
1. Start
2. Declare a stack using STL (stack<int>)
3. Read 5 integer elements from the user
4. Insert each element into the stack using push()
5. Display stack elements by accessing top()
6. Pop each element until the stack is empty
7. Stop

## Program:
```
// C++ implementation of stack
// using list STL
#include <bits/stdc++.h>
using namespace std;
#include<stack>
#include<iostream>
int main()
{
	stack<int> s;
	int n,x;
	cin>>n; 
   //insert elements into stack
   for(int i=0;i<n;i++)
    {
     cin>>x;    
     s.push(x);
    }
	cout << "Current size of the stack is " << s.size()<< endl;
	cout << "The top element of the stack is " << s.top()<< endl;
	s.pop(); // popping from the stack
	cout << "The top element after 1 pop operation is "<< s.top() << endl; // printing the top of the stack
	s.pop(); // popping
	cout << "The top element after 2 pop operations is "
		<< s.top() << endl;
	cout << "Size of the stack after 2 pop operations is "
		<< s.size() << endl;
	return 0;
}
```


## Output:
<img width="1211" height="483" alt="Screenshot 2025-10-11 142205" src="https://github.com/user-attachments/assets/5456b27c-feec-461c-b2b9-c981e75fed0e" />

## Result:
The Program Executed Successfully.



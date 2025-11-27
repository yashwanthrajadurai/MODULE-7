# Ex.No:3
# Ex.Name : Write a CPP program for Infix To Prefix Conversion using Linked List Stack STL

## Aim:
To write a CPP program for Infix To Prefix Conversion using Linked List Stack STL

## Algorithm:
1. Start
2. Read the infix expression
3. Reverse the infix expression
4. Replace ( with ) and vice versa
5. Use a stack to process operators and operands
6. If operand → add to result
7. If operator → pop from stack while precedence is higher, then push current operator
8. After traversal, pop remaining operators
9. Reverse the result to get prefix expression
10. Display prefix result and stop

## Program:
```
#include <iostream>
#include<cstring>
#include<stack>
#include <bits/stdc++.h>
using namespace std;

struct Node{
    char data;
    struct Node * next;
}*top=NULL;

void Push(char x)
{   struct Node* p=new Node;
    if(p==NULL)
        cout<<"\nStack Overflow";
    else{
        p->data=x;
        p->next=top;
        top=p;
    }
}  

char Pop(){
    int x=-1;
    struct Node * p;
    if(top==NULL)
        cout<<"\nStack is Empty";
    else{
         p=top;
         x=p->data;
         top = top->next;
         delete p;
    }
    return x;
}

int isEmpty(){
    return top?0:1;
}

int precedence(char ch)
{
  if(ch=='+'||ch=='-')
    return 1;
  else{
    if(ch=='*'||ch=='/')
      return 2;
    else
      return 3;
  }
}

string infixToPrefix(string infix){
    stack<char> s;
    int length=0,i,t;
string prefix="";
    cin>>infix;
    
    length=infix.length();
    
    // Reverse infix
    reverse(infix.begin(), infix.end());

    for(i=0;i<length;i++){
      t=precedence(infix[i]);
      if(t==3){
        prefix+=infix[i];
        continue;
      }
      else{
        if(s.empty() || t>=precedence(s.top())){
          s.push(infix[i]);
          continue;
        }
        else{
          while(!s.empty() && t<precedence(s.top())){
            prefix+=s.top();
            s.pop();
          }
          s.push(infix[i]);
          continue;
        }
      }
    }
    while(!s.empty()){
      prefix +=s.top();
      s.pop();
    }

    reverse(prefix.begin(),prefix.end());

    return prefix;
}
int main(){
    char *infix = new char[0];
    cin>>infix;
   cout<<infixToPrefix(infix);
}
```


## Output:
<img width="857" height="379" alt="Screenshot 2025-10-11 141855" src="https://github.com/user-attachments/assets/e43c7753-3f12-4d99-b9a9-1319c658c13b" />

## Result:
The Program Executed Successfully.

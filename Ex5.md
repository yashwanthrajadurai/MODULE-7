# Ex.No:5
# Ex.Name :write a C++ program to implement FCFS algorithm(to read no of.process p1,p2,p3 and p4 and its burst time from the user) & find out waiting time ,Turn Around time  & Average turn around time of the the process?

## Aim:
To write a C++ program to implement FCFS algorithm(to read no of.process p1,p2,p3 and p4 and its burst time from the user) & find out waiting time ,Turn Around time  & Average turn around time of the the process?

## Algorithm:
1. Start
2. Read number of processes and their burst times
3. Set waiting time for first process as 0
4. Calculate each process’s waiting time = sum of previous burst times
5. Calculate turnaround time = burst time + waiting time
6. Find total and average waiting time
7. Find total and average turnaround time
8. Display all results
9. Stop

## Program:
```
#include<iostream>
using namespace std;

    
int main()
{
    int n = 4;
    int bt[n],wt[n],tat[n],ta=0;
    for(int i=0;i<n;i++)
    {
        cin>>bt[i];
    }

    wt[0]=0;
    for (int  i = 1; i < n ; i++ )
        wt[i] =  bt[i-1] + wt[i-1] ;
         for (int  i = 0; i < n ; i++ )
         {
        tat[i] =  bt[i] + wt[i] ;
        ta=ta+tat[i];
         }
 
    cout <<"Processes   BT time   WT time   TA time\n"; 
    for (int  i=0; i<n; i++)
    {
        cout<<"       "<<i+1<<"       "<<bt[i]<<"       "<<wt[i]<<"       "<<tat[i]<<endl;
     
    }
    cout<<"Average turn around time = "<<(float)ta/n;
    
}
```


## Output:
<img width="1016" height="668" alt="Screenshot 2025-10-11 142600" src="https://github.com/user-attachments/assets/b2526883-65b3-4213-ae58-bb8f88788fe0" />

## Result:
The Program Executed Successfully.

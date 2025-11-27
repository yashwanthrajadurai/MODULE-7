# Ex.No:2
# Ex.Name : write a C++ program to implement FCFS algorithm(no of.process p1,p2 and p3 and its burst time are 10,5 & 8) find out waiting time,turn around time,average waiting time & average turn around time?

## Aim:
To write a C++ program to implement FCFS algorithm(no of.process p1,p2 and p3 and its burst time are 10,5 & 8) find out waiting time,turn around time,average waiting time & average turn around time?

## Algorithm:
1. Start
2. Input number of processes and their burst times
3. Set waiting time of first process to 0
4. Calculate each process’s waiting time = sum of previous burst times
5. Compute turnaround time = burst time + waiting time
6. Find total and average waiting time
7. Find total and average turnaround time
8. Display all values
9. Stop

## Program:
```
#include<bits/stdc++.h>
using namespace std;

int main(){
    int processes[] = {1,2,3};
    int n = sizeof processes/sizeof processes[0];
    
    int bt[] = {10,5,8};
    
    cout<<"Processes"<<"   "<<"BT time"<<"   "<<"WT time"<<"   "<<"TA time"<<endl;
    int wt[n],tat[n],total_tat=0;
    float total_wt=0;
    wt[0] = 0;
    for(int i=1;i<n;i++){
        wt[i] = bt[i-1]+wt[i-1];
    }
    
    for(int i=0;i<n;i++){
        tat[i] = bt[i]+wt[i];
    }
    
    for(int i=0;i<n;i++){
        total_wt += wt[i];
        total_tat += tat[i];
        cout<<"       "<<processes[i]<<"       "<<bt[i]<<"       "<<wt[i]<<"       "<<tat[i]<<endl;
    }
    cout<<"Average waiting time = "<<total_wt/n<<endl;
    cout<<"Average turn around time = "<<total_tat/n<<endl;
}
```


## Output:
<img width="1082" height="390" alt="Screenshot 2025-10-11 141512" src="https://github.com/user-attachments/assets/f969b814-380e-4c32-941d-744366ba7094" />

## Result:
The Program Executed Successfully.



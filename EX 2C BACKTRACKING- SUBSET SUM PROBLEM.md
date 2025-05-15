# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE: 11.3.25
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.


## Algorithm
1. Check if the current index has reached the end of the array; if yes, verify if the current sum equals the target.

2. If the current sum exceeds the target, return False early to prune the search.

3. If the current sum matches the target, return True as a subset is found.

4. Recursively explore two choices: excluding the current element or including it in the sum.

5. Return True if either choice leads to a solution, otherwise return False.


## Program:
```
/*
Program to implement Subset sum problem.
Developed by: LISIANA T
Register Number:  212222240053
*/
def SubsetSum(a,i,sum,target,n):
    if i==n:
        return sum==target
    if sum>target:
        return False
    if sum==target:
        return True
    return SubsetSum(a,i+1,sum,target,n) or SubsetSum(a,i+1,sum+a[i],target,n)

a=[]
size=int(input())
for i in range(size):
    x=int(input())
    a.append(x)

target=int(input())
n=len(a)
if(SubsetSum(a,0,0,target,n)==True):
    for i in range(size):
        print(a[i])
    print("True,subset found")
else:
    for i in range(size):
        print(a[i])
    print("False,subset not found")


```

## Output:

![image](https://github.com/user-attachments/assets/7f772352-9d78-44a6-8808-d75260fb297d)



## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.

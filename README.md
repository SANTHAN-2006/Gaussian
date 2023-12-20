# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Read the number of equations n.
Initialize matrix matrix and solution vector x.

2. Use nested loops to input coefficients into the augmented matrix.

3. For each pivot row, eliminate coefficients below the diagonal by subtracting a multiple of the pivot row.

4. Starting from the last row, solve for variables backward using the updated matrix.

5. Print the solution vector x with a formatted message for each variable.
## Program:
```python
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: K Santhan Kumar
RegisterNumber: 212223240065
*/
import numpy as np
import sys
n=int(input())
matrix=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        matrix[i][j]=int(input())
for i in range(n):
    if matrix[i][j]==0.0:
        sys.exit("Divide by zero error")
    for j in range(i+1,n):
        ratio=matrix[j][i]/matrix[i][i]
        for k in range(n+1):
            matrix[j][k]=matrix[j][k]-ratio*matrix[i][k]
#Back Substitution
x[n-1]=matrix[n-1][n]/matrix[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=matrix[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-matrix[i][j]*x[j]
    x[i]=x[i]/matrix[i][i]
for i in range(n):
    print("X%d = %0.2f" %(i,x[i]),end=" ")
```

## Output:
![image](https://github.com/SANTHAN-2006/Gaussian/assets/80164014/40b1d095-9adb-4371-8168-cb1c0744d464)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.


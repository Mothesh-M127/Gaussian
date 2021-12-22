# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. To start the program.
2. Import numpy as np and import sys
3. Using the sys exit to check divide by zero detected.
4. Using the for loop to check the given entries and solve it.
5. To display the output of the program.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Mothesh M
RegisterNumber: 21006007
*/
```
'''Program to solve a matrix using Gaussian elimination with partial pivoting.
Developed by: 
RegisterNumber: 
'''
import numpy as np

import sys

n = int(input())

a = np.zeros((n,n+1))

X = np.zeros(n)

for i in range(n):

    for j in range(n+1):
    
        a[i][j] = float(input())
        
for i in range(n):

    if a[i][i] == 0.0:
    
        sys.exit('Divide by zero detected')
        
    for j in range(i+1, n):
    
        ratio = a[j][i]/a[i][i]
        
        for k in range(n+1):
        
            a[j][k] = a[j][k] - ratio * a[i][k]
            
X[n-1] = a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):

    X[i] = a[i][n]
    
    for j in range(i+1,n):
    
        X[i] = X[i] - a[i][j]*X[j]
        
    X[i] = X[i]/a[i][i]
    
for i in range(n):

    print('X%d = %0.2f' %(i,X[i]), end = ' ')

## Output:
![33](https://user-images.githubusercontent.com/94170892/147045754-2dbf54d3-fbb7-4d3f-a662-f34a41de7316.png)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.


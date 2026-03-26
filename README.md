# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import numpy as np.
2. Obtain the dimension of matrix.  
3. Initialise an augmented A matrix with zeros and a X matrix with zeros.  
4. Obtain values, obtain ratio and perform forward elmination algo
5. Now do back substitution and print results.

## Program:
```python
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Jacob Antony M
RegisterNumber: 212225040137
'''
import os 
os.environ["OPENBLAS_NUM_THREADS"]="1"

import numpy as np
import sys

n = int(input())

a = np.zeros((n, n+1))
x = np.zeros(n)

for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())

for i in range(n):
    if a[i][i] == 0.0:
        sys.exit("Divide by zero detected!")
    
    for j in range(i+1, n):
        ratio = a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]

x[n-1] = a[n-1][n] / a[n-1][n-1]

for i in range(n-2, -1, -1):
    x[i] = a[i][n]
    
    for j in range(i+1, n):
        x[i] = x[i] - a[i][j] * x[j]
    
    x[i] = x[i] / a[i][i]
    
for i in range(n):
    print(f"X{i} = {x[i]:.2f}", end = ' ')

```

## Output:

<img width="1206" height="696" alt="exp 6 -1" src="https://github.com/user-attachments/assets/db112aee-334b-43da-a6b9-2d29ea403884" />

<img width="1196" height="812" alt="exp 6 -2" src="https://github.com/user-attachments/assets/039cbc04-09bf-44d6-bd0b-b8f1a4d8f0eb" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.


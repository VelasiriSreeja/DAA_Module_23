# EX 5A Minimum Cost Path
## DATE:22.05.25
## AIM:
To write a Python program using A Naive recursive implementation of Minimum Cost Path Problem.
## Algorithm
1. If at (0,0), return cost at (0,0).
2. If in the first row (m=0), return cost at (0,n) + min cost from (0, n-1).
3. If in the first column (n=0), return cost at (m,0) + min cost from (m-1, 0).
4. Else, return cost at (m,n) + minimum of min cost from (m-1,n) and (m, n-1).  

## Program:
```

A program to implement to find the Minimum Cost Path Problem using a  Naive recursive Approach.

Developed by:sreeja.v
Register Number: 212222230169 

R = int(input())
C = int(input())
def minCost(cost, m, n):
    tc = [[0 for x in range(C)] for x in range(R)]
    tc[0][0] = cost[0][0]
    for i in range(1, m+1):
        tc[i][0] = tc[i-1][0] + cost[i][0]
    for j in range(1, n+1):
        tc[0][j] = tc[0][j-1] + cost[0][j]
    for i in range(1, m+1):
        for j in range(1, n+1):
            tc[i][j] = min(tc[i-1][j-1], tc[i-1][j], tc[i][j-1]) + cost[i][j]
 
    return tc[m][n]
 
cost = [[1, 2, 3],
        [4, 8, 2],
        [1, 5, 3]]
print(minCost(cost, R-1, C-1))

```

## Output:

![Screenshot 2025-05-22 212548](https://github.com/user-attachments/assets/45307d78-7837-41db-9d29-94c5e90a6879)


## Result:
Thus the above program was executed successfully for finding the minimum cost.

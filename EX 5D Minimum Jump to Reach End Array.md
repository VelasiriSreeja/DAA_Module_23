# EX 5D Minimum Jump to Reach End Array
## DATE:22.05.25
## AIM:
To write a python program for finding the minimum number of jumps needed to reach end of the array using Dynamic Programming.


## Algorithm
1. Initialize jumps[] with size of array, set jumps[0] = 0, rest to infinity.
2. Loop i from 1 to n-1 (end of array).
3. For each j from 0 to i-1:
4. If i is reachable from j (i ≤ j + arr[j]), update jumps[i] = min(jumps[i], jumps[j] + 1).
5. Return jumps[n-1] as the minimum number of jumps to reach the end.
  

## Program:
```

To implement the program to finding the minimum number of jumps needed to reach end of the array.


Developed by: sreeja.v
Register Number: 212222230169 

def minJumps(arr, n):
    ##########  Add your code here ##############
    #Start here
    jumps = [0 for i in range(n)]
    if (n == 0) or (arr[0] == 0):
        return float('inf')
    jumps[0] = 0
    for i in range(1, n):
        jumps[i] = float('inf')
        for j in range(i):
            if (i <= j + arr[j]) and (jumps[j] != float('inf')):
                jumps[i] = min(jumps[i], jumps[j] + 1)
                break
    return jumps[n-1]
    #End here
arr = []
n = int(input()) #len(arr)
for i in range(n):
    arr.append(int(input()))
print('Minimum number of jumps to reach','end is', minJumps(arr,n))
 
```

## Output:
![Screenshot 2025-05-22 220145](https://github.com/user-attachments/assets/99f33b75-bbdc-413a-aeeb-727be256b72b)



## Result:
Thus the program was executed successfully for finding the minimum number of jumps to reach end.

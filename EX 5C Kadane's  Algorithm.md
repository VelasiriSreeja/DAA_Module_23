# EX 5C Kadane's Algorithm
## DATE:22.05.25
## AIM:
To write a python program to find the maximum contiguous subarray.


## Algorithm
1. Initialize max_so_far = current_max = first element of array.
2. Traverse the array from the second element.
3. At each step, set current_max = max(current element, current_max + current element).
4. Update max_so_far = max(max_so_far, current_max).
5. Return max_so_far as the result.
   

## Program:
```

To implement the program to find the maximum contiguous subarray.


Developed by:sreeja.v 
Register Number:  212222230169

def maxSubArraySum(a,size):
    #####################  Add your Code here #############
    #Start here
    max_so_far = a[0]
    max_ending_here = 0
    for i in range(0, size):
        max_ending_here = max_ending_here + a[i]
        if max_ending_here < 0:
            max_ending_here = 0
        elif (max_so_far < max_ending_here):
            max_so_far = max_ending_here
              
    return max_so_far
    #End here
n=int(input())  
a =[] #[-2, -3, 4, -1, -2, 1, 5, -3]
for i in range(n):
    a.append(int(input()))
print("Maximum contiguous sum is", maxSubArraySum(a,n))
```

## Output:

![Screenshot 2025-05-22 213507](https://github.com/user-attachments/assets/ca23ed9f-4723-44d5-ae84-6ff50a304bda)


## Result:
Thus the program was executed successfully for finding the maximum contiguous sum of subarray..

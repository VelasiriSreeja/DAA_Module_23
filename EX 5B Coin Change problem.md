# EX 5B Coin Change Problem
## DATE:22.05.25
## AIM:
To compute the fewest number of coins that we need to make up the amount given.


## Algorithm
1. Initialize an array dp[] where dp[i] stores the fewest coins for amount i; set dp[0] = 0 and others to a large number.
2. For each amount from 1 to target amount:
3.   For each coin in the coin set:
4.     If coin ≤ current amount, update dp[current amount] = min(dp[current amount], dp[current amount - coin] + 1).
5. Return dp[target amount] if it’s not infinity; otherwise, no solution exists.

## Program:
```

Create a python function to compute the fewest number of coins that we need to make up the amount given.

.
Developed by: sreeja.v
Register Number: 212222230169 


class Solution(object):
    def coinChange(self, coins, amount):
        ####################      Add your Code Here ###########
        #End here
        if amount == 0 :
            return 0
        if min(coins) > amount:
            return -1
        dp = [-1 for i in range(0, amount + 1)]
        for i in coins:
            if i > len(dp) - 1:
                continue
            dp[i] = 1
            for j in range(i + 1, amount + 1):
                if dp[j - i] == -1:
                    continue
                elif dp[j] == -1:
                    dp[j] = dp[j - i] + 1
                else:
                    dp[j] = min(dp[j], dp[j - i] + 1)
        return dp[amount]
    #End here
      
ob1 = Solution()
n=int(input())
s=[]
amt=int(input())
for i in range(n):
    s.append(int(input()))
print(ob1.coinChange(s,amt))
```

## Output:

![Screenshot 2025-05-22 213507](https://github.com/user-attachments/assets/8ba3d98f-6c12-4b1d-a76d-8680e08368e8)


## Result:
Thus the program was executed successfully for finding the minimum number of coins required to make amount.

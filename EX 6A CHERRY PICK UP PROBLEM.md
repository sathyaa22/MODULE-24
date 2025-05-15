# EX 6A CHERRY PICK UP PROBLEM

## DATE: 13.05.2025

## AIM:
To Create a python program for the following problem statement.
You are given an n x n grid representing a field of cherries, each cell is one of three possible integers.
0	means the cell is empty, so you can pass through,
1	means the cell contains a cherry that you can pick up and pass through, or
-1 means the cell contains a thorn that blocks your way.
Return the maximum number of cherries you can collect by following the rules below:
Starting at the position (0, 0) and reaching (n - 1, n - 1) by moving right or down through valid path cells (cells with value 0 or 1).
After reaching (n - 1, n - 1), returning to (0, 0) by moving left or up through valid path cells.
When passing through a path cell containing a cherry, you pick it up, and the cell becomes an empty cell 0. If there is no valid path between (0, 0) and (n - 1, n - 1), then no cherries can be collected.



## Algorithm

1. Start the program.
2. Model the problem as two people starting at (0, 0) and moving to (n-1, n-1) simultaneously, each taking only right or down steps.
3. Define a dynamic programming state dp(r1, c1, c2) where person A is at (r1, c1) and person B is at (r2, c2) with r2 = r1 + c1 - c2.
4. If any of the positions are out of bounds or on a thorn (-1), return negative infinity to indicate an invalid path.
5. If both people reach the bottom-right corner, return the cherry value at that cell.
6. At each valid state, collect cherries from both positions, counting only once if both are on the same cell.
7. Recursively compute the best result from the four possible move combinations (right or down for each person) and add to current cherries.
8. Use memoization to optimize the recursion, and return max(0, dp(0, 0, 0)) as the final result.
9. End the program.


## Program:

```
To implement the program for Cherry pickup problem.
Developed by: SATHYAA R
Register Number: 212223100052
```

```
class Solution:
    def cherryPickup(self, grid):
        n = len(grid)
        dp = [[-1] * (n + 1) for _ in range(n + 1)]
        dp[1][1] = grid[0][0]
        for m in range(1, (n << 1) - 1):
            for i in range(min(m, n - 1), max(-1, m - n), -1):
                for p in range(i, max(-1, m - n), -1):
                    j, q = m - i, m - p
                    if grid[i][j] == -1 or grid[p][q] == -1:
                        dp[i + 1][p + 1] = -1
                    else:
                        dp[i + 1][p + 1] = max(dp[i + 1][p + 1], dp[i][p + 1], dp[i + 1][p], dp[i][p])
                        if dp[i + 1][p + 1] != -1: dp[i + 1][p + 1] += grid[i][j] + (grid[p][q] if i != p else 0)
        return max(0, dp[-1][-1])
        n,m=len(grid),len(grid[0])
        dp = [[[-1 for i in range(m)] for j1 in range(n)] for j2 in range(n)]
        return f(0,0,m-1,dp)
obj=Solution()
grid=[[0,1,-1],[1,0,-1],[1,1,1]]        
print(obj.cherryPickup(grid))
```


## Output:

![image](https://github.com/user-attachments/assets/460c038a-8c47-41df-ac2b-2890c5fa2696)


## Result:
Thus the above program was executed successfully for finding the maximum number of cherries from grid.

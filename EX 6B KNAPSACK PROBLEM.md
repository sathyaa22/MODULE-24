# EX 6B KNAPSACK PROBLEM

## DATE: 13.05.2025

## AIM:
To demonstrate a python program using dynamic programming for 0/1 knapsack problem.


## Algorithm

1. Start the program.
2. Take inputs of list of item values and weights, and a total knapsack capacity W.
3. Define a recursive function knapSack(W, wt, val, n) where n is the number of items.
4. If there are no items left (n == 0) or the capacity is zero (W == 0), return 0.
5. If the weight of the current item is more than the remaining capacity, skip it and solve for the remaining items.
6. Otherwise, choose the maximum of two options: including the current item or excluding it.
7. To include the item, add its value and subtract its weight from the remaining capacity in the recursive call.
8. Finally, return the maximum value obtained from both choices as the optimal solution.
9. End the program.


## Program:

```
To implement the program for 0/1 knapsack problem.
Developed by: SATHYAA R
Register Number: 212223100052
```

```
def knapSack(W, wt, val, n):
	if n == 0 or W == 0 :
		return 0
	if (wt[n-1] > W):
		return knapSack(W, wt, val, n-1)
	else:
		return max(val[n-1] + knapSack(W-wt[n-1], wt, val, n-1), knapSack(W, wt, val, n-1))

x=int(input())
y=int(input())
W=int(input())
val=[]
wt=[]
for i in range(x):
    val.append(int(input()))
for y in range(y):
    wt.append(int(input()))

n = len(val)
print('The maximum value that can be put in a knapsack of capacity W is: ',knapSack(W, wt, val, n))
```


## Output:

![image](https://github.com/user-attachments/assets/ec23103c-220d-4b36-922d-aaeabc56880f)


## Result:
Thus the program was executed successfully for finding the maximum value that can be put in a knap sack of capacity .

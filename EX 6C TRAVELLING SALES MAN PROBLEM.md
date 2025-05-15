# EX 6C TRAVELLING SALES MAN PROBLEM

## DATE: 13.05.2025

## AIM:
To Solve Travelling Sales man Problem for the following graph.

![image](https://github.com/user-attachments/assets/653921a4-3d7b-4691-9b41-735e80f7af0b)



## Algorithm

1. Start the program.
2. Create a list of all vertices except the starting vertex to represent cities that need to be visited.
3. Initialize a variable to store the minimum path cost as infinity (a very large number).
4. Generate all possible permutations of the cities to consider every possible visiting order.
5. For each permutation, initialize a path cost and start from the source city.
6. Traverse the cities in the order of the permutation and add the edge weights to the current path cost.
7. After completing the permutation path, add the return cost from the last city back to the starting city.
8. Update the minimum path cost if the current path cost is less than the recorded minimum.
9. End the program.


## Program:

```
To implement the program for TSP.
Developed by: SATHYAA R
Register Number: 212223100052
```

```
from sys import maxsize
from itertools import permutations
V = 4
def travellingSalesmanProblem(graph, s):
    vertex = []
    for i in range(V):
        if i != s:
            vertex.append(i)
    min_path = maxsize
    next_permutation=permutations(vertex)
    for i in next_permutation:
        current_pathweight = 0
        k = s
        for j in i:
            current_pathweight += graph[k][j]
            k = j
        current_pathweight += graph[k][s]
        min_path = min(min_path, current_pathweight)
    return min_path
if __name__ == "__main__":
    graph = [[0, 10, 15, 20], [10, 0, 35, 25],
        [15, 35, 0, 30], [20, 25, 30, 0]]
    s=0
    print(travellingSalesmanProblem(graph, s))
```


## Output:

![image](https://github.com/user-attachments/assets/5c703ffc-6727-4667-b873-15ebfaa4f22e)


## Result:
Thus the program was executed successfully for finding the minimum cost to vist all cities.

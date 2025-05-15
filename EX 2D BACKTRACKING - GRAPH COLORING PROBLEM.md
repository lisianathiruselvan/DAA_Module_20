# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## DATE: 15.3.25
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.



## Algorithm
1. Start with the first vertex and try all possible colors from 1 to m.

2. For each color, check if assigning it to the current vertex is safe (i.e., no adjacent vertex has the same color).

3. If it's safe, assign the color and recursively color the next vertex.

4. If assigning the color leads to a solution, return true; otherwise, backtrack and try the next color.

5. If no color can be assigned to a vertex, return false (no solution exists).


## Program:
```
/*
Program to implement Graph Coloring Problem using backtracking.
Developed by: LISIANA T
Register Number: 212222240053 
*/
class Graph:
    def __init__(self,vertices):
        self.V=vertices
        self.Graph=[[0 for column in range(vertices)]for row in range(vertices)]
    def isSafe(self,v,colour,c):
        for i in range(self.V):
            if self.graph[v][i]==1 and colour[i]==c:
                return False
        return True
    def graphColouringUtil(self,m,colour,v):
        if v==self.V:
            return True
        for c in range(1,m+1):
            if self.isSafe(v,colour,c):
                colour[v]=c
                if self.graphColouringUtil(m,colour,v+1):
                    return True
                colour[v]=c
        return False
        
    def graphColouring(self,m):
        colour=[0]*self.V
        if not self.graphColouringUtil(m,colour,0):
            print("No solution Exist")
            return False
        print("Solution exist and Following are the assigned colours:")
        for c in colour:
            print(c,end=' ')
        print()
        return True
```

## Output:

![image](https://github.com/user-attachments/assets/5e6de3af-10e2-4fe9-9818-d3d0697b20ac)


## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.

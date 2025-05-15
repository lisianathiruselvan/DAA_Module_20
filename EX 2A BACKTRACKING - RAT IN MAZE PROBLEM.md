# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE: 4.3.25
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.


## Algorithm
1. Start at the top-left corner of the maze (0,0).

2. Check if the current cell is safe (within bounds and not blocked).

3. Mark the current cell as part of the solution path.

4. Recursively try to move right or down to find a path to the bottom-right corner.

5. If neither move leads to a solution, backtrack by unmarking the current cell and return false.


## Program:
```
/*
Program to implement Rat in a Maze.
Developed by: LISIANA T
Register Number:  212222240053
*/



N = 4
 
def printSolution( sol ):
     
    for i in sol:
        for j in i:
            print(str(j) + " ", end ="")
        print("")
 

def isSafe( maze, x, y ):
     
    if x >= 0 and x < N and y >= 0 and y < N and maze[x][y] == 1:
        return True
     
    return False
 

def solveMaze( maze ):
     
    # Creating a 4 * 4 2-D list
    sol = [ [ 0 for j in range(4) ] for i in range(4) ]
     
    if solveMazeUtil(maze, 0, 0, sol) == False:
        print("Solution doesn't exist");
        return False
     
    printSolution(sol)
    return True
     

def solveMazeUtil(maze, x, y, sol):
#Write your code here
    if x==N-1 and y==N-1 and maze[x][y]==1:
        sol[x][y]=1
        return True
    if isSafe( maze, x, y ):
        sol[x][y]=1
        if solveMazeUtil(maze, x+1, y, sol):
            return True
        if solveMazeUtil(maze, x, y+1, sol):
            return True
        sol[x][y]=0
    return False

if __name__ == "__main__":
    # Initialising the maze
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]
              
    solveMaze(maze)



```

## Output:

![image](https://github.com/user-attachments/assets/a6235ecf-f93f-42bd-b847-31f72bf57a37)



## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.

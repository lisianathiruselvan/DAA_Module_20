# EX 2B BACKTRACKING - NQUEEN PROBLEM
## DATE: 8.3.25
## AIM:
To solve the N-Queen problem using backtracking, which places N queens on an N*N chessboard such that no two queens threaten each other.


## Algorithm
1. Start placing queens one column at a time, beginning from the leftmost column.

2. For each column, try placing a queen in every row and check if it is safe (no other queen attacks it).

3. If safe, place the queen and move to the next column recursively.

4. If placing a queen leads to no solution, backtrack by removing the queen and try the next row.

5. Repeat until all queens are placed or no solution is found.

## Program:
```
/*
Program to implement N-Queen problem using backtracking.
Developed by: LISIANA T
Register Number:  212222240053
*/

global N
N = int(input())
 
def printSolution(board):
    for i in range(N):
        for j in range(N):
            print(board[i][j], end = " ")
        print()
 
def isSafe(board, row, col):
 
    # Check this row on left side
    for i in range(col):
        if board[row][i] == 1:
            return False
 
    # Check upper diagonal on left side
    for i, j in zip(range(row, -1, -1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    # Check lower diagonal on left side
    for i, j in zip(range(row, N, 1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    return True
 
def solveNQUtil(board, col):
 # Write your code here
      if col>=N:
          return True
      for i in range(N):
          if isSafe(board, i, col):
              board[i][col]=1
              if solveNQUtil(board, col+1):
                  return True
              board[i][col]=0
      return False
def solveNQ():
    board = [ [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0]]
 
    if solveNQUtil(board, 0) == False:
        print ("Solution does not exist")
        return False
 
    printSolution(board)
    return True
 
# Driver Code
solveNQ()

```

## Output:

![image](https://github.com/user-attachments/assets/4fb04545-d136-4f6d-81b8-ad891e75df03)


## Result:
The N-Queens program executed successfully, and a valid board configuration was generated.

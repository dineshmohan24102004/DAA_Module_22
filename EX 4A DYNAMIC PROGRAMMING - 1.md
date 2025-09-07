# EX 4A DYNAMIC PROGRAMMING - 1
## DATE:
## AIM:
To find longest common subsequence using Dynamic Programming.



## Algorithm
Start the program.

Input two strings u and v.

Define the function lcs(u, v) to construct a DP table c:

Initialize a 2D table c of size (len(u)+1) × (len(v)+1) with -1.

Set the last row and last column of c to 0 (base case).

Traverse the strings in reverse order:

If u[i] == v[j], set c[i][j] = 1 + c[i+1][j+1].

Otherwise, set c[i][j] = max(c[i+1][j], c[i][j+1]).

Return the DP table c.

Define the function print_lcs(u, v, c) to reconstruct one possible LCS:

Initialize i = 0, j = 0.

While neither string is fully traversed:

If u[i] == v[j], print the character and move diagonally (i+1, j+1).

Else, move in the direction of the larger value from c[i+1][j] and c[i][j+1].

Call lcs(u, v) to compute the DP table.

Call print_lcs(u, v, c) to display the longest common subsequence. 

## Program:
```
/*
Program to implement the longest common subsequence using Dynamic Programming

.
Developed by: Dinesh M
Register Number: 212222040039

def lcs(u, v):
    """Return c where c[i][j] contains length of LCS of u[i:] and v[j:]."""
    c = [[-1]*(len(v) + 1) for _ in range(len(u) + 1)]
    for i in range(len(u) + 1):
        c[i][len(v)] = 0
    for j in range(len(v)):
        c[len(u)][j] = 0
 
    for i in range(len(u) - 1, -1, -1):
        for j in range(len(v) - 1, -1, -1):
            if u[i] == v[j]:
                c[i][j] = 1 + c[i + 1][j + 1]
            else:
                c[i][j] = max(c[i + 1][j], c[i][j + 1])
    return c
 
def print_lcs(u, v, c):
    """Print one LCS of u and v using table c."""
    i = j = 0
    while not (i == len(u) or j == len(v)):
        if u[i] == v[j]:
            print(u[i], end='')
            i += 1
            j += 1
        elif c[i][j + 1] > c[i + 1][j]:
            j += 1
        else:
            i += 1
 
u = input()
v = input()
c = lcs(u, v)
print_lcs(u, v, c)
*/
```

## Output:
<img width="1313" height="383" alt="Screenshot 2025-09-07 184858" src="https://github.com/user-attachments/assets/91ff10e9-9734-49da-8e14-0039f56f548d" />



## Result:
Thus the program was executed successfully for computing the length of longest common subsequence.

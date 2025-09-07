# EX 4B DYNAMIC PROGRAMMING – 2
## DATE:
## AIM:
To find the longest string (or strings) that is a substring (or are substrings) of two strings..



## Algorithm
Start the program.

Input two strings X and Y.

Define the function LCS(X, Y, m, n) where:

Initialize maxLength = 0 and endingIndex = m.

Create a 2D table lookup[m+1][n+1], initialized with zeros.

For each character X[i-1] and Y[j-1]:

If they match, set lookup[i][j] = lookup[i-1][j-1] + 1.

Update maxLength and endingIndex if a longer substring is found.

Return the substring X[endingIndex - maxLength : endingIndex].

Call the function with lengths m = len(X) and n = len(Y).

Print the longest common substring.

Stop the program. 

## Program:
```
/*
Program to implement the longest common substring problem

.
Developed by: Dinesh M
Register Number: 212222040039

def LCS(X, Y, m, n):
    maxLength = 0
    endingIndex = m
    lookup = [[0 for x in range(n + 1)] for y in range(m + 1)]
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if X[i - 1] == Y[j - 1]:
                lookup[i][j] = lookup[i - 1][j - 1] + 1
                if lookup[i][j] > maxLength:
                    maxLength = lookup[i][j]
                    endingIndex = i
    return X[endingIndex - maxLength: endingIndex]

X = input()
Y = input()
m = len(X)
n = len(Y)
print('The longest common substring is', LCS(X, Y, m, n))       
*/
```

## Output:
<img width="1398" height="383" alt="Screenshot 2025-09-07 185124" src="https://github.com/user-attachments/assets/2c7c64dc-0b2b-476e-87a2-68047b46ffda" />



## Result:
Thus the program was executed successfully for finding the longest common substring .

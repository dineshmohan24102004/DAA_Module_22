# EX 4C DYNAMIC PROGRAMMING – 3
## DATE:
## AIM:
Given a sequence, find the length of the longest palindromic subsequence in it.





## Algorithm
Start the program.

Input a string seq.

Reverse the string and store it as s2.

Define a 2D array dp[1001][1001] initialized with -1 for memoization.

Define a recursive function lps(s1, s2, n1, n2) that:

Returns 0 if n1 == 0 or n2 == 0.

If already computed, return dp[n1][n2].

If s1[n1-1] == s2[n2-1], store 1 + lps(s1, s2, n1-1, n2-1) in dp[n1][n2].

Otherwise, store max(lps(s1, s2, n1-1, n2), lps(s1, s2, n1, n2-1)) in dp[n1][n2].

Return the result.

Call lps(seq[::-1], seq, n, n) to compute the LPS length.

Print the result.

Stop the program.   

## Program:
```
/*
Program to implement to find the length of the longest palindromic subsequence in it

.
Developed by:  Dinesh M
Register Number: 212222040039

dp = [[-1 for i in range(1001)]for j in range(1001)]
def lps(s1, s2, n1, n2):
    if (n1 == 0 or n2 == 0):
        return 0
    if (dp[n1][n2] != -1):
        return dp[n1][n2]
    if (s1[n1 - 1] == s2[n2 - 1]):
        dp[n1][n2] = 1 + lps(s1, s2, n1 - 1, n2 - 1)
        return dp[n1][n2]
    else:
        dp[n1][n2] = max(lps(s1, s2, n1 - 1, n2), lps(s1, s2, n1, n2 - 1))
        return dp[n1][n2]
seq = input()
n = len(seq)
s2 = seq
s2 = s2[::-1]
print(f"The length of the LPS is",lps(s2, seq, n, n)) 
*/
```

## Output:

<img width="1338" height="428" alt="Screenshot 2025-09-07 185849" src="https://github.com/user-attachments/assets/b4a80059-ee54-480e-9c9b-fa0180aa3405" />


## Result:
Thus the program was executed successfully for finding the length of longest palindromic string.

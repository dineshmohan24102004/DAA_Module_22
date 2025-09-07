# EX 4D DYNAMIC PROGRAMMING – 4
## DATE:
## AIM:
To write a Python program that computes the Edit Distance (Levenshtein Distance) between two strings using recursive calls.





## Algorithm
Start the program.

Input two strings str1 and str2.

Define a recursive function LD(s, t) that:

If s is empty, return the length of t (need to insert all characters).

If t is empty, return the length of s (need to delete all characters).

If the last characters of s and t are the same, set cost = 0; otherwise, set cost = 1.

Recursively calculate:

Insertion: LD(s, t[:-1]) + 1

Deletion: LD(s[:-1], t) + 1

Substitution: LD(s[:-1], t[:-1]) + cost

Return the minimum of these three values.

Call the function LD(str1, str2).

Print the Edit Distance.

Stop the program. 

## Program:
```
/*
Program to implement to find the minimum number of operations to convert str1 to str2 using Naive recursive method

.
Developed by: Dinesh M
Register Number: 212222040039
def LD(s, t):
    #########  Add your code here ###########
    if s == "":
        return len(t)
    if t == "":
        return len(s)
    if s[-1] == t[-1]:
        cost = 0
    else:
        cost = 1
    res = min([LD(s[:-1], t)+1, LD(s, t[:-1])+1, LD(s[:-1], t[:-1]) + cost])
    return res
    
str1=input()
str2=input()
print('Edit Distance',LD(str1,str2))


*/
```

## Output:
<img width="1359" height="386" alt="Screenshot 2025-09-07 190048" src="https://github.com/user-attachments/assets/10366618-d613-44e0-8c83-6fb0175ef1d4" />



## Result:
The program was successfully executed.
It calculates and prints the minimum number of operations (insertions, deletions, substitutions) required to transform one string into another.

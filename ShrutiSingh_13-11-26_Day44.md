# POTD Day 44
**Platform:** Codeforces

## PROBLEM 1 – King Moves
**Problem link:** https://codeforces.com/problemset/problem/710/A
**Difficulty:** Beginner

### Problem 
The only king stands on the standard chess board. You are given his position in format "cd", where c is the column from 'a' to 'h' and d is the row from '1' to '8'. Find the number of moves permitted for the king.
#### Input
The only line contains the king's position in the format "cd".
#### Output
Print the only integer x — the number of moves permitted for the king.

### My approach
1. **Define main():** In this function you get input from user and call another function king(user) (user-defined) to solve the problem.
2. **Define king(user):** In this user defined function, we pass the input as the argument in the function, then using if-elif-else statements check for corners boxes, boxes on the sides except the corners and the rest of the boxes, then display accordingly.  
3. **Function call:** main() is invoked.

### Solution
```python
def main() :
    prompt=input().strip()
    king(prompt)

def king(user) :
    if user[0] in 'ha' and user[1] in '18' :
        print(3)

    elif (user[0] in 'ah' and user[1] in '234567' ) or (user[1] in '18' and user[0] in 'bcdefg' ) :
        print(5)

    else :
        print(8)

if __name__=="__main__" :
    main()
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5eebff40-97f5-4e39-9917-a890bd70b034" />





# POTD Day 22
**Platform:** Codeforces

## PROBLEM 1 – Coder
**Problem link:** https://codeforces.com/problemset/problem/384/A
**Difficulty:** Beginner

### Problem 
Lahub invented a new chess piece named Coder. A Coder can move (and attack) one square horizontally or vertically. Lahub wants to know how many Coders can be placed on an n × n chessboard, so that no Coder attacks any other Coder.
#### Input
The first line contains an integer n (1 ≤ n ≤ 1000).
#### Output
- On the first line print an integer, the maximum number of Coders that can be placed on the chessboard.
- On each of the next n lines print n characters, describing the configuration of the Coders. For an empty cell print an '.', and for a Coder print a 'C'.

### My approach
1. **Take Input:** Take integer input from user.
2. **Handle cases:** First check if the number is in required range then check if the number even or odd to display the max. number coders that ca placed and their configuration.
3. **Display the configuration:** Using nested for loops displayed the configuration.

### Solution
```python
user=int(input())
if 1<=user<=1000 :
    if user%2==0 :
        print(user**2//2)
    else:
        print(user**2//2+1)
    flag1=True
    for i in range(user):
        for k in range(user):
            if flag1:
                if k%2==0:
                    print('C',end='')
                else:
                    print('.',end='')
            else :
                if k%2==0:
                    print('.',end='')
                else:
                    print('C',end='')
        print()
        if flag1 :
            flag1=False
        else:
            flag1=True

else :
    print('The number should in range 1<=n<=1000')
    
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ab963c0d-4457-4ed4-8111-fcd63903aae5" />





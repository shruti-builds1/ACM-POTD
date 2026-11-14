# POTD Day 45
**Platform:** Codeforces

## PROBLEM 1 – Anton and Danik
**Problem link:** https://codeforces.com/problemset/problem/734/A
**Difficulty:** Beginner

### Problem 
Anton and Danik played n chess games. Each game had a winner, either Anton ('A') or Danik ('D').
Determine who won more games or if they won equally.
#### Input
- Integer n (1 ≤ n ≤ 100,000).
- String s of length n, containing only 'A' and 'D', representing each game's winner.
#### Output
- "Anton" if Anton won more games.
- "Danik" if Danik won more games.
- "Friendship" if both won equally.

### My approach
1. **Define main():** In this function you get input from user and call another function chess(user2) (user-defined) to solve the problem.
2. **Define chess(user2):** In this user defined function, we pass the input as the argument in the function, then check how many times "A" and "D" occurs using count() and whose occurrence is more or if they occur equally, then display accordingly.  
3. **Function call:** main() is invoked.

### Solution
```python
def main() :
    prompt1=int(input())
    prompt2=input().strip()
    chess(prompt2)

def chess(user2) :
    if user2.count("D")>user2.count("A") :
        print("Danik")

    elif user2.count("D")<user2.count("A") :
        print("Anton")

    else :
        print("Friendship")

if __name__=="__main__" :
    main()
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b0520262-bff4-4802-8b96-59d68f619c5d" />




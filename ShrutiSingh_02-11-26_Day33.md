# POTD Day 33
**Platform:** Codeforces

## PROBLEM 1 – Calculating Function
**Problem link:** https://codeforces.com/problemset/problem/486/A
**Difficulty:** Beginner

### Problem 
For a positive integer n let's define a function f:
f(n) =  - 1 + 2 - 3 + .. + ( - 1)nn
Your task is to calculate f(n) for a given integer n.
#### Input
The single line contains the positive integer n (1 ≤ n ≤ 1015).
#### Output
Print f(n) in a single line.

### My approach
1. **Define main():** In this function you get input from user and call another function calculate(user) (user-defined) to solve the problem.
2. **Define calculate(user):** In this user defined function, we pass the input as the argument in the function, then check if user is even or odd. If it's even display the half of user, otherwise display negative of the sum of the half of user(i.e., calculated using //) and 1.  
3. **Function call:** main() is invoked.

### Solution
```python
def main():
    prompt=int(input())
    calculate(prompt)

def calculate(user):
    if 1<=user<=(10**15) :
        if user%2==0:
            print(user//2)

        else:
            print(-(user//2 + 1))
    else:
        print("The requirement is not fulfilled!")

if __name__=="__main__" :
    main()
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/57b8db9d-68c6-412a-85b2-ed389aa074e7" />





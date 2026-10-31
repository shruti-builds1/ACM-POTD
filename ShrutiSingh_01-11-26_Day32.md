# POTD Day 32
**Platform:** Codeforces

## PROBLEM 1 – Design Tutorial: Learn from Math
**Problem link:** https://codeforces.com/problemset/problem/472/A
**Difficulty:** Beginner

### Problem 
Given an integer n (n ≥ 12), express it as the sum of two composite numbers.
#### Input
A single integer n (12 ≤ n ≤ 10⁶).
#### Output
Print any two composite integers x and y such that x + y = n and 1 < x, y < n.

### My approach
1. **Define main():** In this function you get input from user and call another function math(user) (user-defined) to solve the problem.
2. **Define iscomposite(num):** In this user defined function, we pass an argument we want to check if it is composite or not. Iterate over loop of range(2, num//2+1), then check if num is divisible by any number from the range and return True or False accordingly.
3. **Define math(user):** In this user defined function, we pass the input as the argument in the function, then iterate over a loop of range(4,user+1) then check if the number and difference of the number and user is composite or not by calling the iscomposite(num), then display the numbers.  
4. **Function call:** main() is invoked.

### Solution
```python
def main():
    prompt=int(input())
    math(prompt)

def iscomposite(num):
    flag=True
    for k in range(2,num//2+1):
        if num%k==0 :
            return True
    else:
        return False
        
def math(user) :
    if 12<=user<=(10**6) :
        for j in range(4,user+1):
            if iscomposite(j) and iscomposite(user-j) :
                print(j,user-j,sep=' ')
                break  
    else:
        print("The requirement ia not fulfilled!")

if __name__=="__main__" :
    main()
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/03a255f3-b41d-47cc-9e97-98692c9076b3" />





# POTD Day 36
**Platform:** Codeforces

## PROBLEM 1 – Soldier and Bananas
**Problem link:** https://codeforces.com/problemset/problem/546/A
**Difficulty:** Beginner

### Problem 
A soldier wants to buy w bananas. The i-th banana costs i × k dollars. He has n dollars. Calculate how much money he needs to borrow to buy all the bananas. If he has enough money, output 0.
#### Input
Three integers k, n, and w (1 ≤ k, w ≤ 1000, 0 ≤ n ≤ 10⁹).
#### Output
The minimum amount of money he needs to borrow.

### My approach
1. **Define main():** In this function you get input from user and call another function banana(user) (user-defined) to solve the problem.
2. **Define banana(user):** In this user defined function, we pass the input as the argument in the function, then store the input values in 3 variables p, q, and r. calculate the sum using for loop and store it in variable sum, then check if sum>q and display the money required if it True, otherwise 0.
3. **Function call:** main() is invoked.

### Solution
```python
def main() :
    prompt=input().strip()
    banana(prompt)

def banana(user) :
    p, q, r= user.split()
    sum=0
    for k in range(1, int(r)+1) :
        sum+= int(p)*int(k)

    if sum>int(q) :
        print(sum-int(q))
    else:
        print(0)

if __name__=="__main__" :
    main()
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/76f73bcd-3876-4b24-aec7-f3b985de25bd" />




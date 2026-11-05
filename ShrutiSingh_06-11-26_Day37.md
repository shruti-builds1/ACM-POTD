# POTD Day 37
**Platform:** Codeforces

## PROBLEM 1 – Vasya the Hipster
**Problem link:** https://codeforces.com/problemset/problem/581/A
**Difficulty:** Beginner

### Problem 
Vasya has a red and b blue socks. Each day, he wears a new pair and discards it.
He must first wear different-colored socks (red on the left, blue on the right), then wear same-colored socks until he runs out of socks or cannot form a pair.
Find the maximum number of days he can wear different-colored socks and the number of additional days he can wear same-colored socks.
#### Input
Two integers a and b (1 ≤ a, b ≤ 100).
#### Output
Two space-separated integers: the number of days with different-colored socks and the number of days with same-colored socks.

### My approach
1. **Define main():** In this function you get input from user and call another function hipster(user) (user-defined) to solve the problem.
2. **Define hipster(user):** In this user defined function, we pass the input as the argument in the function, then store the input values in variables in p and q, then check which number is smaller and display the smaller number with the number of days with same-colored socks(i.e., abs(int(p)-int(q))//2).
3. **Function call:** main() is invoked.

### Solution
```python
def main():
    prompt=input().strip()
    hipster(prompt)

def hipster(user):
    p, q=user.split()
    # print(p, q)
    if int(p)>int(q):
        print(q, abs(int(p)-int(q))//2)
    else:
        print(p, abs(int(p)-int(q))//2)
        
if __name__=="__main__" :
    main()
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/10f5ea4a-f65e-41ae-9a25-22d81f3319a8" />





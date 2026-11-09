# POTD Day 40
**Platform:** Codeforces

## PROBLEM 1 – Johny Likes Numbers
**Problem link:** https://codeforces.com/problemset/problem/678/A
**Difficulty:** Beginner

### Problem 
Johny likes numbers n and k very much. Now Johny wants to find the smallest integer x greater than n, so it is divisible by the number k.
#### Input
The only line contains two integers n and k (1 ≤ n, k ≤ 109).
#### Output
Print the smallest integer x > n, so it is divisible by the number k.

### My approach
1. **Define main():** In this function you get input from user and call another function numbers(user) (user-defined) to solve the problem.
2. **Define numbers(user):** In this user defined function, we pass the input as the argument in the function, then store n and k i  variables p and q respectively. Now, check if p is divisible by q, if True display the next multiple of q, otherwise check if p>q, if True display q*(p//q+1) else q.  
3. **Function call:** main() is invoked.

### Solution
```python
def main():
    prompt=input().strip()
    numbers(prompt)

def numbers(user) :
    p, q=user.split()
    if int(p)%int(q)==0 :
        print(int(p)+int(q))

    else:
        if int(p)>int(q):
            print(int(q)*(int(p)//int(q)+1))
        else:
            print(int(q))

if __name__=="__main__" :
    main()
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/66e3d772-2d8f-4360-8905-c150ed069b80" />




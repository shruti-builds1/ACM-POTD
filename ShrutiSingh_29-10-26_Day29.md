# POTD Day 29
**Platform:** Codeforces

## PROBLEM 1 – Little Pony and Crystal Mine
**Problem link:** https://codeforces.com/problemset/problem/454/A
**Difficulty:** Beginner

### Problem 
Twilight Sparkle found a crystal in the Crystal Mine. A crystal of odd size \(n>1\) is an \(n \times n\) matrix containing a diamond.
Given an odd integer \(n\), print the crystal using D for diamond cells and * for all other cells.
#### Input
An odd integer n (3 <= n <= 101).
#### Output
Print the crystal of size n.

### My approach
1. **Define main():** In this function you get input from user and call another function crystal(user) (user-defined) to solve the problem.
2. **Define crystal(user):** In this user defined function, we pass the input as the argument in the function, then using for loop we display the pattern.  
3. **Function call:** main() is invoked.

### Solution
```python
def main():
    prompt=int(input())
    crystal(prompt)

def crystal(user):
    if 3<=user<=101 and user%2!=0 :
        dcell=1
        for i in range(user):
            if dcell<=user :
                num1=(user-dcell)//2
                print('*'*num1 + 'D'*dcell + '*'*num1)
                dcell+=2

            else:
                break

        # print(dcell)
        dcell-=4
        for j in range(user):
            if dcell>0 :
                num2=(user-dcell)//2
                print('*'*num2+ 'D'*dcell+ '*'*num2)
                dcell-=2

            else:
                break
            
    else:
        print(' the number should be in range 3 ≤ n ≤ 101; n is odd')


if __name__=="__main__":
    main()
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/59c56c1d-7011-4aaf-ac2d-1072b187489a" />




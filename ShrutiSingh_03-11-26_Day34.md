# POTD Day 34
**Platform:** Codeforces

## PROBLEM 1 – Vanya and Cubes
**Problem link:** https://codeforces.com/problemset/problem/492/A
**Difficulty:** Beginner

### Problem 
Vanya has n cubes and wants to build a pyramid where the i-th level contains (1+2+...+i) cubes.
Determine the maximum height of the pyramid he can build.
#### Input
A single integer n (1 ≤ n ≤ 10⁴), the number of available cubes.
#### Output
Print the maximum possible height of the pyramid.

### My approach
1. **Define main():** In this function you get input from user and call another function cube(user) (user-defined) to solve the problem.
2. **Define cube(user):** In this user defined function, we pass the input as the argument in the function, then initially create a list L to store the no. of cubes in 1 line and set a variable sum=1, then iterate over a while loop till the user>=sum. Inside the while loop append the sum in L and subtract sum from user and increase the sum by the len(L) + 1. Display len(L).  
3. **Function call:** main() is invoked.

### Solution
```python
def main():
    prompt=int(input())
    cube(prompt)

def cube(user):
    if 1<=user<=(10**4) :
        L=[]
        sum=1
        while sum<=user :
            L.append([sum])
            user-=sum
            # prev_sum=sum
            sum+=len(L)+1

        print(len(L))    

    else:
        print("The requirement is not fulfilled!")

if __name__=="__main__" :
    main()
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c5f754e5-ac4d-43f1-9756-cf281f19388a" />




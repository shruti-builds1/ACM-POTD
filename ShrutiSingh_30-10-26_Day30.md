# POTD Day 30
**Platform:** Codeforces

## PROBLEM 1 – George and Accommodation
**Problem link:** https://codeforces.com/problemset/problem/467/A
**Difficulty:** Beginner

### Problem 
George and Alex want to share a dorm room. Given n rooms, each with p_i current occupants and capacity q_i, count the rooms with at least 2 vacant places.
#### Input
An integer n, followed by n lines containing p_i and q_i.
#### Output
The number of rooms that can accommodate both George and Alex.

### My approach
1. **Define main():** In this function you get input from user and call another function dorm(user) (user-defined) to solve the problem.
2. **Define dorm(user):** In this user defined function, we pass the input as the argument in the function, then create a list in wchich we store the lines as list(nested list) containing integers, then iterate over this list and check if the difference of q_i and p
_i is greater than or equal to 2, then display the count.  
3. **Function call:** main() is invoked.

### Solution
```python
def main():
    prompt=int(input())
    dorm(prompt)

def dorm(user):
    if 1<=user<=100 :
        L=[]
        for k in range(user):
            p, q=input().strip().split(' ')
            flag=True
            if 0<=int(p)<=100 and 0<=int(q)<=100:
                L.append([int(p),int(q)])
                continue
            else:
                flag=False
                print("The number of people living and room's capacity should be in range 0 ≤ p, q ≤ 100.")
                break

        if flag:
            count=0
            for k in L:
                if (k[1]-k[0])>=2 :
                    count+=1

            print(count)
            
    else:
        print('The number of rooms should be in range 1 ≤ n ≤ 100.')

if __name__=='__main__':
    main()
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/522f037e-ab29-4d3e-9519-7631255964db" />




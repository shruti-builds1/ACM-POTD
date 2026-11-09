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

## PROBLEM 2 – Array
**Problem link:** https://codeforces.com/problemset/problem/300/A
**Difficulty:** Intermediate

### Problem 
Given an array of n distinct integers, divide its elements into three non-empty sets such that:
1. The product of elements in the first set is negative.
2. The product of elements in the second set is positive.
3. The product of elements in the third set is zero.
4. Every element belongs to exactly one set.
#### Input
- First line: Integer n (3 ≤ n ≤ 100).
- Second line: n distinct integers a₁, a₂, ..., aₙ (|aᵢ| ≤ 10³).
A solution is guaranteed to exist.
#### Output
Print three lines, each containing the size of a set followed by its elements, in the order specified above. Any valid division is accepted.

### My approach
1. **Define main():** In this function you get input from user and call another function array(user2) (user-defined) to solve the problem.
2. **Define array(user2):** In this user defined function, we pass the input as the argument in the function, then store the integers in a list L. Create a list L1 with 3 lists inside it, then iterate over L and check for <0, >0 and ==0 and append in L1[0], L1[1], and L1[2] respectively. Now, check if product of elements of L1[0] is >0 ,if True remove a element from L1[0] and append it to L[2]. Check if L[1] is empty, if True remove 2 elements from L[0] and append it to L[1]. Now, display the length and elements of the lists in L1 on separate lines.  
3. **Function call:** main() is invoked.

### Solution
```python
from math import prod
def main() :
    prompt1=int(input())
    prompt2=input().strip()
    array(prompt2)

def array(user2) :
    L=user2.split()
    L1=[[],[],[]]
    # p1=1; p2=1; p3=1
    for k in L :
        if int(k)<0 :
            L1[0].append(int(k))
        elif int(k)>0:
            L1[1].append(int(k))
        else:
            L1[2].append(int(k))

    if prod(L1[0])>0 :
        l=L1[0].pop()
        L1[2].append(l)

    if len(L1[1])==0 :
        for l in range(2):
            L1[1].append(L1[0].pop())
            
    for j in L1 :
        print(len(j),end=" ")
        for i in j :
            print(i,end=" ")
        print()

if __name__=="__main__" :
    main()     
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/930f4a7f-2dd5-4ac7-ad6a-dc189f18c644" />



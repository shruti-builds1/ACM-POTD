# POTD Day 25
**Platform:** Codeforces

## PROBLEM 1 – Pasha and Hamsters
**Problem link:** https://codeforces.com/contest/421/problem/A
**Difficulty:** Beginner

### Problem 
Pasha has n apples and two hamsters, Arthur and Alexander, each liking specific apples. Distribute all apples so that each hamster receives only apples it likes. An apple liked by both can be given to either hamster. The input guarantees a valid distribution exists.
#### Input
- First line: integers n, a, b — total apples, apples Arthur likes, and apples Alexander likes.
- Second line: a distinct integers representing Arthur’s preferred apples.
- Third line: b distinct integers representing Alexander’s preferred apples.
Apples are numbered from 1 to n.
#### Output
Print a string of n characters: 1 if the apple goes to Arthur, or 2 if it goes to Alexander. Any valid distribution is accepted.

### My approach
1. **Take Input:** Take 3 string inputs from user and use split() to make lists from the strings.
2. **Handle cases:** First check if all the 3 inputs are in required range, then make a dictionary to store which apples has to be given to alexander(assuming that the all the apples selected by arthur are given to it, but it is not neccessary that the apples selected by alexander are given to it.), then using for loops to assign the apples and store the values(either 1 or 2) in a list. 
3. **Display:** Display the elements of list.

### Solution
```python
user=input().strip().split(' ')
arth=input().strip().split(' ')
alex=input().strip().split(' ')
if 1<=int(user[0])<=100 and 1<=int(user[1])<=int(user[0]) and 1<=int(user[2])<=int(user[0]) :
    # apples=0
    D={"Alexander":[]}
    for k in alex:
        if k not in arth:
            D["Alexander"].append(int(k))

    # for i in arth:
    #     D['Arthur'].append(int(i))

    # print(D)

    L=[]
    # L=D['Arthur'].copy()
    if len(arth)>0:
        for j in range(len(arth)):
            L.append(1)

    if len(D['Alexander'])>0:
        for k in D["Alexander"]:
            L.insert(k-1,2)

    for i in L:
        print(i,end=' ')

    print()

else:
    print('the numbers should be in required range')
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/bd2e1b3b-0979-4e92-9d0f-587ea9fbf700" />

## PROBLEM 2 – Candy Bags
**Problem link:** https://codeforces.com/problemset/problem/334/A
**Difficulty:** Intermediate

### Problem 
Gerald has an even number n of younger brothers and n^2 candy bags containing 1,2,...,n^2 candies, one bag per number. Distribute exactly n bags to each brother so that every brother receives the same total number of candies.
#### Input
A single even integer n (2<=n<=100).
#### Output
Print n lines, each containing n distinct integers from 1 to n^2, representing the bags given to each brother. Every integer must appear exactly once, and all brothers must receive the same total number of candies.

### My approach
1. **Take Input:** Take integer input from the user.
2. **Handle cases:** First check if the input fulfills the requirement, then create a dictionary to store the bags that is to be given t the brothers. Moving forward, using for loops to assign the bags.
3. **Display:** Display the elements of values(i.e., a list) of dictionary.

### Solution
```python
user=int(input())
if 2<=user<=100 and user%2==0 :
    D={}
    for k in range(1,user+1):
        D.update({str(k):[]})

    # print(D)

    L=[]
    for i in range(1, user**2+1):
        L.append(i)

    for j,v in D.items():
        for k in range(user//2):
            candy1=L.pop(0)
            v.append(candy1)

        for j in range(user//2):
            candy2=L.pop(-1)
            v.append(candy2)

    for l,m in D.items():
        for i in m:
            print(i,end=' ')
        print()
        

else:
    print('The input should be even and in required range(2 ≤ n ≤ 100)')
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4c9c4257-4d4a-4e11-a54f-c694a1fc0865" />




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

## PROBLEM 2 – Choosing Symbol Pairs
**Problem link:** https://codeforces.com/problemset/problem/50/B
**Difficulty:** Advanced

### Problem 
Given a string S of length N, count the number of ordered pairs (i, j) such that:
1. 1<= i,j <=N
2. S[i] = S[j]
#### Input
A non-empty string S containing lowercase Latin letters and digits, with length at most (10^5).
#### Output
Print the total number of valid ordered pairs. Pairs (i, j) and (j, i) are considered different.

### My approach
1. **Define main():** In this function you get input from user and call another function symbol(user) (user-defined) to solve the problem.
2. **Define symbol(user):** In this user defined function, we pass the input as the argument in the function, then define variables "pairs" to store the number of pairs, "l" to store the length of user, and "flag" to store a boolean value True. Now, iterate over a range(l) then check no. of user[0] in user using count() and store it in a variable "num", then replace all the user[0] using replace() and store the new string in "user" itself, then add "num" in "pairs" and check if "pairs" is equal to l, no. of iteration is only 1, and len(user)==0. If this if condition is True, display pairs**2 (this means that all the characters are same in string.), flag==False  and break. Otherwise continue with loop and display "pairs", if flag==True in the end.
3. **Function call:** main() is invoked.

### Solution
```python
def main():
    prompt=input().strip()
    symbol(prompt)

def symbol(user) :
    pairs=0
    l=len(user)
    flag=True
    for k in range(l):
        # for i in user :
        #     if k==i:
        if len(user)>0 :
            num=user.count(user[0])
            user=user.replace(user[0],"")
            # print(user)
            pairs+=num**2
            # print(num, pairs)
            if pairs==l and k==0 and len(user)==0 :
                print(pairs**2)
                flag=False
                break

    if flag:
        print(pairs)

if __name__=="__main__" :
    main()
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6384bd34-e9fb-4317-8861-13e1761bf482" />





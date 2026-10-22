# POTD Day 22
**Platform:** Codeforces

## PROBLEM 1 – Coder
**Problem link:** https://codeforces.com/problemset/problem/384/A
**Difficulty:** Beginner

### Problem 
Lahub invented a new chess piece named Coder. A Coder can move (and attack) one square horizontally or vertically. Lahub wants to know how many Coders can be placed on an n × n chessboard, so that no Coder attacks any other Coder.
#### Input
The first line contains an integer n (1 ≤ n ≤ 1000).
#### Output
- On the first line print an integer, the maximum number of Coders that can be placed on the chessboard.
- On each of the next n lines print n characters, describing the configuration of the Coders. For an empty cell print an '.', and for a Coder print a 'C'.

### My approach
1. **Take Input:** Take integer input from user.
2. **Handle cases:** First check if the number is in required range then check if the number even or odd to display the max. number coders that ca placed and their configuration.
3. **Display the configuration:** Using nested for loops displayed the configuration.

### Solution
```python
user=int(input())
if 1<=user<=1000 :
    if user%2==0 :
        print(user**2//2)
    else:
        print(user**2//2+1)
    flag1=True
    for i in range(user):
        for k in range(user):
            if flag1:
                if k%2==0:
                    print('C',end='')
                else:
                    print('.',end='')
            else :
                if k%2==0:
                    print('.',end='')
                else:
                    print('C',end='')
        print()
        if flag1 :
            flag1=False
        else:
            flag1=True

else :
    print('The number should in range 1<=n<=1000')
    
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ab963c0d-4457-4ed4-8111-fcd63903aae5" />

## PROBLEM 2 – cAPS lOCK
**Problem link:** https://codeforces.com/problemset/problem/131/A
**Difficulty:** Intermediate

### Problem 
Let's consider that a word has been typed with the Caps lock key accidentally switched on, if:
- either it only contains uppercase letters;
- or all letters except for the first one are uppercase.
In this case we should automatically change the case of all letters. Write a program that applies the rule mentioned above. If the rule cannot be applied, the program should leave the word unchanged.
#### Input
The first line of the input data contains a word consisting of uppercase and lowercase Latin letters. The word's length is from 1 to 100 characters, inclusive.
#### Output
Print the result of the given word's processing.

### My approach
1. **Take Input:** Take string input from user.
2. **Handle cases:** First check the length of input, then display the output accordingly using isupper(), .islower(), .lower(), and .upper() .
   
### Solution
```python
user=input().strip()
if len(user)==1 :
    if user.islower():
        print(user.upper())
    else:
        print(user.lower())
elif 1<len(user)<=100 :
    if user.isupper() :
        print(user.lower())
    elif user[0].islower() and user[1:len(user)].isupper() :
        print(user[0].upper()+user[1:len(user)].lower())
    else :
        print(user)

else:
    print('The input should be 1 to 100 characters long!')    
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5d9e3117-8fe6-4277-9f62-bc7289ddb53b" />






# POTD Day 24
**Platform:** Codeforces

## PROBLEM 1 – Password Check
**Problem link:** https://codeforces.com/problemset/problem/411/A
**Difficulty:** Beginner

### Problem 
Today your task is to implement an automatic password check. Web-developers of the company Q assume that a password is complex enough, if it meets all of the following conditions:
- the password length is at least 5 characters;
- the password contains at least one large English letter;
- the password contains at least one small English letter;
- the password contains at least one digit.
You are given a password. Please implement the automatic check of its complexity for company Q.
#### Input
The first line contains a non-empty sequence of characters (at most 100 characters). Each character is either a large English letter, or a small English letter, or a digit, or one of characters: "!", "?", ".", ",", "_".
#### Output
If the password is complex enough, print message "Correct" (without the quotes), otherwise print message "Too weak" (without the quotes).

### My approach
1. **Take Input:** Take password from the user.
2. **Handle cases:** First check if the length of password is in required range, then check for atleast 1 small letter, 1 large letter, 1 digit and one of the characters: "!", "?", ".", ",", "_"(if special characters are present) using .isupper(), islower(), isdigit(), and .islanum(). 
3. **Display ** Print "Correct" and "Too weak" according to the requirement .

### Solution
```python
user=input().strip()
if len(user)<5 :
    print('Too weak')
elif 5<=len(user)<=100 :
    flag1=False
    flag2=False
    flag3=False
    flag4=False
    for k in user:
        if k.isupper():
            flag1=True

        if k.islower():
            flag2=True

        if k.isdigit():
            flag3=True

        if k in '!?.,_':
            flag4=True

    if flag1 and flag2 and flag3 :
        if not user.isalnum() and flag4 :
            print('Correct')

        elif user.isalnum() :
            print('Correct')

        else:
            print('Too weak')
    else:
        print('Too weak')


else:
    print('the length of password should be in range 5<=n<=100')
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c28e670b-c50c-4ed9-8424-0f693280a7db" />


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
3. **Display:** Print "Correct" and "Too weak" according to the requirement .

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

## PROBLEM 2 – Ciel and Dancing
**Problem link:** https://codeforces.com/problemset/problem/322/A
**Difficulty:** Intermediate

### Problem 
Fox Ciel and her friends are in a dancing room. There are n boys and m girls here, and they never danced before. There will be some songs, during each song, there must be exactly one boy and one girl are dancing. Besides, there is a special rule:
- either the boy in the dancing pair must dance for the first time (so, he didn't dance with anyone before);
- or the girl in the dancing pair must dance for the first time.
Help Fox Ciel to make a schedule that they can dance as many songs as possible.
#### Input
The first line contains two integers n and m (1 ≤ n, m ≤ 100) — the number of boys and girls in the dancing room.
#### Output
In the first line print k — the number of songs during which they can dance. Then in the following k lines, print the indexes of boys and girls dancing during songs chronologically. You can assume that the boys are indexed from 1 to n, and the girls are indexed from 1 to m.

### My approach
1. **Take Input:** Get the number of boys and girls in the room.
2. **Handle cases:** First check if the number of boys and girls are in required range, then make a dictionary to know the status of all dancers (i.e, if they are dancing for first time or not), then handling cases according to number of boys and girls. 
3. **Display:** Display the number of possible ways and all the ways.

### Solution
```python
user=input().strip().split(' ')
dancers=[]
for k in user:
    dancers.append(int(k))

if 1<=dancers[0]<=100 and 1<=dancers[1]<=100 :
    D={'boys':{} , 'girls':{}}
    # L=[]
    # for k in dancers:
    #     if k>1:
    #         for i in range(k) :
    #             L.append(1)
    for j in range(1,dancers[0]+1) :
        D['boys'].update({str(j): False})

    for l in range(1,dancers[1]+1) :
        D['girls'].update({str(l): False})

    # print(D)
    L=[]
    if dancers[0]>dancers[1] or dancers[0]==dancers[1] :
        for k in range(1,dancers[0]+1):
             for i in range(1,dancers[1]+1):
                 if not D['boys'][str(k)] or not D['girls'][str(i)] :
                    s=str(k)+' '+str(i)
                    L.append(s)
                    if D['boys'][str(k)]== False:
                        D['boys'][str(k)]=True

                    if D['girls'][str(i)]== False :
                        D['girls'][str(i)]=True

    elif dancers[0]<dancers[1]  :
        for k in range(1,dancers[1]+1):
             for i in range(1,dancers[0]+1):
                 if not D['boys'][str(i)] or not D['girls'][str(k)] :
                    s=str(i)+' '+str(k)
                    L.append(s)
                    if D['boys'][str(i)]== False:
                        D['boys'][str(i)]=True

                    if D['girls'][str(k)]== False :
                        D['girls'][str(k)]=True

    print(len(L))
    for k in L:
        print(k)

else:
    print('The number of boys and girls should be in range 1 ≤ n, m ≤ 100')
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/aadd1dad-818e-4d60-9e93-fc498f71b254" />




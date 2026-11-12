# POTD Day 43
**Platform:** Codeforces

## PROBLEM 1 – Hulk
**Problem link:** https://codeforces.com/problemset/problem/705/A
**Difficulty:** Beginner

### Problem 
Dr. Bruce Banner's feelings have n alternating layers of hate and love, starting with hate.
For example:
- n = 1: "I hate it"
- n = 2: "I hate that I love it"
- n = 3: "I hate that I love that I hate it"
#### Input
A single integer n (1 ≤ n ≤ 100), representing the number of layers.
#### Output
Print his complete feeling in one line.

### My approach
1. **Define main():** In this function you get input from user and call another function hulk(user) (user-defined) to solve the problem.
2. **Define hulk(user):** In this user defined function, we pass the input as the argument in the function, then create a list L to store the sentence and iterate over a range(user) and check k%2==0, if True append 'I hate that' in L, otherwise 'I love that' . then update the last element of L by removing the word ' that' from it. Now, iterate over L and display the elements on 1 line ending with 'it'.  
3. **Function call:** main() is invoked.

### Solution
```python
def main() :
    prompt=int(input())
    hulk(prompt)

def hulk(user) :
    L=[]
    for k in range(user) :
        if k%2==0 :
            L.append('I hate that')
        else:
            L.append('I love that')

    L[-1]=L[-1].strip(' that')
    for j in L :
        print(j,end=' ')

    print('it')

if __name__=='__main__' :
    main()
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/82d56be4-ec86-45b6-bbed-508d4e2de966" />

## PROBLEM 2 – Hexadecimal's Numbers
**Problem link:** https://codeforces.com/problemset/problem/9/C
**Difficulty:** Intermediate

### Problem 
Megabyte loaded n distinct natural numbers (1 to n) into Hexadecimal's memory. However, Hexadecimal only understands binary-formatted numbers, so only numbers containing digits 0 and 1 exclusively were stored successfully.
Find how many numbers were stored.
#### Input
A single integer n (1 ≤ n ≤ 10⁹).
#### Output
The count of successfully stored numbers.

### My approach
1. **Define main():** In this function you get input from user and call another function virus(user) (user-defined) to solve the problem.
2. **Pattern:** We notice that from 1 to 10 we have 2 values only. Also 1*2**1 + 0*2**0 equals 2 (atarting from right, multiply the digits with 2**n; n=0,1,2,...). but, when we enter a number which contains another digit other than 0 and 1, then we look for number less than that no. and if the number is greater than 1*(length of entered number), it is observed that the lowest will always be 1*(length of entered number), otherwise we replace the digits starting from the index where the first digit comes out to be not 0 and 1. 
3. **Define virus(user):** In this user defined function, we pass the input as the argument in the function, then create a set my_set storing '0' and '1'. convert the user to set and then check if user is not subset of my_set and int(user)>'1'*len(user), then for user is not subset of my_set and int(user)<'1'*len(user), user is updated as required. Now calculate the sum and display it.
4. **Function call:** main() is invoked.

### Solution
```python
def main() :
    prompt=input().strip()
    virus(prompt)

def virus(user) :
    my_set={'0', '1'}
    if  not set(user).issubset(my_set) and int(user)>int('1'*len(user)) :
        user='1'*len(user)
    elif not set(user).issubset(my_set) and int(user)<int('1'*len(user)) :
        for j in user:
            if j not in my_set :
                i=user.index(j)
                break
        s=user[i:len(user)+1:1]
        user=user.replace(s,'1'*len(s))
        
    sum=0
    pow=0
    for k in user[::-1] :
        sum+=int(k)*2**pow
        pow+=1

    print(sum)
    
if __name__=="__main__" :
     main()
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/154e6580-40bc-42a3-b403-2a94531050cb" />




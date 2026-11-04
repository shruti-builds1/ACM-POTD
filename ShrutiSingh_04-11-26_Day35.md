# POTD Day 35
**Platform:** Codeforces

## PROBLEM 1 – Pangram
**Problem link:** https://codeforces.com/problemset/problem/520/A
**Difficulty:** Beginner

### Problem 
A string is a pangram if it contains every letter of the English alphabet (A–Z) at least once, regardless of case.
Given a string of uppercase and lowercase Latin letters, check whether it is a pangram.
#### Input
- First line: An integer n (1 ≤ n ≤ 100), the string length.
- Second line: A string of n uppercase and lowercase Latin letters.
#### Output
Print YES if the string is a pangram; otherwise, print NO.

### My approach
1. **Define main():** In this function you get input from user and call another function pangram(user) (user-defined) to solve the problem.
2. **Define pangram(user):** In this user defined function, we pass the input as the argument in the function, then prompt the user for string input and create a variable user_set to store the set(set()) of the input string in lowercase, then import string and use ascii_lowercase method of string to access all the alphabets in lowercase and convert it into a set which is stored in a variable flag. Now, user subset method on  flag to check if all the 26 letters are present atleast once in user_set. if it is True, display YES otherwise NO.
3. **Function call:** main() is invoked.

### Solution
```python
import string

def main() :
    prompt=int(input())
    pangram(prompt)

def pangram(user) :
    if 1<=user<=100 :
        prompt2=input().strip()
        user_set=set(prompt2.lower())
        flag=set(string.ascii_lowercase).issubset(user_set)

        if flag:
            print("YES")
        else:
            print("NO")

    else:
        print("The requirement is not fulfilled!")

if __name__=="__main__" :
    main()
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c8daa1e6-7eb5-404f-a879-fb5874f92dfa" />




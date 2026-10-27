# POTD Day 28
**Platform:** Codeforces

## PROBLEM 1 – Anton and Letters
**Problem link:** https://codeforces.com/problemset/problem/443/A
**Difficulty:** Beginner

### Problem 
Anton is given a set of lowercase English letters written in curly braces and separated by commas. Some letters may be repeated. Count the number of distinct letters in the set.
#### Input
A line containing the set of letters (length ≤ 1000).
#### Output
A single integer representing the number of distinct letters.

### My approach
1. **Define main():** In this function you get input from user and call another function distinct(user1) (user-defined) to solve the problem.
2. **Define distinct(user1):** In this user defined function, we pass the input as the argument in the function, then using lstrip(), rstrip(), and split() we remove '{', '}', and ','. Moreover, empty list was created to append the distinct letters using for loop, then print the length of the list.  
3. **Function call:** main() is invoked.

### Solution
```python
def main():
    prompt=input()
    distinct(prompt)

def distinct(user1):
    user=user1.lstrip('{').rstrip('}')
    if 0<len(user)<=1000:
        L=[]
        for  k in user.split(','):
            if k.strip() in L:
                continue
            else:
                L.append(k.strip())
        # print(L)
        print(len(L))

    elif len(user)==0 :
        print(0)

    else:
        print('The length of line should not exceed 1000.')


if __name__=='__main__' :
    main()
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c2f60f48-f2fb-41a0-a7d5-5b36a7e33d80" />






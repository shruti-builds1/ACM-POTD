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





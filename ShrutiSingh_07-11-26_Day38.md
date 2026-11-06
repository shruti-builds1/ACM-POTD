# POTD Day 38
**Platform:** Codeforces

## PROBLEM 1 – Bulbs
**Problem link:** https://codeforces.com/problemset/problem/615/A
**Difficulty:** Beginner

### Problem 
Vasya has m initially switched-off bulbs and n buttons, each connected to a specific set of bulbs. Pressing a button turns on all its connected bulbs without affecting those already on. Determine whether all m bulbs can be turned on.
#### Input
- First line: integers n and m (1 ≤ n, m ≤ 100).
- Next n lines: each contains xi, the number of bulbs connected to the i-th button, followed by their bulb numbers yij (1 ≤ yij ≤ m).
#### Output
Print "YES" if all bulbs can be turned on; otherwise, print "NO".

### My approach
1. **Define main():** In this function you get input from user and call another function bulb(user) (user-defined) to solve the problem.
2. **Define bulb(user):** In this user defined function, we pass the input as the argument in the function, then store the no. of buttons and no. of bulbs in p and q respectively. Iterate over a range(int(p)) and prompt the user p times and store the input in a list L. using dictionary comprehension, make a dictionary D with bulb numbers as the keys and boolean value as their values(to find out which bulb number glows.). Now, iterate over the list L, then over the elements of L and fulfill the requirements. Iterate over the values of D and check if any value is False, then display "NO" and break; otherwise, "YES" after checking all the values.
3. **Function call:** main() is invoked.

### Solution
```python
def main() :
    prompt=input().strip()
    bulb(prompt)

def bulb(user) :
    p, q=user.split()
    L=[]
    for k in range(int(p)) :
        num=input().strip()
        L.append(num)

    # L1=[j for j in range(1,int(q)+1)]
    D={j: False for j in range(1,int(q)+1)}
    for i in L :
        for l in i.split()[1:len(i.split())] :
            if D[int(l)]==False:
                D[int(l)]=True

    for v in D.values():
        if v==False:
            print("NO")
            break
    else:
        print("YES")

if __name__=="__main__" :
    main()
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/500d90cc-2a14-48bd-94af-541cc7b152e4" />





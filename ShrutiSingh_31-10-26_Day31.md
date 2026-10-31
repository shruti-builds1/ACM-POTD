# POTD Day 31
**Platform:** Codeforces

## PROBLEM 1 – I Wanna Be the Guy
**Problem link:** https://codeforces.com/problemset/problem/469/A
**Difficulty:** Beginner

### Problem 
Little X and Little Y want to complete a game with n levels. X can pass p levels, while Y can pass q levels. Given the levels each can pass, determine whether they can collectively complete all n levels.
#### Input
-First line: Integer n (1 ≤ n ≤ 100).
- Second line: Integer p, followed by p distinct level indices X can pass.
- Third line: Integer q, followed by q distinct level indices Y can pass.
#### Output
Print "I become the guy." if they can pass all levels together; otherwise, print "Oh, my keyboard!".

### My approach
1. **Define main():** In this function you get input from user and call another function guy(user1) (user-defined) to solve the problem.
2. **Define guy(user1):** In this user defined function, we pass the input as the argument in the function, then prompt for 2 inputs after checking the requirement and after requirements are fulfilled, iterate over a range(1, user1+1) and check if the level is present in the other 2 prompts, then display the result.  
3. **Function call:** main() is invoked.

### Solution
```python
def main():
    prompt1=int(input())
    guy(prompt1)

def guy(user1):
    if 1<=user1<=100 :
        prompt2=input().strip().split()
        prompt3=input().strip().split()
        flag1=True
        for k in prompt2[1::] :
            if not 1<=int(k)<=user1 :
                flag1=False
                break
        flag2=True
        for i in prompt3[1::] :
            if not 1<=int(i)<=user1 :
                flag2=False
                break        

        if flag1 and flag2 and 0<=int(prompt2[0])<=user1 and 0<=int(prompt3[0])<=user1 :
            flag3=True
            for j in range(1, user1+1):
                if str(j) in prompt2[1::] or str(j) in prompt3[1::] :
                    continue
                else:
                    flag3=False
                    break

            if flag3:
                print("I become the guy.")
            else:
                print("Oh, my keyboard!")

        else:
            print("The requirements are not fulfilled!")

    else:
        print("The requirement is not fulfilled!")
        
if __name__=="__main__" :
    main()
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/fc057bcd-29c6-416b-9641-cd7f7d88f757" />

## PROBLEM 2 –  Autocomplete
**Problem link:** https://codeforces.com/problemset/problem/53/A
**Difficulty:** Intermediate

### Problem 
Vasya is developing an autocomplete feature for the browser 'BERowser'. Given a typed prefix s and n previously visited web addresses, find the lexicographically smallest address that starts with s. If no address matches, print s.
#### Input
A string s, an integer n (1–100), followed by n visited addresses (lowercase letters, length 1–100).
#### Output
The lexicographically smallest matching address, or s if no match exists.

### My approach
1. **Define main():** In this function you get 2 inputs from user and call another function autocomplete(user1, user2) (user-defined) to solve the problem.
2. **Define autocomplete(user1, user2):** In this user defined function, we pass the 2 inputs as the arguments in the function, then prompt the user user2 times for the last visited pages and store them in a list adds, then iterate over it store the texts beginning with user1 in another list L, then if len(L)> 0 display the result otherwise user1 .
3. **Call main():** main() is invoked.
   
### Solution
```python
def main():
    prompt1=input().strip()
    prompt2=int(input())
    autocomplete(prompt1, prompt2)

def autocomplete(user1, user2):
    if 1<=user2<=100 :
        adds=[]
        flag1=True
        for k in range(user2):
            prompt3=input().strip()
            if 1<=len(prompt3)<=100 and prompt3.islower():
                adds.append(prompt3)
            else:
                flag1=False
                print("The requirements are not fulfilled!")
                break

        if flag1:
            L=[]
            # flag2=True
            for j in adds:
                if j.startswith(user1) :
                    L.append(j)
            # else:
            #     flag2=False

            # print(flag2)
            if len(L)>0:
                print((sorted(L))[0])
            else:
                print(user1)       
    else:
        print("The requirement is not fulfilled!")

if __name__=="__main__":
    main()
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a3562d0c-81fe-43d7-9239-48df83baa6c6" />



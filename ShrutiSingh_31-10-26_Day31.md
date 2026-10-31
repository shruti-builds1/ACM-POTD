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




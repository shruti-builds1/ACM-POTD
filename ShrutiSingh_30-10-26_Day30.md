# POTD Day 30
**Platform:** Codeforces

## PROBLEM 1 – George and Accommodation
**Problem link:** https://codeforces.com/problemset/problem/467/A
**Difficulty:** Beginner

### Problem 
George and Alex want to share a dorm room. Given n rooms, each with p_i current occupants and capacity q_i, count the rooms with at least 2 vacant places.
#### Input
An integer n, followed by n lines containing p_i and q_i.
#### Output
The number of rooms that can accommodate both George and Alex.

### My approach
1. **Define main():** In this function you get input from user and call another function dorm(user) (user-defined) to solve the problem.
2. **Define dorm(user):** In this user defined function, we pass the input as the argument in the function, then create a list in wchich we store the lines as list(nested list) containing integers, then iterate over this list and check if the difference of q_i and p
_i is greater than or equal to 2, then display the count.  
3. **Function call:** main() is invoked.

### Solution
```python
def main():
    prompt=int(input())
    dorm(prompt)

def dorm(user):
    if 1<=user<=100 :
        L=[]
        for k in range(user):
            p, q=input().strip().split(' ')
            flag=True
            if 0<=int(p)<=100 and 0<=int(q)<=100:
                L.append([int(p),int(q)])
                continue
            else:
                flag=False
                print("The number of people living and room's capacity should be in range 0 ≤ p, q ≤ 100.")
                break

        if flag:
            count=0
            for k in L:
                if (k[1]-k[0])>=2 :
                    count+=1

            print(count)
            
    else:
        print('The number of rooms should be in range 1 ≤ n ≤ 100.')

if __name__=='__main__':
    main()
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/522f037e-ab29-4d3e-9519-7631255964db" />

## PROBLEM 2 – Letter
**Problem link:** https://codeforces.com/problemset/problem/43/B
**Difficulty:** Intermediate

### Problem 
Vasya wants to create an anonymous letter using letters cut from a newspaper heading. Each letter can be used only once, and spaces in the heading are preserved. Determine whether the heading contains enough letters to form the required text.
#### Input
Two non-empty lines, s_1 (heading) and s_2 (letter), containing spaces and uppercase/lowercase English letters. Length ≤ 200. Case matters.
#### Output
Print YES if the letter can be formed, otherwise NO.

### My approach
1. **Define main():** In this function you get 2 input from user and call another function letter(user1, user2) (user-defined) to solve the problem.
2. **Define letter(user1, user2):** In this user defined function, we pass the 2 inputs as the arguments in the function, then check if a letter of user2 is in user1 and the frequency of that letter is less than or equal to that as in user1, using split().  
3. **Function call:** main() is invoked.

### Solution
```python
def main():
    prompt1=input().strip()
    prompt2=input().strip()
    letter(prompt1, prompt2)

def letter(user1, user2):
    flag1=True
    for k in user1.split():
        if not k.isalpha() :
            flag1=False
            break
    flag2=True
    for i in user2.split():
        if not i.isalpha():
            flag2=False
            break

    count1=0
    for j in user1.split() :
        count1+=len(j)

    count2=0
    for l in user2.split() :
        count2+=len(l)

    if flag1 and flag2 and 0<count1<=200 and 0<count2<=200 :
        flag3=True
        flag4=True
        for j in user2.split():
            for k in j:
                if flag3 and flag4:
                    if k not in user1 :
                        flag3=False

                    if user2.count(k)>user1.count(k):
                        flag4=False
                                        
        if flag3 and flag4:
            print("YES")
        else: 
            print("NO")

    else:
        print("The requirements are not fullfilled!")

if __name__=="__main__" :
    main()
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8e9832cc-44e1-4c1b-94fa-d1169623566e" />




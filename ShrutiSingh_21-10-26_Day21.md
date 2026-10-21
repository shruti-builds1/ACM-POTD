# POTD Day 21 
**Platform:** Codeforces

## PROBLEM 1 – Helpful Maths
**Problem link:** https://codeforces.com/problemset/problem/339/A
**Difficulty:** Beginner

### Problem 
Xenia can calculate a sum only if the summands follow in non-decreasing order. The sum only contains numbers 1, 2 and 3. You've got the sum that was written on the board. Rearrange the summans and print the sum in such a way that Xenia can calculate the sum.
#### Input
The first line contains a non-empty string s — the sum Xenia needs to count. It contains only contains digits and characters "+" and no spaces. Besides, string s is a correct sum of numbers 1, 2 and 3. String s is at most 100 characters long.
#### Output
Print the new sum that Xenia can count.

### My approach
1. **Take Input:** Read the given sum as a string and remove any leading or trailing whitespace using strip().
2. **Count Occurrences:** Use the count() method to count the occurrences of 1, 2, and 3 in the string and store them in num1, num2, and num3, respectively.
3. **Handle Single-Digit Sums:** Check whether the string contains only one type of digit. If so, print the original string as it is, since the numbers are already in non-decreasing order.
4. **Arrange the Digits:** If the sum contains more than one type of digit, print all occurrences of 1, followed by 2, and then 3, ensuring that the numbers appear in ascending order.
5. **Handle Separators:** Use + between consecutive numbers and avoid an extra + at the end of the output.
6. **Validate Input Length:** Check whether the input string is at most 100 characters long, as specified in the problem statement.

### Solution
```python
data=input().strip()
num1=data.count('1')
num2=data.count('2')
num3=data.count('3')
if len(data)<=100:
    if num1>0 and (num2==0 and num3==0) :
        print(data)
    elif num2>0 and (num1==0 and num3==0) :
        print(data)
    elif num3>0 and (num2==0 and num1==0) :
        print(data)
    else:
        if num1>0  :
            for k in range(num1):
                print(1,end='+')
        if num2>0:
            if len(data.split('+'))-num1==num2 :
                for k in range(num2-1):
                    print(2,end='+')
                print(2)
            else :
                for k in range(num2):
                    print(2,end='+')

        if num3>0 :
            for k in range(num3-1):
                print(3,end='+')
            print(3)
else:
    print('Input can be atmost 100 characters long only!')

```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8ec25721-158c-4f86-a11f-eb76bb8ad1ff" />

## PROBLEM 2 - Elevator
**Problem link:** https://codeforces.com/contest/120/problem/A
**Difficulty:** Intermediate

### Problem 
A skyscraper has an elevator with two doors (front and back) and two rails (1 and 2). A person enters through one door and holds a rail with their strongest hand. Determine whether the person is left-handed (L) or right-handed (R) based on the entrance door and rail number.

#### Input
- The first line contains the entrance door: front or back.
- The second line contains an integer a (1 ≤ a ≤ 2), representing the rail number.

#### Output
Print L if the person is left-handed or R if the person is right-handed.

### My approach
1. **Open input.txt file:** Extract the lines from the file using readlines() and store the values in door and rail.
2. **Handle cases:** print output as per the problem and also handle errors where user may enter wrong door or rail number.

### Solution
```python
with open('input.txt','r') as f :
    data=f.readlines()
    door=data[0].rstrip('\n')
    rail=data[1].rstrip('\n')
    # print(door, rail)
    if door=='front' :
        if rail=='1' :
            with open('output.txt','w') as file :
                file.write('L')
        elif rail=='2' :
            with open('output.txt','w') as file :
                file.write('R')
        else:
            print(f'The elevator has 2 rails only!')
        

    elif door=='back' :
        if rail=='2' :
            with open('output.txt','w') as file :
                file.write('L')
        elif rail=='1' :
            with open('output.txt','w') as file :
                file.write('R')
        else:
            print(f'The elevator has 2 rails only!')

    else:
        print(f'The elevator has only 2 doors!')

```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ee03fdf4-46ef-476b-968f-bbea51db9495" />



##

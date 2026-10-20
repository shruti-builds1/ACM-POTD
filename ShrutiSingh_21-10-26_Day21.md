# POTD Day 21 – Helpful Maths

**Platform:** Codeforces
**Problem link:** https://codeforces.com/problemset/problem/339/A
**Difficulty:** Beginner

## Problem 
The first line contains a non-empty string s. String s contains no spaces. It only contains digits and characters "+". Besides, string s is a correct sum of numbers 1, 2 and 3. Output should display the sum in ascending order. String s is at most 100 characters long.

## My approach
## Approach

1. **Take Input:** Read the given sum as a string and remove any leading or trailing whitespace using `strip()`.
2. **Count Occurrences:** Use the `count()` method to count the occurrences of `1`, `2`, and `3` in the string and store them in `num1`, `num2`, and `num3`, respectively.
3. **Handle Single-Digit Sums:** Check whether the string contains only one type of digit. If so, print the original string as it is, since the numbers are already in non-decreasing order.
4. **Arrange the Digits:** If the sum contains more than one type of digit, print all occurrences of `1`, followed by `2`, and then `3`, ensuring that the numbers appear in ascending order.
5. **Handle Separators:** Use `+` between consecutive numbers and avoid an extra `+` at the end of the output.
6. **Validate Input Length:** Check whether the input string is at most 100 characters long, as specified in the problem statement.

## Solution
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

## Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8ec25721-158c-4f86-a11f-eb76bb8ad1ff" />


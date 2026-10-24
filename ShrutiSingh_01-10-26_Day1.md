# POTD Day 1 
**Platform:** Codeforces

## PROBLEM 1- Letter
**Problem link:** https://codeforces.com/contest/14/problem/A
**Difficulty:** Beginner

### Problem
The first line of the input data contains numbers n and m (1 ≤ n, m ≤ 50), n — amount of lines, and m — amount of columns on Bob's sheet. The 
following n lines contain m characters each. 

### My Approach
1. **Input:** Read `n` and `m`, then store all rows in the `boxes` list.
2. **Find Column Boundaries:** Use `index('*')` and `rindex('*')` to find the leftmost (`min`) and rightmost (`max`) shaded columns.
3. **Find the First Shaded Row:** Locate the first row containing `*` and store its index in `rank1`.
4. **Check for Gaps:** Use `occur` to detect unshaded rows between shaded rows.
5. **Handle Cases:** If gaps exist, print all rows between the first and last shaded rows; otherwise, print only rows containing `*`.
6. **Extract the Rectangle:** Use `boxes[j][min:max+1]` to extract and print the required columns.

### Solution
```python
data=input()
n, m = data.strip().split(' ')
boxes=[]
max=0
min=int(m)
for k in range(int(n)) :
    box=input()
    boxes.append(box.strip())
    if '*' in box :
        if 0<=box.index('*')<=min :
            min=box.index('*')
        if int(m)>=box.rindex('*')>=max :
            max=box.rindex('*')
        # print('min:',min,'\tmax:',max)
    # boxes.append(box.strip())
# print('min:',min,'\tmax:',max)
for j in boxes: 
    if '*' in j:
        rank1=boxes.index(j)
        break

occur=0
for i in range(rank1, len(boxes)-1,1) :
    if '*' not in boxes[i] and '*' in boxes[i+1] :
        occur+=1
        
if occur>0 :
    # reverse_list=list(reversed(boxes))
    for l in range(len(boxes))  :
        if '*' in boxes[l] :
            rank_last=l
    # print(rank_last)
    # print(reverse_list)
    # print('output:')
    for j in range(rank1, rank_last + 1) :
        print(boxes[j][min:max+1])

else :
    # print('output:')
    for k in boxes :
        if '*' in k :
            rank2=k.index('*')
            print(k[min:max+1])

```

### Proof of acceptance
<img width="1920" height="1080" alt="Screenshot 2026-10-20 223100" src="https://github.com/user-attachments/assets/1c8319cf-bb02-45b9-ab45-10d62b6aa7e4" />


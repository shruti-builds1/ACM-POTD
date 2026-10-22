# POTD Day 23
**Platform:** Codeforces

## PROBLEM 1 – Second-Price Auction
**Problem link:** https://codeforces.com/problemset/problem/386/A
**Difficulty:** Beginner

### Problem 
In an auction, winner pay not the price she/he offers, but the highest price among the offers of other participants (hence the name: the second-price auction).
Write a program that reads prices offered by bidders and finds the winner and the price she/he will pay. Consider that all of the offered prices are different.
#### Input
The first line of the input contains n (2 ≤ n ≤ 1000) — number of bidders. The second line contains n distinct integer numbers p1, p2, ... pn, separated by single spaces (1 ≤ pi ≤ 10000), where pi stands for the price offered by the i-th bidder.
#### Output
The single output line should contain two integers: index of the winner and the price he will pay. Indices are 1-based.

### My approach
1. **Take Input:** Take 1 integer and other a string input from user.
2. **Handle cases:** First check if the bidders are in required range then store the index of the maximum price in bidder and sorting the prices in descending order (using sorted()) then storing the 2 highest price in price. 
3. **Display ** Print bidder and price.

### Solution
```python
bidders=int(input())
prices=input().strip().split(' ')
L=[]
for k in prices:
    L.append(int(k))
# print(L)
# print(sorted(L, reverse=True))
if 2<=bidders<=1000 :
    bidder=L.index(max(L)) + 1
    price= sorted(L, reverse=True)[1]
    print(bidder,price)

else:
    print('The number of bidders should be in range 2 ≤ n ≤ 1000')    
```

### Proof of acceptance
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0262e505-7e4a-4a4e-a313-86d0a509d0d6" />


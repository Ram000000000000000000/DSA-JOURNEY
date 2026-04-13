## 2. 📈 Best Time to Buy and Sell Stock

##  Problem
Find the maximum profit by choosing a day to buy and a later day to sell.

##  Input
prices = [7,1,5,3,6,4]

##  Output
5

##  Explanation
Buy at 1 and sell at 6 → profit = 5

🔗 Problem Link: [Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)

---

##  My Thinking
- Initially thought of checking all pairs (buy-sell)
- That gives O(n^2), not efficient
- Realized I need to track minimum price while traversing
- Calculate profit at each step

---

##  Optimized Approach
- Keep track of minimum price so far
- For each price, calculate profit = current - min_price
- Update maximum profit

---

##  Technique Used
- Greedy
- Array traversal

---

## 💻 Code(LeetCode version) (Python)

```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        min_price = float('inf')
        max_profit = 0
        for i in prices:
            if i < min_price:
                min_price = i
            max_profit = max(max_profit,i-min_price)
        return max_profit
```
## 💻 Code(Input version) (Python)
```python
class Solution:
    def maxProfit(self,prices):
        min_price = float('inf')
        max_profit = 0
        for i in prices:
            if i < min_price:
                min_price = i
            max_profit = max(max_profit,i-min_price)
        return max_profit
prices = list(map(int,input().split()))
s = Solution()
print(s.maxProfit(prices))

```
---
## Iteration walkthrough
prices = [7,1,5,3,6,4]

i = 0 ,price=7 → min=7,max = max(0,7-7)=0
price=1 → min=1 → min = 1<7 = 7,max = max(0,1-1)=0

price=5 → min = 5<1(X) min =1,max = max(0,5-1)=4

price=3 →  min = 3<1(X) min =1,max = max(4,3-1)=4

price=6 →  min = 6<1(X) min =1,max = max(4,6-1)=5

price=4 →  min = 4<1(X) min =1,max = max(5,4-1)=5

---
## ⏱️ Complexity

- **Time Complexity:** O(n)  
  (We traverse the array once while tracking minimum price and profit)

- **Space Complexity:** O(1)  
  (No extra space is used, only variables)

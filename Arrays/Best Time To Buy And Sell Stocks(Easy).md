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

## 💻 Code (Python)

```python
def maxProfit(prices):
    min_price = float('inf')
    max_profit = 0

    for price in prices:
        if price < min_price:
            min_price = price
        else:
            profit = price - min_price
            max_profit = max(max_profit, profit)

    return max_profit

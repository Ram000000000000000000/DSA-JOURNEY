# 1. Two Sum

##  Problem
Find two indices such that their values sum to the target.

## Input
nums = [2,7,11,15], target = 9

## Output
[0,1]

## Explanation
2 + 7 = 9 → indices (0,1)

🔗 Problem Link: [Two Sum - LeetCode](https://leetcode.com/problems/two-sum/)

---

## My Thinking
- First, I tried brute force (checking all pairs)
- This gives O(n^2), which is inefficient
- I needed a faster way to find the complement
- Then I used hashing for quick lookup

---

## Optimized Approach
- Use a hashmap to store elements and their indices
- For each element, check if (target - num) exists
- If found → return indices
- Else → store current element in hashmap

---

## Technique Used
- Hashing
- Array traversal

---

## 💻 Code (Python)


    class Solution(object):
     def twoSum(self, nums, target):
      d = {}
      for i in range(0,len(nums)):
        com = target - nums[i]
        if com in d:
          return [d[com],i]
        d[nums[i]] = i

---
## 🔄 Iteration Walkthrough

nums = [2,7,11,15], target = 9

- i = 0 → num = 2  
  complement = 9 - 2 = 7 → not found  
  store → {2: 0}

- i = 1 → num = 7  
  complement = 9 - 7 = 2 → found in hashmap
  return [d[2], i] = [0,1]
---
## ⏱️ Complexity

### ⚡ Optimized Approach
- Time Complexity: O(n)  
  → We traverse the array once and each lookup in hashmap takes O(1)

- Space Complexity: O(n)  
  → We store elements in hashmap

---

### ❌ Brute Force Approach
- Time Complexity: O(n^2)  
  → Two nested loops to check all pairs

- Space Complexity: O(1)  
  → No extra space used

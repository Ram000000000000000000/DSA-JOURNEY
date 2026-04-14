#  3. Maximum Subarray

##  Problem
Find the contiguous subarray with the largest sum.

##  Input
nums = [-2,1,-3,4,-1,2,1,-5,4]

##  Output
6

##  Explanation
Subarray [4,-1,2,1] has the maximum sum = 6

🔗 Problem Link: [Maximum Subarray](https://leetcode.com/problems/maximum-subarray/)

---

##  My Thinking
- First thought of checking all subarrays (brute force)
- That gives O(n^2), which is inefficient
- Needed a way to track maximum sum dynamically
- Observed that negative sums reduce overall result

---

##  Optimized Approach (Kadane’s Algorithm)
- Maintain current sum while traversing
- If current sum becomes negative → reset to 0
- Keep updating maximum sum

---

##  Technique Used
- Kadane’s Algorithm
- Dynamic Programming (optimized)

---

## 💻 Leetcode-Version Code (Python)

```python
class Solution:
  def maxSubArray(self, nums: List[int]) -> int:
    curr_sum = 0
    max_sum = nums[0]

    for num in nums:
        curr_sum += num
        max_sum = max(max_sum, curr_sum)

        if curr_sum < 0:
            curr_sum = 0

    return max_sum
```
---
## 💻 Input-Version Code (Python)
```python
def maxSubArray(nums):
    curr_sum = 0
    max_sum = nums[0]

    for num in nums:
        curr_sum += num
        max_sum = max(max_sum, curr_sum)

        if curr_sum < 0:
            curr_sum = 0

    return max_sum
  nums = list(map(int,input().split()))
  print(maxSubArray(nums))
  ```
  
---
## Iteration Walkthrough

nums = [-2,1,-3,4,-1,2,1,-5,4]

num=-2 → curr=-2 → max=-2 → reset curr=0

num=1 → curr=1 → max=1

num=-3 → curr=-2 → reset curr=0

num=4 → curr=4 → max=4

num=-1 → curr=3

num=2 → curr=5 → max=5

num=1 → curr=6 → max=6

num=-5 → curr=1

num=4 → curr=5

---

## ⏱️ Complexity
Time Complexity: O(n)

Space Complexity: O(1)

---
## Key Learning

Negative running sums should be discarded to maximize the overall subarray sum.

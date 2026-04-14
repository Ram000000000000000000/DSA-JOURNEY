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
  
```

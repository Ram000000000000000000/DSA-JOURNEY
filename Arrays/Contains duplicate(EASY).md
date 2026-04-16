#  4. Contains Duplicate

##  Problem
Check if any value appears at least twice in the array.

##  Input
nums = [1,2,3,1]

##  Output
True

##  Explanation
Element 1 appears more than once → duplicate exists

🔗 Problem Link: [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)

---

## 💭 My Thinking
- First thought was to compare all pairs
- That gives O(n^2), inefficient
- Needed a faster way to detect duplicates
- Used hashing (set) for quick lookup

---

##  Optimized Approach
- Use a set to store elements
- Traverse array
- If element already exists in set → return True
- Else → add it to set

---

##  Technique Used
- Hashing
- Set data structure

---

## 💻 Leetcode version Code(Python)

```python
class Solution:
  def containsDuplicate(self, nums: List[int]) -> bool:
        
    seen = set()

    for num in nums:
        if num in seen:
            return True
        seen.add(num)

    return False

  ```

  ---
  
  ## 💻   Input version Code(Python)Code
  ```python
def containsDuplicate(nums):
    seen = set()

    for num in nums:
        if num in seen:
            return True
        seen.add(num)

    return False
nums = list(map(int,input().split()))
print(containsDuplicate(nums))

  ```
---
## Iteration Walkthrough

nums = [1,2,3,1]

num=1 → not in set → add → {1}

num=2 → not in set → add → {1,2}

num=3 → not in set → add → {1,2,3}

num=1 → already in set → return True

---

## ⏱️ Complexity

Time Complexity: O(n)

Space Complexity: O(n)

---

## 💡 Key Learning

Using a set helps detect duplicates efficiently in one pass
  

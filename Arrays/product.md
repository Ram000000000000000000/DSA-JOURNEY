# 5. Product of Array Except Self

##  Problem
Return an array where each element is the product of all elements except itself.

##  Input
nums = [1,2,3,4]

##  Output
[24,12,8,6]

##  Explanation
- For index 0 → 2×3×4 = 24  
- For index 1 → 1×3×4 = 12  
- For index 2 → 1×2×4 = 8  
- For index 3 → 1×2×3 = 6  

🔗 Problem Link: [Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/)

---

##  My Thinking
- First thought was to multiply all elements and divide by current element
- But division is not allowed and fails with zero
- Needed a way to compute product without using division
- Used prefix and suffix products

---

##  Optimized Approach
- Create result array
- First pass: store prefix products
- Second pass: multiply with suffix products
- No extra arrays needed (use result array)

---

##  Technique Used
- Prefix Sum (Product variant)
- Array traversal

---

## 💻 Code (Python)

``` python
def productExceptSelf(nums):
    n = len(nums)
    res = [1] * n

    prefix = 1
    for i in range(n):
        res[i] = prefix
        prefix *= nums[i]

    suffix = 1
    for i in range(n-1, -1, -1):
        res[i] *= suffix
        suffix *= nums[i]

    return res
```

---

## Iteration Walkthrough

nums = [1,2,3,4]

Prefix pass:

res = [1,1,2,6]

Suffix pass:

update from right → final res = [24,12,8,6]

## ⏱️ Complexity

Time Complexity: O(n)

Space Complexity: O(1) (excluding output array)

💡 Key Learning

Using prefix and suffix products avoids division and handles zero cases efficiently.


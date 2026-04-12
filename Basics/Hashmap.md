# 🔑 Hashing (Quick Notes)

---

## 🧠 What is Hashing?
Hashing is a technique used to store and retrieve data efficiently using a **key-value pair**.

It allows us to access data in **constant time → O(1)** (on average).

---

## 📦 Data Structure Used
- HashMap / Dictionary (Python: `dict`)
- HashSet (for storing unique values)

---

## ⚡ Why Hashing is Powerful
- Fast lookup
- Avoids nested loops
- Reduces time complexity drastically

👉 Example:
Instead of checking all pairs (O(n²)), we can use hashing to solve in **O(n)**

---

## 🔍 How it Works
1. Store elements in a hashmap
2. While traversing, check if required value exists
3. If exists → use it
4. Else → store current element

---

## 📌 Common Use Cases
- Finding pairs (Two Sum)
- Counting frequency
- Detecting duplicates
- Storing visited elements

---

## 💡 Example (Two Sum Logic)
- Target = 9
- Array = [2, 7, 11, 15]

Steps:
- Check 2 → store it
- Check 7 → 9 - 7 = 2 (already exists) ✅

👉 Pair found!

---

## ⏱️ Complexity
- Time: O(n)
- Space: O(n)

---

## ⚠️ Note
Hashing gives O(1) time **on average**,  
but in worst case it can degrade (rare in interviews).

---

## 🚀 Key Learning
Hashing helps convert slow solutions (O(n²)) into fast ones (O(n)) by storing and reusing information.

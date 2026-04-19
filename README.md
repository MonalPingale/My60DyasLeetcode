# 🚀 60 Days LeetCode Challenge

Welcome to my **#60DaysLeetCodeChallenge** 💻🔥
I have started this journey to improve my **Data Structures & Algorithms (DSA)** skills and become more consistent in problem solving.

---

## 📌 Repository Link

👉 https://github.com/MonalPingale/My60DyasLeetcode/tree/main

---

## 🎯 Goal

* Solve **1 problem daily for 60 days**
* Improve problem-solving skills
* Strengthen concepts like:

  * BFS / DFS
  * Dynamic Programming
  * Graphs
  * Bitmasking
  * Backtracking

---

## 🧠 Day 1

🔹 **Problem:** 864. Shortest Path to Get All Keys
🔗 https://leetcode.com/problems/shortest-path-to-get-all-keys/

### 💡 Approach

* Used **BFS (Breadth First Search)** for shortest path
* Applied **Bitmasking** to track collected keys
* State defined as:
  `(row, col, keyMask)`

### 🔐 Key Concepts

* Same cell with different keys = different state
* Used 3D visited array → `visited[row][col][mask]`
* Efficient key tracking using bit operations

---

## 📈 Progress Tracker

| Day | Problem                       | Status |
| --- | ----------------------------- | ------ |
| 1   | Shortest Path to Get All Keys | ✅      |

---

## 🔥 Tech Stack

* Language: **Java**
* Platform: **LeetCode**

---

## 📌 Why this Challenge?

Consistency is the key to mastering DSA.
This challenge helps me:

* Build discipline
* Improve logical thinking
* Prepare for coding interviews

---

## 🙌 Let's Connect

If you're also solving DSA problems, feel free to connect and collaborate! 🚀

---

⭐ If you like this repo, consider giving it a star!


-------------------------------------------------------------------------------------
## 🧠 Day 2

🔹 **Problem:** 2551. Put Marbles in Bags
🔗 https://leetcode.com/problems/put-marbles-in-bags/

---

### 💡 Approach

Instead of trying all partitions (which is expensive), we optimize using **greedy + sorting**.

* Observed that total score depends on **adjacent pair sums**
* Created an array of all adjacent sums:
  `weights[i] + weights[i+1]`
* Sorted this array

Then:

* **Minimum score →** pick smallest `(k-1)` values
* **Maximum score →** pick largest `(k-1)` values
* **Answer →** `max - min`

---

### 🔐 Key Concepts

* Greedy optimization
* Observational problem solving
* Adjacent pair contribution trick
* Sorting for efficient selection

---
----------------------------------------------------------------------------------
🧠 Day 3

🔹 Problem: Non-overlapping Intervals problem
🔗 https://leetcode.com/problems/non-overlapping-intervals/
---------------
💡 Approach

This problem is solved using a Greedy strategy.

First, sort all intervals by their end time
Why? → Choosing the interval that finishes earliest leaves more room for others

Then:

Keep a variable prevEnd (end of last selected interval)

Traverse all intervals:
If start < prevEnd → overlap → remove it (count++)
Else → no overlap → update prevEnd
-------
🔐 Key Concepts
Greedy Algorithm (Earliest Finish Time)
Interval Scheduling Pattern
Sorting for optimization

---------------------------------------------------------------------------------
🧠 Day 4

🔹 Problem: 2483. Minimum Penalty for a Shop
🔗 https://leetcode.com/problems/minimum-penalty-for-a-shop/

💡 Approach

This problem is solved using a prefix + suffix optimization approach.

Instead of checking all closing times separately, we track penalties efficiently:

Left side (shop open) → count of 'N' (no customers but shop open → penalty)
Right side (shop closed) → count of 'Y' (customers came but shop closed → penalty)

So,

Penalty = leftN + rightY

⚙️ Steps
Count total 'Y' → this is initial rightY (when shop closes at 0)

Initialize:
leftN = 0
minPenalty = rightY
answer = 0

Traverse the string:
If 'Y' → decrease rightY
If 'N' → increase leftN

At every step:
Calculate penalty = leftN + rightY
Update minimum penalty and index
------------------------------------------------
🔐 Key Concepts
Prefix & Suffix counting
Greedy observation
Optimizing brute force
String traversal

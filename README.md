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


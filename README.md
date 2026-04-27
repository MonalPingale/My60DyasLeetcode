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


----------------------------------------------------------------------------------------------
🧠 Day 5

🔹 Problem: 1282. Group the People Given the Group Size They Belong To
🔗 https://leetcode.com/problems/group-the-people-given-the-group-size-they-belong-to/

💡 Approach

This problem is solved using HashMap + Greedy grouping.

👉 Each person tells the size of the group they belong to
👉 We need to form groups accordingly

📌 Problem Understanding (In Simple Words)

You are given an array groupSizes where:

groupSizes[i] = size of group for person i

🎯 Goal:
Form groups such that:

✔ Each group has exactly required size
✔ Each person appears in exactly one group

💡 My Thought Process 🧠

At first, I thought:
👉 Try forming groups manually

But realized:
❌ Managing groups without structure is messy

So I used a map…

🔍 Key Insight

👉 People with same group size should be grouped together

👉 Use:

size → list of people

👉 Once list size == required group size
➡️ Add it to answer & reset

🚀 Approach

Create a HashMap:

groupSize → list of indices
Traverse array:
Add person index to corresponding list
If list size == group size:
Add list to answer
Reset list
🔐 Key Concepts

✔ HashMap grouping
✔ Greedy formation
✔ Bucket filling technique
✔ Index-based grouping


--------------------------------------------------------------
🧠 Day 6
🔹 Problem: 126. Word Ladder II

🔗 https://leetcode.com/problems/word-ladder-ii/

📌 Problem Understanding

Given:

beginWord
endWord
wordList

We need to find all shortest transformation sequences such that:

✔ Only one letter changes at a time
✔ Each intermediate word must be in wordList
✔ Final word must be endWord
--------------------------------------------
💡 Approach

This problem is solved using a combination of:

👉 BFS (for shortest path)
👉 DFS (to build all paths)
-------------------------------------------
🔍 Key Idea

1.BFS Phase
Find shortest distance of each word from beginWord
Store in levelMap

2. DFS Phase
Start from endWord
Go backward using levelMap

Build all valid shortest paths
----------------------------
⚙️ Steps
BFS:
Use queue
For each word → generate all possible transformations
Store level (distance)
Stop when endWord is reached

DFS:
Start from endWord
Move to words with level - 1
Build path recursively
Reverse path at the end
-------------------------------
🔐 Key Concepts
1.BFS for shortest path
2.DFS for path generation
3.Backtracking
4.HashMap for level tracking
5.String transformation


---------------------------------------------------------------------------------------
🧠 Day 7
🔹 Problem: 905. Sort Array By Parity

🔗 https://leetcode.com/problems/sort-array-by-parity/

📌 Problem Understanding

Given an array nums:

👉 Move all even numbers first
👉 Then all odd numbers

✔ Order doesn’t matter

💡 Approach

This problem is solved using Two Pointer technique.

👉 Use two pointers:

l → start
r → end
🔍 Key Idea
If right side has even → swap with left
Else → move right pointer

👉 This ensures:
✔ Even numbers go to front
✔ Odd numbers move to back

⚙️ Steps
Initialize:
l = 0
r = n - 1
While l <= r:
If nums[r] is even → swap with nums[l], l++
Else → r--
🔐 Key Concepts
Two Pointer technique
In-place swapping
Array partitioning








----------------------------------------
)
🧠 Day 8
🔹 Problem: Shortest Distance in a Binary Maze

🔗 https://practice.geeksforgeeks.org/problems/shortest-distance-in-a-binary-maze/

📌 Problem Understanding

You are given a grid where:

1 → valid cell (you can move)
0 → blocked cell (cannot move)

👉 You are also given:

source
destination

🎯 Goal:
Find the shortest distance from source to destination

✔ Move only in 4 directions (Up, Down, Left, Right)
✔ If path not possible → return -1

💡 Approach

This problem is solved using Dijkstra’s Algorithm (Shortest Path).

👉 Since each move has equal weight (1),
👉 It behaves similar to BFS, but we used Priority Queue

🔍 Key Idea

Use a min-heap (PriorityQueue)
Always process the shortest distance first
Maintain a dist[][] array

⚙️ Steps
1. Initialize:
2. Distance array with INF
3. Priority Queue → (distance, row, col)
4.Start from source:
dist[source] = 0
5. Traverse:
6. Pop smallest distance cell
7. Explore 4 directions
8. If shorter path found:
Update distance
Push into queue
9. If destination reached → return distance


🔐 Key Concepts
Dijkstra Algorithm
Priority Queue (Min Heap)
Grid traversal
Shortest Path


--------------------------------------------------------
🧠 Day 9
🔹 Problem: 1503. Last Moment Before All Ants Fall Out of a Plank

🔗 https://leetcode.com/problems/last-moment-before-all-ants-fall-out-of-a-plank/

📌 Problem Understanding

You are given:

A plank of length n
Ants moving:
Left (left[])
Right (right[])

Rules:

✔ Speed = 1 unit/sec
✔ When ants collide → they just change direction
✔ When ant reaches end → falls

🎯 Goal:
Find the last moment when any ant is still on the plank

💡 Approach

👉 Key observation:

Collision doesn’t matter ❗

Why?

👉 Instead of changing direction,
we can assume ants pass through each other

➡️ Result remains SAME

🔍 Key Idea
Ant moving left → time = position
Ant moving right → time = n - position

👉 So answer =

max( max(left[i]), max(n - right[i]) )

⚙️ Steps
1.Initialize max = 0
2.For all ants moving left:
3.Take maximum position
4.For all ants moving right:
5.Take maximum (n - position)
6.Return max

🔐 Key Concepts
Greedy observation
Collision simplification

--------------------------------------------------
🧠 Day 10
🔹 Problem: 1887. Reduction Operations to Make the Array Elements Equal

🔗 https://leetcode.com/problems/reduction-operations-to-make-the-array-elements-equal/

📌 Problem Understanding

You are given an array nums.

👉 In one operation:

Pick the largest element
Reduce it to the next smaller distinct element

🎯 Goal:
Make all elements equal using minimum operations

💡 Approach

This problem is solved using Sorting + Greedy.

👉 Instead of simulating operations,
👉 We count how many times each level needs reduction

🔍 Key Idea
Sort the array
Traverse from right to left

👉 Whenever we find a new smaller element,
➡️ All elements greater than it need operations

⚙️ Steps
Sort array
Start from second last element

If nums[i] != nums[i+1]:

operations += (n - i - 1)
Continue till start


-------------------------------------------
🧠 Day 11
🔹 Problem: Bellman-Ford Algorithm

🔗 https://practice.geeksforgeeks.org/problems/distance-from-the-source-bellman-ford-algorithm/

📌 Problem Understanding

You are given:

V → number of vertices
edges[][] → each edge = [u, v, wt]
src → source node

🎯 Goal:
Find shortest distance from source to all vertices

⚠️ Special Condition

👉 If graph contains negative weight cycle
➡️ Return [-1]

💡 Approach

This problem is solved using Bellman-Ford Algorithm.

👉 Unlike Dijkstra, it works with:
✔ Negative weights
✔ Detects negative cycles

🔍 Key Idea
Relax all edges V-1 times
Then check one more time:
If still relaxing → negative cycle exists
⚙️ Steps

Initialize:

dist[] = INF
dist[src] = 0

Relax edges V-1 times:

if dist[u] + wt < dist[v]
    update dist[v]

Check for negative cycle:

if still relaxable → return [-1]

🔐 Key Concepts
Bellman-Ford Algorithm
Edge relaxation
Negative cycle detection
Graph shortest path

🔐 Key Concepts
Sorting
Greedy counting
Observational optimization
------------------------------------------

🧠 Day 12
🔹 Problem: 1630. Arithmetic Subarrays

🔗 https://leetcode.com/problems/arithmetic-subarrays/

📌 Problem Understanding

You are given:

Array nums
Queries: l[i] to r[i]

👉 For each query:
Check if subarray can be rearranged into an arithmetic sequence

💡 Approach

Instead of sorting every time ❌
👉 Use Math + HashSet optimization ✅

🔍 Key Idea

For an arithmetic sequence:

max - min = (n - 1) * diff

👉 So:

Find min and max
Check if:
(max - min) % (n - 1) == 0
Compute:
diff = (max - min) / (n - 1)
Check all expected elements exist:
min, min+diff, min+2*diff ...

⚙️ Steps
For each query:
Extract subarray
Store elements in set
Find:
min
max
Validate arithmetic condition
Check presence of all expected values

🔐 Key Concepts
HashSet lookup
Arithmetic progression
Mathematical validation
Optimization over sorting

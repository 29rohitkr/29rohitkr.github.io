# 🧩 [Problem Number/ID] - Problem Title

**Difficulty:** [Easy | Medium | Hard]
**Topic:** [Array | Linked List | Graph | Dynamic Programming | etc.]
**Date Solved:** [YYYY-MM-DD]

## 🔗 Links

| Resource | URL |
| :--- | :--- |
| **Question Source** | [Direct URL to LeetCode/GeeksforGeeks/HackerRank question] |
| **Solution Video/Article** | [Optional: Link to an explanation you found helpful] |

## 📝 Problem Statement

> [Copy and paste the core problem description here. Keep it concise, or use blockquotes for full text.]

**Example:**
Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.

## 💡 Thought Process & Approach

1.  **Initial Idea (Brute Force):** Nested loops to check every pair. $O(n^2)$ time complexity. Too slow.
2.  **Optimization (Hash Map):** Use a HashMap to store the numbers we've seen and their required "complement" (i.e., `target - current_number`). This reduces lookup time to $O(1)$.
3.  **Final Approach:** Use the Hash Map strategy for $O(n)$ time complexity.

## ✍️ Java Solution

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        // Use a HashMap to store (Value, Index)
        Map<Integer, Integer> map = new HashMap<>();

        for (int i = 0; i < nums.length; i++) {
            int complement = target - nums[i];

            // Check if the complement is already in the map
            if (map.containsKey(complement)) {
                return new int[]{map.get(complement), i};
            }

            // If not found, add the current number and its index
            map.put(nums[i], i);
        }
        // Should not be reached based on problem constraints
        throw new IllegalArgumentException("No two sum solution");
    }
}

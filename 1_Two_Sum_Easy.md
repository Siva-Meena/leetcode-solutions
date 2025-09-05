# Problem: Two Sum (LeetCode #1)  
[Link to Problem](https://leetcode.com/problems/two-sum/)  
Difficulty: Easy  

---

## Solution (Python)

```python
class Solution:
    def twoSum(self,num,target):
        seen = {}
        for i in range(len(num)):
            other = target - num[i]
            if other in seen:
                return (seen[other],i)
            seen[num[i]] = i
```
## Explanation

We need to find two indices such that the numbers at those indices add up to the given target.
 - Use a dictionary seen to store numbers as keys and their indices as values.
 - Iterate through the array:
    - For each element num[i], compute other = target - num[i].
    - If other is already in seen, we found the solution → return the stored index of other and the current index i.
    - Otherwise, store num[i] with its index i in seen.
 - This ensures we check for the pair in a single pass.

---
## Complexity Analysis

 - Time Complexity: O(n) — We traverse the list once, with dictionary lookups in constant time.
 - Space Complexity: O(n) — At worst, we store all numbers in the dictionary.

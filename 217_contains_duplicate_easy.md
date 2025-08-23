# Problem: Contains Duplicate (LeetCode #217)
[Link to Problem](https://leetcode.com/problems/contains-duplicate/)  
Difficulty: Easy

---

## Solution (Python)

```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        seen = set()        
        for i in nums:
            if i in seen:
                return True
            seen.add(i)
        return False
```
---

## Explanation

- Initialize an empty set `seen` to store unique numbers.  
- Iterate through each element in `nums`:  
  - If the element already exists in `seen`, return `True` (duplicate found).  
  - Otherwise, add it to `seen`.  
- If the loop completes without finding duplicates, return `False`.  

### Complexity Analysis

- **Time Complexity:** `O(n)` — Each lookup and insertion in a set takes `O(1)` on average.  
- **Space Complexity:** `O(n)` — In the worst case, all elements are unique and stored in `seen`.  

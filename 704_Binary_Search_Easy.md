# Problem: Binary Search (LeetCode #704)  
[Link to Problem](https://leetcode.com/problems/binary-search/)  
Difficulty: Easy  

---

## Solution (Python)

```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        left, right = 0, len(nums) - 1
        while left <= right:
            mid = (left + right) // 2
            if nums[mid] == target:
                return mid
            elif nums[mid] < target:
                left = mid + 1
            else:
                right = mid - 1
        return -1
```
## Explanation

We apply the **Binary Search** algorithm:

- Initialize two pointers:
  - `left = 0`
  - `right = len(nums) - 1`
- While `left <= right`:
  - Compute `mid = (left + right) // 2`
  - If `nums[mid] == target`: return `mid`
  - If `nums[mid] < target`: search the right half (`left = mid + 1`)
  - Else: search the left half (`right = mid - 1`)
- If the target is not found:
  - Return `-1`

---

## Complexity Analysis

- **Time Complexity**: `O(log n)`  
  Each iteration halves the search space.
- **Space Complexity**: `O(1)`  
  Only a few variables are used.

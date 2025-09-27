# Problem: Search Insert Position (LeetCode #35)  
[Link to Problem](https://leetcode.com/problems/search-insert-position/)  
Difficulty: Easy  

---

## Solution (Python)

```python
class Solution:
    def searchInsert(self, nums: List[int], target: int) -> int:
        left = 0
        right = len(nums)-1
        while(left<=right):
            mid = (left+right)//2
            if(target == nums[mid]):
                return mid
            if(target < nums[mid]):
                right = mid-1
            if(target > nums[mid]):
                left = mid+1
        return left
```
## Explanation

The goal is to find the index of target in a sorted array or determine the position where it should be inserted to maintain the order.
1. Initialization
   - Two pointers left and right are set at the start and end of the array, respectively.
2. Binary Search
   - Compute the middle index mid = (left + right) // 2.
   - Case 1: If nums[mid] == target, return mid (target found).
   - Case 2: If target < nums[mid], narrow the search to the left half (right = mid - 1).
   - Case 3: If target > nums[mid], narrow the search to the right half (left = mid + 1).
   - Repeat until left > right.
3. Insertion Point
   - If the loop ends without finding the target, left points to the correct insertion index to maintain the sorted order.

## Complexity Analysis
- Time Complexity: O(log n)
  - Each step halves the search range.
- Space Complexity: O(1)
  - Only constant extra variables (left, right, mid) are used.

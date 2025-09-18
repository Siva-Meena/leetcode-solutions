# Problem: Valid Anagram (LeetCode #242)
[Link to Problem](https://leetcode.com/problems/valid-anagram/)
Difficulty:Easy

---

## Solution (Python)

```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        if (len(s)!=len(t)):
            return False
        seen = {}
        for i in s:
            if i in seen:
                seen[i]+=1
            else:
                seen[i]=1
        for i in t:
            if i in seen:
                seen[i]-=1
            else:
                return False
        for v in seen.values():
            if v!=0:
                return False
        return True
```
## Explanation
This function checks if two strings s and t are anagrams (contain the same characters in the same frequency):
1. Length Check:
   - If s and t have different lengths, they cannot be anagrams. Return False.
2. Count Characters in s:
   - Use a dictionary seen to store how many times each character appears in s.
3. Compare with t:
   - For each character in t, subtract 1 from its count in seen.
   - If a character in t doesn’t exist in seen, return False.
4. Verify Counts:
   - After processing, all counts in seen should be zero.
   - If any count is not zero, return False; otherwise, return True.

---
## Complexity Analysis

- Time Complexity: O(n)
  - We iterate through both strings s and t once.
  - n is the length of the strings (since they are the same length).

- Space Complexity: O(n)
  - We use a dictionary seen to store the frequency of characters.
  - In the worst case, all characters are unique, so the space used is proportional to n.

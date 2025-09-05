# Problem: Palindrome Number (LeetCode #9)  
[Link to Problem](https://leetcode.com/problems/palindrome-number/)  
Difficulty: Easy  

---

## Solution (Python)

```python
class Solution:
    def isPalindrome(self, x: int) -> bool:
        if x<0:
            return False
        temp = x
        rev = 0
        while(x>0):
            digit = x%10
            rev = rev*10 + digit
            x= x//10
        if rev==temp:
            return True
        return False
```
## Explanation

We need to check whether an integer reads the same backward as forward.
 - Handle negatives: Any negative number cannot be a palindrome because of the leading - sign.
 - Store the original number: Keep a copy of the input (temp) for comparison later.
 - Reverse the digits: Extract each digit using x % 10 and build a reversed number (rev). After processing each digit, reduce the number by x // 10.
 - Compare: Finally, check if the reversed number (rev) matches the original (temp).
    - If they are equal → the number is a palindrome.
    - Otherwise → it is not a palindrome.
  
---
## Complexity Analysis
 - Time Complexity: O(log x) — The number of digits in x is about log10(x), and we process each digit once.
 - Space Complexity: O(1) — We only use a few integer variables, no extra data structures.

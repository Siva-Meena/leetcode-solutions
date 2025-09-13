# Problem: Perfect Number (LeetCode #507)  
[Link to Problem](https://leetcode.com/problems/perfect-number/)  
Difficulty: Easy  

---

## Solution (Python)

```python
from math import isqrt

class Solution:
    def checkPerfectNumber(self, num: int) -> bool:
        if num < 2:
            return False
        
        total = 1  # 1 is a divisor of every number > 1
        
        for i in range(2, isqrt(num) + 1):
            if num % i == 0:
                total += i
                pair = num // i
                if pair != i:
                    total += pair
        
        return total == num
```
## Explanation

We check if a number is perfect (sum of its positive divisors excluding itself equals the number):
 - Handle small numbers:
   - If num < 2, return False.
 - Initialize total = 1
   - 1 is a divisor for all numbers > 1.
 - Loop from 2 to √num:
   - If i divides num evenly:
     - Add i to total.
     - Add the paired divisor num // i if it’s different from i (to avoid double counting perfect squares).
 - Check if sum equals the number:
   - return total == num.

---
## Complexity Analysis

- Time Complexity: O(√n)
  - Only iterate up to the square root of num.
- Space Complexity: O(1)
  - Only a few variables are used.

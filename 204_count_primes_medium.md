# Problem: Count Primes (LeetCode #204)  
[Link to Problem](https://leetcode.com/problems/count-primes/)  
Difficulty: Medium  

---

## Solution (Python)

```python
from math import isqrt
class Solution:
    def countPrimes(self, n: int) -> int:
        if n <= 2:
            return 0
        isPrime = [True]*n
        isPrime[0] = False
        isPrime[1] = False
        for i in range(2,isqrt(n)+1):
            if(isPrime[i]):
                for x in range(i*i,n,i):
                    isPrime[x]=False
        return sum(isPrime)
```
## Explanation

We use the **Sieve of Eratosthenes** algorithm to efficiently count prime numbers less than `n`.

- Create a boolean list `is_prime` of size `n`, initialized to `True` (assuming all numbers are prime initially).  
- Starting from `2`, for each number `i`:  
   - If `i` is marked as prime, mark all its multiples (`i*i, i*i+i, i*i+2i, ...`) as not prime.  
- We only need to check up to `√n` because any composite number will have a factor less than or equal to its square root.  
- Finally, count how many numbers remain marked as prime. 

---

## Complexity Analysis

- **Time Complexity:** `O(n log log n)` — The sieve algorithm is very efficient because each number is crossed out only a few times.  
- **Space Complexity:** `O(n)` — We store a boolean array of size `n` to track primality.  

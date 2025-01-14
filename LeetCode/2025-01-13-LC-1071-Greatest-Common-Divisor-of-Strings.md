
# ✅ LC 1071: Greatest Common Divisor of Strings

## Problem
Link: https://leetcode.com/problems/greatest-common-divisor-of-strings/description/

## Notes
Solved it with a solution similar to gcd of two numbers:
1. Recursively computed gcd of two strings by removing prefix of shorter from longer if they are equal.
2. Return string once they are equal.
3. All other cases return empty string (`""`).

## Code
```python
def gcd(s1, s2):
    if len(s1) < len(s2):
        return gcd(s2, s1)
    if len(s1) == len(s2):
        return s1 if s1 == s2 else ""
    
    # len(s1) > len(s2) here after

    # if prefix of s1 is s2
    if s1[0:len(s2)] == s2:
        # then gcd(s2, s1 without prefix s2)
        return gcd(s2, s1[len(s2):])
    else:
        # otherwise they don't have any gcd
        return ""

class Solution:
    def gcdOfStrings(self, str1: str, str2: str) -> str:
        return gcd(str1, str2)
```

## Submission

https://leetcode.com/problems/greatest-common-divisor-of-strings/submissions/1507869224

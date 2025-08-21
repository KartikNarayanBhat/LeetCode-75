# Merge Strings Alternately

## Problem Statement
Given two strings `word1` and `word2`, merge them by adding characters in an alternating fashion starting with `word1`. If one string is longer,
append the remaining characters of the longer string to the end.

---

## Approach
- Use two pointers to traverse both strings simultaneously.  
- Append one character from `word1`, then one from `word2`, until one string is exhausted.  
- Append any remaining characters from the longer string.  
- Return the final merged string.

---

## Time Complexity
- **O(n + m)**, where `n` and `m` are the lengths of `word1` and `word2`.  

## Space Complexity
- **O(n + m)** for the output string, with only constant extra space used otherwise.
  ---
  # Greatest Common Divisor of Strings

## Problem Statement
Given two strings `str1` and `str2`, return the largest string `x` such that:  

- `x` divides both `str1` and `str2`.  
- A string `x` divides string `y` if and only if `y` can be constructed by concatenating one or more copies of `x`.  

If no such string exists, return an empty string `""`.

---

## Approach
1. First, check if `(str1 + str2)` equals `(str2 + str1)`.  
   - If not, there is no common divisor string, so return `""`.  
2. If they are equal, compute the greatest common divisor (GCD) of the lengths of `str1` and `str2`.  
3. Return the substring of `str1` from index `0` to the GCD value.  

This works because if two strings share a divisor string, their concatenations in any order must be the same.

---

## Time Complexity
- **O(n + m)**, where `n` and `m` are the lengths of `str1` and `str2`.  
  (String concatenation and equality check dominate the runtime.)  

## Space Complexity
- **O(1)**, excluding the space needed for the output substring.
---

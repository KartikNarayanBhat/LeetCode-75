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
  

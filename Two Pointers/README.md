# Move Zeroes

## Problem Statement
Given an integer array `nums`, move all `0`'s to the end of the array while maintaining the relative order of the non-zero elements.  
You must do this **in-place** without making a copy of the array.

---

## Approach
The algorithm uses a two-pass approach:

1. **First Pass**:  
   - Use a pointer `j` to track the position where the next non-zero element should be placed.  
   - Iterate through the array, and for every non-zero element, place it at index `j` and increment `j`.  
   - Keep a count of how many zeros are encountered.

2. **Second Pass**:  
   - After all non-zero elements are moved to the front, fill the last `count` positions with zeros.  

This ensures the relative order of non-zero elements is preserved and all zeros are shifted to the end.

---

## Time Complexity
- **O(n)** → Each element is processed at most twice.

## Space Complexity
- **O(1)** → No extra space is used; everything is done in-place.
---
# Is Subsequence

## Problem Statement
Given two strings `s` and `t`, return `true` if `s` is a subsequence of `t`, or `false` otherwise.  

A subsequence of a string is a new string generated from the original string with some (can be none) characters deleted without changing the relative order of the remaining characters.

---

## Approach
We use the **two-pointer technique**:

1. Initialize two pointers:  
   - `i` → points to the current character in `s`.  
   - `j` → points to the current character in `t`.

2. Traverse string `t` using pointer `j`:  
   - If `s[i] == t[j]`, move both pointers forward.  
   - Otherwise, move only `j` forward.

3. If pointer `i` reaches the end of `s`, it means all characters of `s` have been found in `t` in order, so return `true`.  
4. If we finish traversing `t` and `i` has not reached the end of `s`, return `false`.

---

## Time Complexity
- **O(n + m)** → `n = length of s`, `m = length of t`.  
- Each string is traversed at most once.

## Space Complexity
- **O(1)** → Only a few pointers are used.

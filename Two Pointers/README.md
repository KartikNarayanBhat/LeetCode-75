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

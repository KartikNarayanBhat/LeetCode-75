# Maximum Average Subarray I

## Problem Statement
Given an array `nums` consisting of `n` integers and an integer `k`, find the contiguous subarray of length `k` that has the maximum average value. Return this maximum average as a **double**.

## Approach
We use the **sliding window technique**:

1. Compute the sum of the first `k` elements.
2. Store this sum as the current maximum.
3. Slide the window one step at a time:
   - Subtract the element that goes out of the window.
   - Add the new element entering the window.
   - Update the maximum sum if the new sum is larger.
4. After processing all windows, divide the maximum sum by `k` to get the maximum average.

This approach ensures we compute the result in linear time without recalculating sums from scratch.

## Time Complexity
- **O(n)**: We traverse the array once, maintaining the sliding window in constant time.

## Space Complexity
- **O(1)**: We use only a few extra variables (`sum`, `max`, indices).
---

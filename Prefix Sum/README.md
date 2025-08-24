# Find the Highest Altitude

##  Problem Statement
There is a biker going on a road trip consisting of `n + 1` points.  
The biker starts at **altitude 0**.  
You are given an integer array `gain` of length `n`, where `gain[i]` is the net gain in altitude between points `i` and `i + 1`.  

Return the **highest altitude** reached during the trip.

---

##  Approach
- Initialize:
  - `sum = 0` → current altitude.  
  - `max = 0` → highest altitude seen so far.  
- Iterate through the array:
  - Add `gain[i]` to `sum` (update current altitude).  
  - Update `max = Math.max(max, sum)` to track the maximum altitude.  
- Return `max` after the loop.

---

##  Complexity
- **Time Complexity:** `O(n)` → single traversal of the array.  
- **Space Complexity:** `O(1)` → only two variables used.  

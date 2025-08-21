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
# Kids With the Greatest Number of Candies

## Problem Statement
You are given an integer array `candies` where `candies[i]` represents the number of candies the **i-th kid** has.  
You are also given an integer `extraCandies`.  

For each kid, check if after giving them all the `extraCandies`, they will have the **greatest number of candies among all kids**.  
Return a list of booleans where `result[i] = true` if the i-th kid can have the greatest number of candies, otherwise `false`.

---

## Approach
1. Find the maximum value in the `candies` array (the current greatest number of candies).  
2. For each kid, add `extraCandies` to their candies count.  
3. If this value is greater than or equal to `maxCandies`, mark it as `true`, otherwise `false`.  
4. Store results in a list and return it.  

This approach avoids checking against every kid repeatedly, reducing time complexity.

---

## Time Complexity
- **O(n)** → One pass to find the maximum, and one pass to build the result.  

## Space Complexity
- **O(n)** → To store the result list.  
- Only a few extra variables are used (`max`), so extra space is constant apart from the output list.  
---
# Can Place Flowers

## Problem Statement
You are given an array `flowerbed` consisting of `0`s and `1`s, where `0` means empty and `1` means not empty (a flower is already planted).  
You are also given an integer `n`.  

Return `true` if `n` new flowers can be planted in the flowerbed without violating the rule that no two flowers can be adjacent, otherwise return `false`.

---

## Approach
1. Iterate through the `flowerbed` array.  
2. At each position `i`:
   - If the current spot is `0`, check if both its left and right neighbors are empty (or out of bounds).  
   - If both neighbors are empty, plant a flower (`flowerbed[i] = 1`) and increment `planted`.  
3. After processing, compare `planted` with `n`.  
   - If `planted >= n`, return `true`.  
   - Otherwise, return `false`.  

---

## Time Complexity
- **O(n)** → One pass through the flowerbed.  

## Space Complexity
- **O(1)** → Only a few extra variables are used (`planted`, `left`, `right`).  
---
# Reverse Vowels of a String

## Problem Statement
Given a string `s`, reverse only all the vowels in the string and return it.  
The vowels are `a, e, i, o, u` (both lowercase and uppercase).

---

## Approach
1. Use a **two-pointer technique**:
   - Start with `i = 0` (beginning of string) and `j = s.length() - 1` (end of string).
2. Convert the string into a character array for easy swapping.
3. While `i < j`:
   - Move `i` forward until it points to a vowel.
   - Move `j` backward until it points to a vowel.
   - Swap the vowels at positions `i` and `j`.
   - Move both pointers inward.
4. Finally, return the new string built from the modified array.

---

## Time Complexity
- **O(n)** → We scan the string at most once.  

## Space Complexity
- **O(n)** → For the character array (if we consider input string immutable).  
- **O(1)** extra space if we count only auxiliary variables.  
---
# Reverse Words in a String

## Problem Statement
Given an input string `s`, reverse the order of the words.  
A word is defined as a sequence of non-space characters. Multiple spaces between words should be reduced to a single space in the output, and there should be no leading or trailing spaces.

---

## Approach
1. Use `s.trim()` to remove leading and trailing spaces.
2. Split the string using regex `\\s+` (handles multiple spaces between words).
   - Example: `"  the sky   is  blue  "` → `["the", "sky", "is", "blue"]`
3. Iterate over the words array in reverse order and append them into a `StringBuilder`.
4. Add a single space `" "` between words (but not after the last one).
5. Return the final string.

---

## Time Complexity
- **O(n)** → Each character is processed a constant number of times (split + reverse building).

## Space Complexity
- **O(n)** → For storing the array of words and building the result string.
---
# Product of Array Except Self

## Problem Statement
Given an integer array `nums`, return an array `answer` such that `answer[i]` is equal to the product of all the elements of `nums` except `nums[i]`.  
Special care must be taken when the array contains zeros.

---

## Approach
The solution handles the problem in three cases:

1. **More than one zero in the array**  
   - If there are at least two zeros, every product will be `0`.

2. **Exactly one zero in the array**  
   - Only the index containing the zero will have the product of all non-zero elements.  
   - All other positions will be `0`.

3. **No zeros in the array**  
   - Compute the total product of the array.  
   - Each result element is obtained by dividing the total product by the element at that index.

---

## Time Complexity
- **O(n)** → One pass to count zeros, another pass to fill the result.

## Space Complexity
- **O(1)** → No extra space used apart from the output array (in-place modification).

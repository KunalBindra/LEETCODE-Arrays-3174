# LEETCODE-Arrays-3174
**Explanation:**

This code removes all digits from a given string and returns the resulting string without the digits.

**Key Idea:**

- The code uses a two-pointer approach:
    - `i`: The main loop counter, iterating through the original string.
    - `j`: A pointer that keeps track of the position to place the next non-digit character in the `arr` array.

**Dry Run Example:**

Let's consider the input string `s = "a1b2c3d"`

1. **Initialization:**
   - `n = 5` (length of the string)
   - `arr = {'a', '1', 'b', '2', 'c', '3', 'd'}`
   - `j = 0`

2. **Iteration:**
   - **i = 0:** 
      - `arr[0]` is 'a' (not a digit). 
      - `arr[j] = arr[0]`, `j++` 
      - `arr` becomes: {'a', '1', 'b', '2', 'c', '3', 'd'} 
      - `j = 1`

   - **i = 1:** 
      - `arr[1]` is '1' (a digit).
      - `j = Math.max(j-1, 0) = Math.max(0, 0) = 0` 
      - `arr` remains: {'a', '1', 'b', '2', 'c', '3', 'd'} 
      - `j = 0`

   - **i = 2:** 
      - `arr[2]` is 'b' (not a digit).
      - `arr[j] = arr[2]`, `j++`
      - `arr` becomes: {'b', '1', 'b', '2', 'c', '3', 'd'} 
      - `j = 1`

   - **i = 3:** 
      - `arr[3]` is '2' (a digit).
      - `j = Math.max(j-1, 0) = Math.max(0, 0) = 0` 
      - `arr` remains: {'b', '1', 'b', '2', 'c', '3', 'd'} 
      - `j = 0`

   - **i = 4:** 
      - `arr[4]` is 'c' (not a digit).
      - `arr[j] = arr[4]`, `j++`
      - `arr` becomes: {'c', '1', 'b', '2', 'c', '3', 'd'} 
      - `j = 1`

   - **i = 5:** 
      - `arr[5]` is '3' (a digit).
      - `j = Math.max(j-1, 0) = Math.max(0, 0) = 0` 
      - `arr` remains: {'c', '1', 'b', '2', 'c', '3', 'd'} 
      - `j = 0`

   - **i = 6:** 
      - `arr[6]` is 'd' (not a digit).
      - `arr[j] = arr[6]`, `j++`
      - `arr` becomes: {'d', '1', 'b', '2', 'c', '3', 'd'} 
      - `j = 1`

3. **Return Result:**

   - `return new String(arr, 0, j)` 
   - Returns the substring of `arr` from index 0 to `j-1` (which is "bcd")

**Output:**

- The function returns the string "bcd".

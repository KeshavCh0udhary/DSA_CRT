# Project Cost Pairs - Editorial

**Difficulty:** Medium  
**Prerequisites:** Arrays, Two Pointers, Sorting, Hashing  

---

## Hint
Consider sorting the array first to enable efficient pair searching, or using a hash-based approach for constant-time lookups.

## Short Explanation
Given an array of unique integers, count all distinct pairs where the absolute difference equals a target value. Multiple approaches exist with different time-space tradeoffs.

## Detailed Explanation

### 1. Brute Force Approach
**Concept:**  
Check all possible pairs in the array using nested loops.  

**Steps:**  
1. Iterate through each element with index i  
2. For each i, iterate through remaining elements with index j (j > i)  
3. Check if absolute difference equals target  
4. Count all valid pairs  

**Complexity:**  
- Time: O(n²) - Quadratic time makes it impractical for large inputs  
- Space: O(1) - No additional space needed  

**Best For:**  
Small input sizes (n < 1000) where simplicity is prioritized over performance  

---

### 2. Hash Set Approach  
**Concept:**  
Use a hash set for O(1) lookups to find complement values.  

**Steps:**  
1. Store all elements in a hash set  
2. For each element x:  
   - Check if (x + target) exists → increment count  
   - Check if (x - target) exists → increment count  
3. Return count/2 (each pair counted twice)  

**Complexity:**  
- Time: O(n) - Linear time on average  
- Space: O(n) - Requires storage of all elements  

**Best For:**  
Medium-sized inputs when average-case performance is acceptable  

---

### 3. Sorting + Two Pointers (Optimal)  
**Concept:**  
Sort the array first, then use two pointers to efficiently find pairs.  

**Steps:**  
1. Sort the array in ascending order  
2. Initialize two pointers (left = 0, right = 1)  
3. While right < array length:  
   - Calculate current difference  
   - If difference == target:  
     - Count pair  
     - Move both pointers forward  
   - If difference < target: move right pointer  
   - If difference > target: move left pointer  
4. Handle edge case where pointers overlap  

**Complexity:**  
- Time: O(n log n) - Dominated by sorting  
- Space: O(1) - Constant extra space (sorting may use O(n) in some implementations)  

**Best For:**  
Large inputs (n ≤ 10⁵) where optimal worst-case performance is required  

---

## Key Insights  
1. **Sorting enables efficient searching**: The two-pointer technique becomes viable after sorting  
2. **Tradeoffs exist**:  
   - Hash set provides better average time but uses more space  
   - Brute force is simple but doesn't scale  
3. **Edge cases to consider**:  
   - Minimum array size (5 elements)  
   - No valid pairs existing  
   - All elements forming valid pairs  
   - Maximum constraint values  

## Complexity Comparison  

| Approach       | Time Complexity | Space Complexity | Best Use Case          |
|----------------|------------------|-------------------|------------------------|
| Brute Force    | O(n²)           | O(1)             | Small inputs (n < 1000)|
| Hash Set       | O(n) average    | O(n)             | Medium inputs          |
| Two Pointers   | O(n log n)      | O(1)             | Large inputs (n ≤ 10⁵) |

## Recommendation  
For programming competitions and large inputs, the **Sorting + Two Pointers** approach is recommended as it provides the best balance between time complexity and space efficiency while handling all edge cases properly. The hash set approach can be preferable when average-case performance is sufficient and memory isn't constrained.

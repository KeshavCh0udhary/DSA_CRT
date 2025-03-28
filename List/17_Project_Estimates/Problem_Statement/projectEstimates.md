# Project Cost Pairs

## Problem Description
Given an array of unique project costs and a target difference value, determine the number of distinct pairs of project costs where their absolute difference equals the target value. Two pairs are considered distinct if they differ in at least one element.

### Key Points:
- Each project cost is unique in the array  
- Pairs are unordered (i.e., (a, b) is the same as (b, a))  
- Count unique pairs that satisfy the difference condition  

## Function Signature
```java
/**
 * Counts distinct pairs with absolute difference equal to target
 * 
 * @param projectCosts List of unique integers representing project costs
 * @param target The required absolute difference between pairs
 * @return Number of distinct pairs with the target difference
 */
public static int countPairs(List<Integer> projectCosts, int target) {
    // Implementation goes here
}
```

## Examples
**Example 1**
- Input:
```python
project_costs = [1, 3, 5]
target = 2
```
- Output:
```python
2
```

## Constraints
```
5 ≤ n ≤ 105
0 <   projectCosts[i] ≤ 2 × 109
Each projectCosts[i] is distinct, i.e. unique within projectCosts
1 ≤ target ≤ 109
```

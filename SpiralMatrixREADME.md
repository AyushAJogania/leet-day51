# leet-day51

# Spiral Matrix

Given an m x n matrix, return all elements of the matrix in spiral order.

## Problem Statement

You are given an `m x n` matrix, and your task is to return all elements of the matrix in spiral order.

### Example 1:

**Input:**
```
matrix = [
 [1, 2, 3],
 [4, 5, 6],
 [7, 8, 9]
]
```

**Output:**
```
[1, 2, 3, 6, 9, 8, 7, 4, 5]
```

### Example 2:

**Input:**
```
matrix = [
 [1, 2, 3, 4],
 [5, 6, 7, 8],
 [9, 10, 11, 12]
]
```

**Output:**
```
[1, 2, 3, 4, 8, 12, 11, 10, 9, 5, 6, 7]
```

## Approach

To solve this problem, we can simulate the process of moving in a spiral order through the matrix. We maintain four pointers: `top`, `bottom`, `left`, and `right`, which represent the boundaries of the current spiral. We iterate through the matrix in a spiral order, adding each element to the result vector. After processing each row or column, we adjust the boundaries accordingly and continue the traversal.

## Pseudocode

1. Initialize `result` as an empty vector to store the elements in spiral order.
2. Initialize `top`, `bottom`, `left`, and `right` as the boundaries of the matrix.
3. While `top` is less than or equal to `bottom` and `left` is less than or equal to `right`:
   - Traverse from left to right along the top row and add elements to `result`.
   - Increment `top`.
   - Traverse from top to bottom along the rightmost column and add elements to `result`.
   - Decrement `right`.
   - Check if there is more than one row left (i.e., `top` is less than or equal to `bottom`):
     - Traverse from right to left along the bottom row and add elements to `result`.
     - Decrement `bottom`.
   - Check if there is more than one column left (i.e., `left` is less than or equal to `right`):
     - Traverse from bottom to top along the leftmost column and add elements to `result`.
     - Increment `left`.
4. Return the `result` vector containing the elements in spiral order.

## Complexity Analysis

- Time Complexity: O(m * n), where m and n are the dimensions of the matrix.
- Space Complexity: O(1) excluding the output vector.

## Summary

This algorithm efficiently traverses the given matrix in a spiral order, collecting the elements along the way, and returns the result in the desired order.

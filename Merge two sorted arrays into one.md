# Merge Two Sorted Arrays

## Problem Description

You are given two sorted arrays containing integers. These arrays can be sorted in either ascending or descending order. Your task is to:

- Merge the two arrays into a single sorted array in ascending order.
- Remove any duplicate values so that each integer appears only once.
- Return an empty array if both inputs are empty.

### Examples

| Input                              | Output                          |
| --------------------------------- | -------------------------------|
| `[1, 2, 3, 4, 5]`, `[6, 7, 8, 9, 10]`  | `[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]` |
| `[1, 3, 5, 7, 9]`, `[10, 8, 6, 4, 2]`  | `[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]` |
| `[1, 3, 5, 7, 9, 11, 12]`, `[1, 2, 3, 4, 5, 10, 12]` | `[1, 2, 3, 4, 5, 7, 9, 10, 11, 12]` |

## Solution Approach

1. **Detect the sort order** of each array by comparing the first two elements.
2. **Reverse the array** if it is sorted in descending order to convert it into ascending order.
3. **Merge the two arrays** by converting them into sets to remove duplicates.
4. **Sort the merged set** in ascending order and return as a list.

This method is efficient and concise, leveraging Python's built-in set operations and sorting.

## Code Implementation

```python
def merge_arrays(arr1, arr2):
    # Convert descending arrays to ascending
    if len(arr1) > 1 and arr1[0] > arr1[1]:
        arr1 = arr1[::-1]
    if len(arr2) > 1 and arr2[0] > arr2[1]:
        arr2 = arr2[::-1]

    # Merge unique elements and sort
    merged_set = set(arr1) | set(arr2)
    return sorted(merged_set)

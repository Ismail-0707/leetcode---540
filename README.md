# LeetCode 540 - Single Element in a Sorted Array

## Problem Statement

You are given a sorted array consisting of only integers where every element appears exactly twice, except for one element which appears exactly once.

Return the single element that appears only once.

---

## Example 1

Input:
nums = [1,1,2,3,3,4,4,8,8]

Output:
2

---

## Example 2

Input:
nums = [3,3,7,7,10,11,11]

Output:
10

---

## Approach (XOR)

The XOR operator has the following properties:

- `a ^ a = 0`
- `a ^ 0 = a`

Since every element appears twice except one:

- Duplicate elements cancel each other out.
- The remaining value is the single element.

### Steps

1. Initialize `xor = 0`.
2. Traverse the array.
3. Perform `xor ^= num` for each element.
4. Return `xor`.

---

## Java Solution

```java
class Solution {
    public int singleNonDuplicate(int[] nums) {
        int xor = 0;

        for (int num : nums) {
            xor ^= num;
        }

        return xor;
    }
}
```

---

## Dry Run

Input:

nums = [1,1,2,3,3]

Calculation:

xor = 0

xor = 0 ^ 1 = 1

xor = 1 ^ 1 = 0

xor = 0 ^ 2 = 2

xor = 2 ^ 3 = 1

xor = 1 ^ 3 = 2

Return:

2

---

## Complexity Analysis

### Time Complexity

- O(n)

The array is traversed once.

### Space Complexity

- O(1)

No extra space is used.

---

## Key Insight

Using XOR is an efficient way to eliminate duplicate elements because identical numbers cancel each other out. After processing the entire array, only the element that appears once remains.

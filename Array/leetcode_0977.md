# [977. Squares of a Sorted Array](https://leetcode.com/problems/squares-of-a-sorted-array/)

<br><br>

## 내 풀이

### (1)

| Time Complexity | Space Complexity |
|---|---|
| | |

```py
class Solution:
    def sortedSquares(self, nums: List[int]) -> List[int]:
        for i, num in enumerate(nums):
            nums[i] = num**2
        nums.sort()
        return nums
```

<br><br>

---

<br><br>

## ~~Solution~~ (lock)

<br><br>

---

<br><br>

## Discussion

### (1)

| Time Complexity | Space Complexity |
|---|---|
| | |

```py
class Solution:
    def sortedSquares(self, nums: List[int]) -> List[int]:
        return sorted([n**2 for n in nums])
```
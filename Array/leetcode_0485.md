# [485. Max Consecutive Ones](https://leetcode.com/problems/max-consecutive-ones/)

<br><br>

## 내 풀이

### (1)

| Time Complexity | Space Complexity |
|---|---|
| | |

```py
class Solution:
    def findMaxConsecutiveOnes(self, nums: List[int]) -> int:
        str_nums = ''.join(str(n) for n in nums)
        splited = str_nums.split('0')
        return len(max(splited))
```

<br><br>

### (2)

| Time Complexity | Space Complexity |
|---|---|
| | |

```py
class Solution:
    def findMaxConsecutiveOnes(self, nums: List[int]) -> int:
        count = 0
        temp = 0
        for n in nums:
            if n == 1:
                temp += 1
            if count < temp:
                count = temp
            if n == 0:
                temp = 0
        return count
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
    def findMaxConsecutiveOnes(self, nums: List[int]) -> int:
        cnt = 0
        ans = 0
        for num in nums:
            if num == 1:
                cnt += 1
                ans = max(ans, cnt)
            else:
                cnt = 0
        return ans
```

<br><br>

### (2)

| Time Complexity | Space Complexity |
|---|---|
| | |

```py
from itertools import groupby


class Solution:
    def findMaxConsecutiveOnes(self, nums: List[int]) -> int:
        return max(sum(g) for _, g in groupby(nums))
```
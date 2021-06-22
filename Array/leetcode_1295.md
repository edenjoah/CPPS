# [1295. Find Numbers with Even Number of Digits](https://leetcode.com/problems/find-numbers-with-even-number-of-digits/)

<br><br>

## 내 풀이

### (1)

| Time Complexity | Space Complexity |
|---|---|
| | |

```py
class Solution:
    def findNumbers(self, nums: List[int]) -> int:
        count = 0
        for num in nums:
            if len(str(num)) % 2 == 0:
                count += 1
        return count
```

<br><br>

### (2)

| Time Complexity | Space Complexity |
|---|---|
| | |

```py
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
    def findNumbers(self, nums: List[int]) -> int:
        return sum(len(str(n)) % 2 == 0 for n in nums) 
```

<br><br>

### (2)

| Time Complexity | Space Complexity |
|---|---|
| | |

```py
class Solution:
    def findNumbers(self, nums: List[int]) -> int:
        # log10(n) + 1 is the # of digits
        return sum(int(math.log10(n)) % 2 for n in nums)
```

<br><br>

### (3)

| Time Complexity | Space Complexity |
|---|---|
| | |

```py
class Solution:
    def findNumbers(self, nums: List[int]) -> int:
        return len([x for x in nums if len(str(x)) % 2 == 0])
```
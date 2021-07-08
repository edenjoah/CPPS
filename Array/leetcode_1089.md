# [1089. Duplicate Zeros](https://leetcode.com/problems/duplicate-zeros/)

<br><br>

## ~~내 풀이~~

| Time Complexity | Space Complexity |
|---|---|
| | |

```py
```

<br><br>

---

<br><br>

## Solution

### (1) Approach 1: Two pass, O(1) space

| Time Complexity | Space Complexity |
|---|---|
| O(N) | O(1) |

```py
class Solution:
    def duplicateZeros(self, arr: List[int]) -> None:
        """
        Do not return anything, modify arr in-place instead.
        """
        possible_dups = 0
        index = len(arr) - 1

        for i in range(index + 1):  # 복제할 0 찾기
            print(i, index, possible_dups)
            
            # i가 modified list의 마지막이 될 original list의 element를 넘으면 중지
            if i > index - possible_dups:
                break

            # 0 카운트
            if arr[i] == 0:

                # Edge case: 0이지만 공간이 없어서 복제할 수 없는 경우
                if i == index - possible_dups:
                    arr[index] = 0  # 이 0의 경우 복제하지 않고 단순 복사
                    index -= 1
                    break
                
                possible_dups += 1

        # modified list의 마지막 element가 될 element부터 거꾸로 시작
        last = index - possible_dups

        # 0은 2번, 0이 아닌 element는 1번씩 복사
        for j in range(last, -1, -1):
            if arr[j] == 0:
                arr[j + possible_dups] = 0
                possible_dups -= 1
                arr[j + possible_dups] = 0
            else:
                arr[j + possible_dups] = arr[j]
```
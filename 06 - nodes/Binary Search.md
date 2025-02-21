#coding/algorithm 
# Problem

# Hint
>[!hint1]- Hint 1
>Text

>[!hint2]- Hint 2
>text here

> [!hint3]- Hint 3
> text here

# Solution 

## Solution 1
Code block
```python 
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        l = 0
        r = len(nums) - 1

        while l <= r:
            m = l + (r - l) // 2
            if nums[m] > target:
                r = m - 1
            elif nums[m] < target:
                l = m + 1
            else:
                return m

        return -1       
```



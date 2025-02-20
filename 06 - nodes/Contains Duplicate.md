#coding/arrays 
https://leetcode.com/problems/contains-duplicate/description/

# Problem 
Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

 

Example 1:

Input: nums = [1,2,3,1]

Output: true

Explanation:

The element 1 occurs at the indices 0 and 3.

Example 2:

Input: nums = [1,2,3,4]

Output: false

Explanation:

All elements are distinct.

Example 3:

Input: nums = [1,1,1,3,3,4,3,2,4,2]

Output: true

 

Constraints:

1 <= nums.length <= 105
-109 <= nums[i] <= 109

```python
class Solution:
    def hasDuplicate(self, nums: List[int]) -> bool:
       
```
# Hints

> [!Hint1]- Hint 1 
A brute force solution would be to check every element against every other element in the array. This would be an O(n^2) solution. Can you think of a better way?

> [!Hint2]- Hint 2 
Is there a way to check if an element is a duplicate without comparing it to every other element? Maybe there's a data structure that is useful here.

> [!Hint1]- Hint 3 
We can use a hash data structure like a hash set or hash map to store elements we've already seen. This will allow us to check if an element is a duplicate in constant time.



# Solutions 

# Brute Force O(n2) / O(1)

```python 
class Solution:
    def hasDuplicate(self, nums: List[int]) -> bool:
        for i in range(len(nums)):
            for j in range(i + 1, len(nums)):
                if nums[i] == nums[j]:
                    return True
        return False
```

# Sorting O(n) / O(n)
```python 
class Solution:
    def hasDuplicate(self, nums: List[int]) -> bool:
        nums.sort()
        for i in range(1, len(nums)):
            if nums[i] == nums[i - 1]:
                return True
        return False
```

# Hash Set O(n) / O(n)
```python
class Solution:
    def hasDuplicate(self, nums: List[int]) -> bool:
        seen = set()
        for num in nums:
            if num in seen:
                return True
            seen.add(num)
        return False
```

# Hash Set Length O(n) / O(n)
```python
class Solution:
    def hasDuplicate(self, nums: List[int]) -> bool:
        return len(set(nums)) < len(nums)
```



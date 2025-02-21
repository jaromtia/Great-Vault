#coding/algorithm 

# Problem
Given an array of integers `nums` and an integer `target`, return _indices of the two numbers such  kthat they add up to `target`_.

You may assume that each input would have **_exactly_ one solution**, and you may not use the _same_ element twice.

You can return the answer in any order.

**Example 1:**

**Input:** nums = [2,7,11,15], target = 9
**Output:** [0,1]
**Explanation:** Because nums[0] + nums[1] == 9, we return [0, 1].

**Example 2:**

**Input:** nums = [3,2,4], target = 6
**Output:** [1,2]

**Example 3:**

**Input:** nums = [3,3], target = 6
**Output:** [0,1]

**Constraints:**

- `2 <= nums.length <= 104`
- `-109 <= nums[i] <= 109`
- `-109 <= target <= 109`
- **Only one valid answer exists.**

**Follow-up:** Can you come up with an algorithm that is less than `O(n2)` time complexity?

```python3
# Given an array of integers nums and an integer target

# - array can be any size
# - get answer but optimization will be done later

# return indices of the two numbers such that they add up to target

# - You can return the answer in any order.
# - returns in backet array format
# - should only be two numbers in the answer
# - order does not matter

# You may assume that each input would have exactly one solution

# and you may not use the same element twice.

# - check element and move on
# - we can go left to right and not look back within the array


# Input: nums = [2,7,11,15], target = 9
# Output: [0,1]
# Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].


class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        # have the first element of the array check every number
            # return solution if it exists
        # if there is no solution then have the second element of the array look through the entire array
            # return solution if it exists
        # continue until a solution is found with each array

        for i in range(len(nums) - 1):
            for k in range(i + 1, len(nums)):
                if nums[i] + nums[k] == target:
                    return {i, k}
        return {}
            
```
# Hints

#coding/algorithm 

# Problem
Given an array of integers `nums` and an integer `target`, return _indices of the two numbers such that they add up to `target`_.

You may assume that each input would have **_exactly_ one solution**, and you may not use the _same_ element twice.

You can return the answer in any order.

**Example 1:**

**Input:** nums = [2,7,11,15], target = 9
**Output:** [0,1]
**Explanation:** Because nums[0] + nums[1] == 9, we return [0, 1].

**Example 2:**

**Input:** nums = [3,2,4], target = 6
**Output:** [1,2]

**Example 3:**

**Input:** nums = [3,3], target = 6
**Output:** [0,1]

**Constraints:**

- `2 <= nums.length <= 104`
- `-109 <= nums[i] <= 109`
- `-109 <= target <= 109`
- **Only one valid answer exists.**

**Follow-up:** Can you come up with an algorithm that is less than `O(n2)` time complexity?

```python3
# Given an array of integers nums and an integer target

# - array can be any size
# - get answer but optimization will be done later

# return indices of the two numbers such that they add up to target

# - You can return the answer in any order.
# - returns in backet array format
# - should only be two numbers in the answer
# - order does not matter

# You may assume that each input would have exactly one solution

# and you may not use the same element twice.

# - check element and move on
# - we can go left to right and not look back within the array


# Input: nums = [2,7,11,15], target = 9
# Output: [0,1]
# Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].


class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        # have the first element of the array check every number
            # return solution if it exists
        # if there is no solution then have the second element of the array look through the entire array
            # return solution if it exists
        # continue until a solution is found with each array

        for i in range(len(nums) - 1):
            for k in range(i + 1, len(nums)):
                if nums[i] + nums[k] == target:
                    return {i, k}
        return {}
            
```
# Hints

> [!Hint1]- Hint 1 
> A really brute force way would be to search for all possible pairs of numbers but that would be too slow. Again, it's best to try out brute force solutions for just for completeness. It is from these brute force solutions that you can come up with optimizations 

> [!Hint2]- Hint 2 
So, if we fix one of the numbers, say `x`, we have to scan the entire array to find the next number `y` which is `value - x` where value is the input parameter. Can we change our array somehow so that this search becomes faster?

> [!Hint3]- Hint 3 
The second train of thought is, without changing the array, can we use additional space somehow? Like maybe a hash map to speed up the search?


# Solution
#coding/python 
## Brute Force 
```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        for i in range(len(nums)):
            for j in range(i + 1, len(nums)):
                if nums[j] == target - nums[i]:
                    return [i, j]
        return []
            
```

## Two-pass Hash Table
```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        hashmap = {}
        for i in range(len(nums)):
            hashmap[nums[i]] = i
        for i in range(len(nums)):
            complement = target - nums[i]
            if complement in hashmap and hashmap[complement] != i:
                return [i, hashmap[complement]]
        # If no valid pair is found, return an empty list
        return []
```

## One-pass Hash Table 

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        hashmap = {}
        for i in range(len(nums)):
            complement = target - nums[i]
            if complement in hashmap:
                return [i, hashmap[complement]]
            hashmap[nums[i]] = i
        # Return an empty list if no solution is found
        return []
```



> [!Hint2]- Hint 2 
So, if we fix one of the numbers, say `x`, we have to scan the entire array to find the next number `y` which is `value - x` where value is the input parameter. Can we change our array somehow so that this search becomes faster?

> [!Hint3]- Hint 3 
The second train of thought is, without changing the array, can we use additional space somehow? Like maybe a hash map to speed up the search?


# Solution
#coding/python 
## Brute Force 
```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        for i in range(len(nums)):
            for j in range(i + 1, len(nums)):
                if nums[j] == target - nums[i]:
                    return [i, j]
        return []
            
```

## Two-pass Hash Table
```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        hashmap = {}
        for i in range(len(nums)):
            hashmap[nums[i]] = i
        for i in range(len(nums)):
            complement = target - nums[i]
            if complement in hashmap and hashmap[complement] != i:
                return [i, hashmap[complement]]
        # If no valid pair is found, return an empty list
        return []
```

## One-pass Hash Table 

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        hashmap = {}
        for i in range(len(nums)):
            complement = target - nums[i]
            if complement in hashmap:
                return [i, hashmap[complement]]
            hashmap[nums[i]] = i
        # Return an empty list if no solution is found
        return []
```


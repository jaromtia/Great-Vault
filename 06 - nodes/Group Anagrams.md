#coding/data-structure 

#coding
# Problem

Given an array of strings strs, group all anagrams together into sublists. You may return the output in any order.

An anagram is a string that contains the exact same characters as another string, but the order of the characters can be different.

Example 1:

Input: strs = ["act","pots","tops","cat","stop","hat"]

Output: [["hat"],["act", "cat"],["stop", "pots", "tops"]]
Example 2:

Input: strs = ["x"]

Output: [["x"]]
Example 3:

Input: strs = [""]

Output: [[""]]
Constraints:

1 <= strs.length <= 1000.
0 <= strs[i].length <= 100
strs[i] is made up of lowercase English letters.


# Hint
>[!hint1]- Hint 1
>A naive solution would be to sort each string and group them using a hash map. This would be an O(m * nlogn) solution. Though this solution is acceptable, can you think of a better way without sorting the strings?

>[!hint2]- Hint 2
>By the definition of an anagram, we only care about the frequency of each character in a string. How is this helpful in solving the problem?

> [!hint3]- Hint 3
> We can simply use an array of size O(26), since the character set is a through z (26 continuous characters), to count the frequency of each character in a string. Then, we can use this array as the key in the hash map to group the strings.

# Solution 

## 
Code block
```python 
```



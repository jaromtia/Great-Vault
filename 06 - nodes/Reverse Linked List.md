#coding/data-structure 
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
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        prev = None
        curr = head

        while curr:
            temp = curr.next
            curr.next = prev
            prev = curr
            curr = temp
        return prev
```



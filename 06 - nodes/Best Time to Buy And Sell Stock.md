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
    def maxProfit(self, prices: List[int]) -> int:
        l = 0 # buy
        r = 1 # sell
        maxP = 0 

        while r < len(prices):
            #profit?
            if prices[l] < prices[r]:
                profit = prices[r] - prices[l]
                maxP = max(maxP, profit)
            else: 
                l = r
            r += 1

        return maxP
```



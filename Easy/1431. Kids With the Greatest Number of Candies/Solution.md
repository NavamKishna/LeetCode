# Intuition
To determine if each kid will have the greatest number of candies after receiving the extra candies, we need to find the maximum number of candies among all the kids. Then, we check if each kid's total number of candies after receiving the extra candies is greater than or equal to the maximum.

# Approach
1. Find the maximum number of candies among all the kids.
2. Iterate through each kid's candies and check if adding the extra candies to their total will make it greater than or equal to the maximum.
3. Store the result for each kid in a boolean array.

# Complexity
- Time complexity: $$O(n)$$, where n is the number of kids. We iterate through the candies array once.
- Space complexity: $$O(n)$$, where n is the number of kids. We store the result for each kid in a boolean array of length n.

# Code
```python
class Solution(object):
    def kidsWithCandies(self, candies, extraCandies):
        """
        :type candies: List[int]
        :type extraCandies: int
        :rtype: List[bool]
        """
        result=[]
        cand_max=max(candies)
        for candy in candies:
            result.append(candy+extraCandies>=cand_max)

        return result
```
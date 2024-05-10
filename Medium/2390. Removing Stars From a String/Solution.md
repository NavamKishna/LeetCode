# Intuition
To remove stars from the string, we can perform the following steps:
1. Iterate through the string characters.
2. If the current character is not a star, add it to the output list.
3. If the current character is a star, remove the closest non-star character to its left (including the star itself) by popping the last character from the output list.

# Approach
1. Initialize an empty list to store the output string.
2. Iterate through the characters of the input string:
   - If the current character is not a star, append it to the output list.
   - If the current character is a star, pop the last character from the output list.
3. Join the characters in the output list to form the resulting string.

# Complexity
- Time complexity: O(n), where n is the length of the input string s. We iterate through the string once.
- Space complexity: O(n), where n is the length of the input string s. We store the output string characters in a list. 

# Code
```
class Solution(object):
    def removeStars(self, s):
        """
        :type s: str
        :rtype: str
        """
        out_list = []
        for i in s:
            if i != "*":
                out_list.append(i)
            else:
                out_list.pop()
        return "".join(out_list)
```
# Intuition
To reverse the order of words in the string, we can split the string into words, reverse the order of the words, and then join them back together.

# Approach
1. Split the string s into words using the split() method.
2. Reverse the order of the words using the reverse() method.
3. Join the reversed words back together using the join() method, with a single space as the separator.

# Complexity
- Time complexity: O(n), where n is the length of the string s. Splitting the string and joining the words take linear time.
- Space complexity: O(n), where n is the length of the string s. We store the words in a list during splitting, and the reversed string during joining.


# Code
```
class Solution(object):
    def reverseWords(self, s):
        """
        :type s: str
        :rtype: str
        """
        words = s.split()
        words.reverse()
        return ' '.join(words)
```
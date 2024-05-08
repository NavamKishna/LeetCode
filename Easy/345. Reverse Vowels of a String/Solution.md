# Intuition
To reverse only the vowels in the string, we can use a two-pointer approach. We start with one pointer at the beginning of the string and another pointer at the end. Then, we swap the vowels encountered by these pointers until they meet in the middle of the string.

# Approach
1. Define a set of vowels.
2. Convert the string s into a list of characters for easy manipulation.
3. Initialize two pointers, i and j, at the beginning and end of the string, respectively.
4. Iterate while i is less than j:
   - If both s_list[i] and s_list[j] are vowels, swap them and move both pointers towards the middle.
   - If s_list[i] is a vowel but s_list[j] is not, move j towards the middle.
   - If s_list[j] is a vowel but s_list[i] is not, move i towards the middle.
   - If neither s_list[i] nor s_list[j] are vowels, move both pointers towards the middle.
5. After the iteration, join the characters in the list to form the reversed string and return it.

# Complexity
- Time complexity: O(n), where n is the length of the string s. We traverse the string once with two pointers.
- Space complexity: O(n), where n is the length of the string s. We use a list to store the characters of the string. 

# Code
```
class Solution(object):
    def reverseVowels(self, s):
        """
        :type s: str
        :rtype: str
        """
        vowels = set('aeiouAEIOU')
        s_list = list(s)
        i, j = 0, len(s_list) - 1

        while i < j:
            if s_list[i] in vowels and s_list[j] in vowels:
                s_list[i], s_list[j] = s_list[j], s_list[i]
                i += 1
                j -= 1
            elif s_list[i] in vowels:
                j -= 1
            elif s_list[j] in vowels:
                i += 1
            else:
                i += 1
                j -= 1

        return ''.join(s_list)
```
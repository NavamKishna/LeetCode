# Intuition
To determine if a word is valid according to the given conditions, we need to ensure that:
1. It contains at least one vowel and one consonant.
2. Its length is at least 3 characters.
3. It consists only of valid characters, i.e., digits, uppercase and lowercase English letters.

# Approach
We use regular expressions to define patterns for vowels and consonants. Then, we check if the word satisfies the conditions:
1. Check if all characters are valid (digits or English letters).
2. Check if the length of the word is at least 3.
3. Verify if there is at least one vowel and one consonant present in the word.

# Complexity
- Time complexity: `O(n)`, where `n` is the length of the word. Checking if each character is valid and searching for vowels and consonants takes linear time.
- Space complexity: `O(1)`. The regular expression patterns and the additional variables used do not scale with the input size, so the space complexity is constant.

# Code
```
class Solution(object):
    def isValid(self, word):
        """
        :type word: str
        :rtype: bool
        """
        vowel_pattern = re.compile(r'[aeiouAEIOU]')
        consonant_pattern = re.compile(r'[bcdfghjklmnpqrstvwxyzBCDFGHJKLMNPQRSTVWXYZ]')
        
        if not all(char.isdigit() or char.isalpha() for char in word):
            return False
        
        if len(word) < 3:
            return False
        

        if not vowel_pattern.search(word) or not consonant_pattern.search(word):
            return False
        
        return True
```
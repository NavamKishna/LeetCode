# Intuition
We need to calculate the altitude at each point along the road trip and find the highest altitude reached during the trip.

# Approach
1. Initialize variables max_altitude and current_altitude to 0.
2. Iterate through the gain array:
   - Add the current gain to the current altitude.
   - Update max_altitude if the current altitude surpasses it.
3. Return max_altitude.

# Complexity
- Time complexity: O(n), where n is the length of the gain array. We iterate through the array once.
- Space complexity: O(1), as we only use a constant amount of extra space for variables.

# Code
```
class Solution(object):
    def largestAltitude(self, gain):
        """
        :type gain: List[int]
        :rtype: int
        """
        max_alti=0
        alti=0
        for altitude in gain:
            alti+=altitude
            if max_alti<alti:
                max_alti=alti
        
        return max_alti


```
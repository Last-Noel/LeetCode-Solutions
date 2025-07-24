# TwoSum

Difficulty : <code>Easy</code> 🟢 \
Completed : 2025-07-23

I'll figure out how to make this prettier next time with pictures and what not but for now doing this easy problem actually cooked me I need to lock in.

## New Learned Concepts
- .extend for Lists
- better understanding of how for loops worked for Python
- importance of range in tandem with for loops

## Solution:
```
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        answer = []
        for i in range(len(nums)):
            if (nums[i] <= target):
                for j in range(i + 1, len(nums)): 
                    if(nums[i] + nums[j] == target):
                        answer.extend([i, j])
                        return answer
        return None
```
# Update:
On second view of this I realized that I was doing the brute force way of solving this problem, which is
simply no bueno IMO. I need to be better about utilizing hash maps and what not for these kind of things.

You can easily get a faster processing speed by using a hashmap to find the complement over bruteforcing.
Here's the new version of this I was able to implement (thank you LeetCode solutions)

```
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        values = {}
        for i in range(len(nums)):
            values.update({nums[i] : i})

        for i in range(len(nums)):
            complement = target - nums[i]
            if complement in values and values[complement] != i:
                return [i, values[complement]]
```

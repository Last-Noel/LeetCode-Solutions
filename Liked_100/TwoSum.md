# TwoSum

Difficulty : Easy

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

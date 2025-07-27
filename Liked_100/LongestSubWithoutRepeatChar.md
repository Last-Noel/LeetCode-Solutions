# LeetCode Problem Name

Difficulty : <code>medium</code>  🟡\
Completed : 2025-07-27

Felt smart enough to take too long to solve this by myself - and then realize I was so close to the sun when I gave up.

## Before the Code
- knew an elegant solution was somewhere there, didn't want to make a huge set holding all these different possibilites
- initially had idea of set
## During the Code
- set solution wasn't working out so pivoted to tuple, since existence of where the duplicate element mattered in the substring
- ran into some trouble that I still am not sure why it doesn't work (will check later)
- gave up and realized was close with combining previous idea of set with pointers with logic developed with tuple idea
## Solution:
```
seen = set()
        max_length = 0
        left = 0

        for right in range(len(s)):
            if s[right] not in seen:
                seen.add(s[right])
                max_length = max(max_length, (right - left) + 1)
                
            else:
                while s[right] in seen:
                    seen.remove(s[left])
                    left += 1
                seen.add(s[right])

        return max_length
```
## Closing Thoughts:
- proud to have started thinking along the lines of making things efficient - I like the process of trying to figure things out on paper and let edge cases refine the idea
- might give myself a timer for how long I will allow myself to work on something before siwtching it up.
